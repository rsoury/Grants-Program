# Milestone Delivery

## Content

The submission includes the following information:

- NFT Minting dApp Deployment and Testing
- **Open-source code/delivery**:
  - Bitte Plugin for NFT Minting UX: [Bitte Plugin](https://github.com/usherlabs/x-twitter-nfts/blob/83de18a1291319d46a878c1395f407bb123b6e2c/src/bitte_plugin/README.md)
- **[Documentation](#documentation)**
- **[Formatted Code](#formatted-code), adhering to set guidelines**
- **[Testing Guide](#testing-guide)**
- **List of [Milestone Deliverables](#milestone-deliverables)**

## License

Licensed under Apache 2.0.

## Documentation

This milestone centres on the production readiness of the X NFTs project. It primarily focuses on the Bitte Plugin for NFT Minting UX, which is a plugin that allows Bitte AI to interact with the X NFTs project.

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

### Testing Bitte Plugin

1. Start the server:

   ```bash
   cargo run
   ```

2. Run the agent on the mainnet:

   ```bash
   npx make-agent dev -p 8007
   ```

3. Run the agent on the testnet:

   ```bash
   npx make-agent dev -p 8007 -t
   ```

### A Step-by-Step Guide Demonstrating How Code Achieves the Milestone

A video has been created to walk you through the execution of the project for this milestone. The explanation is provided on how the code/logic achieves the outlined deliverables.

- [🌁 See Workflow Walkthrough](https://www.loom.com/share/78595bceeedc4e95bac4a291588773d3?sid=a25f0721-9766-40ba-8ec3-06d7af1272d0)  
- [🤖 See Code Walkthrough](https://www.loom.com/share/a808fe84f97f4b86b0ff58c32e693711?sid=80f1b04b-4df6-494c-a06d-ae8a421d4fc6)  

## Milestone Deliverables

| Number | Deliverable | Specification | Links & Notes |
| --- | --- | --- | --- |
| 0a. | License | Apache 2.0 | [LICENSE](https://github.com/usherlabs/x-twitter-nfts/blob/4af72cebba82a5c73b3f3aec5448ebfeda5fac39/LICENSE) |
| 0b. | Documentation | Comprehensive documentation on the modified NFT minting dApp, including integration details with NEAR/Mintbase libraries. Reference to third-party packages used. | [README.md](https://github.com/usherlabs/x-twitter-nfts/blob/83de18a1291319d46a878c1395f407bb123b6e2c/src/bitte_plugin/README.md) |
| 0c. | Testing Guide | End-to-end testing guide for the NFT minting process with zkProof verification. | [🌁 See Workflow Walkthrough](https://www.loom.com/share/78595bceeedc4e95bac4a291588773d3?sid=a25f0721-9766-40ba-8ec3-06d7af1272d0)   |
| 0d. | Docker | Deployment of Docker environment for the final dApp. | No docker related changes for this deliverable. |
| 0e. | Article | Publication detailing the project's achievements, impact on the Mintbase, NEAR, and wider blockchain 
ecosystems. | [Preliminary publications](https://x.com/usher_web3/status/1818285628292792577) have been made preparing for the release of the Bitte Plugin. Co-marketing initiatives are advised alongside preparation of a full-length blog post. |
| 1. | dApp Modification and Integration | Modification and deployment of an existing open-source NFT Minting dApp, 
incorporating NEAR/Mintbase libraries for minting NFTs with zkProof verification from the zkOracle. Reference to 
third-party packages like https://github.com/AnishDe12020/twnft. | As per discussions with the Bitte/Mintbase team, we found a better solution to integrate a new **X NFTs - Assistant** [Bitte Plugin](https://github.com/usherlabs/x-twitter-nfts/blob/f268186395302354babb08f8279b842eec06ae53/src/bitte_plugin/src/main.rs) in place of the NFT minting dApp. |
| 2. | Smart Contract Deployment | Deployment of the complete suite of Smart Contracts to Mainnets. | Near Core Contracts are deployed to Testnet successfully. 

- Near NFT Contract: [https://testnet.nearblocks.io/address/x-bitte-nft.testnet](https://testnet.nearblocks.io/address/x-bitte-nft.testnet)
- Near Verifier Contract: [https://testnet.nearblocks.io/address/local-verifier.testnet](https://testnet.nearblocks.io/address/local-verifier.testnet)
As the project is prepared with marketing for production deployment, the same guidelines for deployment can be applied.|
| 3. | E2E Testing | Conducting end-to-end tests to ensure unique Twitter Data minting and listing on the Mintbase Marketplace. | Alongside production deployment, with co-marketing initiatives, we aim to re-conduct the full e2e testing flow shown here: [https://www.loom.com/share/78595bceeedc4e95bac4a291588773d3?sid=a25f0721-9766-40ba-8ec3-06d7af1272d0](https://www.loom.com/share/78595bceeedc4e95bac4a291588773d3?sid=a25f0721-9766-40ba-8ec3-06d7af1272d0) |