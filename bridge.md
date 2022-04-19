# Summary

Users can map ETH, BTC, stable coins and other assets to Darthion through the asset cross-chain bridge, which is achieved by locking a certain number of assets on the source chain and generating the corresponding number of Tokens in Darthion.

Darthion encourages community developers to provide more decentralized cross-chain solutions.

This document describes the option for project parties to map Tokens from the source chain to Darthion on their own.

> [Darthion-brige ref here](./bridge2.md)

The project owner **self** maintains the total balance of Token on the multi-chain including Darthion, and endorses the credibility of Token.

The main processes include：

```
1）Initial Preparation
2）Source Chain -> Darthion Chain
3）Darthion Chain -> Source Chain
```

## Glossary 

Source Chain: The source chain where the Token is located (e.g. Ethereum)

Src_Token: Token on the source chain, possibly a contract, or a native Token

Locked address or contract: the address used to lock the Token

Darthion_Token: Token on Darthion's chain
## Initial Preparation

1) Deploy the lock address or contract on the source chain `Src_Lock_Addr`

2) Deploy Token on Darthion: `Darthion_Token`

3) Deploy a lock address or contract on Darthion `Darthion_Lock_Addr`

If you need multiple sign contracts, you can refer to [gnosis/MultiSigWallet](https://github.com/gnosis/MultiSigWallet).

If you need contracts with mint/burn, you can refer to [OpenZeppelin/openzeppelin-contracts](https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/) contracts/token/ERC20).


> In order to maintain credibility, the project needs to publicize the above information to the community and invite the community to supervise it. And to monitor the total amount of coins on both chains.

## Source Chain->Darthion Chain

1) Source chain locking `Src_Token`

Transfer a certain amount of `Src_Token` to `Src_Lock_Addr` for locking

2) Release `Darthion_Token` on the Darthion chain

Execute mint operation to give `Darthion_Lock_Addr` the corresponding amount of `Darthion_Token`

## Darthion chain->Source chain

1) Darthion chain lock `Darthion_Token`

Execute burn operation, destroy `Darthion_Token`

2) Release `Src_Token` on the source chain

operation `Src_Lock_Addr` to unlock the corresponding volume