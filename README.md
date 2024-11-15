# TakeProfitsHook ( [Atrium](https://atrium.academy/uniswap-old),  Uniswap Hook Incubator 3)
This repository contains the implementation of the `TakeProfitsHook` contract, which provides a mechanism for placing and executing take-profit orders on the Uniswap V4 protocol.

## Key Features
1. **Placing Take-Profit Orders**: Users can place take-profit orders by specifying the pool, the tick at which they want to sell, the direction of the swap (zeroForOne or oneForZero), and the input amount.
2. **Executing Orders**: The `TakeProfitsHook` contract executes pending orders whenever the tick moves in the appropriate direction. It conducts the swap and settles the balances accordingly.
3. **Claim Tokens**: Users receive ERC-1155 claim tokens when placing an order. They can later redeem these claim tokens to receive the output tokens from the executed order.
4. **Canceling Orders**: Users can cancel their pending orders and receive their input tokens back.
5. **Tick Tracking**: The contract keeps track of the last known tick for each pool to efficiently determine when to execute pending orders.

## Installation and Testing
This project uses the Foundry development framework. To set up the project and run the tests, follow these steps:

1. Install Foundry:
   ```
   curl -L https://foundry.paradigm.xyz | bash
   foundryup
   ```
2. Clone this repository:
   ```
   git clone https://github.com/ProfSaz/limit-order-hook.git
   cd limit-order-hook
   ```
3. Install dependencies:
   ```
   forge install
   ```
4. Run the tests:
   ```
   forge test
   ```

The `TakeProfitsHookTest` contract in the `TakeProfitsHook.t.sol` file contains the test cases that verify the behavior of the `TakeProfitsHook` contract.

## Test Cases
The test cases cover the following scenarios:
1. Placing an order
2. Canceling an order
3. Executing orders (zeroForOne)
4. Executing orders (oneForZero)
5. Executing multiple orders (only one executed)
6. Executing multiple orders (both executed)

## Conclusion
The `TakeProfitsHook` contract provides a take-profit mechanism for the Uniswap V4 protocol. By allowing users to place and execute take-profit orders, the contract enhances the trading experience and provides an additional tool for managing their positions.