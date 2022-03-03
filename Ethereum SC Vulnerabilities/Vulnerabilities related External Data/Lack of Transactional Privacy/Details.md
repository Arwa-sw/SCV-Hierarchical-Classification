Untrustworthy External Data Feeds (Oracles) (Lack of Trusted Data Feeds (Oracles)/Lack of trustworthy / Off-chain Safety 

Describe: 
Oracles are external sources of information (from services outside the blockchain), either from software (Big-data 
applications) or hardware (Internet-of-Things) that feed smart contracts and serve requests by other contracts to 
source data from outside the blockchain, such as from websites (e.g., websites). However, these data feeds which 
are brought to the blockchain also bring risk and it is hard to guarantee the trustworthiness of their sources. 
Which make it worse that there is a lack of a standard method in handling external data feed.

Sample code:
pragma solidity ^0.6.7;
3import "@chainlink/contracts/src/v0.6/interfaces/AggregatorV3Interface.sol";
contract PriceConsumerV3 {
    AggregatorV3Interface internal priceFeed;
    /**
     * Network: Kovan
     * Aggregator: ETH/USD
     * Address: 0x9326BFA02ADD2366b30bacB125260Af641031331
     */
    constructor() public {
        priceFeed = AggregatorV3Interface(0x9326BFA02ADD2366b30bacB125260Af641031331);
    }
   /**
     * Returns the latest price
     */
    function getLatestPrice() public view returns (int) {
        (
            uint80 roundID,
            int price,
            uint startedAt,
            uint timeStamp,
            uint80 answeredInRound
        ) = priceFeed.latestRoundData();
        return price;
    }
}
Source:  Chainlink Data Feeds
https://ethereum.org/de/developers/docs/oracles/
Its danger: 
Solution: Check the return value of send. Secret contracts (Enigma's secret contracts). Use caution when making external calls Use of “town crier (TC)” tool
Tools can detect:  Town Crier tool, it provides a bridge between HTTPS-enabled data websites and the  Ethereum blockchain.
