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
./openethereum account new --config nodes/moc/moc.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
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

    To stake CLD coin, all you should do is sending your CLD coin to the EgonCoin Consensus contract address over the EgonCoin network from the validator address.
    The EgonCoin Consensus contract address: 0x641dCb1B53966084Ca59dc9985a164D414ac1D28
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to EgonCoin and send the CLD coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /EgonCoin/nodes/validator/keys/EgonCoin/UTC--xxxx
    /EgonCoin/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
