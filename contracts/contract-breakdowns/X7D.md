https://medium.com/@mikemurpher/x7-finance-x7d-token-contract-45b2edc886a6

7 min read

# X7 Finance X7D Token Contract

X7D is the ETH backed token of the X7 ecosystem. X7D can be minted from ETH by authorizedMinters and burned to ETH by authorizedRedeemers.
All ETH underpinning X7D will be custodied by smart contracts.

Unlike a strictly wrapped token like WETH, the X7D token contract does not have custody of any ETH itself. It instead defers this job to authorizedMinters and authorizedRedeemers. This provides flexibility to deploy multiple mechanisms for minting X7D and redeeming X7D into ETH at various timescales, with various associated caveats, and with various multipliers or percentage returns.

The X7D Lending Pool Reserve smart contract will be the first authorizedMinter and authorizedRedeemer.

The contract “X7D” inherits from four other contracts: “ERC20”, “Ownable”, “TokensCanBeRecovered”, and “ETHCanBeRecovered”, and “IX7D”. The contract also has several mapping variables that store whether an address is an authorized minter or redeemer, as well as arrays that store a list of authorized minters and redeemers. The contract has several functions that allow the owner to add or remove an address as an authorized minter or redeemer, and also has functions for minting and burning tokens, as well as a function to check the circulating supply of the token. The “receive()” function allows the contract to receive ether. The contract also has events for emitting when the minter or redeemer is set.

```solidity
// The primary X7D interface for minting and burning from authorized Minters and Burners.
interface IX7D {
    function mint(address to, uint256 amount) external;
    function burn(address from, uint256 amount) external;
}


interface X7DMinter {
// A minter should implement the following two functions.

    // Call this function to explicitly mint X7D
    function depositETH() external payable;

    // Call this function to return ETH to this contract without minting X7D
    //
    //  This is important as a valid mechanism for a minter to mint from ETH
    //  would be to implement a receive function to automatically mint X7D.
    function returnETH() external payable;
}


interface X7DBurner {
// A burner/redeemer should implement the following two functions.

    // Call this function to redeem (burn) X7D for ETH
    function withdrawETH(uint256 amount) external;
}
```

Contract Interfaces with External contracts.

```solidity
abstract contract TokensCanBeRecovered is Ownable {
    bytes4 private constant TRANSFERSELECTOR = bytes4(keccak256(bytes('transfer(address,uint256)')));
    address public recoveredTokenRecipient;

    event RecoveredTokenRecipientSet(address oldRecipient, address newRecipient);

    function setRecoveredTokenRecipient(address tokenRecipient_) external onlyOwner {
        require(recoveredTokenRecipient != tokenRecipient_);
        address oldRecipient = recoveredTokenRecipient;
        recoveredTokenRecipient = tokenRecipient_;
        emit RecoveredTokenRecipientSet(oldRecipient, tokenRecipient_);
    }

    function recoverTokens(address tokenAddress) external {
        require(recoveredTokenRecipient != address(0));
        _safeTransfer(tokenAddress, recoveredTokenRecipient, IERC20(tokenAddress).balanceOf(address(this)));
    }

    function _safeTransfer(address token, address to, uint value) private {
        (bool success, bytes memory data) = token.call(abi.encodeWithSelector(TRANSFERSELECTOR, to, value));
        require(success && (data.length == 0 || abi.decode(data, (bool))), 'TRANSFER_FAILED');
    }
}
```

This contract allows to set of a recipient address where recovered tokens will be sent, and provides a method to recover tokens from a specified address. It also has an event “RecoveredTokenRecipientSet” which will be emitted when the recovered token recipient is set. The “\_safeTransfer” function is used to transfer tokens from the current contract to the recipient address and it uses the “transfer” function from the ERC20 standard. The constant variable “TRANSFERSELECTOR” is used for encoding the function signature of the “transfer” function.

```solidity
 mapping(address => bool) public authorizedMinter;
 mapping(address => bool) public authorizedRedeemer;

 address[] public authorizedMinters;
 address[] public authorizedRedeemers;

 // Internal index mapping for array maintenance
 mapping(address => uint256) authorizedMintersIndex;
 mapping(address => uint256) authorizedRedeemersIndex;

 event AuthorizedMinterSet(address indexed minterAddress, bool isAuthorized);
 event AuthorizedRedeemerSet(address indexed redeemerAddress, bool isAuthorized);
```

The “authorizedMinter” and “authorizedRedeemer” mappings are used to track whether a given address has been authorized to mint or redeem tokens, respectively. The “authorizedMinters” and “authorizedRedeemers” arrays are used to store the addresses of authorized minters and redeemers, in order, for easy iteration. The “authorizedMintersIndex” and “authorizedRedeemersIndex” mappings are used to keep track of the index of each authorized minter and redeemer in their respective arrays, for efficient removal when necessary.

The “AuthorizedMinterSet” and “AuthorizedRedeemerSet” events are emitted when a minter’s or redeemer’s authorization status is changed, with the address and new authorization status included as indexed event parameters.

```solidity
 constructor() ERC20("X7 Deposit", "X7D") Ownable(msg.sender) {}
```

The constructor function is initializing the token with the name “X7 Deposit” and the symbol “X7D”, and also sets the msg.sender as the owner of the contract.

```solidity
receive() external payable {}
```

The receive() function is a built-in function in Solidity that allows a contract to accept incoming Ether without the need for a function call. It is similar to the fallback function, but can only be called when the contract is the recipient of a transaction. It is typically used when a contract is expected to receive Ether as a form of payment or funding. The payable keyword means that the function can receive ether.

```solidity
 function authorizedMintersCount() external view returns (uint256) {
        return authorizedMinters.length;
    }
```

This function returns the number of authorized redeemers that have been set by the contract owner. It is marked as “external view” which means that it is a read-only function that can be called by any external (off-contract) parties, and it returns a uint256 (unsigned 256-bit integer) value. The “view” keyword means that this function is not modifying the state of the contract and will not cost gas to execute.

```solidity
 function authorizedRedeemersCount() external view returns (uint256) {
        return authorizedRedeemers.length;
    }
```

This function returns the number of authorized redeemers that have been set by the contract owner. It is marked as ÔÇ£external viewÔÇØ which means that it is a read-only function that can be called by any external (off-contract) parties, and it returns a uint256 (unsigned 256-bit integer) value. The ÔÇ£viewÔÇØ keyword means that this function is not modifying the state of the contract and will not cost gas to execute.

```solidity
function setAuthorizedMinter(address minterAddress, bool isAuthorized) external onlyOwner {
        require(authorizedMinter[minterAddress] != isAuthorized, "Minter already has specified authorization");
        authorizedMinter[minterAddress] = isAuthorized;

        if (isAuthorized) {
            authorizedMintersIndex[minterAddress] = authorizedMinters.length;
            authorizedMinters.push(minterAddress);
        } else {
            uint256 lastMinterIndex = authorizedMinters.length - 1;
            address lastMinter = authorizedMinters[lastMinterIndex];
            uint256 minterIndex = authorizedMintersIndex[minterAddress];
            authorizedMinters[minterIndex] = lastMinter;
            authorizedMintersIndex[lastMinter] = minterIndex;
            delete authorizedMintersIndex[minterAddress];
            authorizedMinters.pop();
        }

        emit AuthorizedMinterSet(minterAddress, isAuthorized);
    }
```

The function setAuthorizedMinter(address minterAddress, bool isAuthorized) allows the contract owner to set the authorization status of a specific address (minterAddress) as a minter for the token. The function first checks that the minter's authorization status is not already set to the specified value, and then updates the authorization status of the minter in the authorizedMinter mapping. If the minter is being authorized, their address is added to the authorizedMinters array and the authorizedMintersIndex mapping is updated to reflect the new index of the minter in the array. If the minter is being de-authorized, their address is removed from the authorizedMinters array and the authorizedMintersIndex mapping is updated accordingly. Finally, the function emits an event AuthorizedMinterSet with the minter's address and their new authorization status as arguments.

```solidity
    function setAuthorizedRedeemer(address redeemerAddress, bool isAuthorized) external onlyOwner {
        require(authorizedRedeemer[redeemerAddress] != isAuthorized, "Redeemer already has specified authorization");
        authorizedRedeemer[redeemerAddress] = isAuthorized;

        if (isAuthorized) {
            authorizedRedeemersIndex[redeemerAddress] = authorizedRedeemers.length;
            authorizedRedeemers.push(redeemerAddress);
        } else {
            uint256 lastRedeemerIndex = authorizedRedeemers.length - 1;
            address lastRedeemer = authorizedRedeemers[lastRedeemerIndex];
            uint256 redeemerIndex = authorizedRedeemersIndex[redeemerAddress];
            authorizedRedeemers[redeemerIndex] = lastRedeemer;
            authorizedRedeemersIndex[lastRedeemer] = redeemerIndex;
            delete authorizedRedeemersIndex[redeemerAddress];
            authorizedRedeemers.pop();
        }

        emit AuthorizedRedeemerSet(redeemerAddress, isAuthorized);
    }
```

The function setAuthorizedRedeemer is used to set the authorization of a redeemer address, meaning whether or not it is allowed to redeem tokens from the contract. The function takes in two parameters:

- redeemerAddress: the address of the redeemer to set the authorization for
- isAuthorized: a boolean value indicating whether the redeemer should be authorized (true) or unauthorized (false)
  The function starts by checking if the redeemer already has the specified authorization using an require statement, if true it will throw an error message. Then the function updates the authorization status of the redeemer by assigning the value of isAuthorized to the mapping authorizedRedeemer[redeemerAddress].

It then checks if the redeemer is being authorized or unauthorized:

- If isAuthorized is true, it adds the redeemer address to the authorizedRedeemers array and assigns the redeemer's index in the array to the authorizedRedeemersIndex mapping.
- If isAuthorized is false, it finds the redeemer's index in the authorizedRedeemers array using the authorizedRedeemersIndex mapping. It then replaces the redeemer address at that index with the last redeemer address in the array, updates the authorizedRedeemersIndex mapping to reflect this change, and removes the redeemer address from the authorizedRedeemersIndex mapping. Finally, it removes the redeemer address from the authorizedRedeemers array.
  Finally, the function emits an AuthorizedRedeemerSet event, which logs the redeemer address and its new authorization status.

```solidity
    function mint(address to, uint256 amount) external {
        require(authorizedMinter[msg.sender], "Not authorized to mint X7D");
        _mint(to, amount);
    }
```

This function is used to mint new tokens of the X7D ERC20 token. The function takes in two parameters: the address of the recipient of the tokens (to), and the amount of tokens to be minted (amount).

The function starts by checking if the message sender (msg.sender) is an authorized minter. If not, the function will stop execution and return an error message “Not authorized to mint X7D”. If the sender is authorized, the function proceeds to call the internal \_mint() function, passing in the recipient address and the amount of tokens to be minted as arguments.

It is important to note that this function is only meant to be called by the owner of the contract. The owner can authorize other addresses to mint new tokens using the setAuthorizedMinter() function.

```solidity
    function burn(address from, uint256 amount) external {
        require(authorizedRedeemer[msg.sender], "Not authorized to burn X7D");
        _burn(from, amount);
    }
```

This is a function that allows a contract to burn (destroy) a specified amount of the token from a specific address. The function first checks if the message sender (msg.sender) is an authorized redeemer by checking the “authorizedRedeemer” mapping. If the sender is not authorized, the function will stop execution and return an error message “Not authorized to burn X7D”. If the sender is authorized, the function will then call an internal function “\_burn(from, amount)” to burn the specified amount of tokens. This internal function is not provided in the code you have given. It is assumed that this function will have the necessary logic to decrease the balance of the “from” address and decrease the total supply of the token.

```solidity
    function circulatingSupply() external view returns (uint256) {
        return totalSupply() - balanceOf(address(0xdEaD));
    }
```

The function “circulatingSupply()” is an external view function that returns the total supply of the X7D token minus the balance of a specific address, “address(0xdEaD)”. The function calculates the circulating supply of the token by subtracting the balance of an address that is assumed to be a “dead” or “burn” address, where the tokens are permanently removed from circulation. This is a common way to calculate the circulating supply of a token.
