# Oracles

Oracles are used and integrated into smart contracts to get secure & reliable real time data. This live data can be used for dapps, flashloans, yield farms, DEX's and more! With the Binance Smart Chain being reletively new in popularity there arent enough oracles in the ecosystem and we intent to solve that. 

What happens when there arent enough oracles? Without enough oracles data can be skewed and manipulated easily which may incentivize bad actors. One example is the flash loan "hack" which a user took out a large loan and pumped the price on one exchange, which made the contract that was relying on data from the one source give false numbers allowing the hacker to withdraw large amounts of dai at a much higher ratio and draining the exchange. 



Below is an example of how you will be able to implement our oracle interface in your source code.



Implementing future Pegasus dynamic price oracles:

```text
contract BtcPriceContract is UsingPegasus {

  //This Contract now have access to all functions on PegasusProtocol

  uint256 btcPrice;
  uint256 btcRequetId = 1;

  constructor(address payable _pegasusAddress) UsingPegasus(_pegasusAddress) public {}

  function setBtcPrice() public {
    bool _didGet;
    uint _timestamp;
    uint _value;

    (_didGet, btcPrice, _timestamp) = getCurrentValue(btcRequetId);
  }
}
```

