# SPL Token Management Guide

This guide outlines the process for creating and managing SPL tokens on the Solana blockchain, specifically targeting the Devnet for testing purposes. Follow these steps to mint your custom SPL tokens, named here as "Token-22", and connect your paper wallet to the Phantom Wallet for a seamless Solana blockchain experience.

## Prerequisites

Before starting, ensure you have installed the following tools:

- **Solana CLI**: [Installation Guide](https://docs.solana.com/cli/install-solana-cli-tools)
- **SPL Token CLI**: Follow the instructions in the Solana documentation or install it via npm with `npm install -g @solana/spl-token`
- **Node.js**: [Download Page](https://nodejs.org/)
- **`ts-node`**: Install via npm with `npm install -g ts-node`

## Step 1: Generate a Key Pair

Generate a key pair that starts with a specific prefix (e.g., "KVN"). This command searches for a key pair that meets the criteria, which can take some time.

```bash
solana-keygen grind --starts-with KVN:1
```

Upon completion, rename your key pair file to match the pattern `KVN__________.json` for easier reference.

## Step 2: Configure Solana CLI

Set the Solana CLI to use your newly generated key pair and target the Devnet.

```bash
solana config set --keypair /path/to/KVN__________.json
solana config set --url https://api.devnet.solana.com
```

Replace `/path/to/KVN__________.json` with the actual path to your key pair file.

## Step 3: Request Airdrop

Request an airdrop of 2 SOL to your account on the Devnet to cover transaction fees and other operations.

```bash
solana airdrop 2
```

## Step 4: Create Your SPL Token

You can create your SPL token in two ways. The recommended approach does not require specifying a key pair file explicitly if you've set it in the Solana CLI config.

**Option 1: With Key Pair File**

```bash
spl-token create-token -p TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb /path/to/KVNmDjP8vhUTCk6toCtLu5gXDurV5CJfX6JGgbrBzsJ.json
```

**Option 2: Recommended Method**

```bash
spl-token create-token -p TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb
```

## Step 5: Run Your TypeScript File

After adjusting addresses and keys in your `mpl_token22.ts` file, execute it:

```bash
ts-node ./mpl_token22.ts
```

## Step 6: Mint Tokens

Create a token account and mint your desired amount of tokens.

```bash
spl-token create-account <token_address>
spl-token mint <token_address> 10000000
```

Replace `<token_address>` with your token's address. Adjust the mint count as necessary.

## Step 7: Connect to Phantom Wallet

Extract and convert the private key from your JSON file for Phantom Wallet import.

```bash
more /path/to/KVN__________.json
```

Copy the output, which is an array of numbers, to import into Phantom Wallet:

1. Open Phantom Wallet and switch to **Testnet** mode in Settings.
2. Choose to **Import Private Key**.
3. Paste the key array, name the account, and proceed despite any format warning.

---

### Notes

- **Security**: Be cautious with your key pair and private keys. Never share them publicly.
- **Devnet**: This guide is for the Devnet. Remember to switch to the Mainnet settings for real transactions.
- **Phantom Wallet**: Always ensure your Phantom Wallet is up to date. [Phantom Wallet Guide](https://help.phantom.app/hc/en-us)

By following this guide, you'll be able to create and manage your own SPL tokens on Solana's Devnet and interact with them using Phantom Wallet.
