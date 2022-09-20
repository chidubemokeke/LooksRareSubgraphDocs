# LOOKS Distribution Subgraph Entities

### Entities for the LOOKS Distribution Subgraph are all listed below.
- [User](#User)
- [DailySnapshot](#DailySnapshot)
- [Overview](#Overview)
- [RewardPeriod](#RewardPeriod)
- [AggregatorConversion](#AggregatorConversion)

## User
| Field                                   | Type        | Description                                   |
| --------------------------------------- | ----------- | --------------------------------------------- |
| id                                      | ID!         | User Id                                       |
| airdropAmount                           | BigDecimal! | Airdrop amount claimed (LOOKS)                |
| airdropClaimDate                        | BigInt!     | Airdrop claim date                            |
| aggregatorAdjustedDepositAmount         | BigDecimal! | Aggregator adjusted deposit amount (LOOKS)    |
| aggregatorTotalCollectedLooks           | BigDecimal! | Aggregator total LOOKS collected              |
| aggregatorLastDepositDate               | BigInt!     | Aggregator last deposit date                  |
| aggregatorLastWithdrawDate              | BigInt!     | Aggregator last withdraw date                 |
| aggregatorIsActive                      | Boolean!    | Checks wether aggrgator is active or not      |
| feeSharingAdjustedDepositAmount         | BigDecimal! | Fee sharing - Adjusted deposit amount (LOOKS) |
| feeSharingTotalCollectedLooks           | BigDecimal! | Fee Sharing - Total LOOKS collected           |
| feeSharingTotalCollectedWETH            | BigDecimal! | Fee Sharing - Total WETH collected            |
| feeSharingLastDepositDate               | BigInt!     | Fee Sharing - Last deposit date               |
| feeSharingLastHarvestDate               | BigInt!     | Fee Sharing - Last harvest date               |
| feeSharingLastWithdrawDate              | BigInt!     | Fee Sharing - Last withdraw date              |
| feeSharingIsActive                      | Boolean!    | Checks wether fee sharing is active or not    |
| listingRewardsAmount                    | BigDecimal! | Listing Rewards - Total LOOKS collected       |
| listingRewardsLastClaimDate             | BigInt!     | Listing Rewards - Last claim date             |
| tradingRewardsAmount                    | BigDecimal! | Trading Rewards - Total LOOKS collected       |
| tradingRewardsLastClaimDate             | BigInt!     | Trading Rewards - Last claim date             |
| stakingPoolUniswapV2TotalCollectedLOOKS | BigDecimal! | UniswapV2 Staking - Total LOOKS collected     |
| stakingPoolUniswapV2LastDepositDate     | BigInt!     | UniswapV2 Staking - Last deposit date         |
| stakingPoolUniswapV2LastHarvestDate     | BigInt!     | UniswapV2 Staking - Last harvest date         |
| stakingPoolUniswapV2LastWithdrawDate    | BigInt!     | UniswapV2 Staking - Last withdraw date        |

## DailySnapshot 
| Field                         | Type        | Description                                                |
| ----------------------------- | ----------- | ---------------------------------------------------------- |
| id                            | ID!         | Daily Snapshot Id                                          |
| date                          | BigInt!     | Daily Snapshot date                                        |
| activeStakers                 | BigInt!     | Number of unique active stakers (Aggregator + Fee Sharing) |
| newStakers                    | BigInt!     | Daily new stakers (Aggregator + Fee Sharing)               |
| removedstakers                | BigInt!     | Daily removed stakers (Aggregator + Fee Sharing)           |
| aggregatorActiveUsers         | BigInt!     | Aggregator - Number of active users                        |
| aggregatorNewUsers            | BigInt!     | Aggregator - Daily new users                               |
| aggregatorRemovedUsers        | BigInt!     | Aggregator - Daily removed users                           |
| aggregatorDailyInflowLOOKS    | BigDecimal! | Aggregator - Daily inflow (LOOKS)                          |
| aggregatorDailyOutflowLOOKS   | BigDecimal! | Aggregator - Daily outflow (LOOKS)                         |
| aggregatorTotalStakedLOOKS    | BigDecimal! | Aggregator - Total LOOKS staked                            |
| aggregatorTotalWETHSold       | BigDecimal! | Aggregator - Total WETH sold                               |
| aggregatorTotalLOOKSReceived  | BigDecimal! | Aggregator - Total LOOKS received from sales               |
| aggregatorConversionCount     | BigInt!     | Aggregator - Number of conversions                         |
| feeSharingActiveUsers         | BigInt!     | Fee Sharing - Number active users                          |
| feeSharingNewUsers            | BigInt!     | Fee Sharing - Daily new users                              |
| feeSharingRemovedUsers        | BigInt!     | Fee Sharing - Daily removed users                          |
| feeSharingDailyInflowLOOKS    | BigDecimal! | Fee Sharing - Daily inflow (LOOKS)                         |
| feeSharingDailyOutflowLOOKS   | BigDecimal! | Fee Sharing - Daily outflow (LOOKS)                        |
| feeSharingTotalStakedLOOKS    | BigDecimal! | Fee Sharing - Total LOOKS staked                           |

## Overview 
| Field                         | Type        | Description                                                |
| ----------------------------- | ----------- | -----------------------------------------------------------|
| id                            | ID!         | Overview Id                                                |
| activeStakers                 | BigInt!     | Number of unique active stakers (Aggregator + Fee Sharing) |
| aggregatorActiveUsers         | BigInt!     | Aggregator - Number of active users                        |
| aggregatorTotalStakedLOOKS    | BigDecimal! | Aggregator - Total LOOKS staked                            |
| feeSharingActiveUsers         | BigInt!     | Fee Sharing - Number active users                          |
| feeSharingTotalStakedLOOKS    | BigDecimal! | Fee Sharing - Total LOOKS staked                           |

## RewardPeriod
| Field                 | Type        | Description                               |
| --------------------- | ----------- | ------------------------------------------|
| id                    | ID!         | ID (transaction hash)                     |
| block                 | BigInt!     | Block number                              |
| date                  | BigInt!     | Date (timestamp)                          |
| numberBlocks          | BigInt!     | Period length (in blocks)                 |
| reward                | BigDecimal! | Reward amount for the period (in WETH)    |
| rewardPerBlock        | BigDecimal! | Reward per block for the period (in WETH) |

## AggregatorConversion
| Field                 | Type        | Description                |
| --------------------- | ----------- | ---------------------------|
| id                    | ID!         | ID (transaction hash)      |
| block                 | BigInt!     | Block number               |
| date                  | BigInt!     | Date (timestamp)           |
| amountSold            | BigDecimal! | Reward sold (in WETH)      |
| amountReceived        | BigDecimal! | Reward received (in LOOKS) |
| priceOfETHInLOOKS     | BigDecimal! | Price of 1 WETH in LOOKS   |
