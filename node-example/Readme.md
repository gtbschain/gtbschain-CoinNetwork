# Run a GTBS Validator
## Setting up a node
1. Git clone https://github.com/gtbschain/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/GTBS  /root/
```
3. Create an Account

```
cd /root/GTBS
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

    To stake GTBS coin, all you should do is sending your GTBS coin to the GTBS Consensus contract address over the GTBS network from the validator address.
    The GTBS Consensus contract address: 0x73D22450B43adc1f67e08e983664323d67cE62b4
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to GTBS and send the GTBS coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /GTBS/nodes/validator/keys/GTBS/UTC--xxxx
    /GTBS/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
