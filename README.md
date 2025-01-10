# Blockchain CLI Tools

Command line tools for managing wallets and checking balances across multiple blockchain networks (Arweave, Solana, and Metaplex).

## Features

- Generate and manage wallets for multiple chains
- Check wallet balances and token values
- Validate encryption keys and wallet addresses
- Support for Arweave, Solana, and Metaplex

## Quick Start

```bash
# Generate new wallets
python arweave/generate_wallet.py
python solana/generate_keypair.py

# Check Arweave wallet balance
python arweave/check_balance.py --address YOUR_WALLET_ADDRESS
```

## Arweave Tools

### Wallet Generation
Generate new Arweave wallet and get deposit instructions.

```bash
python arweave/generate_wallet.py [--output wallet.json]
```

**Options:**
- `--output`: Path to save wallet JWK file (default: arweave-key.json)

### Balance Checker
Check wallet balance using address or JWK file.

```bash
python arweave/check_balance.py [--address ADDRESS | --jwk WALLET_FILE]
```

**Options:**
- `--address`: Arweave wallet address
- `--jwk`: Path to JWK wallet file

### Wallet Verification
Verify JWK wallet files and match against expected addresses.

```bash
python arweave/test_wallet_match.py
```

## Solana Tools

### Generate Keypair
Create new Solana wallet keypair.

```bash
python solana/generate_keypair.py
```

**Outputs:**
- Wallet address (public key)
- Private key (base58 encoded)

## Metaplex Tools

### Encryption Key Management
Generate and validate Fernet encryption keys for Metaplex API.

```bash
# Generate new key
python metaplex/generate_key.py

# Validate existing key
python metaplex/generate_key.py --validate -k YOUR_KEY
```

## Common Operations

1. Create and verify Arweave wallet:
```bash
# Generate wallet
python arweave/generate_wallet.py --output my_wallet.json

# Check balance
python arweave/check_balance.py --jwk my_wallet.json

# Verify wallet
python arweave/test_wallet_match.py
```

2. Setup Solana wallet:
```bash
python solana/generate_keypair.py
```

## Dependencies

- Python 3.7+
- cryptography
- arweave-python
- solders
- click
- requests

## Installation

1. Clone the repository
2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Security Notes

- Always backup your wallet files and private keys
- Never share private keys or JWK files
- Store sensitive files in secure locations
- Use encryption when storing wallet files

## License

MIT License
