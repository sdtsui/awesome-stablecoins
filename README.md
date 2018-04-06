# Awesome Stablecoins

A curated list of stable cryptocurrency resources and projects

## What are stable cryptocurrencies?
> "Stablecoins, in their most ideal form, are simply cryptocurrencies with stable value...usable as a store of value, medium of exchange, and unit of account."
  -- [Multicoin Capital: An Overview of Stablecoins](https://multicoin.capital/2018/01/17/an-overview-of-stablecoins/)

Technically, most stablecoins are digital tokens pegged to a stable store of value. This is especially true in the case of issuer-backed tokens, where the store of value is the collateral.
Credit to Buck Perley (Engineer at Purse) for pointing this out.

## Prior art
  - Issuing shares, [fiat](https://www.coindesk.com/lhv-bank-backs-wallet-app-built-on-bitcoins-blockchain/), and other assets with [Bitcoin Script](https://en.bitcoin.it/wiki/Colored_Coins#Issuing_shares), most commonly using  `OP_RETURN` to attach metadata to fractions of a Bitcoin.

## Applications
- Markets/Exchanges: as a hedge against crypto volatility for traders, creation of new trading pairs, fiat-denominated on-chain derivates and other financial instruments, prediction markets
- DApps: medium of exchange for DApps, prediction markets, insurance
- Commerce: international remittance, on-chain fiat payment integrations

## Types of stable cryptocurrencies
- Crypto-Collateralized
- Non-Crypto-Collateralized
- Uncollateralized/Other

Note that this categorization is intentionally as general as possible, and emphasizes implementation (from a product perspective), not market segmentation.  For example, liquidity can be shared between categories, as in the case of a Dai or Set partially collateralized with TrueUSD, Basecoin, or Tether. Credit to Panashe Mahachi (Growth at L4, Investment at The Stable Fund) for emphasizing this.

## Maintaining stability (Incomplete)

  - CFD ([Contract For Difference](https://www.investopedia.com/terms/c/contractfordifferences.asp)), related derivates, [trades](https://www.investopedia.com/terms/c/cashandcarry.asp), and futures contracts
    - In a way, this is a naive
    - See also:
      - Arthur Hayes' [BitMEX blog posts](https://blog.bitmex.com/xbtusd-the-philosophers-stone/) on [Synthetic USD](https://blog.bitmex.com/in-depth-creating-synthetic-usd/)
      - VariabL's [exploration of the problem space](https://blog.variabl.io/stabl-becomes-variabl-first-derivatives-trading-platform-on-ethereum-a9a06a59b818), previously they were productionizing similar ideas using Ethereum smart contracts, as [StabL](https://blog.variabl.io/stabl-bringing-stable-tokens-and-derivative-products-to-the-ethereum-blockchain-df4d5eba89d9).

  - CDP (Collateralized Debt Position)
    > CDPs hold collateral assets deposited by a user and permit this user to generate Dai, but
generating also accrues debt. This debt effectively locks the deposited collateral assets
inside the CDP until it is later covered by paying back an equivalent amount of Dai, at which
point the owner can again withdraw their collateral . Active CDPs are always collateralized in
excess, meaning that the value of the collateral is higher than the value of the debt.
  -- The Maker Team, [MakerDAO Whitepaper](https://makerdao.com/whitepaper/DaiDec17WP.pdf)

CDPs and CFDs commonly require:
  - Price Oracles
    - They publish the price to a centralized issuing authority, or smart contract. Also known as price feeds.
    - There are currently few schemes being used or considered:
      - Fully Trusted/Centralized
        - See:
          - TR's Work on [BlockOne](https://blockoneiq.thomsonreuters.com/)
          - The [price indicies](https://www.bitmex.com/app/index/.BXBT) used by BitMEX's contracts, and their [Fair Price Marking methods](https://www.bitmex.com/app/fairPriceMarking)
      - Partially Centralized, Distributed, Delegated, Staked, or Peer to Peer
        - See:
          - [MKR's price feeds](https://developer.makerdao.com/feeds/)
          - Bitcoinhivemind's [oracle protocol](http://bitcoinhivemind.com/)
          - 
        > A semi-decentralized approach is to select a
small group of feed uploaders by vote from holders of Basecoin. Given this set of
feed uploaders, the system can choose the median exchange rate from them at
fixed intervals. If any bad actor is consistently identified as trying to corrupt the
feed, they can be voted out of the system by coin-holders who have an incentive
to preserve the system’s long-term value. This captures most of the benefits of
decentralization. A similar scheme called Delegated Proof of Stake (DPoS) is
even used in other protocols to generate entire blocks, though some argue that
it’s gameable.

          -- Basecoin Team, [Basecoin Whitepaper](http://www.getbasecoin.com/basecoin_whitepaper_0_99.pdf)

      - Schelling Point Schemes
        - Vitalik's [blog](https://blog.ethereum.org/2014/03/28/schellingcoin-a-minimal-trust-universal-data-feed/) describing schellingcoin-derivated data feeds.
        - 100000 14237 59049 76241 81259 90215 132156 157604
        - 
        > Carbon utilizes a decentralized schelling point scheme to achieve distributed consensus
on Carbon’s exchange rate. Every 24 hours, also known as the rebasement
period, a schelling point scheme is initiated where nodes submit bids for what
they believe the true exchange rate of Carbon to be. Each bid is weighted by
a collateral, denominated in Carbon. At the end of the 24 hours, bids are totaled
and the protocol takes a weighted average of the bids. Anyone who bids
outside the 25th and 75th percentiles will have their balances slashed. Anyone
within the 25th and 75th percentiles receive a normal distribution of the loser’s
balances, with the highest reward distribution at 50% and normally diminishing
on the right and left respectively
        -- [Carbon Whitepaper](https://www.carbon.money/whitepaper.pdf)


  - [Seignorage Shares](https://bravenewcoin.com/assets/Whitepapers/A-Note-on-Cryptocurrency-Stabilisation-Seigniorage-Shares.pdf), first introduced by Robert Sams
    - [Repo](https://github.com/rmsams/stablecoins), [Epicenter](https://www.youtube.com/watch?v=V7-xSVJQrgI), and [Vitalik's Summary](https://blog.ethereum.org/2014/11/11/search-stable-cryptocurrency/)
    - Uses one of the schemes above (commonly schelling coins) as a price oracle.
    - There is a lot of variation between projects, but roughly:
      - When price is above the peg, new tokens are printed to increase supply, and distributed amongst 'shareholders', holders of the governance token, or some other token.
      - When price is below the peg, rights to future profits (sometimes referred to as 'bonds') are created. These are sold for the stablecoin, which are locked up or burned, contracting supply.

  - [CDOs (Collateralized Debt Obligations)](https://ethresear.ch/t/collateralized-debt-obligations-for-issuer-backed-tokens/525)
    - Proposes combining multiple issuer-backed tokens with a bidding process on the open market, so the risk of individual issuers can be accurately priced. Potentially removes the need for heavy reliance on price oracles.

## Debates, limitations, criticisms, and instances of broken pegs
> "Crypto-collateralized stablecoins are the perpetual motion machines of modern finance.
...A stablecoin that is collateralized by itself is a complex and fragile [Nakamoto Scheme](https://prestonbyrne.com/2017/12/08/bitcoin_ponzi/) doomed to fail. A stablecoin that is collateralized by real assets and structured correctly is not a stablecoin, but a unit trust."
  -- [Preston Byrne](https://prestonbyrne.com)

  - [Stablecoins are doomed to fail](https://prestonbyrne.com/2017/12/10/stablecoins-are-doomed-to-fail/)
  - [Stablecoins are doomed to fail, Part II: MakerDAO’s “DAI” stablecoin is breaking, as predicted](https://prestonbyrne.com/2018/01/11/epicaricacy/)
    - [Reddit](https://www.reddit.com/r/ethereum/comments/7pqwnj/stablecoins_are_doomed_to_fail_part_ii_makerdaos/), and [HN](https://news.ycombinator.com/item?id=16141759) threads.
    - [Twitter thread](https://twitter.com/AFDudley0/status/951355773724045312), with Rick Dudley, in response to a perceived break of the peg: volume was unclear.
  - [Stablecoins are doomed to fail, Pt. III: SAGA](https://prestonbyrne.com/2018/03/22/stablecoins-are-doomed-to-fail-pt-iii-saga/)
  - [Basecoin: the worst idea in cryptocurrency, reborn](https://prestonbyrne.com/2017/10/13/basecoin-bitshares-2-electric-boogaloo/amp/)


Project Comparisons:
  - [MakerDAO vs Basecoin](https://www.reddit.com/r/MakerDAO/comments/76mup4/makerdao_vs_basecoin/)
  - Vitalik's [comments](https://ethresear.ch/t/collateralized-debt-obligations-for-issuer-backed-tokens/525/8) on Maker's CDPs and price feed Rune's [response](https://www.reddit.com/r/MakerDAO/comments/7z0wvr/vitalik_comments_on_manipulating_the_price_feed/)
  - 
  > Another thing I have thought about is that in an economic model where you do not assume altruistic honesty or non-coordination, it’s not clear that makerdao has a higher security level, or even that it’s possible to achieve a higher security level, than seignorage shares. If the total discounted expected future profits of the scheme are lower than the amount of capital inside it, then the shareholders have the incentive to manipulate the price feed in order to siphon everyone’s money out. I’d be interested in seeing more detailed analysis on this.
  -- Vitalik, [Ethresear.ch thread](https://ethresear.ch/t/collateralized-debt-obligations-for-issuer-backed-tokens/525/5)


On NuBits:
  - [NuBits: A Tumultuous Stablecoin](https://medium.com/coinforward/nubits-a-tumultuous-stablecoin-afe94cbe9df8)
  - [Jordan Lee, NuBits community thread on replacing Liquidity Providers](https://discuss.nubits.com/t/withdrawn-make-firing-and-replacing-incompetent-liquidity-providers-our-top-priority/4036)
  - [Dan Larimer's Critique](http://archive.is/EmBdj)

On Tether:
  - [BitMex Research: Tether](https://blog.bitmex.com/tether/)
  - [Bitfinex'd](https://medium.com/@bitfinexed)
  - [1](https://www.financemagnates.com/cryptocurrency/news/analysis-bitfinex-tether-still-close-comfort/), [2](https://www.cnbc.com/2018/02/02/tether-what-you-need-to-know-about-the-cryptocurrency-worrying-markets.html), [3](https://hackernoon.com/a-closer-look-at-tethers-blockchain-5c3032328e52)

## Project Table

##### Crypto-Collateralized  
---------
| Project Name  | Link | Notes |
| ------------- | ------------- | ------------- |
| Augmint/A-Euro| [Augmint](https://www.augmint.cc/) | Collateralized by Native Token |
| BitShares/BitUSD  | [Bitshares](https://bitshares.org/technology/price-stable-cryptocurrencies/)  | 100% collateralized, BTS  |
| Havven/Nomin | [Havven](https://havven.io) | >100% Collateralized by Native Token |
| MakerDAO/Dai  | [MakerDAO](https://makerdao.com/)  [Dai Dashboard](https://dai.makerdao.com/) | >100% collateralized, P-ETH CDPs for now, with a [Haskell Reference Implementation](https://makerdao.com/purple/). One of few stablecoins actively used to [compensate](https://forum.makerdao.com/t/dapphub-invoice-june-2017/883) the implementing team's developers.  |
| NuShares/NuBits | [NuBits](https://www.nubits.com/) | - |
| Set | [Set Protocol](https://setprotocol.com/) | Not technically a stablecoin-focused project. Set is working on fully collateralized ERC-20 baskets. Mentioned here because it will be used to hold baskets of other stable tokens. |
| Sweetcoin/BridgeCoin | [Sweetbridge.com](https://sweetbridge.com/product) | ETH collateralized for now |

##### Non-Crypto-Collateralized  
---------
| Project Name  | Link | Notes |
| ------------- | ------------- | ------------- |
| AAA Reserve  | [AAA Reserve](https://www.aaareserve.com/)  | Fiat |
| DigixDAO/DigixGold | [DigixDAO](https://digix.global/) | Gold |
| Saga | [Saga](https://saga.org/) | Hybrid model where crypto is deposited as collateral but exchanged for fiat.  Uses a fractional reserve. Included in this section for simplicity. |
| Stably  | [Stably](https://www.stably.io/)  | Fiat |
| TrueUSD | [TrueUSD](https://www.trueUSD.com) | Fiat |
| Tether | [Tether](https://tether.to/) | Fiat, on Omni |

##### Uncollateralized/Other  
---------
| Project Name  | Project Link | Notes |
| ------------- | ------------- | ------------- |
| Basecoin  | [Basecoin](http://www.getbasecoin.com/)  | Three-token model of basecoin, shares, and bonds, which are paid in a specific order |
| Carbon  | [Carbon](https://www.carbon.money/) | Two-token 'Aztec' Model, supply contraction via reverse dutch auction  |
| Fragments  | [Fragments.org](https://www.fragments.org/)  | Three-token model, USD Fragments, USD Fragment Bonds, and reserve collateral (ETH for now)  |
| Kowala  | [Kowala](https://kowala.tech/)  | Uses fees, arbitrage, and variable block reward for PoW miners to control supply |

## How to help:
  - Improve this repo by making a PR!
  - The Stable Fund is working on accelerating adoption, in collaboration with L4 and Maker. See their [Request for Startups](https://stable.fund/rfs)
  - [Kyokan](https://angel.co/kyokan) is open to collaborating with projects and funds interested and exchange/payments applications, and improving usability of cryptoassets.

----------
----------
----------

#### Misc/Uncategorized Resources
  - https://thecontrol.co/stablecoins-a-holy-grail-in-digital-currency-b64f3371e111
  - https://hackernoon.com/stablecoins-designing-a-price-stable-cryptocurrency-6bf24e2689e5
  - Phi:
      - https://medium.com/@danfinlay/phi-decentralized-lending-and-stable-currency-might-not-actually-be-stable-36f472948591
      - https://www.reddit.com/r/ethereum/comments/5fjncm/a_critique_of_phi_the_lending_platform_and_stable/dalltg6/