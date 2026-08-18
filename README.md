# OzoneChain Token List

Official token metadata and logos for tokens deployed on [OzoneChain](https://ozonechain.io/).

This repository provides standardized token information, logos, and metadata for wallets, decentralized applications, explorers, exchanges, and other services integrating with the OzoneChain ecosystem.

## Supported Assets

| Asset | Symbol | Type | Network |
|---|---|---|---|
| Ozone | OZO | Native Coin | OzoneChain |
| Baby OZO | BABYOZO | ERC-20 | OzoneChain |
| LOB | LOB | ERC-20 | OzoneChain |

> Contract addresses and metadata are maintained by the OzoneChain ecosystem team.

## Repository Structure

```text
token-list/
├── assets/
│   ├── ozo/
│   │   └── logo.png
│   ├── baby-ozo/
│   │   └── logo.png
│   └── lob/
│       └── logo.png
│
├── tokens/
│   ├── ozo.json
│   ├── baby-ozo.json
│   └── lob.json
│
├── tokenlist.json
├── LICENSE
└── README.md


```

## Token Metadata

Each token should contain the following information:
```text
{
  "chainId": 0,
  "address": "0x0000000000000000000000000000000000000000",
  "name": "Token Name",
  "symbol": "TOKEN",
  "decimals": 18,
  "logoURI": "https://raw.githubusercontent.com/ozonechain/token-list/main/assets/token/logo.png"
}
```


## Token List

The complete token list is available in:

```text
tokenlist.json
```

The raw token list can be consumed by compatible applications using:

```text
https://raw.githubusercontent.com/ozonechain/token-list/main/tokenlist.json
```

## Logo Guidelines

Token logos should follow these guidelines:

PNG format preferred
Square dimensions
Recommended size: 256 × 256 px
Transparent background preferred
No unnecessary text
High-quality source image
Consistent branding
Logo must represent the official token

Recommended structure:

assets/
└── token-name/
    └── logo.png
Adding a New Token

To add an OzoneChain token:

Create the token logo.
Add the logo under assets/<token-name>/logo.png.
Create the token metadata under tokens/<token-name>.json.
Add the token to tokenlist.json.
Verify the contract address and decimals.
Submit a pull request.

All token information must correspond to a token actually deployed on OzoneChain.

Token Verification

Before adding a token, verify:

Contract address
Chain ID
Token name
Token symbol
Decimals
Contract ownership/project information
Official project website
Official logo

Submitting a token to this repository does not constitute an endorsement, audit, or investment recommendation by OzoneChain.

Usage

Applications can consume the token list directly:

const TOKEN_LIST_URL =
  "https://raw.githubusercontent.com/ozonechain/token-list/main/tokenlist.json";


const response = await fetch(TOKEN_LIST_URL);
const tokenList = await response.json();

Example:

const babyOzo = tokenList.tokens.find(
  (token) => token.symbol === "BABYOZO"
);


console.log(babyOzo);
MetaMask Integration

Applications can use the token metadata from this repository when requesting users to add an OzoneChain token to MetaMask.

Example:

await window.ethereum.request({
  method: "wallet_watchAsset",
  params: {
    type: "ERC20",
    options: {
      address: token.address,
      symbol: token.symbol,
      decimals: token.decimals,
      image: token.logoURI
    }
  }
});

This repository provides token metadata and does not guarantee automatic token recognition or display by any specific wallet.

Security

Do not submit:

Fake token contracts
Unverified token information
Malicious token metadata
Impersonation tokens
Copyrighted logos without authorization
Contracts that are not deployed on OzoneChain

If you discover incorrect or malicious information, please open an issue or contact the OzoneChain team.

Contributing

Contributions are welcome from projects building on OzoneChain.

Before submitting a pull request, ensure that all metadata has been verified and follows the repository structure and naming conventions.

License

Token metadata and repository configuration are provided for ecosystem integration purposes.

Individual token logos and project trademarks remain the property of their respective owners.
