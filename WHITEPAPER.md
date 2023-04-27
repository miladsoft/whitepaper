
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
*   [Roadmap](#roadmap)
*   [Team](#team)
*   [Legal and regulatory considerations](#legal-and-regulatory-considerations)
*   [Release Process](#release-process)
*   [Conclusion](#conclusion)
*   [References](#references)



# **Introduction:**

**W**elcome to Blockcore's white paper for its cutting-edge and open-source blockchain project. The aim of Blockcore is to create free and open-source solutions for modern decentralized societies with the vision to "decentralize everything". By providing the building blocks for decentralized societies, their software can make existing centralized systems redundant. Decentralization in the context of Blockcore refers to distributing power, control, and authority away from centralized organizations, giving individuals and communities greater control over their data, assets, and decision-making. Blockcore's vision aligns with the principles of Web5, which advocates for a more decentralized and user-centric internet.

Blockcore’s team of experienced blockchain developers and engineers created this initiative with the mission of empowering users to build unique blockchain solutions using a wide range of software tools, including Block Explorer, Block Indexing, Block Analytics, Wallets, API Wallet Service, Atomic Swaps, Developer Tooling, and Documentation.

The Blockcore’s platform offers a decentralized web node and decentralized identifiers, all designed to enhance the capabilities of the platform and make it accessible to a wide range of users. Blockcore's objectives include continuing the development of the C# Stratis full node, maintaining the C# Bitcoin full node, supporting projects and teams using the underlying technology, extending the technology by building developer and user tools, providing a forum for developers and teams to collaborate and to improve the technology, and building relationships with potential sponsors and partners to boost the pace of development.

Blockcore's guiding principles emphasize collaboration, contribution to open-source software, making it easier for everyone to contribute to the ecosystem, and encouraging projects to adopt Blockcore technology to strengthen the platform. We believe that our platform, Blockcore, can drive innovation and foster a collaborative environment for blockchain development. Committed to staying at the forefront of Bitcoin and blockchain technology through continuous development and improvements, let us endeavor together for what we can accomplish through Blockcore and blockchain technology.


# **Architecture:**

Blockcore is an eco-system comprised of different parts, with the foundation being its blockchain node software.

![image](https://user-images.githubusercontent.com/6504337/234680656-7bbd9b24-c16a-4035-bca4-6c8c0c826637.png)


This software can be used to run a UTXO-based blockchain, similar to Bitcoin, with added support for Proof-of-Stake, and it also supports Proof-of-Work blockchains. Each node has the full data of the blockchain, which normally does not contain much additional data other than limited OP_RETURN data, and nodes should not be exposed to public consumption.

The indexer is responsible for building a queryable database of the history of the blockchain, for specific addresses, transactions, and blocks. On top of the indexer, Blockcore has built various user interface surfaces such as the explorer, which allows insight into the blockchain, including rich lists, network nodes, known public addresses, and more.

Blockcore also offers different software options for users, including a non-custodial wallet that runs in the web browser and is distributed on add-ons stores for easy discovery, installation, and automatic updates. This extension relies on the indexer to access blockchain data. The Blockcore Hub is a full-node wallet, which is the optimal wallet for advanced users performing Proof-of-Stake operations, as it downloads the entire blockchain for improved privacy.

Blockcore also offers a tipping-bot software called Blockcore Tipbot, which allows users to easily give and receive tips in the form of coins and tokens. The tipbot is a custodial service, meaning that the keys do not belong to the individual users, so it is only recommended for smaller amounts. Users can withdraw from their tipbot balance into Blockcore Hub or Blockcore Extension wallets.

Additionally, Blockcore offers a server software called Blockcore Vault, which allows for distributed data storage and sharing. The software implements open standards for decentralized identity (DID) and can store a user's verifiable credentials, including private direct messages, NFTs, receipts from purchases, favorite music, videos, and more. The software supports both public (unencrypted) and encrypted (private) information to be hosted.

Blockcore also has cross-system documentation for all of its software, in combination with tooling for generating new blockchains and more. It also runs a community provided and supported server infrastructure of blockchain nodes, tipbots, indexers, explorers, and more.

# **Scalability:**
Blockcore, a novel approach to addressing the scalability issue in cryptocurrencies, offers multiple solutions to the limitations of traditional blockchain systems like Bitcoin. These solutions work together to mitigate the problems associated with transaction volumes, block sizes, and centralization of mining power, making the platform more attractive for businesses and organizations. Here's a summary of the key features that address these issues:

1. Configurable private blockchains: Blockcore allows organizations to create and manage their own private blockchains, tailoring block sizes to suit their specific needs and available resources. This customization enables businesses to optimize their blockchain's performance without being constrained by a single, global blockchain.

2. Host chain and dedicated ledgers: Blockcore operates on a host chain from which businesses can deploy their own ledgers based on their specific requirements. This structure provides the versatility of an extensive 2.0 platform combined with the full control of a private chain, which is secured by the host blockchain but managed by the owning organization.

3. Proof-of-Stake consensus: Blockcore employs a Proof-of-Stake (PoS) consensus mechanism, aligning the interests of end-users (businesses) and network security providers (full nodes). This allows businesses to run their own nodes without the overheads associated with specialized mining hardware, reducing the barriers to entry and preventing centralization of mining power.

4. Anti-bloat measures: To ensure the main chain remains lightweight and efficient, Blockcore implements a series of measures to combat bloat. This ensures that the host chain's primary purpose is to secure child chains, keeping the overall system streamlined and manageable.

In summary, Blockcore addresses the scalability and centralization issues faced by traditional blockchain systems like Bitcoin through the use of configurable private blockchains, a host chain with dedicated ledgers, a PoS consensus mechanism, and anti-bloat measures. These features make it an attractive option for businesses and organizations seeking a more efficient, secure, and adaptable blockchain solution.


# **Technical details:**

### What is POS vs POW

Proof Of Stake is an alternative way to achieve consensus to Proof Of Work, the difference with POS is that block producers use ownership of coins as the right to produce blocks and participating nodes can verify such claims by validating cryptographic signatures and the chain history.
A good comparison is that POW uses CPU cycles as measurement while POS uses units of coins.

### Definitions and explanations:

#### Coinbase

A special transaction that is produced by the miners (the producers of POW blocks) and contains information about the block.

#### Coinstake

A special transaction that is produced by the stakers (the producers of POS blocks) and contains the tx input and outputs of coins used to create a block.  
A coinstake input can be split in to several outputs, this is done in order to reduce the size of a staking output.  
Splitting a big output to many smaller outputs increases the chance of producing new blocks.  

#### StakeMinConfirmations

The minimum confirmations required for a coin to be good enough to participate in staking.  
Must be equal or greater than MaxReorg this is to discourage attackers to stake in isolation and then force a reorg.

#### MaxReorg

Long reorganization protection or the maximal length of reorganization that the node is willing to accept.
The reason to prevent long reorganization is to prevent "history attack" or in other words old spent coins can't be reused to create a longer chain in isolation and cause big reorgs.

Honest nodes will not switch to a chain that forked earlier than MaxReorg, and because StakeMinConfirmations will not allow to reuse coins before MaxReorg then staking in isolation cannot cause long reorganisations.

#### Coin maturity

The number of confirmations a newly found coinstake needs to be buried under before it can be spent.
(Not to be confused with StakeMinConfirmations which is for staking)

#### Proven Headers
 
Those are headers that contain all the information that is needed to validate a coinstake.
Proven headers are used as a `headers first` approach where the node will first download the headers of blocks and only if the header is valid will the node fetch the entire block for full validation.

The full Proven Headers specification can be found here
https://github.com/block-core/blockcore/blob/master/Documentation/Features/ProvenHeaders.md

#### Target Difficulty

The difficulty target for the next block, or how hard will it be to find the next valid Kernel to satisfy the target difficulty.

#### Kernel hash

A sha256 hash created from a number of parameters corresponding to the coinstake.
A valid stake kernel hash satisfies the target difficulty.

#### Target Spacing

The expected block time in seconds, or how often do we expect the network to produce a block.  
The target spacing should be multiples of the Mask.  

#### Future Drift

Future drift is maximal allowed block's timestamp difference over adjusted time.
We set the future drift to be a fixed value of 15 seconds which is close to the Mask value.

#### Mask

A bit mask for the coinstake header's timestamp. Used to decrease granularity of timestamp.  
This corresponds to the number of blocks that can be produced in a given time span.

For example if the bit mask is 15 (0x0000000F) then a valid coinstake's timestamp must be divisible by 16.

#### Stake Modifiers

The stake modifier forms a chain of hashes made from the previous stake modifier and the kernel all the way bacl to the first POS block.
It's used to introduce an additional input parameter to the Kernel calculations, in order to scramble computation to make it very difficult to precompute future proof-of-stake

### How it works on Blockcore

#### Hashing a valid kernel

How is a valid coinstake found? This is the heart of the processes.

The processes of staking will go as following, every time the masking of the timestamp is valid the node will iterate over all its stakeable outputs (the outputs that reached maturity and are beyond MaxReorg)

Then each output will be hashed with the following parameters:

- Previous StakeModifier - the stake modifier is a chain of coinstake hashes 
- Output hash - the hash of the output of the coins that are being spent to find the kernel 
- Output N - the position of the output of the coins that are being spent to find the kernel 
- New coinstake current time - (the timestamp of the new output that will be created, this must fit the MASK rule)

The output hash of the above is called the Kernel.

The Target:
The target is the number of which a kernel hash needs to be below in order to be considered valid.
In order to give a better chance to bigger outputs (a UTXO with more coins) The target is pushed up by a factor to the number of coins a UTXO has,
This is called the weighted target, it means the target of the UTXO is higher the more coins it has, as a result statistically it will find a solution faster.

If the resulting kernel hash of the above calculations is below the weighted target it means the coinstake is valid and can be used to create a block.

#### The importance of syncing time correctly (future drift)

Each node has a consensus rule of a fixed interval of 15 seconds that will enforce how far in the future it will accept blocks,
blocks with a time stamp that is 15 seconds further than local nodes current datetime will be rejected.

But such rejected blocks will not be considered invalid, in case our local node just had the wrong time in comparison to the network, 
and the network accepts such a block our local node would fork away form the network consensus.

This means it is crucial that nodes on the network that participate in full consensus rules validation will be on the same UTC datetime.
To achieve that we use the computers local current time, and double check that against all connected peers datetime 
(when a peer first connects it will advertise its current UTC datetime) giving the datetime samples for outbound nodes 3x more weight in the measurements 
(this is in order to prevent a certain attack on a node where an attacker can initiate many inbound connections and effect our local nodes avg time).
If the local time and peers avg time do not match the node will print out a warning message and default to the peers time.

#### Block Signatures (why sign a block with the private key owning the UTXO)

The coinstake that found a valid kernel and thus was selected to create a block is used to proof ownership of the UTXO by providing the signature that spends the outputs.  
However such an output has no cryptographic strong link to the block itself, meaning an attacker can take the valid coinstake utxo and put it in another block which the attacker created and propagate that to the network, the attacker could then censor transactions at will.

By signing the block with the same key that owns the UTXO peers can validate the block was created by the owner of the coinstake.
The block signature is attached at the end of the serialized block and is not part of the header hash.

#### How is the next difficulty target calculated 

The calculation of the next target is based on the last target value and the block time (aka spacing) (i.e. difference in time stamp of this block and its immediate predecessor). 
The target changes every block and it is adjusted down (i.e. towards harder to reach, or more difficult) if the time to mine last block was lower than the target block time.
And it is adjusted up if it took longer than the target block time. The adjustments are done in a way the target is moving towards the target-spacing (expected block time) exponentially, so even a big change in the mining power on the network will be fixed by retargeting relatively quickly.

#### Changes made in POSv4

Two changes were made in POSv4.

- The removal of the time stamp from the transaction serialization:
this makes POS transactions serialize the same as Bitcoin transactions, 
the benefit of that is easier to use various blockchain tools that are made for Bitcoin.
That time stamp was used in the kernel hash however the kernel hash was anyway defaulting to the header timestamp 
so there was no need to serialize the time stamp also in each transaction.

- The removal of the coinstake time from the kernel hash calculations:
when checking the kernel validity a few parameters are hashed together to find a valid kernel,
previously the timestamp of the utxo that is being spent was also included in that hash 
however it provides no additional value because the previous outpoint is used as well and that is already unique

#### Coldstaking (multisig staking) 

Coldstaking is a mechanism that eliminates the need to keep the coins in a hot wallet.
When setting up coldstaking a user generates two wallets (two different private keys) one key can only be used for staking (creating other coinstakes) and the other key is used for spending the coins. 

Cold staking still requires to have a fully synced node running and connected to the network.

The full Coldstaking specification can be found here
https://github.com/block-core/blockcore/blob/master/Documentation/Features/ColdStaking.md

## Weaknesses

#### NAS (nothing at stake)

Nothing-at-stake is a theoretical security issue in proof-of-stake consensus systems in which validators have a financial incentive to mine on every fork of the blockchain that takes place, which is disruptive to consensus and potentially makes the system more vulnerable to attacks

Assuming the majority of staking power (coins at stake) are honest an attacker which exercises NAS can make it very hard for honest nodes to know what is the chain with the total honest staking power (even if the attacker stakes on forks with less total stake this can confuse nodes in IBD) 

However this attack is not obvious to execute as an attacker would have to be economically invested in the chain in order to execute the attack and will be risking the value of their own coins.

https://golden.com/wiki/Nothing-at-stake_problem
https://medium.com/coinmonks/understanding-proof-of-stake-the-nothing-at-stake-theory-1f0d71bc027

#### Stake Grinding
 
Stake grinding is a class of attack where a validator performs some computation or takes some other step to try to bias the randomness in their own favour.  

In a stake grinding attack, the attacker has a small amount of stake and goes through the history of the blockchain and finds places where their stake wins a block. In order to consecutively win, they modify the next block header until some stake they own wins once again.
 
https://dyor-crypto.fandom.com/wiki/Grinding_Attack
  
#### The IBD problem

Proof of stake networks are more vulnerable during Initial Block Download (IBD), during initial sync a local node will try to find peers to sync the consensus history, however if a fake chain is presented (a fake chain is any chain that is not the chain accepted by the majority of stakers) a local node cannot rewind away from the fake chain if it's fork is beyond the maxreorg parameter and will result in our local node being stuck on the "wrong" chain.  

To address that the local node uses checkpoints (regularly hard coding in to the software the correct chain), and to mitigate that attack during IBD a node will only accept outgoing connections.  

#### Known issues of POS

POS is considered less decentralized than POW because: 
- Complexity: the POS protocol is more complex, more unknown attacks may be found 
- The IBD problem: means in some cases users needs to use some external trust in order to find the best chain.
- In case of a 51% attack: user intervention is needed like checkpoints in order to recover.
- IBD: the reliance on checkpoints for IBD.
- Time sync: the requirement that a majority of nodes have the correct global time.


# **Roadmap:**

This section should outline the development roadmap of the blockchain system and cryptocurrency. Some additional questions to consider include:

* What are the short-term and long-term goals of the project?
* What milestones need to be achieved in order to reach these goals?
* What is the timeline for achieving each milestone?
* What resources are needed to achieve these milestones?

# **Team:**

This section should introduce the team behind the blockchain system and cryptocurrency. Some additional questions to consider include:

* What is the background and experience of each team member?
* How did the team come together to launch this project?
* What is the team's vision for the project?

# **Legal and regulatory considerations:**

This section should discuss the legal and regulatory considerations associated with launching the blockchain system and cryptocurrency. Some additional questions to consider include:

* What is the legal status of cryptocurrency in the target jurisdiction(s)?
* What regulations apply to the project and how will the project ensure compliance?
* What risks are associated with the legal and regulatory landscape?

# **Release Process:**

This process describes the steps that is needed to go through to release new and updated packages and software.

### RocksDB Native and NuGet package

1: [https://github.com/block-core/blockcore-rocksdb-native](https://github.com/block-core/blockcore-rocksdb-native)

2: [https://github.com/block-core/blockcore-rocksdb](https://github.com/block-core/blockcore-rocksdb)

If there is a new release of RocksDB, then RocksDB native must be built and released. Next step is to build the NuGet package, then release when ready.

After releasing on NuGet, wait at least 10 minutes before proceeding to ensure scanning, approval and indexing of the package is completed.

### Blockcore NuGet packages

3: [https://github.com/block-core/blockcore](https://github.com/block-core/blockcore)

The main repository that contains the majority of our NuGet packages, must be updated to new version. After a build is completed from the `master` branch, then a new release will be added to the repository, in draft state.

Verify the NuGet packages locally by downloading and installing, if possible.

To publish new version of NuGet packages to the NuGet website, simply edit the new draft release and publish it. This will automatically trigger an workflow that will publish the NuGet packages.

Wait at least 10 minutes before proceeding, as the NuGet packages must be scanned for malware, approved and indexed.

### Blockcore Features

4: [https://github.com/block-core/blockcore-features](https://github.com/block-core/blockcore-features)

We maintain some custom features that extends the basic functionality. Upgrade the version number, perform a build, and publish the draft release.

The source code has reference to Blockcore NuGet packages in the pattern "1.1.\*", which means each build will always take the latest available. There is no need to manually update NuGet packages from Visual Studio, except of course other third party packages that might need to be updated.

Wait at least 10 minutes before proceeding, due to NuGet scanning, approval and indexing.

### Blockcore Reference Nodes

5: [https://github.com/block-core/blockcore-nodes](https://github.com/block-core/blockcore-nodes)

We maintain an multi-node that can be utilized to run all the Blockcore-based blockchains using a single package.

Upgrade the version number, perform a build, and publish the draft release.

The source code has reference to Blockcore NuGet packages in the pattern "1.1.\*", which means each build will always take the latest available. There is no need to manually update NuGet packages from Visual Studio, except of course other third party packages that might need to be updated.

When the draft release is published, the workflow will automatically build and publish container images to Docker Hub.

Image: [https://hub.docker.com/repository/docker/blockcore/node-multi](https://hub.docker.com/repository/docker/blockcore/node-multi)

### Blockcore Indexer

6: [https://github.com/block-core/blockcore-indexer](https://github.com/block-core/blockcore-indexer)

Add any new network NuGet packages, if new blockchains has been added.

When the draft release is published, the workflow will automatically build and publish container images to Docker Hub.

Image: [https://hub.docker.com/repository/docker/blockcore/indexer](https://hub.docker.com/repository/docker/blockcore/indexer)

### Blockcore Explorer

7: [https://github.com/block-core/blockcore-explorer](https://github.com/block-core/blockcore-explorer)

Update the version, also verify if there is any NPM packages that should be updated on the UI project.

When the draft release is published, the workflow will automatically build and publish container images to Docker Hub.

The Explorer does not depend on the network NuGet packages and does not need to be updated for every new blockchain.

Image: [https://hub.docker.com/repository/docker/blockcore/explorer](https://hub.docker.com/repository/docker/blockcore/explorer)

### Blockcore TipBot

8: [https://github.com/block-core/blockcore-tipbot](https://github.com/block-core/blockcore-tipbot)

The TipBot is hosted by Blockcore as a community service, but we advice teams to use their own dedicated tipbot for individual blockchains.

The TipBot does not depend on the network NuGet packages and does not need to be updated for every new blockchain.

### Blockcore Hub

9: [https://github.com/block-core/blockcore-hub](https://github.com/block-core/blockcore-hub)

Blockcore Hub requires that the multi-node to be released first, it embeds the full node software.

Upgrade packages and version, then publish the draft release after build is complete.

### Chains configurations

10: [https://github.com/block-core/chaininfo](https://github.com/block-core/chaininfo)

The Blockcore software utilizes an hosted server for configuration. This makes it possible to update configurations of software without re-installations and updated releases.

It is the responsibility of individual blockchains to maintain their own configurations, but the Blockcore team will support and help with instructions.

The configurations are published on the website: [https://chains.blockcore.net/](https://chains.blockcore.net/)


# **Conclusion:**

This section should summarize the key points of the white paper and encourage readers to participate in the project. Some additional questions to consider include:

* What is the call-to-action for readers?
* What are the potential benefits of participating in the project?
* What are the next steps for interested parties?

# **References:**

#### Older whitepapers  
POS whitepaper - [pos.pdf](/pos-whitepapers/pos.pdf)  
POSv2 whitepaper - [posv2.pdf](/pos-whitepapers/posv2.pdf)  
POSv3 whitepaper - [posv3.pdf](/pos-whitepapers/posv3.pdf)  

#### Additional references  
https://en.bitcoin.it/wiki/Proof_of_Stake  
Bitcointalk discussion on the issues of POS https://bitcointalk.org/index.php?topic=1382241.0  
https://github.com/libbitcoin/libbitcoin-system/wiki/Proof-of-Stake-Fallacy  
http://earlz.net/view/2017/07/27/1904/the-missing-explanation-of-proof-of-stake-version  
https://www.reddit.com/r/Bitcoin/comments/1oi7su/criticisms_of_proofofstake/  
https://blog.ethereum.org/2014/07/05/stake/  
https://eprint.iacr.org/2018/248.pdf  
http://tselab.stanford.edu/downloads/PoS_LC_SBC2020.pdf  


Updated: April 27, 2023 

Version: Draft 1
