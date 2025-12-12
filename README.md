
# Mento V3 Audit Overview

Mento V3 is an evolution of the Mento Protocol, transitioning from a Reserve-backed stablecoin and swap protocol to a **CDP-backed decentralized Foreign Exchange (FX) protocol**.

V3 introduces:

* **FPMM (Fixed Price Market Maker)** — enabling fixed-price stablecoin swaps
* **Liquidity management** via rebalancing strategies
* **User-driven stablecoin minting through CDPs**, based on an upgraded Liquity v2 fork fully integrated with Mento

---

## Prize Distribution & Scoring

**Total Prize Pool:** $60,000

* Scoring is described on the competition scoring page
* Finding severity categories are detailed in the docs

---

## Documentation

* **Technical Documentation**
* **Code Walkthrough**

---

## Scope

### Repositories

* **mento-core (feat/mento-v3)**
  Commit: `78fc103fab67e798258621e04176e25561b6f093`
  [https://github.com/mento-protocol/mento-core/tree/feat/mento-v3](https://github.com/mento-protocol/mento-core/tree/feat/mento-v3)

* **bold (feat/mento-v3)**
  Commit: `d8735b6ecd5b3915918340cf278868703d845fb6`
  [https://github.com/mento-protocol/bold/tree/feat/mento-v3](https://github.com/mento-protocol/bold/tree/feat/mento-v3)

---

## In-Scope Files

### **bold**

Including new & unchanged contracts, excluding deleted files:
Diff: [https://github.com/mento-protocol/bold/pull/17/files](https://github.com/mento-protocol/bold/pull/17/files)
Branch: [https://github.com/mento-protocol/bold/tree/feat/mento-v3/contracts/src](https://github.com/mento-protocol/bold/tree/feat/mento-v3/contracts/src)

```
contracts/src/Dependencies/AddRemoveManagers.sol
contracts/src/Dependencies/AggregatorV3Interface.sol
contracts/src/Dependencies/Constants.sol
contracts/src/Dependencies/LiquityBase.sol
contracts/src/Dependencies/LiquityBaseInit.sol
contracts/src/Dependencies/LiquityMath.sol
contracts/src/Dependencies/Ownable.sol
contracts/src/PriceFeeds/FXPriceFeed.sol
contracts/src/Types/BatchId.sol
contracts/src/Types/LatestBatchData.sol
contracts/src/Types/LatestTroveData.sol
contracts/src/Types/TroveChange.sol
contracts/src/Types/TroveId.sol
contracts/src/ActivePool.sol
contracts/src/AddressesRegistry.sol
contracts/src/BatchManagerOperations.sol
contracts/src/BorrowerOperations.sol
contracts/src/CollateralRegistry.sol
contracts/src/CollSurplusPool.sol
contracts/src/DefaultPool.sol
contracts/src/GasPool.sol
contracts/src/HintHelpers.sol
contracts/src/MultiTroveGetter.sol
contracts/src/SortedTroves.sol
contracts/src/StabilityPool.sol
contracts/src/SystemParams.sol
contracts/src/TroveManager.sol
contracts/src/TroveNFT.sol
```

---

### **core v3**

Diff: [https://github.com/mento-protocol/mento-core/pull/631](https://github.com/mento-protocol/mento-core/pull/631)
Branch: [https://github.com/mento-protocol/mento-core/tree/feat/mento-v3](https://github.com/mento-protocol/mento-core/tree/feat/mento-v3)

```
contracts/libraries/LiquidityStrategyTypes.sol
contracts/libraries/TradingLimitsV2.sol
contracts/liquidityStrategies/CDPLiquidityStrategy.sol
contracts/liquidityStrategies/LiquidityStrategy.sol
contracts/liquidityStrategies/ReserveLiquidityStrategy.sol
contracts/oracles/OracleAdapter.sol
contracts/oracles/breakers/MarketHoursBreaker.sol
contracts/swap/router/Router.sol
contracts/swap/virtual/VirtualPool.sol
contracts/swap/virtual/VirtualPoolFactory.sol
contracts/swap/FPMM.sol
contracts/swap/FPMMFactory.sol
contracts/swap/FPMMProxy.sol
contracts/swap/FactoryRegistry.sol
contracts/swap/OneToOneFPMM.sol
contracts/swap/ReserveV2.sol
contracts/tokens/StableTokenV3.sol
contracts/tokens/StableTokenSpoke.sol
```

---

## Build Instructions

```bash
cd mento-core
yarn
forge install
forge build

cd ../bold/contracts
forge install
forge build
```

---

## Out of Scope

### Previous Security Reports

* ChainSecurity Report 1
* ChainSecurity Report 2
* Expected behaviors such as trusted/untrusted roles
* Accepted risks

**Trusted Assumptions:**

* Owner/Governance must be trusted
* Liquidity Strategies are developed internally and treated as trusted

### LightChaser Reports

* Bold
* Core

---

## Basic PoC Requirements

* Mandatory PoC rule applies
* Integration tests may be used as foundations for PoCs:

[https://github.com/mento-protocol/mento-core/tree/feat/mento-v3-dev/test/integration/v3](https://github.com/mento-protocol/mento-core/tree/feat/mento-v3-dev/test/integration/v3)

---

## Contact

For issues or questions related to this competition, contact the **Cantina core team** via Discord.

---

If you want this exported as a file (`.md`) ready for download, tell me — I can generate it directly.
