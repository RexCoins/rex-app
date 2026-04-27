# 🔗 RexChain

**RexCoin (RXC)** — Advanced Blockchain Platform

---

## 📋 Overview

| Property | Value |
|---|---|
| Blockchain | RexChain |
| Coin | RexCoin (RXC) |
| Total Supply | 1,000,000,000 RXC |
| Consensus | Delegated Proof of Stake (DPoS) |
| Chain ID | 1337 |
| Block Reward | 10 RXC |
| TX Fee | 0.1% |
| Smart Contract | WASM + RXC-20 Tokens |

---

## 🚀 Quick Start (Termux)

### 1. Setup
```bash
pkg update && pkg upgrade -y
pkg install rust golang python git nodejs cmake openssl clang -y
```

### 2. Run Core Node (Port 8545)
```bash
cd RexChain/core
cargo run
```

### 3. Run P2P Network (Port 8546)
```bash
cd RexChain/node
go run main.go
```

---

## 🌐 API Endpoints (Port 8545)

### Chain
```
GET  /              → Node info
GET  /chain         → All blocks
GET  /block/{id}    → Single block
GET  /stats         → Chain stats
```

### Wallet
```
POST /wallet/new    → Create wallet
POST /wallet/import → Import wallet
GET  /balance/{addr}→ Get balance
```

### Transactions
```
POST /transaction   → Send RXC
GET  /mempool       → Pending TXs
POST /mine          → Mine block
```

### Smart Contracts
```
GET  /contracts          → All contracts
POST /contract/deploy    → Deploy RXC-20 token
POST /contract/call      → Call contract function
```

### Validators (DPoS)
```
GET  /validators          → Active validators
POST /validator/register  → Become validator
POST /validator/delegate  → Delegate stake
```

---

## 📝 API Examples

### Create Wallet
```bash
curl -X POST http://localhost:8545/wallet/new
```

### Check Balance
```bash
curl http://localhost:8545/balance/0xYOUR_ADDRESS
```

### Send RXC
```bash
curl -X POST http://localhost:8545/transaction \
  -H "Content-Type: application/json" \
  -d '{"from":"0xADDRESS","to":"0xADDRESS2","amount":100}'
```

### Deploy Token
```bash
curl -X POST http://localhost:8545/contract/deploy \
  -H "Content-Type: application/json" \
  -d '{"creator":"0xADDRESS","name":"MyToken","symbol":"MTK","total_supply":1000000}'
```

### Register Validator
```bash
curl -X POST http://localhost:8545/validator/register \
  -H "Content-Type: application/json" \
  -d '{"address":"0xADDRESS","stake":10000,"commission":0.05}'
```

### Mine Block
```bash
curl -X POST http://localhost:8545/mine \
  -H "Content-Type: application/json" \
  -d '{"validator":"0xVALIDATOR_ADDRESS"}'
```

---

## 📁 Project Structure

```
RexChain/
├── core/          # Rust — Main blockchain engine
│   └── src/
│       ├── main.rs        # Entry point
│       ├── block.rs       # Block structure
│       ├── chain.rs       # Blockchain
│       ├── transaction.rs # TX engine
│       ├── crypto.rs      # Hashing & addresses
│       ├── wallet.rs      # Wallet system
│       ├── balance.rs     # Balance tracker
│       ├── mempool.rs     # TX pool
│       ├── vm.rs          # Smart contract engine
│       ├── consensus.rs   # DPoS consensus
│       └── rpc.rs         # HTTP API server
│
├── node/          # Go — P2P networking
│   └── main.go            # P2P node
│
├── explorer/      # cPanel — Block Explorer
│   └── index.html         # Web explorer
│
└── wallet/        # cPanel — Web Wallet
    └── index.html         # Browser wallet
```

---

## 🌍 cPanel Deployment

1. Upload `explorer/index.html` → `public_html/explorer/`
2. Upload `wallet/index.html` → `public_html/wallet/`
3. Set Node URL to your server IP:8545

---

## 🔧 Technologies

| Layer | Technology |
|---|---|
| Core | Rust |
| Networking | Go |
| Explorer | HTML/CSS/JS |
| Wallet | HTML/CSS/JS |
| Consensus | DPoS |
| Cryptography | secp256k1, SHA256, Keccak256 |

---

## ⚡ Coming Next

- [ ] ZK-Proof privacy transactions
- [ ] Cross-chain bridge
- [ ] Mobile wallet (Android)
- [ ] DEX (Decentralized Exchange)
- [ ] Staking rewards distribution
- [ ] Governance voting

---

**Built with ❤️ — RexChain Team**
