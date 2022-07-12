# Crypto-DAO
we want to allow your NFT holders to create and vote on proposals to use that ETH for purchasing other NFTs from an NFT marketplace, and speculate on price. Maybe in the future when you sell the NFT back, you split the profits among all members of the DAO.

Requirements
Anyone with a CryptoDevs NFT can create a proposal to purchase a different NFT from an NFT marketplace
Everyone with a CryptoDevs NFT can vote for or against the active proposals
Each NFT counts as one vote for each proposal
Voter cannot vote multiple times on the same proposal with the same NFT
If majority of the voters vote for the proposal by the deadline, the NFT purchase is automatically executed
What we will make
To be able to purchase NFTs automatically when a proposal is passed, you need an on-chain NFT marketplace that you can call a purchase() function on. There exist a lot of NFT marketplaces out there, but to avoid overcomplicating things, we will create a simplified fake NFT marketplace for this tutorial as the focus is on the DAO.
We will also make the actual DAO smart contract using Hardhat.
We will make the website using Next.js to allow users to create and vote on proposals
Prerequisites
You have completed the NFT-Collection Tutorial
You must have some ETH to give to the DAO Treasury
BUIDL IT
Smart Contract Development
We will start off with first creating the smart contracts. We will be making two smart contracts:

FakeNFTMarketplace.sol
CryptoDevsDAO.sol
To do so, we will use the Hardhat development framework we have been using for the last few tutorials.

Create a folder for this project named DAO-Tutorial, and open up a Terminal window in that folder.

Setup a new hardhat project by running the following commands in your terminal:

mkdir hardhat-tutorial
cd hardhat-tutorial
npm init --yes
npm install --save-dev hardhat
Now that you have installed Hardhat, we can setup a project. Execute the following command in your terminal.

In the same directory where you installed Hardhat run:

npx hardhat
Select Create a basic sample project

Press enter for the already specified Hardhat Project root

Press enter for the question on if you want to add a .gitignore

Press enter for Do you want to install this sample project's dependencies with npm (@nomiclabs/hardhat-waffle ethereum-waffle chai @nomiclabs/hardhat-ethers ethers)?

Now you have a hardhat project ready to go!

If you are not on mac, please do this extra step and install these libraries as well :)

npm install --save-dev @nomiclabs/hardhat-waffle ethereum-waffle chai @nomiclabs/hardhat-ethers ethers
and press Enter for all the questions (Choose the Create a basic sample project) option.

Now, let's install the @openzeppelin/contracts package from NPM as we will be using OpenZeppelin's Ownable Contract for the DAO contract.

npm install @openzeppelin/contracts
