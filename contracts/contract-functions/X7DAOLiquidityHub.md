## X7DAO Discount Liquidity Hub

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface ILiquidityHub](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L212)\
[interface IX7EcosystemSplitter](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L216)\
[interface IWETH](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L220)\

### Contract events

[event SharesSet(uint256 distributeShare, uint256 liquidityShare, uint256 auxiliaryShare, uint256 treasuryShare)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L261)\
[event OffRampPairSet(address indexed offRampPair)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L262)\
[event DistributeTargetSet(address indexed oldTarget, address indexed newTarget)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L263)\
[event AuxiliaryTargetSet(address indexed oldTarget, address indexed newTarget)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L264)\
[event TreasuryTargetSet(address indexed oldTarget, address indexed newTarget)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L265)\
[event LiquidityRatioTargetSet(uint256 liquidityRatioTarget)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L266)\
[event LiquidityTokenReceiverSet(address indexed oldReciever, address indexed newReceiver)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L267)\
[event BalanceThresholdSet(uint256 threshold)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L268)\
[event RouterSet(address router)](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L269)\
[event TreasuryTargetFrozen()](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L270)\
[event AuxiliaryTargetFrozen()](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L271)\
[event DistributeTargetFrozen()](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L272)\
[event BalanceThresholdFrozen()](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L273)\

### External Functions

[function setShares(uint256 distributeShare\_, uint256 liquidityShare\_, uint256 auxiliaryShare\_, uint256 treasuryShare\_) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L283)\
[function setRouter(address router\_) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L299)\
[function setOffRampPair(address offRampPairAddress) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L305)\
[function setBalanceThreshold(uint256 threshold) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L311)\
[function setLiquidityRatioTarget(uint256 liquidityRatioTarget\_) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L317)\
[function setLiquidityTokenReceiver(address liquidityTokenReceiver\_) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L324)\
[function setDistributionTarget(address target) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L336)\
[function setAuxiliaryTarget(address target) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L348)\
[function setTreasuryTarget(address target) external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L360)\
[function freezeTreasuryTarget() external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L372)\
[function freezeDistributeTarget() external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L378)\
[function freezeAuxiliaryTarget() external onlyOwner ](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L384)\
[function freezeBalanceThreshold() external onlyOwner](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L390)\
[function processFees(address tokenAddress) external](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L396)\
[function rescueWETH() external](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L549)\

### Internal Functions

[function sendAuxiliaryBalance() internal](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L465)\
[function buyBackAndAddLiquidity() internal](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L480)\
[function addLiquidityETH(uint256 tokenAmount, uint256 ethAmount) internal](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L510)\
[function swapTokensForEth(address tokenAddress, uint256 tokenAmount) internal](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L522)\
[function swapEthForTokens(uint256 ethAmount) internal](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L537)\

### Public Functions

[function sendDistributeBalance() public](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L433)\
[function sendTreasuryBalance() public](/contracts/contract-source-code/X7DAOLiquidityHub.sol#L450)\
