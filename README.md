# UniswapV2_Arbitrage-Analysis
## Data Description

Given that this paper focuses on analyzing data extracted from Liquidity Pools at a specific block height. The dataset provides a snapshot of the state of various liquidity pools, capturing the dynamics of token pairs within the DeFi ecosystem. Each row in the dataset represents a token pair, detailing the block number, transaction timestamp, unique transaction hash, log index, transaction index, token contract addresses, reserves of the two tokens, pair contract address, token identifiers, and the price of the token pair. This comprehensive dataset allows for a multifaceted analysis of the DeFi market, offering insights into liquidity provision, price dynamics.

We selected the Liquidity Pool data at a certain block height, and the raw data is represented as one token pair, where each row is formatted as shown in the following table:

| Column | Description |
| ------ | ----------- |
| `block_number` | The blockchain block number where the transaction was recorded. |
| `timestamp` | The timestamp of the transaction. |
| `tx_hash` | The unique transaction hash. |
| `log_index` | The log index of the transaction within the block. |
| `transactionIndex` | The transaction index within the block. |
| `token_contract_address` | The contract address of the token involved in the transaction. |
| `reserve0`, `reserve1` | The reserves of the two tokens in the liquidity pool. |
| `pair_contract_address1` | The contract address of the token pair. |
| `token0.id`, `token1.id` | Identifiers for the first and second tokens in the pair. |
| `price` | The price of the token pair (exchange ratio of token0 and token1). |

## Pathfinding Algorithm and Arbitrage Calculation

The main goal of this part is to find raw Cycles in a directed graph. This algorithm starts at a specified start node and uses Depth First Search (DFS) to traverse all paths in the directed graph, looking for paths that form true loops...

The adjusted price considering slippage is given by:
Slippage = (Theoretical Amount - Actual Amount Received) / Theoretical Amount

## Code Files Description

- `Arbitrage Verification.ipynb`: A tool for assisting verification of token_pair conversion to path correctness.
- `Arbitrage_Analysis with different Length.ipynb`: Code file for analyzing different cycle lengths starting from a specific token.
- `Arbitrage_Analysis with different token.ipynb`: Analysis of arbitrage amounts and distributions for different tokens on the same path length.
- `Network Visualization.ipynb`: A tool for the visualization of directed graph networks.
- `Triangular Arbitrage Analysis.ipynb`: Code for basic triangular arbitrage calculations.
