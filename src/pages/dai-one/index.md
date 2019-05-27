---
title: 'DAI Stable Coins: Why Stable Coins Matter'
description: This post is Part 1 of the ongoing series DAI Stable Coins.
date: '2019-02-15T04:01:01.646Z'
categories: []
keywords: []
slug: /@taisukemino/dai-one
language: "en"
---

![[https://coinmarketcap.com/currencies/dai/](https://coinmarketcap.com/currencies/dai/)](https://cdn-images-1.medium.com/max/800/1*OIrH5NKBhtZtxK2kLCP8pg.png)
[https://coinmarketcap.com/currencies/dai/](https://coinmarketcap.com/currencies/dai/)

This post is Part 1 of the ongoing series _DAI Stable Coins_.

Last year, a part of my salary was paid with Ether. It made sense for both my client and me because it was easy and cost-efficient. As you may know, the market price of ether plummeted last year, and as a lazy person who didn’t bother exchanging ether immediately with fiat money, I lost a fair amount of money.

It was around that time of the bear market that I first seriously looked into stable coins. How wonderful is it if cryptocurrencies protect us from downward fluctuations without going through a tedious process of exchanging volatile cryptocurrencies with fiat money?

You may say it would be difficult to control the price once people start to trade coins in the open market. However, considering the stability of the YEN or USD and how people trade it in the open market, this is possible. In fact, some of the stable coins have been working well so far. The beauty of stable coins is that they cannot fake their legitimacy: look at the price change. Last year, Ethereum [plummeted](https://etherscan.io/chart/etherprice) from $1400 to $90, but DAI(one of the stable coins) [fluctuated slightly](https://coinmarketcap.com/currencies/dai/) around $1. Sure, they fluctuate a little bit, but this is much more stable than other cryptocurrencies that fluctuate as much as 25% in a day.

In essence, you can use stable coins as a store of value: they ensure that value is retained. The volatility of cryptocurrencies might be a good feature for investors, but a bug for other uses such as payments and savings. People would not want to use unstable cryptocurrencies for everyday currencies. Stable coins enable us to use cryptocurrencies other than speculative purposes.

Permission-less nature of the blockchain allowed citizens of unstable national currencies to gain access to censorship-resistant currencies like bitcoin. Stable coins add a new layer of stability to help them retain the value. Immigrants can remit their earning to their family back home without worrying about the price change. International workers, shop owners or customers don’t have to worry about the price change when they pay or get paid with cryptocurrencies for goods and services.

Moreover, the long-term stability enables other essential financial functions such as loans and credit. People don’t want to take out the loan in something volatile. Why would I borrow 1 bitcoin today if it could be worth twice as much next month? Now I owe a lot more money than I borrowed. Conversely, why would I lend out 1 bitcoin today if it could be worth half as much next month? Now I lost money just by lending it out.

Furthermore, as we build more smart contract-based systems where the contracts control fund, the stability of the fund becomes a critical part of the system. For example, token holders of [DAICO system](https://medium.com/icovo/what-is-daico-b88286fa7b7f) don’t want to see their Ether lose its value by half when they withdraw it.

My hunch is that stable coins play a critical role in the mass adaption of cryptocurrencies.

There are different implementations of stable coins, and in this piece, I focus on DAI: one of the crypto-collateralized stable coins by MakerDAO(Don’t worry if you don’t understand what this means right now.) I start from the basics of their decentralized stabilization system. Then I go over the process of generating DAI through their smart contracts to get an intuitive understanding of it. Next, we see how DAI system handles black swan events where Ether crushes and lose its value substantially. Finally, I take a brief look at their smart contracts to understand what is happening behind the scene.
