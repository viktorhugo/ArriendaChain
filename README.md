# 🏠 ArriendaChain

> Decentralized reputation and fair pricing protocol for Colombia's rental housing market, built on Celo blockchain.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Celo](https://img.shields.io/badge/Built%20on-Celo-35D07F)](https://celo.org)
[![Self](https://img.shields.io/badge/KYC-Self-blue)](https://www.self.app/)

## 📋 Tabla de Contenidos

- [Visión General](#-visión-general)
- [El Problema](#-el-problema)
- [Nuestra Solución](#-nuestra-solución)
- [Características Principales](#-características-principales)
- [Arquitectura Técnica](#-arquitectura-técnica)
- [Modelo de Negocio](#-modelo-de-negocio)
- [Roadmap](#-roadmap)
- [Tecnologías](#-tecnologías)
- [Comenzar](#-comenzar)
- [Contribuir](#-contribuir)
- [Equipo](#-equipo)
- [Licencia](#-licencia)

## 🎯 Visión General

ArriendaChain es un protocolo descentralizado que transforma el mercado de arriendo en Colombia mediante:

- **🤝 Sistema de Reputación Triple**: Puntajes on-chain para arrendatarios, arrendadores e inmuebles
- **💰 Oráculo de Precio Justo**: Prevención de sobrevaloración mediante datos verificables del mercado
- **🔐 KYC Descentralizado**: Integración con Self para privacidad y cumplimiento normativo
- **💵 Pagos en cCOP**: Transacciones nativas en pesos colombianos sin fricción cambiaria

### Impacto Esperado

- 🎯 **1M+ trabajadores informales** construyendo historial crediticio verificable
- 💸 **Reducción de costos** del 10% al 2-3% en comisiones de intermediación
- 📉 **40% menos tiempo** de propiedades desocupadas
- ⚖️ **$100M+ procesados** con <0.1% tasa de impago

## 🚨 El Problema

El mercado de arriendo colombiano ($15B+) enfrenta crisis de confianza y transparencia:

### Para Arrendatarios
- ❌ No existe historial de pagos portable entre propiedades
- 💸 Sobrevaloraciones frecuentes que exceden límites legales (1% mensual, incrementos IPC)
- 📄 Procesos KYC repetitivos para cada aplicación
- 🏦 60%+ de trabajadores informales sin acceso a crédito tradicional
- ⚖️ Conflictos que toman 12-18 meses en resolverse

### Para Arrendadores
- 🔍 Asimetría de información sobre historial de inquilinos
- 💰 Altas comisiones de inmobiliarias (8-10% del canon anual)
- ⏱️ 45+ días promedio para resolver falta de pago
- 📋 Solicitudes fraudulentas con documentos falsos
- 🏚️ Sin mecanismos de rendición de cuentas por daños

### Para el Mercado
- 📈 18% de propiedades sin arrendar por desconfianza
- 💔 Falta de señales de precio transparentes
- 📊 Datos centralizados en silos
- 🌍 40M+ colombianos sin acceso a sistema financiero formal

## 💡 Nuestra Solución

### 1. Sistema de Reputación Triple 🏆

**Puntaje de Arrendatarios (0-1000)**
- 40% - Historial de pagos on-chain
- 25% - Historial crediticio externo (Datacrédito/TransUnion)
- 20% - Comportamiento en inmuebles anteriores
- 10% - Antigüedad en el sistema
- 5% - Documentación verificada (Self)

**Puntaje de Arrendadores (0-1000)**
- 30% - Transparencia y justicia en precios
- 25% - Mantenimiento y respuesta
- 25% - Cumplimiento contractual
- 20% - Calificaciones de arrendatarios

**Puntaje de Inmuebles (0-1000)**
- 35% - Precio vs. mercado
- 30% - Estado de conservación
- 20% - Servicios incluidos
- 15% - Historial de ocupación

### 2. Oráculo de Precio Justo 📊

Cumplimiento automático de regulación colombiana:
- ✅ Máximo 1% del valor comercial mensual
- ✅ Valor comercial ≤ 2x avalúo catastral
- ✅ Incrementos limitados al IPC (5.20% para 2025)

**Algoritmo de Valoración:**
```
Precio Base = min(Avalúo Catastral × 2 × 0.01, Valor Comercial × 0.01)
Precio Ajustado = Precio Base × Factor(ubicación, área, servicios, estado)
Rango Aceptable = Precio Ajustado ± 15%
```

**Sistema de Alertas:**
- 🟢 Verde: Precio justo dentro del rango
- 🟡 Amarillo: 15-30% sobre mercado
- 🔴 Rojo: >30% sobrevalorado

### 3. Infraestructura de Smart Contracts 🔗

**Contratos Principales:**
- `RentalRegistry.sol` - Registro de contratos y pagos automáticos
- `ScoreManager.sol` - Gestión de reputación y puntajes
- `PaymentManager.sol` - Pagos en cCOP con escrow
- `PriceOracle.sol` - Integración con datos externos
- `KYCManager.sol` - Verificación con Self credentials
- `DisputeResolution.sol` - Arbitraje descentralizado

### 4. KYC Descentralizado con Self 🔐

**Niveles de Verificación:**

| Nivel | Requisitos | Acceso |
|-------|------------|--------|
| **Basic** | Cédula + Selfie | Ver inmuebles, contactar |
| **Standard** | + Ingresos verificados | Aplicar hasta 2M COP/mes |
| **Premium** | + Referencias + Score | Propiedades premium, depósitos reducidos |

**Datos Compartidos:** Solo pruebas criptográficas, NO datos personales raw

## ✨ Características Principales

### Para Arrendatarios
- 🎖️ **Reputación Portable**: Historial que te sigue entre propiedades
- 💰 **Descuentos por Buen Score**: 0.5-2% de reducción en canon
- 🚀 **Acceso Preferencial**: Prioridad en mejores inmuebles
- 🎫 **NFT "Inquilino Confiable"**: Badge verificable
- 📱 **Pagos Automáticos**: Débito mensual en cCOP sin fricción

### Para Arrendadores
- ✅ **Verificación Instantánea**: Historial completo del arrendatario
- 💸 **Reducción de Costos**: 2-3% vs 8-10% tradicional
- 🔒 **Depósitos Protegidos**: Smart contract escrow automático
- ⚡ **Cobro Garantizado**: Ejecución automática de pagos
- 📊 **Analytics de Mercado**: Dashboard con insights de precios

### Para el Ecosistema
- 🌐 **Transparencia Total**: Datos de mercado públicos y verificables
- 🏛️ **Cumplimiento Normativo**: Aplicación automática de ley colombiana
- 🌱 **Inclusión Financiera**: Acceso para trabajadores informales
- ♻️ **ReFi Alignment**: Impacto social + sostenibilidad

## 🏗️ Arquitectura Técnica

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
│  ├─ Catastro API (avalúo oficial)        │
│  ├─ DANE (IPC actualizado)               │
│  ├─ Datacrédito/TransUnion (score)       │
│  └─ Crowdsourced Market Data             │
└──────────────────────────────────────────┘
```

### Stack Tecnológico

**Blockchain Layer:**
- Celo Mainnet (low fees)
- Solidity 0.8.x (Smart contracts)
- Foundry (Development environment)
- OpenZeppelin (Audited contract libraries)

**Frontend:**
- Next.js 15 - React framework
- TypeScript - Type safety
- Tailwind CSS - Styling
- Reown AppKi - Wallet connection
- Wagmit - React hooks for Ethereum
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

## 💼 Modelo de Negocio

### Fuentes de Ingreso

**1. Comisiones por Transacción (70% de ingresos)**
- 2.5% sobre pagos mensuales de arriendo
- Distribución: 1.5% tesorería, 0.5% validadores, 0.5% liquidez

**2. Servicios Premium (15%)**
- KYC Express 24h: 50,000 COP
- Verificación Profunda: 80,000 COP
- Certificación de Inmueble: 150,000 COP
- Seguro de Daños: 2% del depósito

**3. Marketplace (10%)**
- Anuncios destacados: 100,000 COP/mes
- Dashboard Analytics: 50,000 COP/mes
- API White-label B2B: desde 5M COP/año

**4. Resolución de Disputas (5%)**
- 3% sobre montos disputados (paga quien pierde)

### Economics por Contrato

```
Arriendo Promedio:     1,200,000 COP/mes
Comisión ArriendaChain:   30,000 COP/mes
Duración promedio:     12 meses
──────────────────────────────────────
LTV por contrato:        360,000 COP
CAC:                      50,000 COP
Margen Bruto:                   86%
Payback Period:          1.7 meses
```

### Proyecciones de Crecimiento

| Año | Contratos Activos | Ingresos Anuales |
|-----|-------------------|------------------|
| 2025 | 1,000 | 360M COP ($90K) |
| 2026 | 10,000 | 3.6B COP ($900K) |
| 2027 | 50,000 | 18B COP ($4.5M) |

**Impacto Social:** 10% de fees destinados a vivienda social

## 🗓️ Roadmap

### Q1 2025 - Foundation ✅ (In Progress)
- [x] Investigación de mercado y validación
- [x] Arquitectura técnica definida
- [x] Registro del proyecto en Karma GAP
- [ ] Desarrollo de Smart Contracts v1
- [ ] Integración Self KYC (testnet)
- [ ] Frontend MVP básico
- [ ] Deploy en Celo Alfajores (testnet)

### Q2 2025 - MVP Launch 🚀
- [ ] Auditoría de seguridad (CertiK/OpenZeppelin)
- [ ] Mainnet deployment
- [ ] Programa piloto con 10 propiedades en Medellín
- [ ] Integración cCOP payment rails
- [ ] Dashboard de analytics v1
- [ ] Onboarding de 50 usuarios beta
- [ ] Aplicación a grants (Celo Camp, Gitcoin)

### Q3 2025 - Scale & Iterate 📈
- [ ] Expansión a Bogotá y Cali
- [ ] Integración con Datacrédito/TransUnion
- [ ] Oracle de precios con ML predictions
- [ ] Mobile PWA optimizado
- [ ] 500 contratos activos
- [ ] Pre-seed fundraising ($200-300K)
- [ ] Contratación de equipo (3 devs, 1 marketing)

### Q4 2025 - Market Fit 🎯
- [ ] 2,000+ contratos activos
- [ ] Lanzamiento de token $ARRIENDO (governance)
- [ ] DAO para resolución de disputas
- [ ] Partnerships con PropTech tradicionales
- [ ] API pública para desarrolladores
- [ ] Expansión a 5 ciudades colombianas

### 2026 - Regional Expansion 🌎
- [ ] Lanzamiento en México, Argentina, Chile
- [ ] Integración con programas de vivienda gubernamentales
- [ ] 50,000+ usuarios activos
- [ ] Seed Round ($1-2M)
- [ ] Licencias regulatorias en múltiples países

## 🛠️ Tecnologías

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
    "web3": "wagmi ^2.0 + Reown AppKi"
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

## 🚀 Comenzar

### Prerequisites

```bash
node >= 18.0.0
npm >= 9.0.0
git
```

### Instalación Local

```bash
# Clonar repositorio
git clone https://github.com/viktorhugo/ArriendaChain.git
cd ArriendaChain

# Instalar dependencias
npm install

# Configurar variables de entorno
cp .env.example .env.local
# Editar .env.local con tus API keys

# Iniciar nodo local de desarrollo
npx hardhat node

# Deploy contracts a local
npx hardhat run scripts/deploy.js --network localhost

# Iniciar frontend
npm run dev
```

Accede a `http://localhost:3000`

### Testing

```bash
# Tests de smart contracts
npx hardhat test

# Coverage
npx hardhat coverage

# Tests de frontend
npm run test

# Tests E2E
npm run test:e2e
```

### Deploy a Testnet (Alfajores)

```bash
# Compilar contratos
npx hardhat compile

# Deploy
npx hardhat run scripts/deploy.js --network alfajores

# Verificar en explorer
npx hardhat verify --network alfajores DEPLOYED_CONTRACT_ADDRESS
```

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Por favor lee nuestro [CONTRIBUTING.md](CONTRIBUTING.md) para detalles sobre el proceso.

### Áreas de Contribución

- 🔧 **Smart Contracts**: Mejoras de eficiencia, nuevas features
- 🎨 **Frontend**: UI/UX, responsive design, accessibility
- 📊 **Data Science**: Algoritmos de pricing, ML models
- 📝 **Documentation**: Traducciones, tutoriales, guías
- 🐛 **Testing**: Unit tests, integration tests, audits
- 🌐 **Community**: Marketing, education, partnerships

### Código de Conducta

Este proyecto adhiere al [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md).

## 👥 Equipo

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

## 📞 Contacto

- **Website**: [arriendachain.com](https://arriendachain.com) (coming soon)
- **Email**: contact@arriendachain.com
- **Twitter**: [@ArriendaChain](https://twitter.com/ArriendaChain)
- **Discord**: [Join our community](https://discord.gg/arriendachain)
- **Karma GAP**: [Project Profile](https://gap.karmahq.xyz/)

## 📄 Licencia

Este proyecto está licenciado bajo MIT License - ver [LICENSE](LICENSE) para detalles.

## 🙏 Agradecimientos

- **Celo Foundation** - Por el ecosistema ReFi y soporte técnico
- **Self Protocol** - Por infraestructura de identidad descentralizada
- **OpenZeppelin** - Por contracts auditados y seguros
- **Colombian Blockchain Community** - Por feedback y validación

---

**⚠️ Disclaimer**: ArriendaChain está en desarrollo activo. Los smart contracts no han sido auditados. Usar en mainnet bajo tu propio riesgo hasta auditoría completa.

**🌱 Built with 💚 for Colombia's housing future / Cappy**
