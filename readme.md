# This is the Source code for the TimpiChain on the Testnet.

# To get started you have to
- copy this repo
- install go (https://go.dev/doc/install) version 1.18.1 works.
- go to /cmd/TimpiChain
- execute "go build"
- now you can start setting up the node.

# To run a standalone node to play around with

- ./TimpiChain init TimpiChain --chain-id WhatYouWant
- ./TimpiChain keys add MainValidator --keyring-backend test
- ./TimpiChain add-genesis-account MainValidator 4000000000stake --keyring-backend test
- ./TimpiChain gentx MainValidator 1000000stake --keyring-backend test --chain-id WhatYouWant
- ./TimpiChain collect-gentxs
- ./TimpiChain start

# To run a linked node you do
-./TimpiChain init TimpiChain

copy the genesis.json file from http://173.249.54.208/genesis.json into root/.TimpiChain/config and replace the old one.
edit the config.toml in the same directory and change 

[rpc]

TCP or UNIX socket address for the RPC server to listen on
laddr = "tcp://127.0.0.1:26657"

to

[rpc]

TCP or UNIX socket address for the RPC server to listen on
laddr = "tcp://0.0.0.0:26657"

and add "7d6938bdfce943c1d2ba10f3c3f0fe8be7ba7b2c@173.249.54.208:26656" to
persistent_peers = "" like so persistent_peers = "7d6938bdfce943c1d2ba10f3c3f0fe8be7ba7b2c@173.249.54.208:26656"

# To use the faucet
- add a key to your node and use this link http://173.249.54.208:1337/YOURWALLET. Replace YOURWALLET with your address.

