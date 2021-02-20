# Oracles

Oracles are used and integrated into smart contracts to get secure & reliable real time data. This live data can be used for dapps, flashloans, yield farms, DEX's and more! With the Binance Smart Chain being relatively new in popularity there arent enough oracles in the ecosystem and we intend to solve that. 

What happens when there aren't enough oracles? Without enough oracles data can be skewed and manipulated easily which may incentivize bad actors. One example is the flash loan "hack" which a user took out a large loan and pumped the price on one exchange, which made the contract that was relying on data from the one source give false numbers allowing the hacker to withdraw large amounts of dai at a much higher ratio and thus draining the exchange. 

We believe that by expanding the network of decentralized oracles smart contracts and dapps in the future running on the binance smart chain will be much more stable & secure. Below is an example of how you will be able to implement our oracle interface in your source code.

Example Implementing future Pegasus dynamic price oracle for BNB:

```text
contract BNBPriceContract is UsingPegasus {

  //This Contract now has access to all the functions on PegasusProtocol

  uint256 bnbPrice;
  uint256 bnbRequetId = 1;

  constructor(address payable _pegasusAddress) UsingPegasus(_pegasusAddress) public {}

  function setBNBPrice() public {
    bool _didGet;
    uint _timestamp;
    uint _value;

    (_didGet, bnbPrice, _timestamp) = getCurrentValue(bnbRequetId);
  }
}
```

