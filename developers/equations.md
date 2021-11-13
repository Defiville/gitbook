# Equations

## Minting

Minting a new **bAny** happens by allowing users to purchase bonds. This bond price is the Mint price.

$$
bond Price = TBA + Premium
$$

Every **bAny** has an intrinsic value, its related **TBA** (treasury backed amount), In order to make a profit from minting, it charges a premium for each minting action.

$$
Premium = debt Ratio * BCV
$$

The premium is derived from the debt ratio of the system and a scaling variable called BCV. BCV allows us to control the rate at which bond prices increase.

The premium determines profit due to the protocol and in turn, stakers. This is because new **bAny** token is minted from the profit and subsequently distributed among all stakers.

$$
debt Ratio = bondsOutstanding/bAnySupply
$$

The debt ratio is the total of all **bAny** promised to bonders divided by the total supply of **bAny**. This allows us to measure the debt of the system.

$$
bondPayout_{reserveBond} = marketValue_{asset}\ /\ bondPrice
$$

Bond payout determines the number of **bAny** sold to a minter. For reserve mints, the market value of the assets supplied by the minter is used to determine the bond payout. For example, if a user supplies 1000 **Any** and the mint price is 250 **Any**, the user will be entitled 4 **bAny**.

$$
bondPayout_{lpBond} = marketValue_{lpToken}\ /\ bondPrice
$$

For liquidity mints, the market value of the LP tokens supplied by the minter is used to determine the bond payout. For example, if a user supplies 1 BDAI-DAI LP token which is valued at 1000 DAI at the time of bonding, and the bond price is 250 DAI, the user will be entitled 4 BDAI.&#x20;



## bAny Supply

$$
bAny_{supplyGrowth} = bAny_{stakers} + bAny_{bonders} + bAny_
{DAO}
$$

**bAny** tokens supply does not have a hard cap. Its supply increases when:

* **bAny** is minted and distributed to the stakers.
* **bAny** is minted for the bonder. This happens whenever someone purchases a bond.
* bAny is minted for the DAO. This happens whenever someone purchases a bond. The DAO gets the same number of bAny as the bonder.

$$
bAny_{stakers} = bAny_{totalSupply} * rewardRate
$$

At the end of each epoch, the treasury mints bAny at a set reward rate. These bAny will be distributed to all the stakers in the protocol.&#x20;

$$
bAny_{bonders} = bondPayout
$$

Whenever someone purchases a bond, a set number of **bAny** tokens is minted. These **bAny** will not be released to the minter all at once - they are vested to the bonder linearly over time. The bond payout uses a different formula for different types of bonds. Check the Minting section above to see how it is calculated.

$$
bAny_{DAO} = bAny_{bonders}
$$

The DAO receives the same amount of **bAny** as the minter. This represents the DAO profit.

## Backing per bAny token

$$
bAny_{backing} = TBA * bAny_{tolalBalance}
$$

Every **bAny** in circulation is backed by its related **TBA **(Treasury Backed Amount).

$$
treasuryBalance_{stablecoin} = TBA_{reserveBond} + TBA_{lpBond}
$$

The backed balance in the treasury grows when bonds are sold. Backing per **bAny** is calculated differently for different mints types.

$$
BackingPerbAny_{reserveBond} = assetSupplied
$$

