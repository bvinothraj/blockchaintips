---
layout: default
title: Blockchain Tips
description: A knowledge-sharing platform
---

# NatSpec format for writing smart contract

_Contributed By: Siddharth Choudhury_  
_Dated: Feb 15, 2022_

Solidity supports both C-style and C++-style comments, Thus −

> Any text between a  //  and the end of a line is treated as a comment and is ignored by Solidity Compiler.

> Any text between the characters /* and */ is treated as a comment. This may span multiple lines.

Example :

```
    /**
     * @notice this function returns the sum
    */
    function getResult() public view returns(uint){ 
        uint a = 1; 
        uint b = 2;
        uint result = a + b; // the sum is stored in result variable
        return result;
 }
```
## Standard to write comment for a state variable and mapping

Single line comments are usually used to describe state variable and mapping

Example :

```   
    //stores the address of owner
    address public owner;

    //emits when mint function is called
    event Minted(string uri, uint256 id);

    //mapping from NFT contract address to  tokenid to offer count
    mapping(address => mapping(uint256 => uint256)) public addressToOfferCount;
```

## Standard to write comment for a function

Use multi line comment to describe a function which must contain the following things :

1: What does the function do?
2: Parameters
3: What does it return?

Some of the tags usually used are :
1: @title A title that should describe the contract/interface
2: @notice Explain to an end user what this does
3: @dev Explain to a developer any extra details
4: @param Documents a parameter it's name and description
5: @return Documents the return variables of a contract’s function

Example :

```
    /**
      * @notice transfer NFT from owner to another account
      * @param _to receiver address
      * @param _id tokenId
      * @param _amount Number of token to be transfered
      * @return success true if success
     */
    function transfer(
        address _to,
        uint256 _id,
        uint256 _amount
    ) public returns (bool success) {
        safeTransferFrom(owner, _to, _id, _amount, "");
        return true;
    }
```
Source [Natspec format](https://docs.soliditylang.org/en/v0.8.10/natspec-format.html#natspec)

[back](../)
