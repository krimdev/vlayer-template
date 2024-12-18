# Vlayer Templates Testing Guide

## Prerequisites

Before starting, ensure you have these tools installed:

`Bun` `Foundry` `Git`

Install vlayer:
```bash
curl -L https://install.vlayer.xyz | bash
```

## Simple Template: ERC20 Balance Proof

1. Initialize project
```bash
mkdir vlayer-simple
cd vlayer-simple
vlayer init simple --template simple
```

2. Build and install dependencies
```bash
cd simple
forge build
cd vlayer
bun install
```

3. Create your `.env.testnet.local`
```bash
EXAMPLES_TEST_PRIVATE_KEY=your_private_key
CHAIN_NAME=optimismSepolia
JSON_RPC_URL=https://sepolia.optimism.io
PROVER_URL=https://test-prover.vlayer.xyz
```

4. Start vlayer server (in a new terminal)
```bash
vlayer serve --rpc-url '11155420:https://sepolia.optimism.io'
```

5. Run proof generation
```bash
bun run prove:testnet
```

## Email Proof Template

1. Initialize project
```bash
mkdir vlayer-email
cd vlayer-email
vlayer init emailproof --template simple-email-proof
```

2. Build and install dependencies
```bash
cd emailproof
forge build
cd vlayer
bun install
```

3. Use same `.env.testnet.local` configuration as Simple Template

4. Run proof generation
```bash
bun run prove:testnet
```

## Teleport Template

1. Initialize project
```bash
mkdir vlayer-teleport
cd vlayer-teleport
vlayer init teleportproof --template simple-teleport
```

2. Build and install dependencies
```bash
cd teleportproof
forge build
cd vlayer
bun install
```

3. Use same `.env.testnet.local` configuration as Simple Template

4. Run proof generation
```bash
bun run prove:testnet
```

## Requirements

- OptimismSepolia ETH needed for transactions
- Get testnet ETH from [Optimism Faucet](https://www.optimism.io/faucet) or [Alchemy Faucet](https://sepoliafaucet.com/optimism-sepolia)

## Important Notes

- Keep vlayer server running during all operations
- Each template needs its own clean directory
- Run server and client commands in separate terminals
- Make sure you have enough OptimismSepolia ETH before starting
