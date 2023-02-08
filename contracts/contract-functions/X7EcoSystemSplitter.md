## X7 Eco System Splitter

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface IWETH](/contracts/contract-source-code/X7EcosystemSplitter.sol#L103)\
[interface IERC20](/contracts/contract-source-code/X7EcosystemSplitter.sol#L109)\
[interface IX7EcosystemSplitter](/contracts/contract-source-code/X7EcosystemSplitter.sol#L114)

### Contract events

[event SharesSet(uint256 x7RShare, uint256 x7DAOShare, uint256 x7100Share, uint256 lendingPoolShare, uint256 treasuryShare)](/contracts/contract-source-code/X7EcosystemSplitter.sol#L142)\
[event OutletRecipientSet(Outlet outlet, address oldRecipient, address newRecipient)](/contracts/contract-source-code/X7EcosystemSplitter.sol#L143)\
[event OutletFrozen(Outlet outlet)](/contracts/contract-source-code/X7EcosystemSplitter.sol#L144)

### External Functions

[receive () external payable](/contracts/contract-source-code/X7EcosystemSplitter.sol#L156)\
[function setWETH(address weth\_) external onlyOwner](/contracts/contract-source-code/X7EcosystemSplitter.sol#L164)\
[function setOutlet(Outlet outlet, address recipient) external onlyOwner](/contracts/contract-source-code/X7EcosystemSplitter.sol#L168)\
[function freezeOutletChange(Outlet outlet) external onlyOwner](/contracts/contract-source-code/X7EcosystemSplitter.sol#L178)\
[function setShares(uint256 x7rShare\_ , uint256 x7daoShare\_ , uint256 x7100Share\_ , uint256 lendingPoolShare\_ , uint256 treasuryShare\_) external onlyOwner](/contracts/contract-source-code/X7EcosystemSplitter.sol#L185)\
[function takeBalance() external](/contracts/contract-source-code/X7EcosystemSplitter.sol#L200)\
[function pushAll() external](/contracts/contract-source-code/X7EcosystemSplitter.sol#L223)\
[function rescueWETH() external](/contracts/contract-source-code/X7EcosystemSplitter.sol#L231)\
[function rescueTokens(address tokenAddress) external](/contracts/contract-source-code/X7EcosystemSplitter.sol#L235)

### Internal Functions

[function \_sendBalance(Outlet outlet) internal](/contracts/contract-source-code/X7EcosystemSplitter.sol#L206)
