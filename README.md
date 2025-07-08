<div id="top"></div>

<!-- ABOUT THE PROJECT -->
## Decentral-medium

This a decentralized web3.0 version of the Medium application built on the Ethereum/Polygon network (or any EVM compatible blockchain), users can create posts and save them directly into the blockchain using IPFS.

![image](https://github.com/user-attachments/assets/70aeeeef-bd80-45f7-a272-cfa3f58d63bf)

### Built With

* [Solidity](https://docs.soliditylang.org/)
* [Hardhat](https://hardhat.org/getting-started/)
* [React.js](https://reactjs.org/)
* [ethers.js](https://docs.ethers.io/v5/)
* [web3modal](https://github.com/Web3Modal/web3modal)
* [material ui](https://mui.com/getting-started/installation/)

<!-- GETTING STARTED -->
## Getting Started

### Prerequisites

Please install or have installed the following:
* [nodejs](https://nodejs.org/en/download/) and [yarn](https://classic.yarnpkg.com/en/)
* [MetaMask](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn) Chrome extension installed in your browser
* [Ganache](https://trufflesuite.com/ganache/) for local smart contracts deployement and testing

### Initial Setup
1. Clone the repository and install all the required packages by running:
   ```sh
   git clone https://github.com/kaymen99/Decentral-medium.git
   cd Decentral-medium
   yarn
   ```
2. Private key & Network Urls setup: in the hardhat folder you'll find a .env file, it's used to store all the sensible data/keys like your private key, RPC url for mainnet, rinkeby, kovan... (you get RPC url from services like Infura or Alchemy for free), you can also provide Etherscan api key to allow automatic contracts verifications :
   ```sh
    RINKEBY_ETHERSCAN_API_KEY="your etherscan api key"
    RINKEBY_RPC_URL="https://eth-rinkeby.alchemyapi.io/v2/apiKey"
    POLYGON_RPC_URL="Your polygon RPC url from alchemy or infura"
    MUMBAI_RPC_URL="Your mumbai RPC url from alchemy or infura"
    PRIVATE_KEY="ganahce-private-key"
   ```
* <b>IMPORTANT : </b> For the purpose of testing you can just provide the ganache private key and ignore all the other variables.

3. As infura recently removed its free IPFS storage gateway i used `web3.storage` api for storing data into IPFS, this api is as simple as infura it requires the creation of a free account and a new api token which you can do [here](https://web3.storage), when you finish add your api token into the `src/utils/ipfsStorage.js` file:
   ```js
    const web3storage_key = "YOUR-WEB3.STORAGE-API-TOKEN";
   ```
   
<p align="right">(<a href="#top">back to top</a>)</p>

<!-- Working EXAMPLES -->
## How it Works

### Contracts

The blog is based on the MediumBlog.sol smart contract which contains all the backend logic :

<h4>Core functions:</h4>
<ul>
  <li><b>subscribe:</b> allow any user to subscribe & create a profile in the app for posting articles.</li>
  <li><b>editProfile:</b> enable author to update his profile (username, picture, description).</li>
  <li><b>createPost:</b> once subscribed each user can add it's own posts by providing a title,an overview, main content and the read time</li>
  <li><b>updatePost:</b> author can change the details of previously published posts </li>
  <li><b>tipPostCreator:</b> allow any user to give a tip to a certain post author</li>
</ul>

<h4>Admin functions: (admin is the only one that can call this functions)</h4>
<ul>
  <li><b>changeListingFee:</b> change the fee charged when posting a new article</li>
  <li><b>withdrawBalance:</b> the admin is able to withdraw th contract balance which is accumulated from the charged posting fee</li>
</ul>

