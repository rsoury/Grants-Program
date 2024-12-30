# Milestone Delivery

## Content

The submission includes the following information:

- Refinement and Modularisation
- **Open-source code/delivery**:
  - Verity zkTLS Data Processor Framework: [https://github.com/usherlabs/verity-dp](https://github.com/usherlabs/verity-dp)
  - zkVM for TLS Proof Rollups and ZK Verifier Contracts: [https://github.com/usherlabs/x-twitter-nfts/blob/a79999a68801b8ecf2a29d2a4892cde6c5f8e933/src/zkaf/README.md](https://github.com/usherlabs/x-twitter-nfts/blob/a79999a68801b8ecf2a29d2a4892cde6c5f8e933/src/zkaf/README.md)
  - X (Twitter) NFTs Project: [https://github.com/usherlabs/x-twitter-nfts](https://github.com/usherlabs/x-twitter-nfts)
  - Near Core Contract: [https://github.com/usherlabs/x-twitter-nfts/blob/a79999a68801b8ecf2a29d2a4892cde6c5f8e933/src/contracts/README.md](https://github.com/usherlabs/x-twitter-nfts/blob/a79999a68801b8ecf2a29d2a4892cde6c5f8e933/src/contracts/README.md)
- **[Documentation](#documentation)**
- **[Formatted Code](#formatted-code), adhering to set guidelines**
- **[Testing Guide](#testing-guide)**
- **List of [Milestone Deliverables](#milestone-deliverables)**

## License

Licensed under Apache 2.0.

## Documentation

This milestone focuses on the refinement and modularisation of the X (Twitter) NFTs repository. In a prior milestone, the repository was disorganised, with code for various functionalities distributed across folders. Now, each folder has its own specific purpose, and any additional modules and functions that can be used across projects incorporating Usher Labs' zkTLS Protocol can be found in a [dedicated repository](https://github.com/usherlabs/verity-dp).

The X NFTs project folder structure is as follows:

- `src/bitte_plugin`: The Bitte Plugin includes an API that allows Bitte AI to interact with the X NFTs project.
- `src/near_indexer`: The Near Indexer orchestrates the X NFTs project, including Near NFT Contract Indexing and ZK Prover processes management.
- `src/zkaf`: The zkAF utility generates the ZK Prover ELF binary, loaded into `src/near_indexer/src/generated/methods.rs`. It includes zkVM logic and code generation for the ZK Verifier Smart Contracts.
- `src/contracts`: The Near Contracts represent the X NFTs project on the Near blockchain.
  - `src/contracts/nft`: The Near NFT Contract manages mint intents, cancellations, and verifiable metadata from the ZK Prover.
  - `src/contracts/verifier`: The ZK Verifier Contract verifies ZK Proofs on the Aurora blockchain. A Near <> Aurora message prootocol is used to bridge verified proofs from the EVM environment to the NEAR environment.

### Workflow

1. Request a Tweet to be minted via your Bitte Wallet.
2. Use AI to generate NFT art or use an automatic snapshot of the Tweet.
3. Provide a Twitter handle for notifications once the zkTLS proof is verified on-chain.
4. Wait for zkProof verification and NFT minting to complete.
5. **Brag and bet with your friends on whether your 1-of-1 X NFT will represent a Tweet that will go viral!**

### Execution

The full setup and execution flow for the X NFTs project is outlined in the [README.md](https://github.com/usherlabs/x-twitter-nfts/blob/a79999a68801b8ecf2a29d2a4892cde6c5f8e933/README.md). Each component/folder within the repository also has its own README.md with instructions relative to the component.

## Formatted Code

**The code distribution:**

1. Solidity Smart Contracts are designed to deploy to Aurora to manage the registry of verified zkProofs.
2. Near Core Contracts are programmed in strictly typed Rust.
3. zkVM logic for TLS proof rollup is programmed in strictly typed Rust.
4. Bitte Plugin API is developed in Rust, implemented through the Rocket.rs API framework.
5. Comments are included among various steps in the logic to aid in understanding the flow and processing of data.

## Testing Guide

### Testing Near NFT Smart Contract

1. `cd ./src/near_nft`
2. `cargo test`

### Testing Aurora Smart Contracts

1. `cd ./src/zkaf`
2. `cargo build`
3. `forge build`
4. `forge test`

### A Step-by-Step Guide Demonstrating How Code Achieves the Milestone

A video has been created to walk you through the execution of the project for this milestone. The explanation is provided on how the code/logic achieves the outlined deliverables.

- [🌁 See Workflow Walkthrough](https://www.loom.com/share/78595bceeedc4e95bac4a291588773d3?sid=a25f0721-9766-40ba-8ec3-06d7af1272d0)  
- [🤖 See Code Walkthrough](https://www.loom.com/share/a808fe84f97f4b86b0ff58c32e693711?sid=80f1b04b-4df6-494c-a06d-ae8a421d4fc6)  

### Unit Tests

Unit tests have been developed for both the Near and Aurora Smart Contracts. Follow the [Testing Guide](#testing-guide) to execute these unit tests.

## Milestone Deliverables

| Number | Deliverable | Specification | Links & Notes |
| --- | --- | --- | --- |
| 0a. | License | Apache 2.0 | [LICENSE](https://github.com/usherlabs/x-twitter-nfts/blob/4af72cebba82a5c73b3f3aec5448ebfeda5fac39/LICENSE) |
| 0b. | Documentation | Documentation detailing the separation of the zkOracle Framework and Twitter NFTs Example, including Docker service separation. | [README.md](https://github.com/usherlabs/x-twitter-nfts/tree/feature/x-nfts-v1?tab=readme-ov-file#getting-started) |
| 0c. | Testing Guide | Distinguishing testing procedures for zkOracle Framework and Twitter NFTs Example. | zkTLS (previously named zkOracle) tests are isolated to the separate framework covering data processing for the [Verity zkTLS protocol](https://github.com/usherlabs/verity-dp). Tests for the X NFTs project are isolated to each of the components that comprise the project. |
| 0d. | Docker | Docker setup update to separate services by their respective purposes. | Docker is now reincorporated as a primary mechanism through which zkProofs are built, ensuring deterministic builds. This is a [paradigm set by RiscZero](https://dev.risczero.com/terminology#deterministic-builds) and is specific to the RiscZero ZK Co-processor. |
| 1. | ZK Circuit Refinement | Refinement of the ZK Circuit for verifying Twitter Data Sub-proofs. | [zkVM Logic](https://github.com/usherlabs/x-twitter-nfts/blob/edca0b7636bd4efa7cae5b91d82fe279c163f4fb/src/zkaf/methods/guest/src/bin/verify.rs) |
| 2. | Framework Modularisation | Modularisation of the zkOracle Framework to abstract from the Twitter API 
Integration. | [Verity DP ZK libraries](https://github.com/usherlabs/verity-dp/tree/main/examples/zktls) and X NFTs [supported binaries.](https://github.com/usherlabs/x-twitter-nfts/blob/3705f04bb385749bf3207422462f011716118026/src/zkaf/apps/src/bin/publisher.rs) |
| 3. | Orchestration Layer Development | Development of an Orchestration Layer for the zkOracle Framework, facilitating frontend feedback. | The Orchestrator is the [`near_indexer` component](https://github.com/usherlabs/x-twitter-nfts/blob/2dd039c3d0834c228fc96a9673bfa0be0a672930/src/near_indexer/src/main.rs) in the X NFTs project. |