## Trading Functionality

### Swap

Similar to Uniswap, token swaps in Xchange are a simple way to trade one ERC-20 token for another.

For end-users, swapping is intuitive: a user picks an input token and an output token. They specify an input amount, and the protocol calculates how much of the output token they’ll receive. They then execute the swap with one click, receiving the output token in their wallet immediately.

Swaps in Xchange are different from trades on traditional centralized exchange platforms. Xchange does not use an order book to represent liquidity or determine prices. Xchange uses a constant product automated market maker mechanism to provide instant feedback on rates and slippage.

### Pricing

Similar to Uniswap, Xchange uses the constant product formula.

### Constant Price Formula

When a token is withdrawn (bought), a proportional amount must be deposited (sold) to maintain the constant. The ratio of tokens in the pool, in combination with the constant product formula, ultimately determine the price that a swap executes at.
