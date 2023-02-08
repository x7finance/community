## X7D

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface ILiquidityHub](/contracts/contract-source-code/X7DAO.sol#L265)\
[interface IDiscountAuthority](/contracts/contract-source-code/X7DAO.sol#L269)\

### Contract events

[event LiquidityHubSet(address indexed liquidityHub)](/contracts/contract-source-code/X7DAO.sol#L293)\
[event DiscountAuthoritySet(address indexed discountAuthority)](/contracts/contract-source-code/X7DAO.sol#L294)\
[event FeeNumeratorSet(uint256 feeNumerator)](/contracts/contract-source-code/X7DAO.sol#L295)\
[event AMMSet(address indexed pairAddress, bool isAMM)](/contracts/contract-source-code/X7DAO.sol#L296)\
[event OffRampPairSet(address indexed offRampPair)](/contracts/contract-source-code/X7DAO.sol#L297)\
[event LiquidityHubFrozen()](/contracts/contract-source-code/X7DAO.sol#L298)\
[event DiscountAuthorityFrozen()](/contracts/contract-source-code/X7DAO.sol#L299)\

### External Functions

[function setLiquidityHub(address liquidityHub\_) external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L311)\
[function setDiscountAuthority(address discountAuthority\_) external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L317)\
[function setFeeNumerator(uint256 feeNumerator\_) external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L323)\
[function setAMM(address ammAddress, bool isAMM) external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L329)\
[function setOffRampPair(address ammAddress) external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L334)\
[function freezeLiquidityHub() external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L339)\
[function freezeDiscountAuthority() external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L345)\
[function circulatingSupply() external view returns (uint256)](/contracts/contract-source-code/X7DAO.sol#L351)\
[function enableTrading() external onlyOwner](/contracts/contract-source-code/X7DAO.sol#L355)\
[function rescueETH() external](/contracts/contract-source-code/X7DAO.sol#L408)\
[function rescueTokens(address tokenAddress) external](/contracts/contract-source-code/X7DAO.sol#L413)\

### Internal Functions

[function \_transfer(address from, address to, uint256 amount) internal override](/contracts/contract-source-code/X7DAO.sol#L360)\
