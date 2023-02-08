## X7 DEX Maxi

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface IX7Migration](/contracts/contract-source-code/X7DEXMaxi.sol#L1267)

### Contract events

[event MintingOpen()](/contracts/contract-source-code/X7DEXMaxi.sol#L1287)
[event MintFeeDestinationSet(address indexed oldDestination, address indexed newDestination)](/contracts/contract-source-code/X7DEXMaxi.sol#L1288)
[event MintPriceSet(uint256 oldPrice, uint256 newPrice)](/contracts/contract-source-code/X7DEXMaxi.sol#L1289)
[event BaseURISet(string oldURI, string newURI)](/contracts/contract-source-code/X7DEXMaxi.sol#L1290)
[event WhitelistActivitySet(bool whitelistActive)](/contracts/contract-source-code/X7DEXMaxi.sol#L1291)
[event WhitelistAuthoritySet(address indexed oldWhitelistAuthority, address indexed newWhitelistAuthority)](/contracts/contract-source-code/X7DEXMaxi.sol#L1292)

### External Functions

[function whitelist(address holder) external view returns (bool)](/contracts/contract-source-code/X7DEXMaxi.sol#L1299)
[function setMintFeeDestination(address mintFeeDestination\_) external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1303)
[function setBaseURI(string memory baseURI\_) external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1310)
[function setMintPrice(uint256 mintPrice\_) external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1317)
[function setWhitelist(bool isActive) external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1324)
[function setWhitelistComplete() external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1331)
[function setWhitelistAuthority(address whitelistAuthority\_) external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1337)
[function openMinting() external onlyOwner](/contracts/contract-source-code/X7DEXMaxi.sol#L1344)
[function mint() external payable](/contracts/contract-source-code/X7DEXMaxi.sol#L1351)
[function mintMany(uint256 numMints) external payable](/contracts/contract-source-code/X7DEXMaxi.sol#L1355)

### Internal Functions

[function \_mintMany(uint256 numMints) internal](/contracts/contract-source-code/X7DEXMaxi.sol#L1359)
[function \_baseURI() internal view override returns (string memory)](/contracts/contract-source-code/X7DEXMaxi.sol#L1383)
