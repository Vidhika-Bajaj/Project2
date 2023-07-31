# Create a Token
This contract program creates a token containing burn and mint functions and various public variables.
## Description

In this code, two functions have been created that is mint and burn, the mint function is used to store the values for totalSupply(public variable) and balances(mapping variable) that will show the current amount of tokens, and the burn function to transact some amount of token and accordingly the values of totalSupply and balances get updated. And to do all this account address needs to be copied and pasted into the address section of the mint and burn function. Also, there are two more public variables denoting tokenName and tokenAbbrv.

## Getting Started
### Executing program
       
```javascript
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value)public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile project.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button. 

Once the contract is deployed, you can interact with it by calling the mint and burn function and pasting the account address and the value that has to be stored or deducted. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" function. Finally, click on the "transact" button to execute the function and retrieve the tokenSupply and balance amount.

## Authors
Vidhika Bajaj

## License
This project is licensed under the MIT License.
