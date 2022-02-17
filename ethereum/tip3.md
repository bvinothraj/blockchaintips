---
layout: default
title: Blockchain Tips
description: A knowledge-sharing platform
---

# How to add chainlink price oracle for your contract
_Contributed By: Sunny Sourav_  
_Dated: Feb 12, 2022_  

## Follow these steps to add price oracle to your smart contract
Suppose we want real time price feed from Ether to DAI token

 - Import the chainlink Interface 'import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";'
 - Find the contract address for your datafeed from <a href="https://docs.chain.link/docs/ethereum-addresses/"> Chainlink</a>
   by selecting correct network you deploying your contract
 - For now considering rinky testnetwork and conversion we need is DAI to ETH then the address will be "0x8A753747A1Fa494EC906cE90E9f37563A8AF630e"
 - Now add the pricefeed conversion to your constructor
   ```
   priceFeed = AggregatorV3Interface(
            0x8A753747A1Fa494EC906cE90E9f37563A8AF630e
        );

   ```
 - Add function to get latest price
   ```
   function getLatestPrice()
        public
        view
        returns (
            uint80,
            int256,
            uint256,
            uint256,
            uint80
        )
    {
        (
            uint80 roundID,
            int256 price,
            uint256 startedAt,
            uint256 timeStamp,
            uint80 answeredInRound
        ) = priceFeed.latestRoundData();
        // for ETH / USD price is scaled up by 10 ** 8
        price = price / 1e8;
        return (roundID, price, startedAt, timeStamp, answeredInRound);
    }
   ```
   
 - Call the function getLatestPrice() wherever you need the price,it will
   return you the latest price

 - Source <a href="https://docs.chain.link/">Chainlink price oracle</a>

[back](./)