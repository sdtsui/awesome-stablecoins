# Awesome Stablecoins

A curated list of stable cryptocurrency resources and projects

## What are stable cryptocurrencies?
> "Stablecoins, in their most ideal form, are simply cryptocurrencies with stable value...usable as a store of value, medium of exchange, and unit of account."
  -- [Multicoin Capital: An Overview of Stablecoins](https://multicoin.capital/2018/01/17/an-overview-of-stablecoins/)

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

## Maintaining stability (Incomplete)
  - CFD ([Contract For Difference](https://www.investopedia.com/terms/c/contractfordifferences.asp)), related derivates, [trades](https://www.investopedia.com/terms/c/cashandcarry.asp), and futures contracts
    - See also: Arthur Hayes' [BitMEX blog posts](https://blog.bitmex.com/xbtusd-the-philosophers-stone/) on [Synthetic USD](https://blog.bitmex.com/in-depth-creating-synthetic-usd/)
  - CDP (Collateralized Debt Position)
  - Price Oracles
    - Fully Trusted/Centralized
      - Reuters
    - Decentralized/Delegated
      - MKR
      - Basecoin Price Feed (todo: link to paper)
    - Peer to Peer
      - Truthcoin/Bitcoinhivemind?
    - Schelling Point Schemes (Carbon or Kowala, need to check)
      - [V's post](https://blog.ethereum.org/2014/03/28/schellingcoin-a-minimal-trust-universal-data-feed/)
      - 100000 14237 59049 76241 81259 90215 132156 157604

  - [Seignorage Shares](https://bravenewcoin.com/assets/Whitepapers/A-Note-on-Cryptocurrency-Stabilisation-Seigniorage-Shares.pdf)
    - [Repo](https://github.com/rmsams/stablecoins) and [Vitalik's Summary](https://blog.ethereum.org/2014/11/11/search-stable-cryptocurrency/)
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
  - [Stablecoins are doomed to fail, Pt. III: SAGA](https://prestonbyrne.com/2018/03/22/stablecoins-are-doomed-to-fail-pt-iii-saga/)
  - [Basecoin: the worst idea in cryptocurrency, reborn](https://prestonbyrne.com/2017/10/13/basecoin-bitshares-2-electric-boogaloo/amp/)

Project Comparisons:
  - [MakerDAO vs Basecoin](https://www.reddit.com/r/MakerDAO/comments/76mup4/makerdao_vs_basecoin/)
  - Vitalik's [comments](https://ethresear.ch/t/collateralized-debt-obligations-for-issuer-backed-tokens/525/8) on Maker's CDPs and price feed Rune's [response](https://www.reddit.com/r/MakerDAO/comments/7z0wvr/vitalik_comments_on_manipulating_the_price_feed/)
  > Another thing I have thought about is that in an economic model where you do not assume altruistic honesty or non-coordination, it’s not clear that makerdao has a higher security level, or even that it’s possible to achieve a higher security level, than seignorage shares. If the total discounted expected future profits of the scheme are lower than the amount of capital inside it, then the shareholders have the incentive to manipulate the price feed in order to siphon everyone’s money out. I’d be interested in seeing more detailed analysis on this.



## Project List

##### Crypto-Collateralized  
---------
| Project Name  | Link | Notes |
| ------------- | ------------- | ------------- |
| Augmint/A-Euro| [Augmint](https://www.augmint.cc/) | Collateralized by Native Token |
| BitShares/BitUSD  | [Bitshares](https://bitshares.org/technology/price-stable-cryptocurrencies/)  | 100% collateralized, BTS  |
| Havven/Nomin | [Havven](https://havven.io) | >100% Collateralized by Native Token |
| MakerDAO/Dai  | [MakerDAO](https://makerdao.com/)  [Dai Dashboard](https://dai.makerdao.com/) | >100% collateralized, P-ETH CDPs for now, one of few stablecoins being used [compensate developers](https://forum.makerdao.com/t/dapphub-invoice-june-2017/883)  |
| Set | [Set Protocol](https://setprotocol.com/) | Set is working on fully collateralized ERC-20 baskets, one of which will be a collateralized by other stable tokens |
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
| Tether | [Tether](https://tether.to/) | Fiat |

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
  - [The Stable Fund: Request for Startups](https://stable.fund/rfs)
  - [Kyokan](https://angel.co/kyokan) is open to collaborate with projects and funds interested in accelerating adoption of cryptocurrencies by designing incentives, building generalized tools/payment integrations, and improving usability.
