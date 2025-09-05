# NexaVault - Next-Generation Asset Tokenization Protocol

![Stacks](https://img.shields.io/badge/Stacks-Clarity-5546FF)
![Bitcoin](https://img.shields.io/badge/Bitcoin-Secured-F7931A)
![License](https://img.shields.io/badge/license-MIT-green)

## Overview

NexaVault pioneers the future of digital asset management by creating a comprehensive ecosystem where traditional and digital assets converge through advanced tokenization, intelligent staking mechanisms, and community-driven governance on Bitcoin's unbreakable foundation.

Built on Stacks to leverage Bitcoin's security while enabling sophisticated smart contract functionality, NexaVault transforms static digital assets into dynamic, yield-generating instruments.

## 🚀 Core Innovation Pillars

- **Collateral-Backed Asset Tokenization** - Bitcoin-level security guarantees
- **Dynamic Fractional Ownership** - Democratized investment opportunities  
- **Intelligent Yield Generation** - Automated staking and reward distribution
- **Zero-Gas Decentralized Trading** - Built-in protocol revenue mechanisms
- **Enterprise-Grade Security** - Multi-layered validation and overflow protection
- **Community-Driven Economics** - Transparent fee distribution and governance

## 🏗️ Architecture

### Protocol Constants

- **Minimum Collateral Ratio**: 150% (overcollateralized security)
- **Protocol Fee**: 2.5% (marketplace transactions)
- **Annual Yield Rate**: 5% (staking rewards)
- **Maximum URI Length**: 256 characters

### Core Data Structures

#### NFT Registry

Central hub for all tokenized assets containing:

- Asset ownership and metadata
- Collateral backing information
- Staking status and history
- Fractional share allocation

#### Marketplace Listings

Decentralized trading infrastructure:

- Asset pricing and availability
- Seller information and listing history
- Active/inactive status tracking

#### Ownership Ledger

Fractional ownership management:

- Share distribution tracking
- Multi-holder asset support
- Transfer history and validation

#### Yield Tracker

Intelligent reward distribution:

- Accumulated rewards calculation
- Claim history and timestamps
- Total distributed analytics

## 🔧 Core Functions

### Asset Tokenization

#### `mint-bitcoin-nft`

Creates collateral-backed asset tokens secured by STX deposits.

```clarity
(mint-bitcoin-nft metadata-uri collateral-amount)
```

**Parameters:**

- `metadata-uri`: Asset metadata location (max 256 chars)
- `collateral-amount`: Base asset value for collateral calculation

**Security Features:**

- 150% overcollateralization requirement
- URI validation and length limits
- Automatic escrow of collateral funds

#### `transfer-ownership`

Executes secure asset ownership transfers with multi-layer validation.

```clarity
(transfer-ownership token-id new-owner)
```

### Marketplace Operations

#### `create-listing`

Lists assets for sale on the decentralized marketplace.

```clarity
(create-listing token-id asking-price)
```

#### `execute-purchase`

Performs atomic purchase transactions with automatic fee distribution.

```clarity
(execute-purchase token-id)
```

**Transaction Flow:**

1. Validates active listing status
2. Transfers payment to seller (minus protocol fee)
3. Transfers protocol fee to treasury
4. Updates asset ownership
5. Deactivates marketplace listing

### Fractional Ownership

#### `transfer-shares`

Enables fractional asset share transfers between holders.

```clarity
(transfer-shares token-id recipient share-amount)
```

**Security Validations:**

- Sufficient share balance verification
- Arithmetic overflow protection
- Recipient address validation

### Staking & Yield Generation

#### `stake-for-yield`

Activates asset staking to earn continuous yield rewards.

```clarity
(stake-for-yield token-id)
```

#### `release-stake`

Deactivates staking and claims final accumulated rewards.

```clarity
(release-stake token-id)
```

## 📊 Analytics & Queries

### Asset Information

```clarity
(get-nft-details token-id)           ;; Comprehensive asset data
(get-listing-details token-id)       ;; Marketplace listing info
(get-share-balance token-id holder)  ;; Fractional ownership data
(get-yield-status token-id)          ;; Staking and rewards status
```

### Reward Calculations

```clarity
(calculate-pending-rewards token-id) ;; Real-time reward calculation
(get-protocol-stats)                 ;; Global protocol analytics
```

## 🛡️ Security Features

### Input Validation

- **URI Validation**: Length and format verification
- **Price Validation**: Economic viability checks
- **Recipient Validation**: Address security verification
- **Overflow Protection**: Safe arithmetic operations

### Authorization Controls

- **Ownership Verification**: Multi-layer owner validation
- **Staking Status**: Prevents invalid state transitions
- **Balance Verification**: Ensures sufficient funds/shares

### Error Handling

Comprehensive error code architecture with specific error messages:

- `ERR_OWNER_ONLY` (u100)
- `ERR_NOT_TOKEN_OWNER` (u101)
- `ERR_INSUFFICIENT_BALANCE` (u102)
- `ERR_INVALID_TOKEN` (u103)
- `ERR_LISTING_NOT_FOUND` (u104)
- `ERR_INVALID_PRICE` (u105)
- `ERR_INSUFFICIENT_COLLATERAL` (u106)
- `ERR_ALREADY_STAKED` (u107)
- `ERR_NOT_STAKED` (u108)
- `ERR_INVALID_PERCENTAGE` (u109)
- `ERR_INVALID_URI` (u110)
- `ERR_INVALID_RECIPIENT` (u111)
- `ERR_OVERFLOW` (u112)

## 🚦 Getting Started

### Prerequisites

- [Clarinet](https://github.com/hirosystems/clarinet) - Stacks development environment
- [Stacks Wallet](https://www.hiro.so/wallet) - For mainnet interactions
- Node.js 16+ (for testing framework)

### Installation

```bash
# Clone the repository
git clone https://github.com/femi-bash/nexa-vault.git
cd nexa-vault

# Install dependencies
npm install

# Run contract checks
clarinet check

# Run tests
npm test
```

### Development Setup

```bash
# Start local development environment
clarinet integrate

# Console testing
clarinet console

# Deploy to testnet
clarinet deploy --testnet
```

## 🧪 Testing

The project includes comprehensive test coverage:

```bash
# Run all tests
npm test

# Run specific test file
npm test -- nexa-vault.test.ts

# Check contract syntax and types
clarinet check
```

### Test Coverage Areas

- Asset tokenization flows
- Marketplace operations
- Fractional ownership transfers
- Staking and yield distribution
- Security validations
- Error handling scenarios

## 📈 Economic Model

### Revenue Streams

1. **Marketplace Fees**: 2.5% on all asset sales
2. **Collateral Management**: Interest on locked collateral
3. **Premium Features**: Advanced analytics and tools

### Yield Distribution

- **Base Rate**: 5% annual yield for staked assets
- **Compound Growth**: Automatic reward reinvestment options
- **Treasury Backing**: Protocol fees fund reward distributions

### Tokenomics

- **Overcollateralization**: 150% minimum ratio ensures asset backing
- **Dynamic Pricing**: Market-driven asset valuations
- **Fee Distribution**: Sustainable protocol treasury growth

## 🛣️ Roadmap

### Phase 1: Core Protocol ✅

- [x] Asset tokenization with collateral backing
- [x] Decentralized marketplace
- [x] Basic staking and yield generation
- [x] Security validations and error handling

### Phase 2: Advanced Features 🚧

- [ ] Governance token implementation
- [ ] Advanced yield strategies
- [ ] Cross-chain asset support
- [ ] Institutional features

### Phase 3: Ecosystem Expansion 📋

- [ ] Mobile application
- [ ] Analytics dashboard
- [ ] Third-party integrations
- [ ] Enterprise partnerships

## 📚 Documentation

### Smart Contract Documentation

- [Contract Architecture](docs/architecture.md)
- [API Reference](docs/api.md)
- [Security Audit](docs/security.md)
- [Deployment Guide](docs/deployment.md)

### Developer Resources

- [Integration Guide](docs/integration.md)
- [Testing Framework](docs/testing.md)
- [Best Practices](docs/best-practices.md)

## 🤝 Contributing

We welcome contributions from the community! Please read our [Contributing Guide](CONTRIBUTING.md) for details on:

- Code of conduct
- Development workflow
- Submission guidelines
- Review process

### Development Workflow

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes and add tests
4. Ensure all tests pass (`npm test`)
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
