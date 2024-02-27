# ERC20 Goerli to Mumbai Bridge Using fxPortal
This project demonstrates how to use the fxPortal contracts to transfer ERC20 tokens from Goerli to Mumbai.

### Steps for Bridging

1. Run npm i to install dependencies
2. Put your private key in the .env.examples file and rename to .env when finished
3. Run npx hardhat run scripts/deploy.js --network goerli to deploy ERC20 contract
4. Paste the newly deployed contract address in the tokenAddress variable for the other scripts
5. Make sure to fill in your public key
6. Run npx hardhat run scripts/mint.js --network goerli to mint tokens to your wallet
7. Run npx hardhat run scripts/approveDeposit.js --network goerli to approve and deposit your tokens to polygon
8. Wait 20-30ish minutes for tokens to show on polygon account
9. Use polyscan.com to check your account for the tokens. Once they arrive, you can click on the transaction to get the contract address for polygon.
10. Use this polygon contract address for your getBalance script's tokenAddress
11. Run npx hardhat run scripts/getBalance.js --network mumbai to see the new polygon balance


### Prerequisites

- Node.js (version 12 or above)
- Hardhat (for compiling and deploying smart contracts)
- MetaMask browser extension

### Executing Program
To run the solidity code, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.



## Installation
1. Clone the repository:


git clone https://github.com/your-username/your-repository.git


2. Install the dependencies:


cd your-repository
npm install


### Minting NFTs

After successful deployment,you will get a `contract address`.

1. Update the `batchMint.js` script with that `contract address` and `private key` of your wallet account.

2. Create a file named `ipfs_urls.txt` and add the IPFS URLs for the NFT images, each URL on a new line.

3. Run the script to mint the NFTs:


node batchMint.js


### Mapping 

Map Your NFT Collection using `Polygon network token mapper`. 

### Batch Transfer of NFTs

After successful Mapping you will get a `child address` also known as `fxPortalBridge` address.

1. Update the `batchTransfer.js` script with that deployed `contract address`, `fxPortalBridge address` , and your `private key`.

2. Run the script to transfer all minted NFTs to the  Polygon Mumbai network :


node batchTransfer.js



## Author 

Prajyan

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
