# Create a Token
This is a contract program creating a token that contains burn and mint functions along with various public variables.
## Description
    In this code, two functions has been created that is mint and burn  
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
## Authors
Metacrafter Chris  
[@metacraftersio](https://twitter.com/metacraftersio)

## License
This project is licensed under the MIT License
