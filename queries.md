---
sidebar_position: 3
title: Sample Queries
---

# Exchange Subgraph Examples

## Sample Queries

Below are some sample queries to help you get started with the LOOKS Distribution Subgraph.

You can build your own queries using a [GraphQL Explorer](https://api.thegraph.com/subgraphs/name/looksrare/looks-distribution) and enter your endpoint to limit your queries to the exact data desired.

### Get Pending Rewards for User
`Note: user address should be all lowercase`

```graphql
query GetPendingRewards($user: String = "0x123...") {
  user(id: $user) {
    tradingRewardsAmount
    listingRewardsAmount
    tradingRewardsLastClaimDate
    listingRewardsLastClaimDate
    feeSharingAdjustedDepositAmount
    aggregatorAdjustedDepositAmount
    feeSharingLastWithdrawDate
    feeSharingLastHarvestDate
    aggregatorLastDepositDate
  }
}
```

### Get Recent Snapshots

Description: Get the recent user activity metric snapshots

```graphql
query GetSnapshots {
 dailySnapshots(first: 500, orderBy:date, orderDirection: desc) {
    id
    date
    aggregatorActiveUsers
    aggregatorTotalStakedLOOKS
    feeSharingActiveUsers
    feeSharingTotalStakedLOOKS
  }
}
```

### Get Looks Poundin'

Description: Get the recent conversions of ETH to Looks conversions from compounding staking

```graphql
query QueryName {
aggregatorConversions(first: 1000, orderBy:block, orderDirection: desc) {
      id
      block
      amountSold
      amountReceived
      priceOfETHInLOOKS
  }
}
```
