**---
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

## Use Safecast if you feel you wasting too much memory

 - Import the library at top using 'import "@openzeppelin/contracts/utils/math/SafeCast.sol" '
 - Add "using SafeCast for uint256;"
 
## Use Ownable interface to transfer ownership

 - Import the library at top using 'import "@openzeppelin/contracts/access/Ownable.sol";'
 - Add the Ownable interface to the contract like "contract Pool is Ownable"

## Add Chainlinks if contract want to consume any data feed

 - Import the chainlink interface at top 
 - Add the function for the chainlink used
 
## Add comments to every function.
 - Add comments before function
[back](./)