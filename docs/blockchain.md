# Blockchain

_A comprehensive guide to blockchain technology._

---

## Table of Contents

1. [Introduction](#introduction)
2. [How Blockchain Works](#how-blockchain-works)
3. [Key Concepts](#key-concepts)
    - [Centralization vs Decentralization](#centralization-vs-decentralization)
    - [Hashes](#hashes)
    - [Blocks](#blocks)
    - [Blockchain Structure](#blockchain-structure)
    - [Distributed Blockchain](#distributed-blockchain)
    - [Tokens](#tokens)
    - [Ethereum Standards and Token Types](#ethereum-standards-and-token-types)
    - [Ethereum Account Types](#ethereum-account-types)
    - [Ethereum Transactions](#ethereum-transactions)
    - [Ethereum Nodes and Clients](#ethereum-nodes-and-clients)
    - [The Ethereum Stack](#the-ethereum-stack)
4. [Applications](#applications)
    - [Crypto Exchanges: Centralized vs Decentralized](#crypto-exchanges-centralized-vs-decentralized)
    - [Decentralized Applications (dApps)](#decentralized-applications-dapps)
    - [Ethereum: Decentralized Computation and Smart Contracts](#ethereum-decentralized-computation-and-smart-contracts)
5. [Advantages and Challenges](#advantages-and-challenges)
6. [Conclusion](#conclusion)

---

## Introduction

Blockchain is a revolutionary technology that enables secure, transparent, and decentralized record-keeping. Unlike traditional centralized systems, blockchain distributes data across a network of independent participants, eliminating single points of failure and reducing the risk of censorship or manipulation. Each record, or "block," is cryptographically linked to the previous one, creating an immutable chain of data. Originally developed for cryptocurrencies like Bitcoin and Ethereum, blockchain technology now underpins a wide range of applications, from digital assets and decentralized finance (DeFi) to supply chain management and digital identity. Its core features—decentralization, transparency, and immutability—are transforming how we store, transfer, and verify information in the digital age.

---

## How Blockchain Works

A blockchain is a distributed ledger composed of a sequence of blocks, each containing a set of transactions or data. Every block includes a unique hash, the hash of the previous block, a nonce, and the block's data. When a new transaction occurs, it is broadcast to the network and grouped with other transactions into a block. To add a block to the chain, participants (nodes) must reach consensus—often through mechanisms like Proof of Work or Proof of Stake—ensuring that only valid transactions are recorded. The cryptographic linkage between blocks means that altering any block would require recalculating all subsequent blocks, making tampering computationally impractical. Multiple copies of the blockchain exist across the network, and consensus protocols ensure all participants agree on the current state. This structure provides security, transparency, and resilience, making blockchain a powerful foundation for decentralized applications and digital assets.

---

## Key Concepts

### Centralization vs Decentralization

| Centralized Systems | Decentralized Systems |
|---------------------|----------------------|
| Low network diameter (all participants are connected to a central authority); information propagates quickly, as propagation is handled by a central authority with lots of computational resources. | The furthest participants on the network may potentially be many edges away from each other. Information broadcast from one side of the network may take a long time to reach the other side. |
| Usually higher performance (higher throughput, fewer total computational resources expended) and easier to implement. | Usually lower performance (lower throughput, more total computational resources expended) and more complex to implement. |
| In the event of conflicting data, resolution is clear and easy: the ultimate source of truth is the central authority. | A protocol (often complex) is needed for dispute resolution, if peers make conflicting claims about the state of data which participants are meant to be synchronized on. |
| Single point of failure: malicious actors may be able to take down the network by targeting the central authority. | No single point of failure: network can still function even if a large proportion of participants are attacked/taken out. |
| Coordination among network participants is much easier, and is handled by a central authority. Central authority can compel network participants to adopt upgrades, protocol updates, etc., with very little friction. | Coordination is often difficult, as no single agent has the final say in network-level decisions, protocol upgrades, etc. In the worst case, network is prone to fracturing when there are disagreements about protocol changes. |
| Central authority can censor data, potentially cutting off parts of the network from interacting with the rest of the network. | Censorship is much harder, as information has many ways to propagate across the network. |
| Participation in the network is controlled by the central authority. | Anyone can participate in the network; there are no “gatekeepers.” Ideally, the cost of participation is very low. |

> Note: These are general patterns and may not hold true in every network. Centralization and decentralization exist on a spectrum.

---

### Hashes

A hash is a digital fingerprint of data. If you change anything in the data, the hash changes, but the hash will always have the same length. Hashes are used to ensure data integrity.

---

### Blocks

A block contains:
- **Nonce**: A number used once, crucial for mining.
- **Data**: The information stored in the block (e.g., transactions).
- **Hash**: The unique identifier for the block, which must start with a certain number of zeros (e.g., "0000") to be considered valid.

If you change the data in a block, the hash changes. To restore a valid hash (one that starts with "0000"), you must "mint" or mine the block by finding the correct nonce.

---

### Blockchain Structure

A blockchain is a chain of blocks, where each block contains:
- Its own hash
- The hash of the previous block

If you change a block, you must re-mint that block and all subsequent blocks, since the change affects the entire chain.

---

### Distributed Blockchain

Instead of a single blockchain, there are many copies (peers: A, B, C, etc.). If a block in one peer has a different hash than the majority, that peer's blockchain is considered invalid or out of sync.

---

### The Oracle Problem

A well-known limitation of blockchain technology is the "oracle problem." Blockchains are intentionally isolated networks—think of them as computers with no internet access. This isolation is a core part of blockchain security, preventing unauthorized data from entering or leaving the system. However, it also means that blockchains cannot directly access external (off-chain) data or interact with outside systems.

To bridge this gap, specialized infrastructure called oracles is used. Oracles securely connect on-chain smart contracts with off-chain data sources, enabling blockchains to "pull" or "push" information to and from the outside world. The reliability and security of these oracles are critical, as they become the trust anchor for any external data used on-chain. The oracle problem highlights the challenge of maintaining blockchain security while enabling access to real-world information.

---

### Tokens

A simple use case of blockchain is tokens. In this case, the data inside each block contains transactions such as transfers or minting of tokens.

---

### Asset Tokenization

Asset tokenization is a revolutionary way of owning an asset via smart contracts on the blockchain, allowing individuals to have verifiable ownership over digital tokens that represent real-world or digital assets. Major institutions such as BlackRock, Deloitte, and Boston Consulting Group have studied tokenization projects across various asset classes and concluded that this technology has the potential to disrupt multiple industries. Asset tokenization remains one of the most popular and practical uses of blockchain technology.

**Examples of tokenizable assets include:**
- Fiat currencies
- Commodities
- Intellectual properties
- Stocks and equities
- Game assets (e.g., skins, weapons)
- Artworks

By enabling fractional ownership, increased liquidity, and transparent transfer of assets, tokenization is transforming how value is created, managed, and exchanged in the digital economy.

#### How Does Asset Tokenization Work?

Asset tokenization streamlines the entire lifecycle of an asset—origination, distribution, trading, clearing, settlement, and safekeeping—by consolidating these processes onto a single blockchain-based layer. This integration increases efficiency, transparency, and security, as blockchain records are immutable and resistant to tampering.

**Key steps in creating a tokenized asset:**
- **Select the asset:** Choose the asset to tokenize, such as equities, commodities, currencies, securities, fine art, carbon credits, intellectual property, or digital game assets.
- **Define the token type:** Decide on the token standard (e.g., ERC-20 for fungible tokens, ERC-721 or ERC-1155 for non-fungible or multi-asset tokens), the total supply, minting mechanism, and any custom rules.
- **Choose the blockchain:** Select a public or permissioned blockchain, or consider frameworks for custom networks or rollups, based on the asset’s requirements.
- **Verify offchain assets:** Use third-party auditors and decentralized oracle services (like Chainlink Proof of Reserve and Price Feeds) to ensure that offchain assets are properly collateralized and that market data is accurate. For cross-chain assets, protocols like Chainlink CCIP maintain data consistency and interoperability.
- **Enable secure token minting:** Implement decentralized verification (e.g., Chainlink Proof of Reserve Secure Mint) to ensure that every newly minted token is fully backed by reserves, providing cryptographic guarantees and preventing unbacked token creation.

The decentralized nature of blockchain ensures that asset ownership records are transparent, immutable, and accessible, giving users greater confidence in the integrity and security of tokenized assets.

#### Real-World Example: PAXG (Tokenized Gold)

A prominent example of asset tokenization is [PAXG (Pax Gold)](https://www.paxos.com/pax-gold), a tokenized gold asset listed on Binance and other major exchanges. Each PAXG token is fully backed by physical gold held in reserve, ensuring that the total supply of tokens always matches the amount of gold owned by holders (fully hedged). 

When traditional gold markets are open, PAXG maintains its peg through transparent reserves and regular audits. When markets are closed, PAXG operates its own order book, leveraging high liquidity from its Binance listing and other platforms. This structure allows arbitrageurs to keep the token price closely aligned with the underlying gold price, preventing significant divergence between the token and spot market prices. PAXG demonstrates how tokenization can bring real-world assets onto the blockchain, providing liquidity, transparency, and accessibility to a global audience.

---

### Ethereum Standards and Token Types

#### Types of EIPs

There are three main types of Ethereum Improvement Proposals (EIPs):

- **Standards Track:** Describes any change that affects most or all Ethereum implementations.
- **Meta Track:** Describes a process surrounding Ethereum or proposes a change to a process.
- **Informational Track:** Describes an Ethereum design issue or provides general guidelines or information to the Ethereum community.

The Standards Track is further subdivided into four categories:
- **Core:** Improvements requiring a consensus fork.
- **Networking:** Improvements around devp2p, Light Ethereum Subprotocol, and network protocol specifications.
- **Interface:** Improvements around client API/RPC specifications and standards, and certain language-level standards like method names and contract ABIs.
- **ERC:** Application-level standards and conventions.

#### Token Standards

- **ERC-20:** Standard interface for fungible (interchangeable) tokens, such as voting tokens, staking tokens, or virtual currencies.
- **ERC-223:** Fungible token standard that makes tokens behave like ether and supports token transfer handling on the recipient's side.
- **ERC-1363:** Extends ERC-20 to support executing recipient code after transfer or transferFrom, or spender code after approve.
- **ERC-721:** Standard interface for non-fungible tokens (NFTs), such as deeds for artwork or songs.
- **ERC-2309:** Standardized event for creating/transferring one or many NFTs using consecutive token identifiers.
- **ERC-4400:** Interface extension for EIP-721 consumer role.
- **ERC-4907:** Adds a time-limited role with restricted permissions to ERC-721 tokens.
- **ERC-777:** (Not recommended) A token standard improving over ERC-20.
- **ERC-1155:** Token standard supporting both fungible and non-fungible assets.
- **ERC-4626:** Tokenized vault standard for optimizing and unifying yield-bearing vaults.

For more details, see [EIP-1](https://eips.ethereum.org/EIPS/eip-1).

---

### Ethereum Account Types

Ethereum has two main account types:

- **Externally-owned account (EOA):** Controlled by anyone with the private keys.
- **Contract account:** A smart contract deployed to the network, controlled by code.

Both account types can:
- Receive, hold, and send ETH and tokens
- Interact with deployed smart contracts

#### Key Differences

| Externally-owned Account (EOA) | Contract Account |
|--------------------------------|-----------------|
| Creating an account costs nothing | Creating a contract has a cost (network storage) |
| Can initiate transactions | Can only send messages in response to receiving a transaction |
| Transactions between EOAs can only be ETH/token transfers | Transactions from EOAs to contracts can trigger code execution (e.g., transfer tokens, create new contracts) |
| Made up of a cryptographic key pair (public/private keys) | Controlled by the logic of the smart contract code; no private keys |

#### Account Structure

Each Ethereum account has four fields:
- **nonce:** Number of transactions sent (EOA) or contracts created (contract account); protects against replay attacks.
- **balance:** Amount of wei (1 ETH = 1e18 wei) owned by the address.
- **codeHash:** Hash of the account's code (for contracts) or empty for EOAs.
- **storageRoot:** Hash of the root node of a Merkle Patricia trie encoding the account's storage contents.

#### Key Management and Account Creation

- EOAs are made up of a public/private key pair. The private key is used to sign transactions and must be kept secret.
- The public address is derived from the public key (last 20 bytes of the Keccak-256 hash, with 0x prefix).
- Example private key: `fffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd036415f`
- Example address: `0x5e97870f263700f46aa00d967821199b9bc5a120`
- Contract accounts also have 42-character hexadecimal addresses, usually assigned at deployment.

**Validator keys:**  
With Ethereum's proof-of-stake consensus, validator keys (BLS keys) are used to identify validators and aggregate signatures for efficient consensus.

#### Note on Wallets

An account is not a wallet. A wallet is an interface or application that lets you interact with your Ethereum account (EOA or contract account).

---

### Ethereum Transactions

An Ethereum transaction is an action initiated by an externally-owned account (EOA), such as sending ETH or interacting with a smart contract. Transactions change the state of the Ethereum Virtual Machine (EVM) and must be broadcast to the network, validated, and included in a block.

#### Transaction Structure

A transaction includes:
- **from:** Sender's address (EOA)
- **to:** Recipient's address (EOA or contract)
- **signature:** Proves the sender authorized the transaction (signed with private key)
- **nonce:** Sequential counter for the sender's account
- **value:** Amount of ETH to transfer (in wei)
- **input data:** Optional data (e.g., contract call data)
- **gasLimit:** Maximum gas units allowed for the transaction
- **maxPriorityFeePerGas:** Max tip to validator
- **maxFeePerGas:** Max total fee per gas unit

Example transaction object:
```json
{
  "from": "0xEA674fdDe714fd979de3EdF0F56AA9716B898ec8",
  "to": "0xac03bb73b6a9e108530aff4df5077c2b3d481e5a",
  "gasLimit": "21000",
  "maxFeePerGas": "300",
  "maxPriorityFeePerGas": "10",
  "nonce": "0",
  "value": "10000000000"
}
```

#### Signing and Broadcasting

Transactions must be signed with the sender's private key. The signature proves authenticity and prevents forgery. Ethereum clients (e.g., Geth) handle signing and broadcasting.

#### Types of Transactions

- **Regular transactions:** Transfer ETH between accounts.
- **Contract deployment:** No 'to' address; data field contains contract code.
- **Contract execution:** Interact with a deployed contract (to = contract address).

Ethereum supports multiple transaction types:
- **Type 0 (Legacy):** Original format, no EIP-1559 features.
- **Type 1:** Includes access lists (EIP-2930).
- **Type 2 (EIP-1559):** Introduces base fee and priority fee for better fee predictability.
- **Type 3 (Blob, EIP-4844):** Supports efficient handling of large data blobs.

#### Gas and Fees

- **Gas** is the computational cost to process a transaction.
- **GasLimit** sets the maximum gas allowed.
- **maxFeePerGas** and **maxPriorityFeePerGas** determine the transaction fee.
- Unused gas is refunded; the base fee is burned, and the validator receives the tip.

#### Transaction Lifecycle

1. Transaction is created and signed.
2. Broadcast to the network and added to the transaction pool.
3. Validator includes it in a block.
4. Block is justified and finalized, making the transaction irreversible except by a major network attack.

#### Data Field and Contract Calls

- The data field is used for contract interactions, specifying the function selector and arguments (ABI-encoded).
- View and pure functions do not require gas when called externally (eth_call), but do when called internally.

---

### Ethereum Nodes and Clients

A **node** is any instance of Ethereum client software connected to other computers running Ethereum, forming a network. A **client** is an implementation of Ethereum that verifies data against protocol rules and keeps the network secure. Each node runs two clients:

- **Execution client (EL client):** Listens for new transactions, executes them in the EVM, and maintains the latest state and database.
- **Consensus client (CL client):** Implements the proof-of-stake consensus algorithm, validating data from the execution client and maintaining network agreement.

A third piece of software, the **validator**, can be added to the consensus client to participate in securing the network.

#### Client Diversity

Both execution and consensus clients exist in multiple programming languages, developed by different teams. This diversity strengthens the network by reducing dependency on a single codebase and encourages a broader developer community. All clients follow a single specification (Yellow Paper, execution specs, consensus specs, EIPs).

#### Node Types

- **Full node:** Validates the blockchain block-by-block, stores recent data, and can regenerate older data as needed. Participates in block validation and serves data to the network.
- **Archive node:** Like a full node, but never deletes historical data, storing all states from genesis. Useful for querying historical data but requires significant storage.
- **Light node:** Downloads only block headers and requests additional data from full nodes as needed. Enables participation with lower hardware and bandwidth requirements but does not participate in consensus.

#### Benefits of Running a Node

- **Privacy and trustlessness:** Verify all transactions and blocks yourself, without relying on third parties.
- **Security:** Full nodes enforce consensus rules and protect against invalid blocks.
- **Network robustness:** More nodes increase decentralization, censorship resistance, and reliability.
- **Custom services:** Run your own wallet, dapps, or provide RPC endpoints for others.
- **Staking:** Run a validator to secure the network and earn rewards.

You can use third-party API providers or community nodes if you do not want to run your own node, but running your own node maximizes privacy, security, and decentralization.

---

### The Ethereum Stack

The Ethereum stack consists of several layers that together enable decentralized applications and services:

**Level 1: Ethereum Virtual Machine (EVM)**
- The EVM is the runtime environment for all smart contracts on Ethereum.
- It executes all transactions and state changes, using a set of opcodes to perform computations.
- The EVM is Turing-complete and runs on thousands of distributed nodes.

**Level 2: Smart Contracts**
- Executable programs written in languages like Solidity and compiled to EVM bytecode.
- Serve as open-source libraries and open API services, always available and permissionless.
- Developers can deploy new contracts or integrate with existing ones to add functionality.

**Level 3: Ethereum Nodes**
- Applications interact with the blockchain by connecting to Ethereum nodes.
- Nodes run client software, verify transactions, and maintain the blockchain state.
- Applications use the JSON-RPC API to read data and broadcast transactions.

**Level 4: Ethereum Client APIs**
- Libraries and SDKs (e.g., JavaScript, Python) that simplify interaction with Ethereum nodes.
- Abstract away low-level details and provide utility functions for developers.

**Level 5: End-User Applications**
- User-facing web and mobile apps that leverage the underlying stack.
- The user experience is similar to traditional apps, often without users knowing blockchain is involved.

This layered architecture allows developers to build robust, decentralized applications while abstracting away much of the underlying complexity.

---

## Applications

### Crypto Exchanges: Centralized vs Decentralized

A crypto exchange can be either centralized or decentralized:

**Centralized Exchange (CEX):**
- Controlled by a single organization or company
- Users create accounts and deposit funds into the exchange
- The exchange manages order books, matches buyers and sellers, and holds your cryptocurrency
- Examples: Binance, Coinbase, Kraken

**Decentralized Exchange (DEX):**
- Not controlled by a single entity
- Operates on blockchain technology using smart contracts
- Users trade directly from their wallets; no funds are held by the exchange
- Examples: Uniswap, PancakeSwap, SushiSwap

---

### Decentralized Applications (dApps)

A **dapp** (decentralized application) has its backend code running on a decentralized peer-to-peer network, unlike traditional apps that run on centralized servers. The frontend can be written in any language and may be hosted on decentralized storage solutions like IPFS.

**Key characteristics of dApps:**
- **Decentralized:** Operate on open, public platforms like Ethereum, with no single entity in control.
- **Deterministic:** Perform the same function regardless of the execution environment.
- **Turing complete:** Can perform any computation given sufficient resources.
- **Isolated:** Executed in the Ethereum Virtual Machine (EVM), so bugs in smart contracts do not affect the blockchain's core operation.

#### Smart Contracts and dApps

Smart contracts are the backend of dApps. They are immutable programs deployed on the blockchain, running exactly as programmed. This immutability ensures that dApps are governed by code, not by individuals or companies, but also requires careful design and thorough testing.

---

### Ethereum: Decentralized Computation and Smart Contracts

**Ethereum** is a blockchain platform that embeds a global computer, known as the Ethereum Virtual Machine (EVM), enabling decentralized, permissionless, and censorship-resistant applications. Every participant in the Ethereum network maintains a copy of the EVM's state, and any user can request computations (called transactions) to be executed by the network. These computations are validated, executed, and recorded on the blockchain, ensuring transparency and immutability.

**Ether (ETH)** is Ethereum's native cryptocurrency. It is used to pay for computation, incentivize validators, and secure the network. Users must pay ETH to execute transactions or deploy smart contracts, which prevents abuse and rewards those who maintain the network.

**Smart contracts** are reusable programs uploaded to the EVM. They execute automatically when called with specific parameters, enabling the creation of decentralized applications (dApps) such as marketplaces, games, and financial instruments.

#### Key Ethereum Terminology

- **Blockchain**: The ordered sequence of all blocks ever committed to the Ethereum network.
- **ETH**: The native cryptocurrency used to pay for computation and transactions.
- **EVM (Ethereum Virtual Machine)**: The global virtual computer whose state is agreed upon by all network participants.
- **Nodes**: Machines that store the EVM state and propagate information across the network.
- **Accounts**: Where ETH is stored; users can transfer ETH and interact with smart contracts.
- **Transactions**: Requests for code execution on the EVM, resulting in state changes.
- **Blocks**: Batches of transactions committed together to the blockchain.
- **Smart contracts**: Programs published to the EVM, enabling decentralized applications (dApps).

Ethereum's architecture allows for the creation of complex, decentralized systems that are transparent, secure, and resistant to censorship.

**Summary:**  
- Ethereum is a blockchain platform with a built-in global computer (EVM) that enables decentralized applications and organizations.
- Ether (ETH) is the native cryptocurrency, used to pay for computation, incentivize validators, and secure the network.
- Smart contracts are reusable programs that automate transactions and logic, forming the backbone of decentralized apps (dApps).
- The network is maintained by nodes, and all transactions and state changes are recorded on the blockchain, ensuring transparency and security.

---

## Advantages and Challenges

### Benefits of dApp Development

- **Zero downtime:** Once deployed, smart contracts are always available; denial-of-service attacks cannot target individual dApps.
- **Privacy:** No real-world identity is required to deploy or interact with a dApp.
- **Resistance to censorship:** No single entity can block users from submitting transactions, deploying dApps, or reading blockchain data.
- **Complete data integrity:** Data on the blockchain is immutable and indisputable due to cryptographic security.
- **Trustless computation/verifiable behavior:** Smart contracts execute predictably and transparently, without needing to trust a central authority.

---

### Drawbacks of dApp Development

- **Maintenance:** Code and data on the blockchain are difficult to modify, making updates and bug fixes challenging.
- **Performance overhead:** Every node processes every transaction, leading to significant performance and scalability limitations.
- **Network congestion:** High resource usage by one dApp can slow down the entire network; transaction throughput is limited.
- **User experience:** Securely interacting with dApps can be complex for end-users, impacting usability.
- **Centralization risks:** Solutions built on top of Ethereum may reintroduce centralization (e.g., server-side key storage or business logic), negating blockchain's advantages.

---

## Conclusion

<!-- Add summary and final thoughts here -->
