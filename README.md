# Decentralized Cupcakes
A digital cupcake vending machine built with Solidity smart contracts. </br>
The [contract](https://sepolia.arbiscan.io/address/0xb6057e08a11da09a998985874FE2119e98dB3D5D) is deployed to [Arbitrum](https://arbitrum.io/) Sepolia testnet. </br>
It can also be deployed to local [Hardhat](https://hardhat.org/) testnet or [Arbitrum](https://arbitrum.io/) One Mainnet. </br>

This project is from the Arbitrum Docs at the section [_Quickstart: Build a decentralized app (Solidity)_](https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat). </br>

# Tech Stack
- [Solidity](https://soliditylang.org/) | smart contract language
- [Hardhat](https://hardhat.org/) | smart contract development environment
- [ethers.js](https://ethers.org/) | Ethereum Blockchain library
- [yarn](https://yarnpkg.com/) | package manager

# Setup
> Clone this repo
```
git clone https://github.com/hooyunzhe/DecentralizedCupcakes.git
```

> Install yarn (skip this step if already installed)
```
corepack enable

corepack prepare yarn@stable --activate
```

> Install dependencies via yarn
```
yarn install
```

> Compile smart contract
```
yarn hardhat compile
```

# Deploy (locally)
> Start a local Ethereum network
```
yarn hardhat node
```

> Configure Metamask according to this [section of the docs](https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat#configure-metamask)

> Deploy smart contract locally
```
yarn hardhat run scripts/deploy.js --network localhost
```

> Test the contract at this [section of the docs](https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat#deploy-the-smart-contract-to-your-local-testnet)

# Deploy (testnet)
> Update `hardhat.config.js` to include the private key of the test account for deployment
```js
// ...
const SEPOLIA_TESTNET_PRIVATE_KEY = ''; // <- put the private key here without "0x"
// ...
accounts: [SEPOLIA_TESTNET_PRIVATE_KEY] // <- uncomment this line
// ...
```
> Adding private keys to a config file is **not** a good practice, environment variables should be used in a real project

> Make sure the test account has some $ASPL (most test accounts from running `yarn hardhat node` have enough $ASPL)

> Deploy smart contract to testnet
```
yarn hardhat run scripts/deploy.js --network arbitrumSepolia
```

> Test the contract at this [section of the docs](https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat#deploy-the-smart-contract-to-the-arbitrum-sepolia-testnet)

> View the contract at `https://sepolia.arbiscan.io/address/[your contract address here]`

# Deploy (mainnet)
> Update `hardhat.config.js` to include the private key of the **one-time-use deployment account**
```js
// ...
const ARBITRUM_MAINNET_TEMPORARY_PRIVATE_KEY = ''; // <- put the private key here without "0x"
// ...
accounts: [ARBITRUM_MAINNET_TEMPORARY_PRIVATE_KEY] // <- uncomment this line
// ...
```
> Adding private keys to a config file is **not** a good practice, environment variables should be used in a real project

> Make sure the one-time-use deployment account has some $ETH

> Deploy smart contract to mainnet
```
yarn hardhat run scripts/deploy.js --network arbitrumOne
```

> Test the contract at this [section of the docs](https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat#deploy-the-smart-contract-to-arbitrum-one-mainnet)

> View the contract at `https://arbiscan.io/address/[your contract address here]`

# References
- [Solidity](https://docs.soliditylang.org/)
- [Hardhat](https://hardhat.org/docs)
- [ethers.js](https://docs.ethers.org/)
- [yarn](https://yarnpkg.com/getting-started)
- [Arbitrum](https://docs.arbitrum.io/)
- [Quickstart: Build a decentralized app (Solidity)](https://docs.arbitrum.io/build-decentralized-apps/quickstart-solidity-hardhat)
