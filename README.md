# StableCoin Deep Dive:

- Using Foudary

* This is a section of the Cyfrin Foundry Solidity Course.

### About:

- This project is meant to be a stablecoin where users can deposit WETH and WBTC in exchange for a token that will be pegged to the USD.

### Notes:

1. (Relative Stability : Anchored or Pegged) -> $1.00
   1. Chainlink Price feed.
   2. Set a function to exchange ETH & BTC -> $$$
2. Stability Mechanism (Minting) : Algorithmic (Decentralized)
   1. People can only mint the stablecoin with enough collateral (coded)
3. Collateral: Exogenous (Crypto)
   1. wETH
   2. wBTC

- calculate health factor function
- set health factor id debt is 0
- added a bunch of view functions

1.  What are our invariants/properties ?

### Steps:

1. create project

   ```bash
   forge init
   ```

2. create .env file and run
   ```bash
   source .env
   ```
3. install dependencies on foundry:
   ```bash
   forge install --no-commit smartcontractkit/chainlink-brownie-contracts openzeppelin/openzeppelin-contracts@v4.8.3
   ```
   /foundry.toml
   ```
   remappings = ['@chainlink/contracts/=lib/chainlink-brownie-contracts/contracts/', '@openzeppelin/contracts=lib/openzeppelin-contracts/contracts']
   ```
4. create smart contracts:
   - /src
     - /libraries
       - OracleLib.sol
     - DecentralizedStableCoin.sol
     - DSCEngine.sol
