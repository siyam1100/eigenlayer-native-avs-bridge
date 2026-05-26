# EigenLayer Native AVS Bridge

In the multi-rollup infrastructure ecosystem of 2026, standard multi-signature bridges are a high-risk security vulnerability. This repository provides a professional reference implementation for an **Actively Validated Service (AVS)** designed specifically to act as an ultra-secure cross-chain state attestation bridge.

Rather than relying on isolated operator sets, this bridge utilizes the shared cryptoeconomic security of Ethereum's pool of restakers. If an operator attests to a false transaction or fraudulent deposit block payload across monitored chains, their restaked ETH balance is slashed directly on Ethereum L1.

## Operational Flow
1. **Event Ingestion:** The client relayer listens for deposit events on the Source Rollup.
2. **AVS Attestation:** Operators independently inspect the block data, generating private BLS signatures matching the data payload.
3. **Aggregated Settlement:** The Aggregator contract groups separate signatures into an aggregate cryptographic proof and settles the transaction payload on the Destination Rollup.

## Quick Start
1. Install project dependencies: `npm install`
2. Compile Solidity structures using Hardhat: `npx hardhat compile`
3. Execute the off-chain relayer matching simulation logic: `node bridgeRelayer.js`

## Technical Framework
- Solidity ^0.8.26
- Ethers.js v6
- BLS Signature Aggregate Verification Mechanics
