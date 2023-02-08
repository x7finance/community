## X7D

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface IX7D](/contracts/contract-source-code/X7D.sol#L310)\
[interface X7DMinter](/contracts/contract-source-code/X7D.sol#L316)\
[interface X7DBurner](/contracts/contract-source-code/X7D.sol#L330)\

### Contract events

[event AuthorizedMinterSet(address indexed minterAddress, bool isAuthorized)](/contracts/contract-source-code/X7D.sol#L393)\
[event AuthorizedRedeemerSet(address indexed redeemerAddress, bool isAuthorized)](/contracts/contract-source-code/X7D.sol#L394)\

### Read-Only Functions

[function authorizedMintersCount() external view returns (uint256)](/contracts/contract-source-code/X7D.sol#L400)\
[function authorizedRedeemersCount() external view returns (uint256)](/contracts/contract-source-code/X7D.sol#L404)\
[function circulatingSupply() external view returns (uint256)](/contracts/contract-source-code/X7D.sol#L458)\

### External Functions

[function setAuthorizedMinter(address minterAddress, bool isAuthorized) external onlyOwner](/contracts/contract-source-code/X7D.sol#L408)\
[function setAuthorizedRedeemer(address redeemerAddress, bool isAuthorized) external onlyOwner](/contracts/contract-source-code/X7D.sol#L428)\
[function mint(address to, uint256 amount) external](/contracts/contract-source-code/X7D.sol#L448)\
[function burn(address from, uint256 amount) external](/contracts/contract-source-code/X7D.sol#L453)\
