---
layout: tutorial
title: What is cryptographic hashing and what are it's properties?
permalink: /what-is-hashing-cryptography-used-in-bitcoin-blockchain/
description: Hashing is fundamental to blockchains, bitcoins, and any cryptocurrency and in this lesson, we look at the basic properties of hashing and how these properties makes hashing attractive to blockchains and cryptocurrencies. 
---

Cryptographic hashing is a fundamental concept that you should learn and understand to get a good grip on blockchain, bitcoin, or any cryptocurrency. Hashing is a vast field of research and you can find several college departments dedicated to research on cryptographic hashing. But, for the purposes of this tutorial, we will understand a few fundamentals that will help you get a grip on blockchain technology. Let's get started! 

## Definition of Hashing 
Here's a definition of hashing that I picked up from Wikipedia. **Hashing means taking an input string of any length and giving out an output of a fixed length.** This is the basic definition of hashing. Take some input data (of any length), process it, and produce an output which has a fixed, known number of characters.

## Example of Hashing 
To drive home the definition of hashing, let us look at two examples using the [SHA-256](http://www.iwar.org.uk/comsec/resources/cipher/sha256-384-512.pdf) hashing scheme (the SHA256 algorithm is a very popular hashing function which we will study later) :-
```
input = blockchain  output = EF7797E13D3A75526946A3BCF00DAEC9FC9C9C4D51DDC7CC5DF888F74DD434D1
input = bitcoin     output = 6B88C087247AA2F07EE1C5956B8E1A9F4C7F892A70E324F1BB3D161E05CA107B 
```
In the above example, we used a SHA-256 hash generator and gave it two input strings - "blockchain" and "bitcoin" and asked it to generate the SHA-256 output or hash (_we generally refer to the output as the "hash" of the input_). What you see as the output is the SHA-256 output containing 64 characters each and each character is made up of 4 bits (so that gives us 64x4 = 256 bits of information in the hash). 

With this example, I hope you understand what a hashing function does. Now, let us take a look at the properties of a hashing function that make it interesting and usable for cryptocurrencies. **In the next tutorial, we will see how to apply these properties to blockchains.**


## Fundamental properties of a hashing function
So, let's say you decide to create your own hashing function and you want everyone to use it. There are a few basic properties that your hashing function needs to satisfy in order for others to take it seriously. This is not an exhaustive list, but a few fundamental properties that should be satisfied. Let's take a look! 

* **Deterministic**: what this means, is that if I provide a particular string (e.g., "cryptochainery") a zillion times to the hashing function, then every single time, the hashing function should return the exact same hash. All zillion outputs/hashes should be identical and this is called **deterministic**. 

* **Uniformity**: A good hash function should map the expected inputs as evenly as possible over its output range. If this is not satisfied, then a hashing function might map all of its inputs to a particular range of possible hash values and this might lead to collisions. And, collisions (or two inputs giving the same output) is certainly something that we want to avoid. 

* **Not invertible**: This is sometimes also called the "**one-way requirement**". Simply put, if I cannot guess the input by looking at the output, then it is a non-invertible hash. In the worst case, it should require an impossible amount of computation to reverse-engineer or invert the hash. That is why it is also called the "one-way property".

* **Fixed size / defined range**: It is desirable that the hash function create a hash of a known, fixed, pre-determined length. For example, the popular [SHA-256](https://en.wikipedia.org/wiki/SHA-2) hash produces a 256-bit long hash. Random numbered outputs require extra work for verification and might not make sense for cryptocurrencies.

* **Quick to compute**: this is an interesting property. To have a lot of people use your new hash function, it should be easy for them to compute. It should not need a powerful computer to compute, but, it should be incredibly difficult to reverse-engineer! Being easy to compute is why cryptographic hashes find uses in common uses cases like digitally signing documents (and doesn't need any fancy hardware).

* **Small changes to the input make large changes to the hash**: What this means is that if I change one character in the input (maybe change an "x" to a "y"), then the output/hash should change drastically! Here is an example from [SHA-256](https://en.wikipedia.org/wiki/SHA-2). You can see that by adding a single alphabet "x" to the input string "cryptochainery", the hash completely changes. This is a very important property as it makes the hash incredibly hard to hack. It prevents hackers from running random tests to detect patterns (e.g., if I add an "x" to the string, does the output always change predictably?).
```
input = cryptochainery     output = 0B8A51051650071F36D64ABC1DACB41FE52601B6E8B2C89BFBDCA129FA1650EF
input = cryptochaineryx    output = C8B79109CB23C3E218D8C37D0D787BD95362FA58DEBFE3145D4B469C3E00278F 
```

## Quick summary of hashing
Okay! That was a lot of information - so let's summarize it quickly before we forget:

* the hashing function should produce an output/hash that has a fixed size. 
* you should not be able to guess the input by looking at the output (no recognizable patterns in the output hash).
* no two inputs should give the same hash.
* the hash should be extremely hard to reverse-engineer (computationally speaking).
* computing the hash should be computationally efficient. 

## So how do we apply hashing to cryptocurrency?
If you understand these fundamental properties of hashing, then you have the necessary knowledge to understand how hashing is used in blockchains and cryptocurrencies (bitcoin, altcoins). We will dive into this in another lesson, but I'll give you a sneak peek for now.

Let's say a bitcoin transaction took place and the transaction details are stored as a string. Let this string be our input string and it is sent to the hashing function which produces a hash. This hash is easy to verify (hard but doable), but, you cannot guess the transaction details from just looking at the hash (why? because it satisfies the property of not being invertible). This is a great security feature that helps making blockchains secure.

However, this is just the tip of the iceberg - we need to study a little more about concepts like proof-of-work, double-spending, public/private keys, etc. to fully grasp the use of hashing in cryptocurrencies. Let's take a look at these concepts in future tutorials. 

