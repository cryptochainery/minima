---
layout: page
title: What is hashing in cryptography?
permalink: /what-is-hashing-cryptography-used-in-bitcoin-blockchain/
description: Hashing is fundamental to blockchains, bitcoins, and any cryptocurrency and in this lesson, we get a good understanding of how hashing works and what properties of hashing makes it attractive to blockchains and cryptocurrencies. 
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
In the above example, we gave a SHA-256 Hashing function generator two input strings - "blockchain" and "bitcoin" and asked it to generate the SHA-256 output or hash (_we generally refer to the output as the "hash" of the input_). What you see as the output is the SHA-256 output containing 64 characters each and each character is made up of 4 bits (so that gives us 64x4 = 256 bits of information in the hash). 

With this example, I hope you understand what a hashing function does. Now, let us take a look at the properties of a hashing function that make it interesting and usable for cryptocurrencies. **In the next tutorial, we will see how to apply these properties to blockchains.**


## Fundamental properties of a hashing function
So, let's say you decide to create your own hashing function and you want everyone to use it. There are some basic properties that your hashing function needs to satisfy in order for others to take it seriously. Let's take a look! 

* **Deterministic** : what this means, is that if I provide a particular string (e.g., "cryptochainery") a zillion times to the hashing function, then every single time, the hashing function should return the exact same hash. All zillion outputs/hashes should be identica and this is called **deterministic**. There are some corner cases though which you should be aware of. Some hashing functions might use the system time or memory address to create the hash of a string (i.e., in the hashing algorithm) - but both time and memory addresses are prone to change. In such a situation, if you run the hash function multiple times with the same input, you _**might**_ not get the same output hash. So, in this situation, the hash is deterministic for that session (period of time) only -- if you don't fully understand this, please don't worry. Just be aware that being deterministic is necessary for cryptocurrency (blockchain, bitcoin).

* **Uniformity** : A good hash function should map the expected inputs as evenly as possible over its output range. If this is not satisfied, then a hashing function might map all of its inputs to a particular range of possible hash values and this might lead to collisions. And, collisions (or two inputs giving the same output) is certainly something that we want to avoid. 

* **Not invertible** : This is sometimes also called the "**one-way requirement**". Simply put, if I cannot guess the input by looking at the output, then it is a non-invertible hash. In the worst case, it should require an impossible amount of computation to reverse-engineer or invert the hash. That is why it is also called the "one-way property".

* **Fixed size / defined range** : It is desirable that the hash function create a hash of a known, fixed, pre-determined length. For example, the popular [SHA256](https://en.wikipedia.org/wiki/SHA-2) hash produces a 256 bit long hash. This is helpful in using it in table-lookups, etc. There is 

* **Quick to compute** : this is an interesting property. To have a lot of people use your new hash function, it should be easy for them to compute - right? But, it should not be easy to reverse-engineer! 

* **Small changes to the input make large changes to the hash** : This is an intrinsic property that is connected to Uniformity, Not Invertible properties of the hash. If I change one character to the input (maybe change an "x" to a "y") and I see that only the last character of the output changed from "0" to "1", then that is a clue to a hacker. It is preferable that even the smallest change to the input makes a large change to the output. Here is an example from SHA-256. 

```
input = cryptochainery     output = 0B8A51051650071F36D64ABC1DACB41FE52601B6E8B2C89BFBDCA129FA1650EF
input = cryptochaineryx    output = C8B79109CB23C3E218D8C37D0D787BD95362FA58DEBFE3145D4B469C3E00278F 
```


Okay that was a lot of information. Let's summarize it quickly :-
> * the hash should have a fixed size. 
> * you should not be able to guess the input by looking at the output (because the output has a recognizable pattern).
> * no two inputs should give the same hash.
> * the hash should be sufficiently hard to reverse-engineer (computationally).
> * the hash should be computationally efficient to compute. 

In the context of cryptocurrencies like Bitcoin, the transactions are taken as an input and run through a hashing algorithm (Bitcoin uses SHA-256) which gives an output of a fixed length.




Repeating this from Wikipedia : _A hash function is any function that can be used to map data of arbitrary size to data of a fixed size. The values returned by a hash function are called hash values, hash codes, digests, or simply hashes. A cryptographic hash function allows one to easily verify that some input data maps to a given hash value, but if the input data is unknown, it is deliberately difficult to reconstruct it (or any equivalent alternatives) by knowing the stored hash value._

That is a lot of information to digest - so let's break it down into small chunks. 

[<< Back to the tutorials homepage](https://cryptochainery.github.io/)