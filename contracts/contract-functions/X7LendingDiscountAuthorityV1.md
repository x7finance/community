## X7 Lending Discount Authority V1

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface IX7LendingDiscountAuthority](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L148)\
[interface IDiscountNFT](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L162)\
[interface IConsumableDiscountNFT](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L166)

### Contract [events

[event AuthorizedConsumerSet(address indexed consumer, bool isAuthorized)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L196)\
[event TimeBasedDiscountSet(uint256 oldMin, uint256 oldMax, uint256 min, uint256 max)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L197)\
[event AmountBasedDiscountSet(uint256 oldMin, uint256 oldMax, uint256 min, uint256 max)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L198)\
[event DiscountNFTSet(address indexed oldAddress, address indexed newAddress)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L199)\
[event ConsumableDiscountNFTSet(address indexed oldAddress, address indexed newAddress)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L200)\
[event DiscountNFTDiscountsSet(uint256 oldOriginationFeeDiscount, uint256 oldPremiumFeeDiscount, uint256 originationFeeDiscount, uint256 premiumFeeDiscount)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L201)\
[event ConsumableDiscountNFTDiscountsSet(uint256 oldOriginationFeeDiscount, uint256 oldPremiumFeeDiscount, uint256 originationFeeDiscount, uint256 premiumFeeDiscount)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L202)

### Modifier Functions

[modifier onlyAuthorizedConsumers](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L211)

### Read-Only Functions

[function getFeeModifiers(address borrower,uint256[3] memory loanAmountDetails,uint256[3] memory loanDurationDetails) external view returns (uint256, uint256)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L278)

### External Functions

[function setAuthorizedConsumer(address consumer, bool isAuthorized) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L216)\
[function setTimeBasedDiscount(uint256 min, uint256 max) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L222)\
[function setAmountBasedDiscount(uint256 min, uint256 max) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L231)\
[function setDiscountNFT(address discountNFTAddress) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L240)\
[function setConsumableDiscountNFT(address consumableDiscountNFTAddress) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L247)\
[function setDiscountNFTDiscounts(uint256 premiumFeeDiscount, uint256 originationFeeDiscount) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L254)\
[function setConsumableDiscountNFTDiscounts(uint256 premiumFeeDiscount, uint256 originationFeeDiscount) external onlyOwner](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L266)\
[function useFeeModifiers(address borrower,uint256[3] memory loanAmountDetails,uint256[3] memory loanDurationDetails) external onlyAuthorizedConsumers returns (uint256, uint256)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L292)

### Internal Functions

[function \_getFeeModifiers(address borrower,uint256[3] memory loanAmountDetails,uint256[3] memory loanDurationDetails) internal view returns (uint256 premiumFeeModifier, uint256 originationFeeModifier, bool usedConsumable)](/contracts/contract-source-code/X7LendingDiscountAuthorityV1.sol#L310)
