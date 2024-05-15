# graphprotocol-queries

## graph-network-mainnet:

API: https://api.thegraph.com/subgraphs/name/graphprotocol/graph-network-mainnet

* Query Total Network Signal:
```
query Signal {
  graphNetworks{
  totalTokensSignalled
  }
}
```

Output:

```
{
  "data": {
    "graphNetworks": [
      {
        "totalTokensSignalled": "2511756234728594384913269"
      }
    ]
  }
}
```

* Query Indexer Params:
```
query Indexer {
  indexer(id: "0xa3276e7ab0a162f6a3b5aa6b3089accbaa65d12e") {
  indexingRewardCut
  delegatedTokens
  stakedTokens
  }
}
```

Output:

```
{
  "data": {
    "indexer": {
      "indexingRewardCut": 1000000,
      "delegatedTokens": "489465356184153376574121",
      "stakedTokens": "100000677674648883935653"
    }
  }
}
```

* Query Subgraph Params:
```
query {
                    subgraphs(where:{currentVersion_not:null}, first: 10){
                        id
                        metadata {
                        displayName
                        image
                        }
                            currentVersion {
                                id
                                subgraphDeployment {
                                    id
                                    deniedAt
                                    signalAmount
                                    signalledTokens
                                    stakedTokens
                                    indexingRewardAmount
                                    queryFeesAmount
                                }
                            }
                    }
                }
```

Output:

```
{
  "data": {
    "subgraphs": [
      {
        "id": "213qHEmF8UP7PfxFYAQjf8Gp81pViR7GRyDwnDycnqEC",
        "metadata": {
          "displayName": "Asymmetry  Finance",
          "image": "https://api.thegraph.com/ipfs/api/v0/cat?arg=QmfRUKbtPnG8S2WM1pquZLYtU3ge9pvdsoq7cmMvhtRSk5"
        },
        "currentVersion": {
          "id": "213qHEmF8UP7PfxFYAQjf8Gp81pViR7GRyDwnDycnqEC-2",
          "subgraphDeployment": {
            "id": "0x5a41321ddaa06196d5ad0ace703fcca2ae1d2fde4fea19f79674b22320764aea",
            "deniedAt": 0,
            "signalAmount": "24250254637838341675",
            "signalledTokens": "588074850000000000000",
            "stakedTokens": "0",
            "indexingRewardAmount": "6387582143821293355654",
            "queryFeesAmount": "0"
          }
        }
      }
    ]
  }
}
```

