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
