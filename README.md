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
        - [Thread](https://www.reddit.com/r/MakerDAO/comments/7z0wvr/vitalik_comments_on_manipulating_the_price_feed/) between Rune and V on MKR
      - Basecoin Price Feed (todo: link to paper)
    - Peer to Peer
      - Truthcoin/Bitcoinhivemind?
    - Schelling Point Schemes (Carbon or Kowala, need to check)
      - [V's post](https://blog.ethereum.org/2014/03/28/schellingcoin-a-minimal-trust-universal-data-feed/)
      - 100000 14237 59049 76241 81259 90215 132156 157604

  - CDO (Collateralized Debt Obligation)
    - [V's other post](https://ethresear.ch/t/collateralized-debt-obligations-for-issuer-backed-tokens/525)

  - [Seignorage Shares](https://bravenewcoin.com/assets/Whitepapers/A-Note-on-Cryptocurrency-Stabilisation-Seigniorage-Shares.pdf)
    - Note differences/variations in model between projects

## Project List

##### Crypto-Collateralized  
---------
| Project Name  | Link | Notes |
| ------------- | ------------- | ------------- |
| Augmint/A-Euro| [Augmint](https://www.augmint.cc/) | Collateralized by Native Token |
| BitShares/BitUSD  | [Bitshares](https://bitshares.org/technology/price-stable-cryptocurrencies/)  | 100% collateralized, BTS  |
| Havven/Nomin | [Havven](https://havven.io) | >100% Collateralized by Native Token |
| MakerDAO/Dai  | [MakerDAO](https://makerdao.com/)  [Dai Dashboard](https://dai.makerdao.com/) | >100% collateralized, P-ETH CDPs for now  |
| Sweetcoin/BridgeCoin | [Sweetbridge.com](https://sweetbridge.com/product) | ETH collateralized for now |

##### Non-Crypto-Collateralized  
---------
| Project Name  | Link | Notes |
| ------------- | ------------- | ------------- |
| AAA Reserve  | [AAA Reserve](https://www.aaareserve.com/)  | Fiat |
| DigixDAO/DigixGold | [DigixDAO](https://digix.global/) | Gold |
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
  - [The Stable Fund: Request for Startups](https://stable.fund/rfs)
  - [Kyokan](https://angel.co/kyokan) is open to collaborate with projects and funds interested in accelerating adoption of cryptocurrencies by designing incentives, building generalized tools/payment integrations, and improving usability.
