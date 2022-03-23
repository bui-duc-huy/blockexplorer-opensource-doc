# Build blockscout with docker

1. Create env variable
- Run chain
```sh
./build/bin/geth --datadir ~/.ethereum/myprivatenet --networkid 15 --http --http.vhosts="*" --http.api="eth,net,web3,personal,txpool,miner" --gcmode="archive"
```

- Set up ethereum config
```sh
COIN=DAI \
ETHEREUM_JSONRPC_VARIANT=geth \ 
ETHEREUM_JSONRPC_HTTP_URL=http://host.docker.internal:8545 \
ETHEREUM_JSONRPC_WS_URL=ws://host.docker.internal:8546 \
```
> Base on client we conneted

- Fix docker env (base on Apple silicon)
```sh
HEX_HTTP_CONCURRENCY=1 HEX_HTTP_TIMEOUT=240
```

- Run docker
```sh
cd docker
make start
```
