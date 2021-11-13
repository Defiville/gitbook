# NFTAction

It is a utility NFT useful for managing any type of DeFi action, like a deposit into a strategy or even more complex actions.

The token image (tokenURI) is a loot style, it displays infos related to the action.

![](<../.gitbook/assets/Screen Shot 2021-11-13 at 6.50.20 PM.png>)

It is the fist NFTAction created as test. ([https://opensea.io/collection/nftaction](https://opensea.io/collection/nftaction))

Action steps:

1. Provide liquidity to curve 3pool in DAI/USDC/USDT
2. Deposit the curve LP obtained in 1) into the StakeDAO Passive USD strategy
3. Deposit the stakeDAO LP obtained in 2) into the SDT reward pool

Users have to just choose the amount of DAI/USDC/USDT that we want to use, and the contract will do all actions for them and finally it will mint a new NFTAction. The infos displayed into the image (am3CRV and SDT balances) will change over time, up to date with the actual action earning. The NFT needs to be burned for redeeming every assets related to the action.



