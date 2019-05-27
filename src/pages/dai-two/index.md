---
title: 'DAI Stable Coins: Stabilization System Basics'
description: This post is Part 2 of the ongoing series DAI Stable Coins.
date: '2019-02-18T06:36:00.767Z'
categories: []
keywords: []
slug: /@taisukemino/dai-two
language: "en"
---

![source: [https://makerdao.com/en/dai](https://makerdao.com/en/dai)](https://cdn-images-1.medium.com/max/800/1*TkCA2hl0TkJemykj3pgzvg.png)
source: [https://makerdao.com/en/dai](https://makerdao.com/en/dai)

This post is Part 2 of the ongoing series _DAI Stable Coins_.

In this piece, I’m going to talk about the simplified version of their stabilization system for the sake of understanding the core mechanism. In the upcoming posts, I add more complexity as we think of cases where DAI can be unstable.

MakerDAO achieved the blockchain equivalent of the central bank monetary policy in a decentralized manner to stabilize DAI. There is basically no central entity to control their system. Instead, they beautifully designed the game-theoretical model with their autonomous smart contracts: the contracts financially incentivize people to interact with them so that the system can stabilize the DAI price.

The core smart contracts are called **Collateralized Debt Position (CDP)**. You can interact with these smart contracts to make a loan by locking up your ether as collateral. This permissionless credit system allows anyone to lock their ether up as collateral and issue DAI against them(I demonstrate this in the next post). It’s important to note that their contracts always assume that 1USD = 1DAI.

So, how do they stabilize DAI?

Let’s say you can exchange $100 worth of 1ETH, and get 100DAI.

1ETH(=$100) <=> 100DAI

As I mentioned before, the contracts always assume that 1USD = 1DAI. This constant value might create some gap between the contract price and the market price.

Think of the case where the market price was below before you locked in your ETH:

USD: 100  
DAI: 95

In this situation, it’s a smart move to make more loans. Why? Because you can get 100DAI with $100 worth of 1ETH when in the market you can get only 95DAI. Once you make more loans, you could trade DAI in an open market and gain some capital. If 1DAI is more than 1USD, you are financially incentivized to make more loans. Then the contracts issue more tokens, which pull the price down to 1 dollar due to a shorter supply.

Now let’s think about the other case: you issued DAI a month ago. Below is the market price of DAI right now:

USD: 100  
DAI: 105

In this case, you’d want to pay back this loan. Why? Because you can get $100 worth of 1ETH only with 100DAI and leave 5DAI in your pocket. If 1DAI is less than 1USD, it is cheaper to pay back the loan. When you pay back your loan, the smart contracts burn the DAI and then give ETH back to you, which means the price is pushed up to 1 dollar due to a larger supply.

The key here is the difference between the contract price and the market price. Participants in the DAI ecosystem are either incentivized to make more loans or pay back their loans depending on the gap between the contract price and the market price. You can see that there are two forces at play: pull the price down or push the price up. If 1DAI is more than 1USD, people are incentivized to lock ETH and issue/get more DAI, which pulls down the price of DAI. If 1DAI is less than 1 USD, they are incentivized to pay back the loan and burn DAI, which pushes up the price of DAI.

Their clever smart contracts autonomously respond to humans who are economically incentivized by varying market price dynamics and the constant contract price. The price stability is managed by controlling the supply side of the DAI through this interaction.

Now, this is not a comprehensive explanation of their system because I didn’t take volatility of ETH into consideration. We see how to handle black swan events where ETH crushes in the upcoming posts, but before that, we’ll go over the process of generating DAI so that we can get a more intuitive understanding.
