# Orchave

Making web2 anaytics trustless with the power of mass adoption.

## Comprehensive Decentralized Data Archive

Orchave is a decentralized _instant_ data oracle platform that empowers users to customize data APIs and become data providers. By eliminating centralized incentives, users can not only manage and provide their data, but also become decentralized verifiers, contributing to the integrity and reliability of the network. As there are more people using a specific off chain data archive, there is more incentive on top of it, allowing more verifiers to verify the data, ultimately making it much more trustless.

## Basic Compenents
 - **Orchave Provider App :** For anyone to become a provider on their local machine.
 - **Orchave Verifier Network :** A super light verification network that anyone can join to verify data. This network is not based on 66% consensus, but increasing verifier count: A data can be verified by as many people as possible. Being a verification layer, this does not hurt at all the finality time of the network.
 - **Orchave Dashboard :** A dashboard for dApp users to see and select the best archive endpoint for their use, available on [https://orchave.org](https://orchave.org).
 - **Filecoin FVM Contract :** All application works on top of FVM to provide incentives for verification and have persistent storage. The availability of data for the long run is ensured by the self feed loop of the network, described below.
 - **Avail DA :** Finally, Avail DA acts as a communication layer between light nodes of the Orchave Verifier Network and brings fast finality on the ordering of blocks. This makes sure that very big data sets can be settled on Avail without the fear of misbehavior.

## Detailed Analysis

Blockchains are great at providing immutable storage and deterministic verifiable computations. However, they cannot access trusted real-world information available outside their networks that are not provided by big oracle networks. These networks are:

- slow to respond,
- incentivized centrally,
- limited to a specific set of oracles,
- not stable over long time and big data sets,
- and has constant decentralization over time: the decentralization of data and the usage frequency have no relation.

Orchave has a different approach.

By providing unique features over its own set of **verifier nodes**, Orchave brings decentralized oracles to the next level:

### Reflective

With Orchave, users can seamlessly supply data to the blockchain through demand-driven APIs, creating new monetization opportunities.

Anyone who chose may download Orchave "provider" application to become a provider on the Orchave network.

### Dynamically Decentralized

By allowing users to customize data APIs and become providers, Orchave fosters a collaborative ecosystem where data is decentralized. Each time the provided data is utilized, its value increases, attracting more verifiers to the network. This growing network of decentralized verifiers ensures the reliability and accuracy of the data, setting a new standard for off chain data trustlessness in blockchain applications.

Instead of reaching a 66% consensus, Orchave collects more and more verifiers with the increasing incentive. As the verifier network is only responsible for the _verification_, but not ordering, the finality of the Orchave verifier network is much faster than of regular blockchains. The FVM contracts are also designed specifically to verify independent of the verifier nodes through constant sized verification structures (a.k.a. merkle trees).

### Built with Social Trust

Orchave enables both verifiers and data providers to establish robust social trust systems. By supplying high-quality data, providers not only contribute to the network's integrity but also gain recognition and trust that extends beyond individual blockchains, fostering a more interconnected and reliable environment. Of course, this new decentralized value is rewarded, and providers gain more and more as there are more people using their data.

As well as providers, verifiers also gain the incentive to verify new data points and join existing data sets as there is more request for this data set.

This brings a perfect game theory model into the modular network of Orchave: every party has the interest to keep their services going and act honestly. Moreover, the gain increases over time, so the systems gains exponential power with increasing usage.

### Consistent over Long Time: Filecoin

The provided data is verified only as a hash for efficiency, and the complete file is preserved on top of Filecoin. Filecoin brings availability on historical data, but does not guarantee the existence of data if the data is not paid to be supported. Orchave brings a solution to this by its dynamic decentralization mechanism over social trust: providers gain more and more from their vastly used data, and thus find the incentive to keep supporting the data on top of Filecoin.

Here, Filecoin becomes not only a good choice of data storage, but also completes the architecture fully with its "pay as you use" mechanism. The Orchave network makes sure that unused data will not have the incentives to support its existence over long term.

### Data Availability: Avail

Verifiers can operate a light node with the support of Avail, ensuring continuous activity and maintaining system liveness. While providing massive amount of data to the blockchain in chunks, users can still make sure of the integrity of the submitted data using Avail's fast block order finality. This capability facilitates the creation of a decentralized database, significantly enhancing the accessibility and organization of blockchain data.

### Social Reputation

Orchave also integrates Dynamic to support the social reputation of providers across different Ethereum compatible chains. A data provider has the chance of showcasing an old and frequently used data endpoint to prove their trustlessness. This use case is an excellent example of how social reputation can be used so efficiently in oracle networks, which is a huge missing point in the ecosystem right now.

P.S: Please note that right now Dynamic does not implement FVM with Wagmi, thus our aplication was not able to start both together. However, you can see that both pieces of the product are there and working.

## Architecture Diagram

![Orchave Architecture](./architecture.png)