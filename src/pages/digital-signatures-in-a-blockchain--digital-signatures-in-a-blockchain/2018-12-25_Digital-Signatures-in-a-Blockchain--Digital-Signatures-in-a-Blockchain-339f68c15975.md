---
title: 'Digital Signatures in a Blockchain: Digital Signatures in a Blockchain - Part 4'
description: >-
  In my previous post, I discussed how a digital signature can authenticate the
  sender of the message and the content of the message by…
date: '2018-12-25T09:58:59.492Z'
categories: []
keywords: []
slug: >-
  /@taisukemino/digital-signatures-in-a-blockchain-digital-signatures-in-a-blockchain-339f68c15975
language: "en"
---

In my [previous post](https://medium.com/icovo/digital-signatures-in-a-blockchain-digital-signatures-44b981b75413), I discussed how a digital signature can authenticate the sender of the message and the content of the message by utilizing the private to public usage of asymmetric encryption and a hashing algorithm. In this piece, I will look at how a blockchain integrates a digital signature.

### **Digital Signatures in a Blockchain**

In a blockchain, you send a transaction instead of a message. That’s it. It’s not much different from sending a message as shown below.

![](https://cdn-images-1.medium.com/max/800/1*n2x62TPSDebEtVwI8xOgwg.png)

This means you use a digital signature to prove:

1.  the sender of a transaction is who they say they are
2.  the transaction was unmodified in transit

Let’s think about the case where Alice sends a signed transaction to Bob.

#### **Alice Signs a Transaction**

Alice wants to sign a transaction and thus creates her digital signature. As the owner of the account, she performs the following steps:

1.  describes the transaction with all necessary information such as the involved addresses, the amount being transferred, etc…
2.  creates the hash value of the transaction data
3.  encrypts the hash value with the private key of her account that hands-off ownership
4.  adds the encrypted text created in step 3 to the transaction as its digital signature
5.  broadcasts it to the network

#### **Bob Verifies a Transaction**

In order to verify her transaction, Bob performs the following steps:

1.  creates the hash value of the transaction data to be verified except Alice’s digital signature
2.  decrypts the digital signature of the transaction considering the address that sent the transaction
3.  compare the hash value of step 1 with the value gained in step 2

If both were identical, you can confirm the authenticity of the owner and the integrity of the transaction data. Now Bob knows that Alice is the owner of the fund and the transaction data was not modified in transit. Other full nodes in the network also have access to Alice’s public key, and thus they can verify Alice’s transaction as well.

That’s it!
