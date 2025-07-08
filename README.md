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

