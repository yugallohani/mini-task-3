# 🚀 QuickStart Guide - EduCoin Token System

Get your fungible token system up and running in 5 minutes!

## ⚡ Super Quick Start

```bash
# 1. Setup (run once)
./scripts/setup.sh

# 2. Deploy locally
./scripts/deploy.sh local

# 3. Demo the system
./scripts/demo.sh
```

## 📋 Prerequisites Check

Make sure you have these installed:
- ✅ [DFX](https://internetcomputer.org/docs/current/developer-docs/build/install-upgrade-remove) (dfinity SDK)
- ✅ [Node.js](https://nodejs.org/) v18+
- ✅ [Rust](https://rustup.rs/) with wasm32 target

**Quick install check:**
```bash
dfx --version && node --version && rustc --version
```

## 🎯 What You Get

After deployment, you'll have:

### 🏦 Token System
- **EduCoin (EDU)** fungible token
- **1,000,000** initial supply
- **Creator permissions** for minting
- **Transfer functionality** between users

### 🔐 Authentication
- **Internet Identity** login
- **Principal ID** based user system
- **Secure** and **anonymous**

### 💻 Modern UI
- **Responsive** design
- **Real-time** updates
- **Error handling**
- **TailwindCSS** styling

## 🌍 Deployment Options

### Local Development
```bash
./scripts/deploy.sh local
```
- Runs on local Internet Computer replica
- Perfect for development and testing
- Fast deployment and iteration

### Production (IC Mainnet)
```bash
./scripts/deploy.sh ic
```
- Deploys to Internet Computer mainnet
- Requires ICP tokens for deployment
- Globally accessible via ic0.app

## 🎭 Testing Scenarios

Use `./scripts/demo.sh` for guided testing with:
- **Multiple users** (different browser profiles)
- **Creator privileges** (minting tokens)
- **Transfer testing** between accounts
- **Balance checking** and **explorer**

## 📁 Project Structure

```
fungible-token-project/
├── src/fungible_token_backend/  # Rust canister
├── components/                  # React components
├── pages/                       # Next.js pages
├── utils/                       # Authentication & API
├── types/                       # TypeScript types
├── scripts/                     # Deployment scripts
└── README.md                    # Full documentation
```

## 🔧 Key Features Implemented

### ✅ Step 1: Token Data
- [x] Total supply tracking
- [x] User balance management
- [x] Principal ID based identification
- [x] Creator/admin permissions

### ✅ Step 2: Initial Distribution
- [x] 1M tokens to creator
- [x] EduCoin (EDU) branding
- [x] UI displays token info

### ✅ Step 3: Core Features
- [x] **Balance checking** - any Principal ID
- [x] **Total supply** display
- [x] **Transfer tokens** with validation
- [x] **Mint tokens** (creator only)
- [x] **Token explorer** with user list
- [x] **Real-time UI** updates

### ✅ Advanced Features
- [x] **Internet Identity** authentication
- [x] **Stable memory** persistence
- [x] **Access control** (creator-only minting)
- [x] **Error handling** with user feedback
- [x] **Responsive design**
- [x] **Search functionality**
- [x] **Production deployment** ready

## 🌟 URLs After Deployment

### Local Development
```
Frontend: http://localhost:4943?canisterId={frontend-id}
```

### Production
```
Frontend: https://{frontend-id}.ic0.app
```

## 💡 Pro Tips

1. **Multiple Users**: Use different browser profiles for testing
2. **Principal IDs**: Copy/paste to avoid typos
3. **Creator Status**: First user to access becomes creator
4. **Real-time Updates**: UI updates automatically after transactions
5. **Error Messages**: Check browser console for detailed errors

## 🆘 Need Help?

- **Full docs**: See `README.md`
- **Troubleshooting**: Common issues covered in README
- **Demo guide**: Run `./scripts/demo.sh`
- **Setup issues**: Run `./scripts/setup.sh` to check prerequisites

## 🎉 Success Indicators

You know it's working when:
- ✅ Login with Internet Identity works
- ✅ Token explorer shows creator with 1M tokens
- ✅ Transfers work between users
- ✅ Minting only works for creator
- ✅ Balance checking works for any Principal ID
- ✅ Real-time UI updates after transactions

---

**Ready to launch? Run `./scripts/deploy.sh local` and start exploring!** 🚀
