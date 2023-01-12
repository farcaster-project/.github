## Welcome to the Farcaster Project

Farcaster is a cross-chain atomic swap protocol and implementation who allows to exchange Bitcoin and Monero in a peer-to-peer manner with anyone running a Farcaster node.

Our implementation is done in Rust :crab: and uses electrum and monero nodes to interface with the blockchains. The easiest way to get started is to use our 🐋 Docker images, you can have a look how we create them [here](https://github.com/farcaster-project/containers).

### Want to try?
Have a look at the [Node wiki](https://github.com/farcaster-project/farcaster-node/wiki) to see how to install and run the node. 💡 You can even trade testnet coins on [farcaster.dev](https://farcaster.dev) to learn how it works!

If you have Rust and Docker installed on your machine you can run

```bash
# run a temporary Monero wallet RPC
docker run --rm -d -p 38083:38083 ghcr.io/farcaster-project/containers/monero-wallet-rpc:latest\
    /usr/bin/monero-wallet-rpc --stagenet\
    --disable-rpc-login --wallet-dir wallets\
    --daemon-host stagenet.community.rino.io:38081\
    --rpc-bind-ip 0.0.0.0 --rpc-bind-port 38083\
    --confirm-external-bind
# install and launch your node
cargo install farcaster_node
farcasterd
```

In a new terminal you can now interact with your node through the cli with
```
swap-cli info
swap-cli take --help
```

Or check your browser at [ui.farcaster.dev](https://ui.farcaster.dev)! (You need to activate grpc in your node config)

You are ready to take a deal!

### More resources

If you want to know more about the specifications have a look at the 📜 [RFCs](https://github.com/farcaster-project/RFCs) and the [Core library](https://github.com/farcaster-project/farcaster-core).
