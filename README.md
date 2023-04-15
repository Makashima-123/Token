# Token contract

 The "MyToken" smart contract developed using the Solidity programming language  It provides users with a range of functionalities like token minting, burning, and sending. The contract employs a well-structured combination of functions, mapping, and state variables to facilitate user interactions 

## Description

The "MyToken" smart contract, written in Solidity, enables users to mint, burn, and transfer tokens. It features three functions for user interaction and employs basic Solidity concepts for token creation, burning, and sending.
Create Token contract
1. Token name and abbreviation: The tokenName and tokenAbbrv variables store the name and abbreviation of the token respectively, which are publicly accessible.
2. Total token supply: The totalSupply variable keeps track of the total supply of tokens, which is initially set to 0.
3. Balances mapping: The balances mapping is used to store the token balances of addresses. It associates an address with an unsigned integer representing the token balance of that address.
4. Mint function: The mint function allows tokens to be added to a specified address. It increases the total supply and adds the specified amount of tokens to the address.
5. Burn function: The burn function enables tokens to be removed from a specified address. It decreases the total supply and deducts the specified amount of tokens from the address, if the balance is sufficient.
6. Send function: The send function allows tokens to be transferred from one address to another. It verifies that the sender has sufficient balance before deducting the tokens from the sender's address and adding them to the receiver's address
 
## Getting Started

### Executing program

Step 1: Open Remix
Open the Remix web-based Integrated Development Environment (IDE) in your preferred web browser by navigating to https://remix.ethereum.org/.

Step 2: Create a New File
Click on the "+" icon on the left sidebar of the Remix IDE to create a new file. Name the file "MyToken.sol" (or any preferred name) and click "OK".

Step 3: Copy and Paste the Code given below.
Copy and paste the provided code for the "MyToken" smart contract into the newly created file in the Remix IDE.

Step 4: Compile the Smart Contract
Click on the "Solidity Compiler" tab at the top of the Remix IDE. Under the "Compiler Configuration" section, select the desired compiler version (e.g., 0.8.18) from the drop-down menu. Then, click on the "Compile MyToken.sol" button to compile the smart contract.

Step 5: Deploy the Smart Contract
After successful compilation, switch to the "Deploy & Run Transactions" tab in the Remix IDE. Select the desired environment (e.g., JavaScript VM, Injected Web3, etc.) from the drop-down menu. Then click on the "Deploy" button to deploythe smart contract to the selected environment.

Step 6: Interact with the Smart Contract
Once the smart contract is deployed, you can interact with it using the functions defined in the contract. For example, you can call the "mint", "burn", and "send" functions by providing the appropriate input parameters and clicking on the "Transact" button.

That's it! You have successfully run the "MyToken" smart contract in Remix and interacted with its functions.
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "FutureCompany"; //Name of the token
    string public tokenAbbrv = "Fcom"; //token abbreviation
    uint public totalSupply = 0; //total supply of tokens

    // mapping to store token balances 
    mapping (address => uint) public balances;

    // mint function to add tokens to an address
    function mint(address _address, uint _value) public 
    {
        balances[_address] += _value; //adds tokens to the provided address
        totalSupply += _value; //adds the minted token to the total supply 
    }

    // burn function to burn the token from an address
    function burn(address _address, uint _value) public 
    {
        if(balances[_address] >= _value)
        {
            balances[_address] -= _value; //deducts tokens from the provided address
            totalSupply -= _value; //deducts tokens from the main supply 
        }
    }
    // payable function to transfer tokens from one address to other address
    function send(address Send_address,address Receiver_address, uint _value) public  
    {
        if(balances[Send_address] >= _value)
        {
            balances[Send_address] -= _value; //tokens are deducted from the sender's account
            balances[Receiver_address] += _value; //tokens are added to the receiver's account
        }
    }
}
```

## Help
## Authors

Contributors names and contact info

* Preeti Reddy
* Email: swapna.reddy.010683@gmail.com


## License

This project is licensed under the [MIT License] License - visit https://spdx.org/licenses/MIT for details
