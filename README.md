# KaseiCoin

In the subsections, you’ll create a fungible token that’s ERC-20 compliant. This token will be minted by using a Crowdsale contract from the OpenZeppelin Solidity library.

The crowdsale contract that you create will manage the entire crowdsale process. This process will allow users to send ether to the contract and receive KaseiCoin tokens, or KAI, in return. Your contract will automatically mint the tokens and distribute them to a buyer in one transaction.

Note that you’ll record a short video or animated GIF or take several screenshots that show the deployed contract in action.

In the README.md file of your GitHub repository for this homework assignment, you’ll create a section named Evaluation Evidence. In this section, you’ll share screenshots of your work from each subsection of the assignment.

Step 1: Create the KaseiCoin Token Contract In this subsection, you’ll create a smart contract that defines KaseiCoin as an ERC-20 token. To do so, complete the following steps:

Import the provided KaseiCoin.sol starter file into the Remix IDE.

Import the following contracts from the OpenZeppelin library:

ERC20

ERC20Detailed

ERC20Mintable

Define a contract for the KaseiCoin token, and name it KaseiCoin. Have the contract inherit the three contracts that you just imported from OpenZeppelin.

Inside your KaseiCoin contract, add a constructor with the following parameters: name, symbol, and initial_supply.

As part of your constructor definition, add a call to the constructor of the ERC20Detailed contract, passing the parameters name, symbol, and 18. (Recall that 18 is the value for the decimals parameter.)

Compile the contract by using compiler version 0.5.0.

Check for any errors, and debug them as needed.

Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the README.md file for your GitHub repository.

Step 2: Create the KaseiCoin Crowdsale Contract In this subsection, you’ll define the KaseiCoin crowdsale contract. To do so, complete the following steps:

Import the provided KaseiCoinCrowdsale.sol starter code into the Remix IDE.

Have this contract inherit the following OpenZeppelin contracts:

Crowdsale

MintedCrowdsale

In the KaisenCoinCrowdsale constructor, provide parameters for all the features of your crowdsale, such as rate, wallet (where to deposit the funds that the token raises), and token. Configure these parameters as you want for your KaseiCoin token.

Compile the contract by using compiler version 0.5.0.

Check for any errors, and debug them as needed.

Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the README.md file for your GitHub repository.

Step 3: Create the KaseiCoin Deployer Contract In this subsection, you’ll create the KaseiCoin deployer contract. Start by uncommenting the KaseiCoinCrowdsaleDeployer contract in the provided KaseiCoinCrowdsale.sol starter code.

Next, in the KaseiCoinCrowdsaleDeployer contract, you’ll add variables to store the addresses of the KaseiCoin and KaseiCoinCrowdsale contracts, which this contract will deploy. Finally, you’ll complete the KaseiCoinCrowdsaleDeployer contract. To do so, complete the following steps:

Create an address public variable named kasei_token_address, which will store the KaseiCoin address once that contract has been deployed.

Create an address public variable named kasei_crowdsale_address, which will store the KaseiCoinCrowdsale address once that contract has been deployed.

Add the following parameters to the constructor for the KaseiCoinCrowdsaleDeployer contract: name, symbol, and wallet.

Inside of the constructor body (that is, between the braces), complete the following steps:

Create a new instance of the KaseiCoinToken contract.

Assign the address of the KaseiCoin token contract to the kasei_token_address variable. (This will allow you to easily fetch the token's address later.)

Create a new instance of the KaseiCoinCrowdsale contract by using the following parameters:

The rate parameter: Set rate equal to 1 to maintain parity with ether.

The wallet parameter: Pass in wallet from the main constructor. This is the wallet that will get paid all the ether that the crowdsale contract raises.

The token parameter: Make this the token variable where KaseiCoin is stored.

Assign the address of the KaseiCoin crowdsale contract to the kasei_crowdsale_address variable. (This will allow you to easily fetch the crowdsale’s address later.)

Set the KaseiCoinCrowdsale contract as a minter.

Have the KaseiCoinCrowdsaleDeployer renounce its minter role.

Compile the contract by using compiler version 0.5.0.

Check for any errors, and debug them as needed.

Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the README.md file for your Git repository.

Step 4: Deploy and Test the Crowdsale on a Local Blockchain In this subsection, you’ll deploy the crowdsale to a local blockchain. You’ll then perform a real-world, preproduction test of your crowdsale. To do so, complete the following steps:

Important: Record a short video or take screenshots that illustrate the following steps as evidence of your deployed crowdsale contract.

Deploy the crowdsale to a local blockchain by using Remix, MetaMask, and Ganache.

Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances of those accounts.

Review the total supply of minted tokens and the amount of wei that the crowdsale contract has raised.

<img width="1632" alt="Screen Shot 2022-07-25 at 2 51 47 PM" src="https://user-images.githubusercontent.com/97859377/180868588-a152c76b-ce4e-4deb-8f27-6a45026d28ff.png">
<img width="1650" alt="Screen Shot 2022-07-25 at 2 46 37 PM" src="https://user-images.githubusercontent.com/97859377/180868590-be9c70a6-a6f1-424a-aeab-d68e7085e89b.png">
<img width="1650" alt="Screen Shot 2022-07-25 at 2 46 26 PM" src="https://user-images.githubusercontent.com/97859377/180868593-533dc3f6-5b2d-4de5-902d-7db09553aa28.png">
