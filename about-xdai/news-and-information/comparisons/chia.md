---
description: >-
  Chia and xDai are both energy-efficient consensus, but SSD burnout with Chia
  is creating unintended environmental consequences
---

# Chia

## Introduction

_Posted 5.26.2021_

The [Chia blockchain network](https://www.chia.net/) introduces a unique consensus process called Proof of Space and Time. It is designed to provide secure Nakamoto consensus by taking advantage of “overprovisioned storage” along with a verifiable delay function \(VDF\). It is a decentralized solution and provides conceptual advantages over current Nakamoto designs \(notably energy expenditure is much less than Bitcoin or the current Ethereum POW consensus\).

At xDai we are very much in favor of decentralized consensus mechanisms for public cryptocurrencies. However, Chia is positioning their chain as a “[green, eco-friendly alternative to Proof of Work](https://www.chia.net/assets/Chia-Business-Whitepaper-2021-02-09-v1.0.pdf)”. In practice, this is not the case. 

Here we look at differences between Chia and xDai related to the overall environmental footprint left by each chain. 

## **Energy Expenditure**

Average power consumption from both chains is very low. On May 26, 2021 [Chia reported average consumption of 18,361 kW](https://www.chiastatus.com/). This is a huge improvement relative to Bitcoin and Ethereum, and in fact slightly lower than [xDai’s estimated annual consumption of 21,900 kW](../xdai-energy-efficiency.md). Both are roughly equivalent to the energy usage of 2 US households annually.  

For context, Bitcoin energy consumption is estimated at 121.86 TW and more than 1332 kW for a single transaction, and Ethereum logging 51.62 and 95 kW for a single transaction. Combined, these two Proof of Work chains consume more energy than the entire country of Ukraine.

![](https://lh5.googleusercontent.com/4dmEamXo8Oibx8cgdiEFPF1zVyonfBMBMnxYU2JPhlysDCFckUWwjpoqViTagI0j-1Vqm8JVAPUVViTCU18cawX36JtpPxuMZlrxhgxh88R_P1Lmg8SmrXQlAfCEEsrFaPIXSqHo)

From a strictly energy consumption standpoint, both xDai and Chia are very environmentally friendly.

## **Solid State Drive \(SSD\) Usage**

Here is where we see glaring differences between the two chains. Although Chia was originally designed to use “unprovisioned storage space”, storage farming and SSD constraints are creating some big problems. 

The original Chia vision was that users around the world would provision extra space in their laptops or other devices to provide a decentralized consensus for Chia. Unfortunately, the farming process is burning out consumer grade SSDs at an extremely high rate. [Recent reports](https://www.telegraph.co.uk/technology/2021/05/17/chia-green-cryptocurrency-bounces-elon-musks-bitcoin-u-turn/) suggest that continuous farming reduces a 512GB solid state drive lifecycle from 10 years to 40 days. 

The Chia team has responded by advocating for [data center class SSDs or consumer drives meant for high-end desktops](https://www.chia.net/2021/05/24/SSD-endurance.html). This is at odds with the [chia website FAQ](https://www.chia.net/faq/) which states “Farming is more decentralized because it relies on empty hard disk space and anyone with a mobile phone, laptop, or corporate network tends to have extra space not currently being used.”

Just as Bitcoin and Ethereum miners provisioned specialized hardware to increase mining capacity, Chia farmers are turning to high end SSDs and cloud storage providers to farm more Chia.

According to a recent [Scaleway blog post](https://blog.scaleway.com/scaleway-and-chia/amp/), many SSDs are now being provisioned solely for Chia farming. “The network now represents a total of seven thousand Petabytes globally. If you consider that one HDD is on average 8TB, Chia, as of today, **consumes close to one million hard drives in the world**.”

Typically only [20% of e-waste is recycled](https://arstechnica.com/science/2017/12/just-20-percent-of-e-waste-is-being-recycled/), so if farming stays constant \(unlikely considering it has more than doubled in the past 2 weeks\) this means 800K+ more hard drives in landfills.

In a recent [telegraph UK article](https://www.telegraph.co.uk/technology/2021/05/17/chia-green-cryptocurrency-bounces-elon-musks-bitcoin-u-turn/), Alex de Vries of Digiconomist states ““Chia’s proof of space uses a lot of hard drives. They might reduce the need for energy, but they still have a waste of literal hard drives. They are pushing up the demand for these drives, which break down very fast when you use them for mining. It’s an e-waste issue.” 

This surge in usage is also stretching cloud provider’s capacities to provide storage for other projects, and influencing prices and availability of SSDs worldwide. 

In contrast, xDai nodes can be run from a cloud provider, desktop or laptop with the following specifications for a full node:

* CPU: minimum 2 cores
* RAM: minimum 4GB
* Disk: 50gb SSD

## **Conclusion**

Reducing overall energy usage is crucial for public blockchains. Leaders in the space are already looking to support green and renewable energy practices for mining in the near future. However, we need to look beyond strict usage to see other potential impacts to the environment and marketplace when determining whether a consensus is “green”. This means looking at overall energy usage as well as hardware usage. On both counts, xDai is providing a scalable, green consensus for public blockchain projects and users.  
  
****

