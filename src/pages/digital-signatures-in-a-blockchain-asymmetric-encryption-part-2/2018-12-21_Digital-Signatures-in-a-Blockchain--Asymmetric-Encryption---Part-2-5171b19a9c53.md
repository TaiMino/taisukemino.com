---
title: 'Digital Signatures in a Blockchain: Asymmetric Encryption - Part 2'
description: >-
  I talked about the symmetric encryption system in my previous post. In this
  post, we will look at how the asymmetric encryption system…
date: '2018-12-21T03:22:51.332Z'
categories: []
keywords: []
slug: >-
  /@taisukemino/digital-signatures-in-a-blockchain-asymmetric-encryption-5171b19a9c53
language: "en"
---

I talked about the symmetric encryption system in [my previous post](https://medium.com/icovo/digital-signatures-in-a-blockchain-cryptography-and-symmetric-encryption-af51f071b5ce). In this post, we will look at how the asymmetric encryption system works.

### Asymmetric Encryption System

I cannot overstate how revolutionary the paradigm shift from the symmetric encryption to the asymmetric encryption(also called public-private key encryption) was in the world of cryptography.

The distinct difference between these two systems is that there are two different keys in asymmetric encryption. You **create a pair of complementary keys** by using the cryptographic software. The two keys are different yet mathematically related. **One key is called a public key, and another key is called a private key. You give your public key to everyone else and keep the private key for yourself.**

![](https://cdn-images-1.medium.com/max/800/1*R3ypLg7PrDKsgVmjCafT1g@2x.jpeg)

A public key is your email address in a sense that 1) you can communicate with other people by sharing it and 2) there is no problem with sharing it in terms of security. Whereas, a private key is your password in a sense that you should never, ever share it.

You can easily derive the public key from the private key, but you cannot guess what the private key is from the public key. In other words, they have the _one-way_ relationship. Going the public-to-private direction is equivalent to brute-force guessing an unfathomably large number of possibilities. This is why it’s safe to share your public key.

Let’s say Alice and Bob want to exchange messages. Alice generates a public and a private key pair, send her public key to Bob, and keep her private key to herself. Likewise, Bob generates a key pair, send his public key to Alice, and keep his private key to himself.

![](https://cdn-images-1.medium.com/max/800/1*fkw6A1Yssi8AgsUNCeQ7kw@2x.jpeg)

If Alice wants to send Bob a secret message, she uses Bob’s public key to encrypt the message, and send the message to him. This message will stay encrypted until Bob — and only Bob — unlocks the encrypted message with his private key.

![](https://cdn-images-1.medium.com/max/800/1*_deNqWddNVERqilbAOlWYw@2x.jpeg)

Conversely, if Bob wants to send Alice a secure message, he uses Alice’s public key to encrypt the message, and send the message to her. This message will stay encrypted until Alice — and only Alice — unlocks the encrypted message with her private key. A receiver is in charge of encryption in this system in a sense that a sender uses the receiver’s public key.

![](https://cdn-images-1.medium.com/max/800/1*wpR35EJVu-i_wG_3myifJQ@2x.jpeg)

The beauty of the asymmetric system is that **you don’t have to take the risk of transporting the private key.** Everyone can create a ciphertext with the public key, but only the owner of the private key can decrypt the ciphertext and read the message. Whereas, in a symmetric encryption system, there was only one key, and you had to share that with the other party somehow, which was the significant vulnerability: once one of the parties is compromised, the whole system is broken. In essence, the asymmetric encryption system solved the key distribution problem.

### How To Hack Asymmetric Encryption System

However, we can still hack this system. How do you do that without stealing the private key? Maybe you are wondering if it’s really okay to make one of the keys public.

In short, malicious hackers can spoof the public key. Once they change the public key with his public key, he can intercept and read the ciphertext because it was encrypted with his public key. Obviously, he can use his private key to decrypt the message. Then he can pretend to be the original sender by using the original public key and send the message to the owner of the private key. This attack is called the man-in-the-middle attack. It might look difficult to pull off but it’s still significant vulnerability. When something is hackable, somebody is going to hack it.

![](https://cdn-images-1.medium.com/max/800/1*p5mdZB5DngVjjCp5LlUpLQ@2x.jpeg)
![](https://cdn-images-1.medium.com/max/800/1*-7GgtvhobBIgrOiUOPtXMg@2x.jpeg)

The problem is that there is **no way to prove that 1) the sender is who they say they are and 2) the message was unmodified in transit.** This is where digital signatures come along.
