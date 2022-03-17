# Build blockscout with docker

1. Create env variable
- Set up ethereum config
```sh
COIN=DAI \
ETHEREUM_JSONRPC_VARIANT=geth \ 
ETHEREUM_JSONRPC_HTTP_URL=http://localhost:8545 \
ETHEREUM_JSONRPC_WS_URL=ws://localhost:8546 \
```
> Base on client we conneted

- Fix docker env
```sh
HEX_HTTP_CONCURRENCY=1 HEX_HTTP_TIMEOUT=240
```

- Run docker
```sh
cd docker
make start
```
