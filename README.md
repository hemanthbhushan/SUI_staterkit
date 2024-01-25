## Additional Resources

Here are some additional resources that I found helpful in getting started with Sui blockchain:

### Videos
1. [Introduction to Sui Blockchain](https://www.youtube.com/watch?v=LbAzTzlj3ac)
2. [Sui vs Aptos - A Comparison](https://www.youtube.com/watch?v=X2ogC_uOdZ8&t=135s)
3. [Sui Move Basics - Code in Move](https://www.youtube.com/watch?v=jM5VBxoKPyM&t=1475s)
4. [Unveiling the SUI Blockchain: Pioneering Features and Unique Advantages](https://www.youtube.com/watch?v=jM5VBxoKPyM&t=1478s)
5. [Evan Cheng Talks Sui Blockchain @ Web Summit 2022](https://youtu.be/lWg66640bYU?si=s1GFNRBqUszOW-Ej)

### Medium Articles
1. [CoinEx: Sui Move-Based Public Chains - Sui vs Aptos](https://medium.com/@coinex/coinex-move-based-public-chains-sui-vs-aptos-a0c1ebda44bc)
2. [Code in Move 4: Sui Move Basics](https://medium.com/@BlockRunner/code-in-move-4-sui-move-basics-76c21cc0df1c)
3. [Sui Programmable Transaction Block (PTBs) - Learning Move 0x03](https://noncegeek.medium.com/sui-programmable-transaction-block-ptbs-learning-move-0x03-6b1abef44dea)
4. [I Have Been Using Sui Move for Sometime - In Love With the Language](https://abhi3700.medium.com/i-have-been-using-sui-move-for-sometime-i-am-already-in-love-with-the-language-especially-looking-253899ad1473)

### Blog Posts
1. [Sui Linter & Compile Warnings Update](https://blog.sui.io/linter-compile-warnings-update/)
2. [Sui Series 3 - By Sui, For Sui, Of Sui - Sui Move](https://medium.com/a41-ventures/sui-series-3-by-sui-for-sui-of-sui-sui-move-575518b789e6)

### Documentation
1. [Sui Documentation](https://docs.sui.io/)
2. [Sui CLI Reference](https://docs.sui.io/references/cli)

### GitHub Repositories
1. [Sui Move Intro Course](https://github.com/sui-foundation/sui-move-intro-course?tab=readme-ov-file)
2. [Mysten labs](https://github.com/MystenLabs/sui)

### Cookbook
- [Sui Blockchain Cookbook](https://suibase.io/cookbook/)

Feel free to explore these resources to deepen your understanding of Sui blockchain. The "Evan Cheng Talks Sui Blockchain @ Web Summit 2022" video provides insights from Evan Cheng, contributing to the comprehensive knowledge about Sui blockchain.

# Book My Ticket Sui Move
[Book My Ticket Github](https://github.com/hemanthbhushan/book_my_ticket_sui_move.git)

This repository contains the smart contracts for a decentralized ticket booking platform implemented using Sui Blockchain's Move language. The project aims to provide a secure and transparent ticketing system with features such as buying tickets, claiming profits, adding ticket types, blocking/unblocking users, and more.

## Smart Contracts

### TicketProject Module

#### Overview

The `TicketProject::BookMyTicket` module defines a smart contract for managing the decentralized ticket booking platform. It includes functions for initializing the platform, buying tickets, claiming profits, adding/removing ticket types, blocking/unblocking users, changing ownership, and more.

### TicketProjectToken Module

#### Overview

The `TicketProjectToken::ticket_token` module defines a custom token called `TICKET_TOKEN`. This token is designed for handling transactions related to ticket purchases in the Ticket Project.



# SUI Command Line Interface (CLI) Readme

## Overview

This Readme provides information on various SUI CLI commands for managing addresses, interacting with the blockchain, and handling transactions.

### Create a New Folder Structure

To create a new folder structure named `sui_wallet`, use the following command:

```bash
sui move new sui_wallet
```
### Build the Code

To build the code or check for compilation errors, use the following command:

```bash
sui move build
```

### Create a New Address

Use the following command to generate a new address and keypair:

sui client new-address --help
Generate new address and keypair with keypair scheme flag {ed25519 | secp256k1 | secp256r1} with optional derivation path, default to m/44'/784'/0'/0'/0' for
ed25519 or m/54'/784'/0'/0/0 for secp256k1 or m/74'/784'/0'/0/0 for secp256r1. Word length can be { word12 | word15 | word18 | word21 | word24} default to word12
if not specified

Usage: sui client new-address [OPTIONS] <KEY_SCHEME> [ALIAS] [WORD_LENGTH] [DERIVATION_PATH]

```bash
sui client new-address --help
```

Example:
```bash
sui client new-address ed25519
```
### View Addresses

To see all addresses and identify the active one, use:

```bash
sui client addresses
```

### Active Address

To check the currently active address, run:

```bash
sui client active-address
```

### Switch Active Address

To change the active address, execute:

```bash
sui client switch --address <NEW_ADDRESS>
```

### Call Published Function

For invoking a published function, use the following command:

```bash
sui client call --package <PACKAGE> --module <MODULE> --function <FUNCTION> --args <ARGS> --gas-budget <GAS_BUDGET>
```

Example:
```bash
sui client call --package 0x0e93e988b734751bf57be0ed5fd419fed01eda4fc320637c3e89c65f82c85f78 --module music_coin --function mint_token --args 0x7622369a7f85565664aa0189cb03c4d4fdb484ad6c0f3a1915be9a7767d48108 23333333333 0x0b6ffe868b9b236cbf29316a277ff891e368facf8975e146c950b137f0268adc --gas-budget 10000000000
```

### Publish Module

To publish a module, use:

```bash
sui client publish --gas-budget <GAS_BUDGET>
```

### Call Generic Function

When dealing with generic functions, specify the type using `--type-args`:

```bash
sui client call --package <PACKAGE> --module <MODULE> --function <FUNCTION> --type-args <TYPE_ARGS> --args <ARGS> --gas-budget <GAS_BUDGET>
```

Example:
```bash
sui client call --package 0x101dae433e2b3090ce943f00041057532a433a70e88c193fac9e0f8ad8bd953d --module book_my_ticket_coin --function mint_and_transfer --type-args 0x101dae433e2b3090ce943f00041057532a433a70e88c193fac9e0f8ad8bd953d(packageId)::book_my_ticket_coin::BOOK_MY_TICKET_COIN --args 0x82b735ee14cbba558c4d01f3b13734c22ed47070a75d24aac32689ff74e3029b 2333333333333333 0x0b6ffe868b9b236cbf29316a277ff891e368facf8975e146c950b137f0268adc --gas-budget 1000000000
```

### Get Testnet Tokens

For obtaining testnet tokens for gas, use the following CURL command:

```bash
curl --location --request POST 'https://faucet.devnet.sui.io/gas' \
--header 'Content-Type: application/json' \
--data-raw '{
    "FixedAmountRequest": {
        "recipient": "<RECIPIENT_ADDRESS>"
    }
}'
```

### Check Gas Amount

To know the amount of gas (SUI tokens), run:

```bash
sui client gas
```

### Vector Inputs

For commands involving vector inputs, use the following template:

```bash
sui client call --package <PACKAGE> --module <MODULE> --function <FUNCTION> --args <ARGS> --gas-budget <GAS_BUDGET> --json
```

Example:
```bash
sui client call --package 0x157bef934e5bea375688fb40282d895b1747f994f35d7d939462cee73b8a5415 --module BookMyTicket --function add_ticket_types --args 0xdd70fb36f066239813eaaf45ea049d9945f9633a009eda840c0d205bebf9bc6b "["hemaeenth","fff","ccc"]" "[1,2,2]" --gas-budget 1000000000 --json
```

## Note

Make sure to replace placeholders such as `<PACKAGE>`, `<MODULE>`, `<FUNCTION>`, `<ARGS>`, `<GAS_BUDGET>`, `<NEW_ADDRESS>`, and `<RECIPIENT_ADDRESS>` with actual values when using the commands.


# Sui Framework - Troubleshooting Guide

## Error: Sui E01001 - Invalid Object Construction

If you encounter the error `Sui E01001: invalid object construction` with the specific context pointing to an invalid object creation in the `deny_list.move` file, follow the steps below to resolve the issue.

### Problem Description

The error suggests that an object is being constructed without a newly created UID, and the UID must come directly from `sui::object::new`. For tests, it can come from `sui::test_scenario::new_object`. The error message provides details about the location of the issue in the code.

### Solution

To resolve this issue, make sure that you have the correct version of the Sui Framework in your project dependencies. Add the following line to your project's dependency list in the `Cargo.toml` file:

```toml
Sui = { git = "https://github.com/MystenLabs/sui.git", subdir = "crates/sui-framework/packages/sui-framework", rev = "mainnet-v1.16.2" }
```
OR
```toml
Sui = { git = "https://github.com/MystenLabs/sui.git", subdir = "crates/sui-framework/packages/sui-framework", rev = "framework/mainnet" }
```

This will ensure that you are using version `mainnet-v1.16.2` of the Sui Framework, which should address the object construction issue.
Find the version types here
[latest versions are found here](https://github.com/MystenLabs/sui/releases)
