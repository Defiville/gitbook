# Bany (3,3)

## What is a BToken ?

Every asset can be backed for creating the related bToken, a token with a backed amount represented by the native token, and this value will increase over time, thanks to fees collected by the bond sale.



## How to buy Btoken ?

The protocol will put in sale Btoken via the bonding mechanism introduced by Olympus (OHM docet), and users can start to buy them at a discount price. They can buy bonds using the backed token (DAI for BDAI, USDC for BUSDC), it locks the Btoken for a vesting period&#x20;

## How many bToken will be minted ?

During the bonds sale, it will mint new Btokens and distribute them to the Btoken stakers. Every btoken has a treasury backed amount (TBA), the amount reserved for each token into the treasury, and it will mint a new Btoken for every TBA collected during the bonds sales. &#x20;

* 1% will be dedicated increase the TBA (in the backed token)
*   99% will be dedicated to mint new Btokens:

    * &#x20;0.5% to ISLA stakers
    * &#x20;0.5% to MetaWorld DAO
    * 98% to Btoken stakers&#x20;







## Minting

Minting a new bToken happens by allowing users to purchase bonds. This bond price is the Mint price.

$$
bond Price = TBA + Premium
$$

Every bToken has an intrinsic value, its related TBA (treasury backed amount), In order to make a profit from minting, it charges a premium for each minting action.

$$
Premium = debt Ratio * BCV
$$

The premium is derived from the debt ratio of the system and a scaling variable called BCV. BCV allows us to control the rate at which bond prices increase.

The premium determines profit due to the protocol and in turn, stakers. This is because new bToken is minted from the profit and subsequently distributed among all stakers.

$$
debt Ratio = bondsOutstanding/bTokenSupply
$$

The debt ratio is the total of all bToken promised to bonders divided by the total supply of bToken. This allows us to measure the debt of the system.

$$
bondPayout_{reserveBond} = marketValue_{asset}\ /\ bondPrice
$$

Bond payout determines the number of bToken sold to a minter. For reserve mints, the market value of the assets supplied by the minter is used to determine the bond payout. For example, if a user supplies 1000 DAI and the mint price is 250 DAI, the user will be entitled 4 BDAI.

$$
bondPayout_{lpBond} = marketValue_{lpToken}\ /\ bondPrice
$$

For liquidity mints, the market value of the LP tokens supplied by the minter is used to determine the bond payout. For example, if a user supplies 1 BDAI-DAI LP token which is valued at 1000 DAI at the time of bonding, and the bond price is 250 DAI, the user will be entitled 4 BDAI.&#x20;



## Backing per bToken

$$
bToken_{backing} = TBA * bToken_{tolalBalance}
$$

Every bToken in circulation is backed by its TBA. For every bToken the assets in the treasury can be divided into two categories: backed and non-backed. bToken represented by an ERC20 as backed will have only a treasury represented by the backed value. Instead bToken with an NFTActions as backed will have a treasury represented by both categories.

$$
treasuryBalance_{stablecoin} = TBA_{reserveBond} + TBA_{lpBond}
$$

The backed balance in the treasury grows when bonds are sold. Backing per bToken is calculated differently for different mints types.

$$
BackingPerbToken_{reserveBond} = assetSupplied
$$

For reserve mints such as MIM minting, the Backing per bToken simply equals to the amount of the underlying asset supplied by the minter.

$$
BackingPerTIME_{lpBond} = 2sqrt(constantProduct) * (\%\ ownership\ of\ the\ pool)
$$

For LP Mints such as BTOKEN-TOKEN Minting, the Backing Per bToken is calculated differently because the protocol needs to mark down its value. _Why? _The LP token pair consists of bToken, and each bToken in circulation will be backed by these LP tokens - there is a cyclical dependency. To safely guarantee all circulating bToken are backed, the protocol marks down the value of these LP tokens.
