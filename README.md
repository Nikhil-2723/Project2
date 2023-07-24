# Create a Token
This is a contract program creating a token that contains burn and mint functions along with various public variables.
## Description

In this code, two functions has been created that is mint and burn, mint function is used to store the values for totalSupply(public variable) and balances(mapping variable) that will show the current amount of token and burn function to transact some amount of token and accordingly the values of totalSupply and balances get updated. And to do all this account address needs to be copied and pasted in the address section of mint and burn function. Also there are two more public variables denoting tokenName and tokenAbbrv.

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

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button. 

Once the contract is deployed, you can interact with it by calling mint and burn function by pasting the account address and the value that has ro be store or get deducted . Click on the "myToken" contract in the left-hand sidebar, and then click on the "mint" function. Finally, click on the "transact" button to execute the function and retrieve the tokenSupply and balance amount.

## Authors
Nikhil Upadhyay

## License
This project is licensed under the MIT License.
