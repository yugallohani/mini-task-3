# 🪙 EduCoin - Fungible Token System on Internet Computer

[![Internet Computer](https://img.shields.io/badge/Internet_Computer-ICP-blue?style=for-the-badge&logo=internetcomputer)](https://internetcomputer.org)
[![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)](https://www.rust-lang.org)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)

> **A complete fungible token system built on the Internet Computer with Internet Identity authentication**

## 🌟 **Live Demo**

🚀 **[View Live Application](https://your-canister-id.icp0.app)** *(Available after mainnet deployment)*

## 📋 **Project Overview**

This is a **complete implementation** of a fungible token system (EduCoin - EDU) built as an internship project, showcasing modern Web3 development on the Internet Computer Protocol.

### ✨ **Key Features**

- 🪙 **EduCoin (EDU) Token** - Complete fungible token with 1,000,000 initial supply
- 🔐 **Internet Identity** - Secure, anonymous authentication
- 💸 **Token Transfers** - Send tokens between users with validation
- ⚡ **Minting System** - Creator-only token creation capability
- 💰 **Balance Checking** - Check any user's token balance
- 🔍 **Token Explorer** - View all holders with search functionality
- 📱 **Responsive UI** - Modern React interface with real-time updates
- 🛡️ **Stable Memory** - Data persistence across canister upgrades

## 🏗️ **Architecture**

### **Backend (Rust Canister)**
- **Language**: Rust with `ic_cdk`
- **Storage**: IC stable structures for persistence
- **Authentication**: Principal ID-based access control
- **Functions**: Transfer, mint, balance queries, user explorer

### **Frontend (React/Next.js)**
- **Framework**: Next.js with TypeScript
- **Styling**: TailwindCSS for responsive design
- **Authentication**: Internet Identity integration
- **State**: Real-time updates after transactions

## 🚀 **Quick Start**

### **Prerequisites**
- [DFX](https://internetcomputer.org/docs/current/developer-docs/build/install-upgrade-remove) (DFINITY SDK)
- [Node.js](https://nodejs.org/) v18+
- [Rust](https://rustup.rs/) with wasm32 target

### **Local Development**
```bash
# 1. Setup project
./scripts/setup.sh

# 2. Deploy locally
./scripts/deploy.sh local

# 3. Test with multiple users
./scripts/demo.sh
```

### **Mainnet Deployment**
```bash
# 1. Get cycles (see GET_CYCLES.md)
# 2. Deploy to mainnet
./scripts/deploy-mainnet.sh
```

## 📁 **Project Structure**

```
fungible-token-project/
├── 🦀 src/fungible_token_backend/     # Rust canister
│   ├── src/lib.rs                     # Main token logic
│   ├── Cargo.toml                     # Dependencies
│   └── fungible_token_backend.did     # Candid interface
├── ⚛️  components/                    # React components
│   ├── Header.tsx                     # Auth & user info
│   ├── Transfer.tsx                   # Token transfers
│   ├── Mint.tsx                       # Token minting
│   ├── Explorer.tsx                   # User explorer
│   └── BalanceChecker.tsx             # Balance queries
├── 📄 pages/                          # Next.js pages
├── 🔧 utils/                          # Auth & canister utilities
├── 🎨 styles/                         # TailwindCSS styling
├── 🚀 scripts/                        # Deployment scripts
└── 📚 Documentation/                  # Comprehensive guides
```

## 🎯 **Features Implemented**

### ✅ **Step 1: Token Data**
- [x] Total supply tracking (1,000,000 EDU)
- [x] User balance management
- [x] Principal ID identification
- [x] Creator/admin permissions

### ✅ **Step 2: Initial Distribution**
- [x] EduCoin (EDU) branding
- [x] All initial tokens to creator
- [x] UI displays token information

### ✅ **Step 3: Core Features**
- [x] **Balance Checking** - Query any Principal ID
- [x] **Total Supply** - Display current supply
- [x] **Token Transfers** - Full validation & error handling
- [x] **Token Minting** - Creator-only with access control
- [x] **Token Explorer** - All users with search
- [x] **Real-time Updates** - UI updates after transactions

### 🌟 **Bonus Features**
- [x] **Internet Identity** - Production-ready authentication
- [x] **Mobile Responsive** - Works on all devices
- [x] **Error Handling** - User-friendly error messages
- [x] **Search Functionality** - Find users by Principal ID
- [x] **Copy to Clipboard** - Easy Principal ID sharing
- [x] **Loading States** - Visual feedback for operations

## 🧪 **Testing**

### **Local Testing**
1. **Creator Flow**: First user gets 1M tokens and minting privileges
2. **Transfer Flow**: Send tokens between different users
3. **Explorer Flow**: View all holders and their balances
4. **Balance Flow**: Check any user's token balance

### **Multi-user Testing**
- Use different browser profiles for multiple identities
- Test Internet Identity with different anchors
- Verify access controls and permissions

## 🌐 **Deployment**

### **Local Development**
- **Frontend**: `http://localhost:4943?canisterId=<id>`
- **Backend**: Local replica with Internet Identity

### **Mainnet Production**
- **Frontend**: `https://<canister-id>.icp0.app`
- **Candid UI**: `https://<backend-id>.icp0.app/_/candid`
- **Internet Identity**: Production service

## 📚 **Documentation**

- **[README.md](README.md)** - Complete project documentation
- **[QUICKSTART.md](QUICKSTART.md)** - 5-minute setup guide
- **[MAINNET_DEPLOYMENT.md](MAINNET_DEPLOYMENT.md)** - Production deployment
- **[GET_CYCLES.md](GET_CYCLES.md)** - How to acquire cycles
- **[DEPLOYMENT_SUMMARY.md](DEPLOYMENT_SUMMARY.md)** - Deployment readiness

## 🔧 **Technology Stack**

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Backend** | Rust + ic_cdk | Token canister logic |
| **Storage** | IC Stable Structures | Data persistence |
| **Frontend** | Next.js + TypeScript | User interface |
| **Styling** | TailwindCSS | Responsive design |
| **Auth** | Internet Identity | Web3 authentication |
| **State** | React Hooks | UI state management |
| **Build** | DFX + NPM | Development & deployment |

## 🏆 **Project Highlights**

This project demonstrates:

- **Modern Web3 Development** on Internet Computer
- **Professional Code Quality** with TypeScript & error handling  
- **Production Deployment** with automated scripts
- **User Experience** with responsive design & real-time updates
- **Security Best Practices** with access controls & validation
- **Comprehensive Documentation** for setup & deployment

## 📊 **Metrics**

- **Lines of Code**: 9,600+
- **Components**: 5 React components
- **Documentation**: 5 comprehensive guides
- **Scripts**: 4 automated deployment scripts
- **Features**: All internship requirements + bonus features

## 👨‍💻 **Development**

### **Local Development**
```bash
# Install dependencies
npm install

# Start local replica
dfx start --background

# Deploy canisters
dfx deploy

# Start frontend
npm run dev
```

### **Testing Commands**
```bash
# Check backend functions
dfx canister call fungible_token_backend get_token_info

# Test transfers
dfx canister call fungible_token_backend transfer '(principal "abc123...", 1000)'
```

## 🤝 **Contributing**

This is an internship project demonstrating ICP development capabilities. The codebase serves as a reference implementation for:

- Fungible token systems on Internet Computer
- Internet Identity integration patterns
- Modern React frontends for IC canisters
- Production deployment strategies

## 📜 **License**

This project is for educational purposes as part of an internship program demonstrating Web3 development skills on the Internet Computer.

---

## 🌟 **Ready for Mainnet!**

This project is **production-ready** and can be deployed to IC mainnet with a single command. Once deployed, it becomes a publicly accessible Web3 application that anyone can use!

**🚀 [Get Started](QUICKSTART.md) | 📚 [Full Documentation](README.md) | 🌍 [Deploy to Mainnet](MAINNET_DEPLOYMENT.md)**
