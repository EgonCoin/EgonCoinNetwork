# Run a EgonCoin Validator
## Setting up a node
1. Git clone https://github.com/EgonCoin/EgonCoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r EgonCoinNetwork/node-example/EgonCoin  /root/
```
3. Create an Account
(This is a new EVM blockchain wallet address that will be used as the validator address and the address to be used to stake)

```
cd /root/EgonCoin
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like this - 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2
 You can find and save your key-store (containing your private key) and the password for the created account in:
    /EgonCoin/nodes/validator/keys/EgonCoin/UTC--xxxx
    /EgonCoin/nodes/validator/node.pwd

Copy created address to node.toml
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
5. Validator Stake

    Stake

    To stake EGC coin to activate node, all you should do is sending your 100,000 EGC coin to the EgonCoin Consensus contract address over the EgonCoin network from the new validator address created above. The EgonCoin Consensus contract address: 0x641dCb1B53966084Ca59dc9985a164D414ac1D28
    
    The easiest way to do so, is to import your validator wallet created above into Metamask, switch network to EgonCoin and send the EGC coin to the Consensus contract address.


6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
    
7. Then you contact developer team to add you into Elevator Staking DApp.
    
