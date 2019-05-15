# Build

Execute from git repository root

## Mainnet
```
docker build --build-arg CARDANO_NET=mainnet --build-arg CARDANO_SL_GIT_COMMIT=master -t bethington/cardano-sl-mainnet .
```
## Testnet
```
docker build --build-arg CARDANO_NET=testnet --build-arg CARDANO_SL_GIT_COMMIT=master -t bethington/cardano-sl-testnet .
```
## Both at once
```
for network in testnet mainnet
do
  docker build --build-arg CARDANO_NET=${network} --build-arg CARDANO_SL_GIT_COMMIT=master -t bethington/cardano-sl:${network} .
done
```

# Run

```
docker run -it -p 8000:8000 -p 8100:8100 -p 8110:8110 bethington/cardano-sl-mainnet:latest
```

```
docker run -it -p 8000:8000 -p 8100:8100 -p 8110:8110 bethington/cardano-sl-testnet:latest
```

You'll be able to access to:

* webui: http://localhost:8000
* api: http://localhost:8100
* websocket: http://localhost:8110
