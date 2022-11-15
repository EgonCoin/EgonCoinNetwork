# Run a EgonCoin Validator
## Setting up a node
1. Git clone https://github.com/EgonCoin/EgonCoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r EgonCoinNetwork/node-example/EgonCoin  /root/
```
3. Create an Account

```
cd /root/EgonCoin
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake EGC coin, all you should do is sending your EGC coin to the EgonCoin Consensus contract address over the EgonCoin network from the validator address.
    
    The easiest way to do so, is to import your wallet into Metamask, switch network to EgonCoin and send the EGC coin to the Consensus contract address.

    After import you can access account details here:
    /EgonCoin/nodes/validator/keys/EgonCoin/UTC--xxxx
    /EgonCoin/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
