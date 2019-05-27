---
title: 'Digital Signatures in a Blockchain: Digital Signatures - Part 3'
description: >-
  I talked about the asymmetric encryption system and its problem in my previous
  post. In this post, we will look at how digital signatures…
date: '2018-12-23T07:17:27.230Z'
categories: []
keywords: []
slug: >-
  /@taisukemino/digital-signatures-in-a-blockchain-digital-signatures-44b981b75413
language: "en"
---

I talked about the asymmetric encryption system and its problem in [my previous post](https://medium.com/icovo/digital-signatures-in-a-blockchain-asymmetric-encryption-5171b19a9c53). In this post, we will look at how digital signatures attack this problem in general. Among the cryptographic inventions over the past century, it’s safe to say that a digital signature is the most notable invention.

### **Digital Signatures**

I said that a major goal of cryptography is secrecy, and this is still true, but a digital signature is not about secrecy. It’s about authenticity.

In the previous post, we learned that asymmetric encryption is vulnerable to the man-in-the-middle attack because it fails to prove two things below:

1.  the sender is who they say they are
2.  the message was unmodified in transit

The modern asymmetric algorithm such as the RSA can prove these two things through the combination of:

1.  a private-to-public usage of an asymmetric encryption system
2.  a hash function

This is the digital signature. The former method proves the authenticity of the sender and the latter method proves that of the message.

#### **A Private-To-Public Usage of an Asymmetric Encryption System**

When we encrypted the message in the previous post, we used a public key to encrypt and a private key to decrypt. This is a public-to-private usage of the asymmetric encryption system. There is another way: a private-to-public usage. You use your private key to encrypt the message, and the receiver uses the public key to decrypt the message. If the decryption goes successfully, the receiver will know that they received a message from you because only you have the private key that matches the public key.

![](https://cdn-images-1.medium.com/max/800/1*pGvCdaVE83Xvu5xY5usXWg.png)

#### **A Hash Function**

Now we know that the sender is who they say they are. But how do we know if the message was unmodified in transit? This is where a hash function comes along. The hash function is such an important building block that is widely used in the blockchain that I’d love to spend some time to explain it.

Firstly, what is a function? A function is a set of rules that takes some input and output the value as a result.

![](https://cdn-images-1.medium.com/max/800/1*3sQ3kwo56RBpQlaJWUg3NA.png)

For example, if you put a slice of bread in a toaster as the input, what does that do? It toasts it up. That’s the function. And you get the toasted bread as the output.

![](https://cdn-images-1.medium.com/max/800/1*UPwzJL9ESyNFqeaoxAuh4Q.png)

Now the hash function is a function that produces a hash value as an output for a given input. A hash value is a fixed length of bytes. You always get the fixed length of bytes no matter how big or small the input(aka, preimage) is.

For example, if you give an input “tai” to SHA256 hash function(it’s one of the hash functions. There are different kinds of hash function. Bitcoin uses SHA256. Ethereum uses KECCAK256.), you will get:

```
~> echo -n “tai” | shasum -a 256  
// f4ddd195cab04430d4595e18bd75fd48df4a0dfb3a7a28c6b2fcf3582762d49d
```

\*You can copy the command above to play in your Terminal.

Another interesting aspect of a hash function is that when I capitalize ‘t’, and hash “Tai” string, I get:

```
~> echo -n “Tai” | shasum -a 256  
// e6e6f0079cf211607a8ae808e538511684dfe5950b8afffae89b68243f189cf6
```

I merely capitalized “t”, but you can see that the output is completely different.

Moreover, if I hash “Tai” string again, I get:

```
~> echo -n “Tai” | shasum -a 256  
// e6e6f0079cf211607a8ae808e538511684dfe5950b8afffae89b68243f189cf6
```

Exactly the same result. Hash functions are deterministic, that is, the same input will always produce the same output(Deterministic literally means it has been determined yet.)

I suggest that you can play a bit on [this page](http://www.timestampgenerator.com/tools/sha256-generator/). Input the value and click the button below. You can see the hash value at the bottom. It uses the same hash function I used.

To sum up, hash functions produce:

1.  a fixed length of bytes
2.  the same result for the same input and the different result for the different input

An output of a hash function is called a hash value. You can think of it as **a digital equivalent of a fingerprint**. We use fingerprints to identify humans uniquely. They have been used to investigate crimes or identify offenders. A hash value can be used to identify the data. If you pass identical data through the hash function, you will get an identical hash value because again it is deterministic. If you want to make sure that the message was unmodified in transit, you get the hash value and the message together. Once you get the message, you hash it and compare it with the hash value. If they were exactly the same, it is not modified. If they were different, somebody modified it in transit.

There are other characteristics of a hash function such as being one-way, but you can ignore that for now.

#### **Summary**

To recap, for a digital signature to function properly, we used:

1.  private-to-public usage of the asymmetric encryption system to prove the sender is who they say they are
2.  a hash function to prove that the message was unmodified in transit

### How To Send A Secure Message with The RSA

All right then, to summarize everything we have learned so far, let’s simulate how Alice can send a secret message to Bob without getting maliciously hacked. There are three important things to keep in mind here:

1.  the message should be strongly encrypted so that only Bob can read it
2.  there should be a way to prove that Alice sent the message
3.  there should be a way to prove that the message was not manipulated in transit

We will use:

1.  the public-to-private usage of the asymmetric encryption system to encrypt the message
2.  the private-to-public usage of the asymmetric encryption system to authenticate the sender
3.  a hash function to authenticate the content of the message

First, as we have seen before, Alice and Bob create their private key and public key pair. Bob sends the public key to Alice, and Alice sends the public key to Bob. Before Alice encrypts the message, she would run the message through a hash to generate a hash value. She would then take that value and encrypt it with her private key. The result is her digital signature for this message. This value then gets added to the original message which can be encrypted by Bob’s public key and transmitted to him.

Once received, the encrypted original message is decrypted by Bob’s private key and run through the same hash algorithm to generate a hash value. The digital signature is decrypted using the Alice’s public key and compared to the hash value above. If these hash values are the same, it verifies the digital signature.

![](https://cdn-images-1.medium.com/max/800/1*pOYE8kriCm2e_Ux72CeLgg.png)
