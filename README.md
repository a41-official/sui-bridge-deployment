# sui-bridge-deployment

## Setup

### 1. Set Image Tag
```bash
cp .env.(mainnet|testnet) .env
vi .env
```

### 2. Create config
```bash
cp ./config/bridge.yaml.(mainnet|testnet) ./config/bridge.yaml
```

## Run
```bash
docker compose up -d
```

## Bridge Cli
```bash
source .env
docker run -ti --rm mysten/sui-tools:$IMAGE_TAG sui-bridge-cli --help
```

### Generate Config (for new `metrics-key-pair`)
```bash
docker run -ti --rm -v ./config:/opt/sui/config mysten/sui-tools:$IMAGE_TAG sui-bridge-cli create-bridge-node-config-template /opt/sui/config/bridge.yaml
```

### Generate Key
```bash
docker run -ti --rm -v ./keys:/opt/sui/keys mysten/sui-tools:$IMAGE_TAG sui-bridge-cli create-bridge-validator-key /opt/sui/keys/bridge.key
```