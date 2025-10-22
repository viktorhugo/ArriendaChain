# 🏠 ArriendaChain

> Decentralized reputation and fair pricing protocol for Colombia's rental housing market, built on Celo blockchain.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Celo](https://img.shields.io/badge/Built%20on-Celo-35D07F)](https://celo.org)
[![Self](https://img.shields.io/badge/KYC-Self-blue)](https://www.self.app/)

## 📋 Table of Contents

- [Overview](#-overview)
- [The Problem](#-the-problem)
- [Our Solution](#-our-solution)
- [Key Features](#-key-features)
- [Technical Architecture](#-technical-architecture)
- [Business Model](#-business-model)
- [Roadmap](#-roadmap)
- [Technologies](#-technologies)
- [Getting Started](#-getting-started)
- [Contributing](#-contributing)
- [Team](#-team)
- [License](#-license)

## 🎯 Overview

ArriendaChain is a decentralized protocol that transforms Colombia's rental market through:

- **🤝 Triple Reputation System**: On-chain scores for tenants, landlords, and properties
- **💰 Fair Price Oracle**: Prevention of overpricing through verifiable market data
- **🔐 Decentralized KYC**: Self integration for privacy and regulatory compliance
- **💵 cCOP Payments**: Native Colombian peso transactions without currency friction

### Expected Impact

- 🎯 **1M+ informal workers** building verifiable credit history
- 💸 **Cost reduction** from 10% to 2-3% in intermediation fees
- 📉 **40% less time** with vacant properties
- ⚖️ **$100M+ processed** with <0.1% default rate

## 🚨 The Problem

Colombia's rental market ($15B+) faces a crisis of trust and transparency:

### For Tenants
- ❌ No portable payment history between properties
- 💸 Frequent overpricing exceeding legal limits (1% monthly, CPI increases)
- 📄 Repetitive KYC processes for each application
- 🏦 60%+ informal workers without access to traditional credit
- ⚖️ Conflicts taking 12-18 months to resolve

### For Landlords
- 🔍 Information asymmetry about tenant history
- 💰 High real estate agency fees (8-10% of annual rent)
- ⏱️ 45+ days average to resolve non-payment
- 📋 Fraudulent applications with fake documents
- 🏚️ No accountability mechanisms for damages

### For the Market
- 📈 18% of properties unrented due to distrust
- 💔 Lack of transparent price signals
- 📊 Centralized data in silos
- 🌍 40M+ Colombians without access to formal financial system

## 💡 Our Solution

### 1. Triple Reputation System 🏆

**Tenant Score (0-1000)**
- 40% - On-chain payment history
- 25% - External credit history (Datacrédito/TransUnion)
- 20% - Behavior in previous properties
- 10% - System seniority
- 5% - Verified documentation (Self)

**Landlord Score (0-1000)**
- 30% - Transparency and fair pricing
- 25% - Maintenance and responsiveness
- 25% - Contract compliance
- 20% - Tenant ratings

**Property Score (0-1000)**
- 35% - Price vs. market
- 30% - Condition
- 20% - Included services
- 15% - Occupancy history

### 2. Fair Price Oracle 📊

Automatic compliance with Colombian regulations:
- ✅ Maximum 1% of commercial value per month
- ✅ Commercial value ≤ 2x cadastral appraisal
- ✅ Increases limited to CPI (5.20% for 2025)

**Valuation Algorithm:**
```
Base Price = min(Cadastral Appraisal × 2 × 0.01, Commercial Value × 0.01)
Adjusted Price = Base Price × Factor(location, area, services, condition)
Acceptable Range = Adjusted Price ± 15%
```

**Alert System:**
- 🟢 Green: Fair price within range
- 🟡 Yellow: 15-30% above market
- 🔴 Red: >30% overpriced

### 3. Smart Contract Infrastructure 🔗

**Main Contracts:**
- `RentalRegistry.sol` - Contract registry and automatic payments
- `ScoreManager.sol` - Reputation and score management
- `PaymentManager.sol` - cCOP payments with escrow
- `PriceOracle.sol` - External data integration
- `KYCManager.sol` - Self credentials verification
- `DisputeResolution.sol` - Decentralized arbitration

### 4. Decentralized KYC with Self 🔐

**Verification Levels:**

| Level | Requirements | Access |
|-------|--------------|--------|
| **Basic** | ID + Selfie | View properties, contact |
| **Standard** | + Verified income | Apply up to 2M COP/month |
| **Premium** | + References + Score | Premium properties, reduced deposits |

**Shared Data:** Only cryptographic proofs, NO raw personal data

## ✨ Key Features

### For Tenants
- 🎖️ **Portable Reputation**: History that follows you between properties
- 💰 **Good Score Discounts**: 0.5-2% reduction in rent
- 🚀 **Preferential Access**: Priority on best properties
- 🎫 **"Trusted Tenant" NFT**: Verifiable badge
- 📱 **Automatic Payments**: Monthly cCOP debit without friction

### For Landlords
- ✅ **Instant Verification**: Complete tenant history
- 💸 **Cost Reduction**: 2-3% vs 8-10% traditional
- 🔒 **Protected Deposits**: Automatic smart contract escrow
- ⚡ **Guaranteed Collection**: Automatic payment execution
- 📊 **Market Analytics**: Dashboard with pricing insights

### For the Ecosystem
- 🌐 **Total Transparency**: Public and verifiable market data
- 🏛️ **Regulatory Compliance**: Automatic application of Colombian law
- 🌱 **Financial Inclusion**: Access for informal workers
- ♻️ **ReFi Alignment**: Social impact + sustainability

## 🏗️ Technical Architecture

```
┌─────────────────────────────────────────┐
│     Frontend (Next.js + React)          │
│   - PWA Mobile-First                     │
│   - Responsive Design                    │
│   - Web3 Wallet Integration              │
└─────────────┬───────────────────────────┘
              │
┌─────────────▼───────────────────────────┐
│        Identity & Wallet Layer           │
│  - Self SDK (Decentralized KYC)          │
│  - Valora / MetaMask (Celo wallets)      │
└─────────────┬───────────────────────────┘
              │
┌─────────────▼───────────────────────────┐
│         Celo Blockchain Network          │
│                                           │
│  Smart Contracts:                         │
│  ├─ KYCManager.sol                        │
│  ├─ RentalRegistry.sol                    │
│  ├─ ScoreManager.sol                      │
│  ├─ PaymentManager.sol (cCOP/cUSD)        │
│  ├─ PriceOracle.sol                       │
│  └─ DisputeResolution.sol                 │
└─────────────┬───────────────────────────┘
              │
┌─────────────▼───────────────────────────┐
│      Oracles & External Data             │
│  ├─ Mento (cCOP price feed)              │
│  ├─ Catastro API (official appraisal)    │
│  ├─ DANE (updated CPI)                   │
│  ├─ Datacrédito/TransUnion (score)       │
│  └─ Crowdsourced Market Data             │
└──────────────────────────────────────────┘
```

### Technology Stack

**Blockchain Layer:**
- Celo Mainnet (low fees)
- Solidity 0.8.x (Smart contracts)
- Foundry (Development environment)
- OpenZeppelin (Audited contract libraries)

**Frontend:**
- Next.js 15 - React framework
- TypeScript - Type safety
- Tailwind CSS - Styling
- Reown AppKit - Wallet connection
- Wagmi - React hooks for Ethereum
- Viem - TypeScript Ethereum library
- Self SDK (KYC integration)

**Backend/APIs:**
- Node.js + Nestjs
- PostgreSQL (Off-chain data indexing)
- R-indexer (On-chain data querying)
- IPFS (Document storage)

**Stablecoins:**
- cCOP (Primary - Colombian Peso)
- cUSD (Fallback)
- cEUR (International users)

**Infrastructure:**
- Vercel (Frontend hosting)
- Railway/Fly.io (Backend)
- Infura/QuickNode (RPC nodes)
- Pinata (IPFS gateway)

## 💼 Business Model

### Revenue Streams

**1. Transaction Fees (70% of revenue)**
- 2.5% on monthly rent payments
- Distribution: 1.5% treasury, 0.5% validators, 0.5% liquidity

**2. Premium Services (15%)**
- Express 24h KYC: 50,000 COP
- Deep Verification: 80,000 COP
- Property Certification: 150,000 COP
- Damage Insurance: 2% of deposit

**3. Marketplace (10%)**
- Featured Listings: 100,000 COP/month
- Analytics Dashboard: 50,000 COP/month
- B2B White-label API: from 5M COP/year

**4. Dispute Resolution (5%)**
- 3% on disputed amounts (loser pays)

### Economics per Contract

```
Average Rent:            1,200,000 COP/month
ArriendaChain Fee:          30,000 COP/month
Average Duration:        12 months
──────────────────────────────────────
LTV per contract:          360,000 COP
CAC:                        50,000 COP
Gross Margin:                     86%
Payback Period:            1.7 months
```

### Growth Projections

| Year | Active Contracts | Annual Revenue |
|------|------------------|----------------|
| 2025 | 1,000 | 360M COP ($90K) |
| 2026 | 10,000 | 3.6B COP ($900K) |
| 2027 | 50,000 | 18B COP ($4.5M) |

**Social Impact:** 10% of fees allocated to social housing

## 🗓️ Roadmap

### Q1 2025 - Foundation ✅ (In Progress)
- [x] Market research and validation
- [x] Technical architecture defined
- [x] Project registration on Karma GAP
- [ ] Smart Contracts v1 development
- [ ] Self KYC integration (testnet)
- [ ] Basic MVP frontend
- [ ] Deploy on Celo Alfajores (testnet)

### Q2 2025 - MVP Launch 🚀
- [ ] Security audit (CertiK/OpenZeppelin)
- [ ] Mainnet deployment
- [ ] Pilot program with 10 properties in Medellín
- [ ] cCOP payment rails integration
- [ ] Analytics dashboard v1
- [ ] Onboarding of 50 beta users
- [ ] Grant applications (Celo Camp, Gitcoin)

### Q3 2025 - Scale & Iterate 📈
- [ ] Expansion to Bogotá and Cali
- [ ] Datacrédito/TransUnion integration
- [ ] Price oracle with ML predictions
- [ ] Optimized mobile PWA
- [ ] 500 active contracts
- [ ] Pre-seed fundraising ($200-300K)
- [ ] Team hiring (3 devs, 1 marketing)

### Q4 2025 - Market Fit 🎯
- [ ] 2,000+ active contracts
- [ ] $ARRIENDO token launch (governance)
- [ ] DAO for dispute resolution
- [ ] Partnerships with traditional PropTech
- [ ] Public API for developers
- [ ] Expansion to 5 Colombian cities

### 2026 - Regional Expansion 🌎
- [ ] Launch in Mexico, Argentina, Chile
- [ ] Integration with government housing programs
- [ ] 50,000+ active users
- [ ] Seed Round ($1-2M)
- [ ] Regulatory licenses in multiple countries

## 🛠️ Technologies

### Core Dependencies

```json
{
  "blockchain": {
    "network": "Celo Mainnet",
    "contracts": "Solidity ^0.8.30",
    "framework": "Foundry",
    "libraries": "@openzeppelin/contracts"
  },
  "frontend": {
    "framework": "Next.js 15",
    "ui": "React 19 + TypeScript",
    "styling": "TailwindCSS",
    "web3": "wagmi ^2.0 + Reown AppKit"
  },
  "identity": {
    "kyc": "Self SDK",
    "wallet": "Valora / MetaMask"
  },
  "stablecoins": {
    "primary": "cCOP",
    "fallback": "cUSD, cEUR, cREAL"
  }
}
```

### External Integrations

- **Mento Protocol**: cCOP price stability
- **Self**: Decentralized identity/KYC
- **The Graph**: Blockchain data indexing
- **IPFS**: Decentralized document storage
- **Chainlink (future)**: Additional price oracles
- **Datacrédito/TransUnion**: Credit score data

## 🚀 Getting Started

### Prerequisites

```bash
node >= 18.0.0
npm >= 9.0.0
git
```

### Local Installation

```bash
# Clone repository
git clone https://github.com/viktorhugo/ArriendaChain.git
cd ArriendaChain

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env.local
# Edit .env.local with your API keys

# Start local development node
npx hardhat node

# Deploy contracts locally
npx hardhat run scripts/deploy.js --network localhost

# Start frontend
npm run dev
```

Access at `http://localhost:3000`

### Testing

```bash
# Smart contract tests
npx hardhat test

# Coverage
npx hardhat coverage

# Frontend tests
npm run test

# E2E tests
npm run test:e2e
```

### Deploy to Testnet (Alfajores)

```bash
# Compile contracts
npx hardhat compile

# Deploy
npx hardhat run scripts/deploy.js --network alfajores

# Verify on explorer
npx hardhat verify --network alfajores DEPLOYED_CONTRACT_ADDRESS
```

## 🤝 Contributing

Contributions are welcome! Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for details about the process.

### Contribution Areas

- 🔧 **Smart Contracts**: Efficiency improvements, new features
- 🎨 **Frontend**: UI/UX, responsive design, accessibility
- 📊 **Data Science**: Pricing algorithms, ML models
- 📝 **Documentation**: Translations, tutorials, guides
- 🐛 **Testing**: Unit tests, integration tests, audits
- 🌐 **Community**: Marketing, education, partnerships

### Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md).

## 👥 Team

**Founder & Lead Developer**
- Viktor Hugo - [GitHub](https://github.com/viktorhugo)

**Advisors**
- TBD - Smart Contracts Security
- TBD - Colombian Real Estate Law
- TBD - Celo Ecosystem

**Seeking:**
- Full-stack Developer (Solidity + React)
- Community Manager
- Business Development (PropTech partnerships)

## 📞 Contact

- **Website**: [arriendachain.com](https://arriendachain.com) (coming soon)
- **Email**: contact@arriendachain.com
- **Twitter**: [@ArriendaChain](https://twitter.com/ArriendaChain)
- **Discord**: [Join our community](https://discord.gg/arriendachain)
- **Karma GAP**: [Project Profile](https://gap.karmahq.xyz/)

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

## 🙏 Acknowledgements

- **Celo Foundation** - For the ReFi ecosystem and technical support
- **Self Protocol** - For decentralized identity infrastructure
- **OpenZeppelin** - For audited and secure contracts
- **Colombian Blockchain Community** - For feedback and validation

---

**⚠️ Disclaimer**: ArriendaChain is in active development. Smart contracts have not been audited. Use on mainnet at your own risk until complete audit.

**🌱 Built with 💚 for Colombia's housing future / Cappy**
