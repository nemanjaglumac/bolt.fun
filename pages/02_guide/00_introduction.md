---
layout: guide
nav_order: 1
title: Guide
secondary_nav_title: Introduction
description: 
permalink: /guide/
main_nav: true
secondary_nav: true
main_classes: -no-top-padding
---

<!--

Introduction to the guide

- Why it exists
- What's in it
- How to use it
- How to contribute

Illustration sources

- https://www.figma.com/file/qzvCvqhSRx3Jq8aywaSjlr/Bitcoin-Design-Guide-Illustrations-CO?node-id=238%3A3

-->

{% include picture.html	
   image = "/assets/images/introduction.png"
   retina = "/assets/images/introduction@2x.png"
   mobile = "/assets/images/introduction.png"
   mobileRetina = "/assets/images/introduction@2x.png"
   alt-text = ""
   width = 1600
   height = 900
   layout = "full-width"
%}

# Introduction to the two networks

{% include tip/open.html color="blue" label="Work in progress" icon="info" %}
This section holds all the links to our different areas of research. To explore these areas, use the menu to navigate to the different research sections available.

_For a full overview of what this site will eventually become, feel free to also visit our [Site Plan](/site-plan)._
{% include tip/close.html %}

---

There are limitations in the current financial system that make payment services inaccessible to people in many places of the world — not everyone has access to bank accounts, identification, proof of address or live in countries which support the use of modern financial services.

We have established that [Bitcoin is money](https://bitcoin.design/guide/getting-started/why-bitcoin-is-unique/#its-money-but-digital) and [Bitcoin is global](https://bitcoin.design/guide/getting-started/why-bitcoin-is-unique/#global-by-default) now we dive into how it can facilitate payments.

## Bitcoin is extensible, it's not just a payment network

It should be noted that Bitcoin is not just a mechanism to make simple payments, but it is a complete global financial infrastructure for moving value without intermediaries. Each transaction is like a bit of code, which means it can be programmed — for example, you can set various spending conditions like requiring multiple parties to agree prior to moving the funds. It’s even possible to restrict funds from being moved until a certain time.

## Bitcoin is secure and accessible to all

Some people think Bitcoin is anonymous. This isn’t quite accurate because all transactions are public, therefore anyone can see the entire history of transfers going back to the very first one on [2009-01-03](https://blockstream.info/tx/4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b).

#### Why are transactions public?

They are public so that anyone can verify the entire history of transactions for themselves. We call this a permissionless system. No one needs to ask for permission to send a transaction or to build experiences on top of Bitcoin.

#### What about privacy?

Even though all transactions are stored publicly, there is no personally identifiable information attached to them. Privacy is still important though since every time you make a payment, the person receiving can see where you funded that transaction from, as you would be able to trace which address they spend those funds.

We should inform our users of these risks but also provide mechanisms that help them gain an acceptable amount of privacy[^1].


## Bitcoin is not too slow for payments

Transactions made on-chain can take minutes or days to confirm — depending on the fee you pay. This is because they get secured by the entire network of nodes and miners which exchange transactions they receive from wallets and other services with each other. Every 10 minutes miners validate the payments within the transactions and publish a block. For this service, they typically take the transactions with the highest fees.

This is may not be suitable if you want to make a small payment to a vendor at your local market — but if you're making or receiving a payment from someone accross the world the benefits are made very clear as the current banking and financial system can be quite restrictive, and expensive for some.

### Lightning Payments — A micro-payment network for every day payments

To meet the demands of our modern economy — movement of money needs to be borderless, secure, fast, and cheap.

The Lightning Network is part of the Bitcoin ecosystem that will power this economy. It allows for near-instant payments at much lower fees. This is possible because it extends Bitcoin in a way that does not record each payment on-chain.

#### A Network of Payment Channels and Settlement

If two parties want to make payments between themselves often, they can lock up some funds together in an on-chain transaction. Then they are able to bypass recording their subsequent payments with one another on-chain, by instead keeping track of each of their bitcoin balances in Lightning.

{% include picture.html	
   image = "/assets/images/payment-channels.svg"
   mobile = "/assets/images/payment-channels-mobile.svg"
   alt-text = "A payment channel is like one row of an abacus"
   width = 1600
   height = 900
   layout = "full-width"
%}

This is known as a payment channel, Lightning is essentially a network of payment channels which a sender's payment can be routed through to reach any other beneficiary.

##### How it works

Instead of recording each payment as an on-chain transaction to be secured in a block, they instead keep track of the balance at each side of the payment channel. The two parties only need to make a final settlement on-chain if that relationship ends and they want to "close" the channel which would unlock the balance on their side of the payment channel on-chain.

Lighting payments gain us some privacy since the payments are not individually recorded on-chain in a transaction, only the final settlement is.

###### Who to open a payment channel with?

It's possible to connect two computers to share files or even make calls between themselves without the internet — but if you want to communicate with someone outside of this network, you would have to go to a Telcom (ISP) to get a connection to the global information network. The same with lightning — you can connect to a Lightning Service Provider (LSP) which would provide you access to a larger network of payment channels, a global payment network.

[^1]: https://bitcoin.org/en/protect-your-privacy
