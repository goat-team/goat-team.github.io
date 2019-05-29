---
layout:     post
title:      "Wallet Management"
author:     "MikO"
subtitle:   "A Goat's guide to managing (most of) your cryptocurrency wallets."
date:       "2019-06-01"
categories: [guides, wallet, management, security]
tags:       [private key, wallet management, securing assets, BIP39, BIP44, BIP32]
permalink:  /guides/wallet-management
---

## Welcome

Today you are going to learn how to use an incredibly easy method for storing hundreds of your favorite cryptocurrencies with the use of a `single` passphrase!

This offline wallet management supports your favorite coins like `BTC` (many of its forks), `LTC`, `ETC`, `ETH`, `DOGE`, `CROWN`, `DASH`, etc.  As well as all your favorite Ethereum based tokens like (`ZRX`, `BAT`, `LOOM` and hundreds more).

Follow along as the Goat guides you through the technology, how to generate your own crypto vault as well as other useful tips for storing your phrase, and in future guides how to retrieve and use your keys for different networks.

## Purpose

The intention of this guide is to explain my wallet management strategy for `BIP44` compatible coin networks.  I have used this strategy for years and is what I show to everyone I introduce to crypto.

This strategy brings simplicity to key management of your crypto wealth.  Instead of managing desktop wallets or individual keys for each address you use, this method utilizes a single BIP39 mnemonic phrase that can be used to 'unwrap' the rest of your addresses and corresponding keys.

### Warning

**The Goat cannot stress this enough.**

```
You and only you are the keeper of your crypto wealth.

When handling BIP39 phrases or keys in general, you must make sure you secure them.

After you back up your phrase securely.  Test it out!

Don't send funds until you are comfortable navigating your keyspace.

Always test with a small amount of tokens before sending large amounts.

Make sure you can both send and receive comfortably.
```

### Physical Storage

This guide is not aimed at storage methods, so we won't go into much detail or debate.  Here are some options in no particular order:

#### [Crypto Steel](https://shop.trezor.io/product/cryptosteel?offer_id=23&aff_id=2606)

Not the most secure, but is Fire, Water and Shock Proof.  Overall it is nearly indestructable against even the most harsh conditions.  Great for storing in a very secure location (safe, safety deposit box, etc)

#### Laminated paper backup

Not the most secure, but gives you a waterproof option.

1. Write phrase on paper and fold in half twice.
1. Wrap in another piece of paper folded around the first.
1. Make sure you cannot see through the paper and read the phrase before laminating.
1. Laminate the folded papers.
1. Hide securely!

#### Sealed PVC piping with Laminated paper backup

Slightly more secure, but you risk losing where you buried it.  Might consider multiple lamination layers.

1. Do the steps above.
1. Cap both ends of a PVC pipe.
1. Bury in the ground in a location you won't forget!

### Digital Storage

This guide is not aimed at storage methods, so we won't go into much detail or debate.  Here are some options in no particular order:

#### Tombs
[Tombs](https://bitcoinbulletin.org/tomb-encrypted-storage-vault-bury-your-secrets/) Tombs (Linux / Mac)

Encrypted filesystem with key & password (Password only on Mac)
* Very strong encryption (aes-256)
* Portable.  You can disperse your tomb anywhere.  Email, Family email, thumb drive, dropbox, etc.
  * You can also do this with the Key if you trust your password to the key is very very strong.

#### Password Manager

Not the best solution, but can work.  Would not use for large amounts of crypto.

* Portable.  Accessible from most devices.
* Not the best place to store plain text phrases.  Possibly zipped text file with a very strong password stored in your password manager if it supports files.

### BIP39 Tool

#### Getting Started

Finally getting to the fun parts!  First steps include downloading and opening the offline BIP39 tool, then running it locally from a browser.  This is great because we don't have to goto a website to do any of this, meaning our keys are never broadcast over the internet.

#### Getting the BIP39 Tool

1. Visit [https://github.com/iancoleman/bip39/releases](https://github.com/iancoleman/bip39/releases)
1. Click on **bip39-standalone.html** file on this page and save the file when prompted.
1. Open the **bip39-standalone.html** file you downloaded in your browser.

You will see the main screen that looks like the below image:

![example](https://i.imgur.com/hR30NBd.png)

#### Generating Entropy for Mnemonic

What is entropy?  For simplicity and scope pertaining to keys, entropy is randomness that you introduce to the system to randomize the `BIP39` phrase generated.

##### Entropy Options

1. Let the `BIP39` tool generate randomness for you.
1. Create the entropy yourself to generate your random phrase.

###### Auto Generate Entropy

1. Set the dropdown to 24 words and click the `Generate` button.  Done!

![example](https://i.imgur.com/MErKfRo.png)

###### Manually Generate Entropy

1. Click the `Show entropy details` checkbox
  * You will see a lot more options load, don't worry it is easy!
1. Set the dropdown at the bottom to `24 Words`.

![example](https://i.imgur.com/wkCQJhM.png)

You can do this with a number of objects such as dice, playing cards or coins.  Each of these has a different way to enter the results into the `Entropy` textarea at the top.


**Dice**

Roll as many 6 sided dice that you have so you roll a total of 111 times.  Entering each die into the box.

**Playing Cards**

Shuffle the cards thoroughly and record each card into the box until the deck is completed.

**Coin Toss**

Flip a coin 287 times marking heads as ##### 0] and tails as ##### 1]. You should see the part that says ##### Raw Entropy Words] showing ##### 24] now.  If it is below 24 add more entropy until it says 24, and if it shows more than 24 remove a few bits of entropy until it shows 24.

![example](https://i.imgur.com/AtBKbG6.png)

### BIP39 Phrase

You should now see 24 words in the `BIP39` Mnemonic field.  This is it, you should now `backup this phrase` using the methods above.

![example](https://i.imgur.com/oZjU0mp.png)

Now that we have our phrase created and backed up, we can start deriving addresses from it.  I will run through each of the fields in the main section and explain them, then move onto how to get addresses and properly remember which have been used.

#### BIP39 Tool Fields

![example](https://i.imgur.com/7C5o5NA.png)

##### BIP39 Mnemonic

This is the phrase you backed up.  This is the keys to your crypto kingdom.  Protect it like you would your own life.

##### BIP39 Passphrase

Optionally used to add another layer of encryption to your phrase.  If you set a password, then you will need to remember both your `BIP39` phrase and the password associated with it.  I recommend not using this unless you trust yourself to never forget the password, or you back it up just as well as your phrase.

##### BIP39 Seed

This is the result of hashing your phrase and passphrase together and is unique to your phrase/passphrase combo.

##### Coin

This dropdown is used to switch between different coins to derive addresses, such as `BTC`, `LTC`, `DOGE`, etc.  This will be the only field in this section you ever need to touch.

##### BIP32 Root Key

This is the private key to the root/master node of your tree.  Protect this just as you would your `BIP39` mnemonic, preferably never copy this key as you will never need to use it directly.

### Paths

This is a very important topic.  And a good time to reiterate the structure of `BIP44` and company.

Do not stray from the designed scheme, you will be sorry.  Modern wallets and programs generally adhere to `BIP44` addressing.  Just because 14 is your lucky number, doesn't mean you should use account 14 by default.  No wallet will recognize funds in Bitcoin address. As we went over before, the path used to derive a key is structured.  We will cover `BIP44` addressing as it is the most common that you will likely ever use.


![example](https://i.imgur.com/VFLPykT.png)

This is the default `BIP44` path for Bitcoin, also written as `m/44'/0'/0'/0`.
The first Bitcoin address used under this key tree would be `m/44'/0'/0'/0/0`.

#### Examples

```
# BTC
m/44'/0'/9'/0/2 (Account 10, Address 3)
m/44'/0'/1000'/0/33 (Account 1001, Address 34)
m/44'/0'/5'/1/9 (Account 6, Change Address 10)

# ETC
m/44'/61'/9'/0/2 (Account 10, Address 3)
m/44'/61'/1000'/0/33 (Account 1001, Address 34)
m/44'/61'/5'/1/9 (Account 6, Change Address 10)

# ETH
m/44'/60'/9'/0/2 (Account 10, Address 3)
m/44'/60'/1000'/0/33 (Account 1001, Address 34)
m/44'/60'/5'/1/9 (Account 6, Change Address 10)

# DOGE
m/44'/3'/9'/0/2` (Account 10, Address 3)
m/44'/3'/1000'/0/33` (Account 1001, Address 34)
m/44'/3'/5'/1/9` (Account 6, Change Address 10)
```

### Path Recording

When using this tool to get an address for use in payments, it is best to keep track of what address maps to what path.  This will make your life a lot easier when you want to manually import a private key into a wallet.  You will know which key path to look up quickly.  Not tracking the path can make things a bit difficult.  There is no need to keep the path securely stored.  I will generally store the path and the public address for the coin in an easy to access place for quickly looking up an address I need.

```
m/44'/0'/0'/0/0 1Jp3JSyoSgmYHk4sZDnjqprvWNEGdU3CCb
m/44'/0'/0'/0/1 1GBFiE9i7kezRAdmjj2W6gwd9By2R1XFDW
m/44'/0'/0'/0/2 1BTedtrco6dGFRc93zER1JZiVgTu4bGkwU
m/44'/0'/0'/0/3 1KxG9CkFXE3FpSVC7xyZ8B2WPHqAKq9nvZ
```

### Usage
#### Usage Process

Finally at the end of this guide.  If you have followed along, this part should become easy and obvious.

So you have your `BIP39` phrase secured.  You are now ready to receive some cryptocurrency.  Let us run through the steps to get one.

1. Get your BIP39 phrase out of secure storage.
1. Enter the phrase into the `BIP39` Mnemonic field.
1. Choose the coin you want from the `Coin` dropdown.
1. Make sure you are on the BIP44 tab in the `Derivation Path` section.
1. Grab the first unused address in the `Derived Addresses` section.
1. Record the path of this address and the address somewhere easy to find and remember.
1. That is it!  You are now ready to receive payment to that address.

In a future guide we will cover spending coins that you have stored in your addresses generated by this tool.