---
layout: default
title: Blockchain Tips
description: A knowledge-sharing platform
---

# Things should be considered while writing smart contracts
_Contributed By: Sunny Sourav_  
_Dated: Feb 12, 2022_  

## Follow the proper structure and order
 ```
License Identifier
Choose proper solidity version and define

Groupby Imports
First BuiltIn contracts like chainlinks,opnezepplin

Local Imports

Define state variables
Add mappings if any

Define events for the functions we going to write

Define constructor

receive function (if there is any)

fallback function (if there is any)

external

public

internal

private
```

## Use Safemath to avoid any overflows/underflows
 - Import the library at top using 'import "@openzeppelin/contracts/utils/math/SafeMath.sol";'
 - Define using this using SafeMath for uint256;
 - Now wherever you want to use arithmetic operation use like this
    ```
   a + b becomes a.add(b)
   a - b becomes a.sub(b)
   a * b becomes a.mul(b)
   a / b becomes a.div(b)
   ```
 
## Use Ownable interface to transfer ownership
 - Import the library at top using 'import "@openzeppelin/contracts/access/Ownable.sol";'
 - Add the Ownable interface to the contract like "contract Pool is Ownable"
 
## Add comments to every function.
 - Add comments before function

For more information visit the source  
[Style guide solidity](https://docs.soliditylang.org/en/v0.8.10/style-guide.html) 
[back](./)