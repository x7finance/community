## X7 Lending Pool Reserve

Contains the contract functions only with a link to the full function in the contract code

### Interface

[interface IERC20](/contracts/contract-source-code/X7LendingPoolReserve.sol#L130)\
[interface IX7D](/contracts/contract-source-code/X7D.sol#L134)\
[interface X7DMinter](/contracts/contract-source-code/X7D.sol#L139)\
[interface X7DBurner](/contracts/contract-source-code/X7D.sol#L150)

### Contract events

[event X7DSet(address oldAddress, address newAddress)](/contracts/contract-source-code/X7LendingPoolReserve.sol#L185)\
[event EcosystemRecipientSet(address oldAddress, address newAddress)](/contracts/contract-source-code/X7LendingPoolReserve.sol#L186)\
[event EcosystemPayerSet(address payorAddress, bool isPayer)](/contracts/contract-source-code/X7LendingPoolReserve.sol#L187)\
[event LendingPoolSet(address oldAddress, address newAddress)](/contracts/contract-source-code/X7LendingPoolReserve.sol#L188)\
[event FundsSent(address indexed recipient, uint256 amount)](/contracts/contract-source-code/X7LendingPoolReserve.sol#L189)\
[event FundsReturned(address indexed sender, uint256 amount)](/contracts/contract-source-code/X7LendingPoolReserve.sol#L190)

### External Functions

[receive() external payable](/contracts/contract-source-code/X7LendingPoolReserve.sol#L200)\
[function depositETH() external payable](/contracts/contract-source-code/X7LendingPoolReserve.sol#L210)\
[function depositETHForRecipient(address recipient) external payable](/contracts/contract-source-code/X7LendingPoolReserve.sol#L214)\
[function withdrawETH(uint256 amount) external](/contracts/contract-source-code/X7LendingPoolReserve.sol#L218)\
[function returnETH() external payable](/contracts/contract-source-code/X7LendingPoolReserve.sol#L225)\
[function setLendingPool(address lendingPool\_) external onlyOwner](/contracts/contract-source-code/X7LendingPoolReserve.sol#L229)\
[function setEcosystemRecipientAddress(address recipient) external onlyOwner](/contracts/contract-source-code/X7LendingPoolReserve.sol#L237)\
[function setX7D(address X7DAddress) external onlyOwner](/contracts/contract-source-code/X7LendingPoolReserve.sol#L245)\
[function setEcosystemPayer(address ecosystemPayerAddress, bool value) external onlyOwner](/contracts/contract-source-code/X7LendingPoolReserve.sol#L253)\
[function fundLendingPool(uint256 amount) external onlyOwner](/contracts/contract-source-code/X7LendingPoolReserve.sol#L260)
