---
layout: default
title: Blockchain Tips
description: A knowledge-sharing platform
---

# Defi Flashloan 
_Contributed By: Sunny Sourav_  
_Dated: April 08, 2022_  

# what is flashloan
Flash Loans allow you to borrow any available amount of assets without putting up any collateral,also known as non-collateralized loan

## How does it work
The contract is designed in such a way that the liquidity gets returned to protocol within the same block of transaction.

## Where it is used
**Arbitrage Trading**
Its trading that exploits the tiny differences in price between identical assets in two or more DEX markets.
Suppose Uniswap is giving 3500 DAI token for 1 Ethereum, and Pancakeswap is giving 3550 DAI Token for 1 Ethereum
and user only have that much ethereum from which he can pay gas fee for transaction,In this case user can make use of Flashloan to do the 
swaps without putting any collateral, they just have to pay the gas fee, it can be explained using below steps:
   
 - Borrowing Dai from Aave or dydx using a flash loan
 - Swapping the Dai for Eth on Uniswap
 - Swapping the Dai for Eth on Pancakeswap
 - Repaying the borrowed loan on same transaction + fee


**Collateral Swapping**
Flash loans allow users to swap collateral or debt in a single block of transaction.
Suppose you had borrowed Dai by using an Eth collateral on MakerDAO, you 
could swap the collateral using a flash loan, steps mentioned below:

 - Take a Dai flash loan.
 - Close the MakerDAO loan by repaying Dai and unlocking the Eth collateral.
 - Selling Eth for BAT on Uniswap or any other DEX.
 - Opening the BAT collateral MakerDAO position and borrowing Dai.
 - Closing the flash loan by repaying Dai.

   
**Self-Liquidation**
Self-liquidation is another important use-case of flash loans that could help traders to avoid their position from being liquidated.
Suppose you had borrowed Dai using Eth as collateral from a DeFi lending protocol. Now, if the price of Eth keeps falling downwards 
raising the fear of your position getting liquidated, In that case you can follow below steps to liquidate your collateral :

 - Take a Dai flash loan 
 - Close your collateralized debt position using Dai
 - Unlock your eth and swap it for Dai
 - Close the flash loan position and keep the rest of Eth
 

For more information visit the source <br>
[Aave Flashloan doc](https://docs.aave.com/developers/guides/flash-loans) <br>
[Credits](https://hypertrader.app/use-cases-of-flash-loans/) <br>
[back](./)