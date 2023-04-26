
<p align="center">
  <p align="center">
    <img src="https://avatars3.githubusercontent.com/u/53176002?s=200&v=4" height="100" alt="Blockcore" />
  </p>
  <h3 align="center">
   Blockcore White Paper
  </h3>
</p>


*   [Introduction](#introduction)
*   [Architecture](#architecture)
*   [Scalability](#scalability)
*   [Technical details](#technical-details)
*   [Token economics](#token-economics)
*   [Roadmap](#roadmap)
*   [Team](#team)
*   [Legal and regulatory considerations](#legal-and-regulatory-considerations)
*   [Conclusion](#conclusion)
*   [References](#references)



### **Introduction:**

**W**elcome to Blockcore's white paper for its leading edge and open-source blockchain project. The purpose of this project is to create a decentralized anti-fraudulent online environment, where people feel safe enough to interact with technology to make investments by providing a fully integrated platform for building custom blockchains, with an emphasis on open and public blockchains. Built on the .NET and written entirely in C#. Blockcore is based on the NBitcoin and Stratis projects.

Blockcore envisions a world where "Decentralize Everything" is the guiding principle. By providing the building blocks for modern decentralized societies, our free and open-source software can be adopted to make existing centralized systems permanently unnecessary. In the context of blockchain and Blockcore, decentralization refers to distributing power, authority, or control away from central locations or organizations, enabling individuals and communities to have more control over their data, assets, and decision-making. Blockcore's vision is based on the principles of decentralizing everything, such as Web5, which advocates for a more decentralized and user-centric internet.

Blockcore’s team of experienced blockchain developers and engineers created this initiative with the mission of empowering users to build unique blockchain solutions using a wide range of software tools, including Block Explorer, Block Indexing, Block Analytics, Wallets, API Wallet Service, Atomic Swaps, Developer Tooling, and Documentation.

The Blockcore’s platform offers a decentralized web node and decentralized identifiers, all designed to enhance the capabilities of the platform and make it accessible to a wide range of users. Blockcore's objectives include continuing the development of the C# Stratis full node, maintaining the C# Bitcoin full node, supporting projects and teams using the underlying technology, extending the technology by building developer and user tools, providing a forum for developers and teams to collaborate and to improve the technology, and building relationships with potential sponsors and partners to boost the pace of development.

Blockcore's guiding principles emphasize collaboration, contribution to open-source software, making it easier for everyone to contribute to the ecosystem, and encouraging projects to adopt Blockcore technology to strengthen the platform. We believe that our platform, Blockcore, can drive innovation and foster a collaborative environment for blockchain development. Committed to staying at the forefront of Bitcoin and blockchain technology through continuous development and improvements, let us endeavor together for what we can accomplish through Blockcore and blockchain technology.


### **Architecture:**

Blockcore is an eco-system comprised of different parts, with the foundation being its blockchain node software.

![image](https://user-images.githubusercontent.com/6504337/234680656-7bbd9b24-c16a-4035-bca4-6c8c0c826637.png)


This software can be used to run a UTXO-based blockchain, similar to Bitcoin, with added support for Proof-of-Stake, and it also supports Proof-of-Work blockchains. Each node has the full data of the blockchain, which normally does not contain much additional data other than limited OP_RETURN data, and nodes should not be exposed to public consumption.

The indexer is responsible for building a queryable database of the history of the blockchain, for specific addresses, transactions, and blocks. On top of the indexer, Blockcore has built various user interface surfaces such as the explorer, which allows insight into the blockchain, including rich lists, network nodes, known public addresses, and more.

Blockcore also offers different software options for users, including a non-custodial wallet that runs in the web browser and is distributed on add-ons stores for easy discovery, installation, and automatic updates. This extension relies on the indexer to access blockchain data. The Blockcore Hub is a full-node wallet, which is the optimal wallet for advanced users performing Proof-of-Stake operations, as it downloads the entire blockchain for improved privacy.

Blockcore also offers a tipping-bot software called Blockcore Tipbot, which allows users to easily give and receive tips in the form of coins and tokens. The tipbot is a custodial service, meaning that the keys do not belong to the individual users, so it is only recommended for smaller amounts. Users can withdraw from their tipbot balance into Blockcore Hub or Blockcore Extension wallets.

Additionally, Blockcore offers a server software called Blockcore Vault, which allows for distributed data storage and sharing. The software implements open standards for decentralized identity (DID) and can store a user's verifiable credentials, including private direct messages, NFTs, receipts from purchases, favorite music, videos, and more. The software supports both public (unencrypted) and encrypted (private) information to be hosted.

Blockcore also has cross-system documentation for all of its software, in combination with tooling for generating new blockchains and more. It also runs a community provided and supported server infrastructure of blockchain nodes, tipbots, indexers, explorers, and more.

### **Scalability:**
Blockcore, a novel approach to addressing the scalability issue in cryptocurrencies, offers multiple solutions to the limitations of traditional blockchain systems like Bitcoin. These solutions work together to mitigate the problems associated with transaction volumes, block sizes, and centralization of mining power, making the platform more attractive for businesses and organizations. Here's a summary of the key features that address these issues:

1. Configurable private blockchains: Blockcore allows organizations to create and manage their own private blockchains, tailoring block sizes to suit their specific needs and available resources. This customization enables businesses to optimize their blockchain's performance without being constrained by a single, global blockchain.

2. Host chain and dedicated ledgers: Blockcore operates on a host chain from which businesses can deploy their own ledgers based on their specific requirements. This structure provides the versatility of an extensive 2.0 platform combined with the full control of a private chain, which is secured by the host blockchain but managed by the owning organization.

3. Proof-of-Stake consensus: Blockcore employs a Proof-of-Stake (PoS) consensus mechanism, aligning the interests of end-users (businesses) and network security providers (full nodes). This allows businesses to run their own nodes without the overheads associated with specialized mining hardware, reducing the barriers to entry and preventing centralization of mining power.

4. Anti-bloat measures: To ensure the main chain remains lightweight and efficient, Blockcore implements a series of measures to combat bloat. This ensures that the host chain's primary purpose is to secure child chains, keeping the overall system streamlined and manageable.

In summary, Blockcore addresses the scalability and centralization issues faced by traditional blockchain systems like Bitcoin through the use of configurable private blockchains, a host chain with dedicated ledgers, a PoS consensus mechanism, and anti-bloat measures. These features make it an attractive option for businesses and organizations seeking a more efficient, secure, and adaptable blockchain solution.

### **Technical details:**

This section should provide an overview of the technical aspects of the blockchain system and cryptocurrency. Some additional questions to consider include:

* What is the underlying technology that powers the system?
* How does the consensus mechanism work?
* What is the block size and block time of the system?
* What cryptographic algorithms are used?
* How are smart contracts integrated into the system?

### **Token economics:**

This section should explain the token economics of the cryptocurrency. Some additional questions to consider include:

* What is the total supply of the token and how is it distributed?
* What is the role of the token within the blockchain system?
* How is the token used in transactions and what are the fees associated with using the token?
* What is the token governance structure and how are decisions made about the token?

### **Roadmap:**

This section should outline the development roadmap of the blockchain system and cryptocurrency. Some additional questions to consider include:

* What are the short-term and long-term goals of the project?
* What milestones need to be achieved in order to reach these goals?
* What is the timeline for achieving each milestone?
* What resources are needed to achieve these milestones?

### **Team:**

This section should introduce the team behind the blockchain system and cryptocurrency. Some additional questions to consider include:

* What is the background and experience of each team member?
* How did the team come together to launch this project?
* What is the team's vision for the project?

### **Legal and regulatory considerations:**

This section should discuss the legal and regulatory considerations associated with launching the blockchain system and cryptocurrency. Some additional questions to consider include:

* What is the legal status of cryptocurrency in the target jurisdiction(s)?
* What regulations apply to the project and how will the project ensure compliance?
* What risks are associated with the legal and regulatory landscape?

### **Conclusion:**

This section should summarize the key points of the white paper and encourage readers to participate in the project. Some additional questions to consider include:

* What is the call-to-action for readers?
* What are the potential benefits of participating in the project?
* What are the next steps for interested parties?

### **References:**

This section should include a list of references used in creating the white paper. Some additional questions to consider include:

* What academic papers or research was used in the creation of the white paper?
* What other sources of information were consulted?
* Where can readers find additional information about the topics discussed in the white paper?


Updated: April 26, 2023 

Version: Draft 1
