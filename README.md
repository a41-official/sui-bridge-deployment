# sui-bridge-deployment

# Setup

## 1. Set Image Tag
```bash
cp .env.example .env
vi .env
```

## 2. Create config
```bash
cp ./config/bridge.yaml.(mainnet|testnet) ./config/bridge.yaml
```

# Run
```bash
docker compose up -d
```

# Bridge Cli
```bash
source .env
docker run -ti --rm -v mysten/sui-tools:$IMAGE_TAG sui-bridge-cli --help
```