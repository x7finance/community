## X7DAO Discount Authority

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface IDiscountAuthority](/contracts/contract-source-code/X7DAODiscountAuthority.sol#L85)

### Contract events

[event EcosystemMaxiNFTSet(address indexed oldTokenAddress, address indexed newTokenAddress)](/contracts/contract-source-code/X7DAODiscountAuthority.sol#L94)
[event LiquidityMaxiNFTSet(address indexed oldTokenAddress, address indexed newTokenAddress)](/contracts/contract-source-code/X7DAODiscountAuthority.sol#L95)

### Read-Only Functions

[function discountRatio(address swapper) external view returns (uint256 numerator, uint256 denominator)](/contracts/contract-source-code/X7DAODiscountAuthority.sol#L113)

### External Functions

[function setEcosystemMaxiNFT(address tokenAddress) external onlyOwner](/contracts/contract-source-code/X7DAODiscountAuthority.sol#L99)
[function setLiquidityMaxiNFT(address tokenAddress) external onlyOwner](/contracts/contract-source-code/X7DAODiscountAuthority.sol#L106)
