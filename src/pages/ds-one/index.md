---
title: >-
  Digital Signatures in a Blockchain: Cryptography and Symmetric Encryption -
  Part 1
description: >-
  Cryptography is a core part of blockchain technology. You won’t understand how
  it works if you skip this subject. That said, cryptography…
date: '2018-12-20T08:22:12.032Z'
keywords: []
slug: >-
  /@taisukemino/ds-one
language: "en"
---

Cryptography is a core part of blockchain technology. You won’t understand how it works if you skip this subject. That said, cryptography is not all that difficult to understand(unless you dig deeper into the math-heavy part of it). In this series of posts, I will be explaining general ideas of cryptography, symmetric encryption, asymmetric encryption(aka public-key cryptography) and finally digital signatures. You will be able to understand how blockchain technology uses digital signatures to claim the ownership of cryptocurrencies if you follow along. In this first post, you will learn general ideas of cryptography and symmetric encryption.

### What Is Cryptography?

First things first, “What is cryptography?” This video below is the scene from [The Imitation Game](https://www.imdb.com/title/tt2084970/) where Alan Turing(arguably the father of the computer) is taking a class with his friend.

This is cryptography! He was exchanging encrypted messages with his friend in the classroom so that other people cannot understand what they were talking about. You could see that the clueless teacher thought their notes were gibberish. The major idea of cryptography is **keeping secrets so that we can prevent our data from being accessed by unauthorized people**. In fact, the word _cryptography_ was derived from the Greek word kryptos, meaning “hidden”.

Cryptography might not sound familiar to you, but it is around us. People love gossip and secrets. In that sense, we are all cryptographers.

Now let’s take a look at a specific example of encryption: the Caesar Shift Cipher. Yes, Julius Caesar was using this encryption. Cryptography has been around for a long time.

Here is a demo of the Caesar Shift Cipher. Click on the _Decrypt_ button. You should see the word “_blockchain_”. Now…compare the ciphertext with the plaintext. Spend some time to figure out how this encryption system works.

Here is another demo that uses the same encryption system. What do you think you will get when you decrypt this text?

You should see “ethereum”. Did you get the answer right?

How does this work? It’s quite simple. It replaces each letter in the message with the one that is three places further down the alphabet.

![](https://cdn-images-1.medium.com/max/800/1*E-NPAcnhd303Bo3p733hrA@2x.jpeg)

Before you read further, I suggest that you play a bit with this cryptography [here](http://rumkin.com/tools/cipher/caesar.php) so that you can get an intuitive understanding. Set the number to 3 and type some text. Then you will see encrypted texts at the bottom.

### An Algorithm and Key

Now that you know what cryptography is, let’s dig deeper. There are two important concepts in cryptography: **an algorithm and a key**.

Let’s say Alice wants to send a secret message to Bob in a classroom. In order to keep the secret, she encrypts the plaintext with an algorithm and a key. Once Bob receives the message from her, he uses the same algorithm and key shared with him upfront to decrypt the message. What do I exactly mean by an algorithm and a key?

![](https://cdn-images-1.medium.com/max/800/1*b2jLcOpBFXQNtQDuJufcmQ@2x.jpeg)

In the case of the Caesar Shift Cipher, the algorithm is to replace one alphabet with another by shifting the alphabet. How many patterns are there when you shift alphabets? 26 patterns. This means there are 26 keys. In this case, she chooses the key that replaces each letter in the message with the one that is three places further down the alphabet. So when I told you to select number 3 on [this website](http://rumkin.com/tools/cipher/caesar.php), I was giving you the key.

![](https://cdn-images-1.medium.com/max/800/1*p_eaUMzMuak7z1cnofHUfQ@2x.jpeg)

**The algorithm is a general system for encryption, and it needs to be specified exactly by selecting a specific key**.

Congrats! You already learned one major form of cryptography. It’s called **symmetric** **encryption:** **you** **share the same algorithm and key only with the other party and then you use them to encrypt/decrypt the message**. In this way, only someone with the correct key can communicate.

### How to Hack Symmetric Encryption System

But is symmetric encryption safe? Let’s see if we can hack it. Imagine that Alice and Bob are in a long-distance relationship, and they want to exchange messages secretly. This time, they are not going to use the Caesar Shift Cipher because people can easily crack it once they know the algorithm given that there are only 26 different patterns. It’s important that the encryption system won’t be cracked just by showing the algorithm([Kerckhoffs’ Principle](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle)). Instead, they are going to use a more robust algorithm called AES(Advanced Encryption Standard), which is a widely used symmetric encryption system today. They use keys associated with it so that there is an almost infinite number of patterns the attacker has to try.

![](https://cdn-images-1.medium.com/max/800/1*SUE8pRij9jiAlko9wzQKlw@2x.jpeg)

Sure, the AES is robust encryption, but you desperately want to know what they are talking about. How do you do that? It’s important to note that both parties have to know the same key because it means that they have to share the information somehow.

Yes, you could steal the key when they share it. Symmetric keys are hard to share especially when the two parties are physically far apart. They probably share it on the Internet, and there is a possibility that somebody eavesdrops in transit.

![](https://cdn-images-1.medium.com/max/800/1*lhtbfGeA9WtXZNdnx7V34w@2x.jpeg)

Once you steal the key, you can easily read the message. The problem with a symmetric encryption system is that **both parties need to know the same key, and thus there is a possibility that** **the key might be stolen in transit**.

As a side note, this doesn’t mean symmetric encryption is useless although it is not perfect for everything. For example, [iPhone has a dedicated AES-256 crypto engine](https://www.apple.com/business/docs/iOS_Security_Guide.pdf). All the important data on your phone — photos, messages, contacts, reminders, call history — are encrypted by default. Nobody but you can access the iPhone’s contents unless your passcode is compromised. There is no problem with using symmetric encryption here because you are not gonna share the key. In storage encryption, the “sender” and “recipient” are the same person but at different points in time. On top of that, symmetric encryption is efficient compared to another encryption system. Speed and power efficiency are critical in mobile devices considering performance and battery life problems. In general, symmetric encryption is considered to be a good fit for file encryption on mobile devices.

But what if we want to secretly communicate with somebody who is physically apart? This is where an asymmetric encryption system comes along.
