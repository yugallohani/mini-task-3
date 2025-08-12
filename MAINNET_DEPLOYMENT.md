# 🌍 **MAINNET DEPLOYMENT GUIDE**

Complete step-by-step guide to deploy your EduCoin token system to IC mainnet.

## 🔑 **PREREQUISITES**

### 1. Get Cycles for Deployment
You need cycles to deploy to mainnet. Here are your options:

**Option A: Free Cycles (Limited)**
```bash
# Get free cycles from DFINITY faucet (if available)
# Visit: https://faucet.dfinity.org/
```

**Option B: Buy ICP and Convert to Cycles**
```bash
# 1. Buy ICP on exchange (Coinbase, Binance, etc.)
# 2. Send to your DFX principal
# 3. Convert ICP to cycles
dfx cycles convert --amount 1.0 --network ic
```

**Check your cycles balance:**
```bash
export DFX_WARNING=-mainnet_plaintext_identity
dfx cycles balance --network ic
```

*You need approximately 1-2 trillion cycles (TC) for initial deployment.*

## 🚀 **DEPLOYMENT STEPS**

### Step 1: Set Environment Variable
```bash
export DFX_WARNING=-mainnet_plaintext_identity
```

### Step 2: Create Canisters on Mainnet
```bash
dfx canister create --network ic fungible_token_backend
dfx canister create --network ic fungible_token_frontend
```

### Step 3: Build for Production
```bash
dfx build --network ic
```

### Step 4: Deploy Backend Canister
```bash
dfx deploy --network ic fungible_token_backend
```

### Step 5: Update Environment Variables
```bash
# Get backend canister ID and update production env
BACKEND_CANISTER_ID=$(dfx canister --network ic id fungible_token_backend)
echo "NEXT_PUBLIC_CANISTER_ID_FUNGIBLE_TOKEN_BACKEND=$BACKEND_CANISTER_ID" > .env.production
echo "NEXT_PUBLIC_INTERNET_IDENTITY_CANISTER_ID=rdmx6-jaaaa-aaaah-qdrqq-cai" >> .env.production
```

### Step 6: Build Frontend for Production
```bash
NODE_ENV=production npm run build
```

### Step 7: Deploy Frontend Canister
```bash
dfx deploy --network ic fungible_token_frontend
```

### Step 8: Get Your URLs
```bash
FRONTEND_CANISTER_ID=$(dfx canister --network ic id fungible_token_frontend)
BACKEND_CANISTER_ID=$(dfx canister --network ic id fungible_token_backend)

echo "Frontend URL: https://$FRONTEND_CANISTER_ID.icp0.app"
echo "Candid UI: https://$BACKEND_CANISTER_ID.icp0.app/_/candid"
```

## 🎯 **AUTOMATED DEPLOYMENT**

Use the provided script for automated deployment:

```bash
./scripts/deploy-mainnet.sh
```

## 🔄 **REDEPLOYMENT COMMANDS**

For future updates:

**Backend only:**
```bash
dfx deploy --network ic fungible_token_backend
```

**Frontend only:**
```bash
NODE_ENV=production npm run build
dfx deploy --network ic fungible_token_frontend
```

**Both canisters:**
```bash
dfx deploy --network ic
```

## 🛡️ **STABLE CANISTER IDS**

Your canister IDs will be stored in:
- `.dfx/ic/canister_ids.json` (auto-generated)
- `canister_ids.json` (manual backup)

This ensures redeployments maintain the same canister IDs.

## 🧪 **TESTING ON MAINNET**

### Frontend Testing
1. Open your frontend URL: `https://<canister-id>.icp0.app`
2. Login with Internet Identity (uses production II service)
3. First user becomes the token creator with 1M EDU tokens
4. Test all functionality: transfers, minting, balance checking

### Backend Testing
1. Open Candid UI: `https://<backend-canister-id>.icp0.app/_/candid`
2. Test individual canister methods
3. Verify all functions work correctly

## 🌐 **INTERNET IDENTITY CONFIGURATION**

Your app automatically uses the correct Internet Identity service:

- **Local development**: `http://localhost:4943?canisterId=rdmx6-jaaaa-aaaah-qdrqq-cai`
- **Production**: `https://identity.ic0.app`

No additional configuration needed!

## 🔧 **TROUBLESHOOTING**

### "Insufficient cycles" error
```bash
# Check balance
dfx cycles balance --network ic

# Add more cycles (convert from ICP)
dfx cycles convert --amount 1.0 --network ic
```

### "Canister not found" error
```bash
# Recreate canisters
dfx canister create --network ic fungible_token_backend
dfx canister create --network ic fungible_token_frontend
```

### Frontend not loading
```bash
# Check canister ID is correct
dfx canister --network ic id fungible_token_frontend

# Verify environment variables
cat .env.production
```

### Backend communication issues
```bash
# Check canister is running
dfx canister --network ic status fungible_token_backend

# Test with Candid UI
open "https://$(dfx canister --network ic id fungible_token_backend).icp0.app/_/candid"
```

## 📋 **POST-DEPLOYMENT CHECKLIST**

- [ ] Frontend loads at `https://<canister-id>.icp0.app`
- [ ] Internet Identity login works
- [ ] Token creator gets 1,000,000 EDU tokens
- [ ] Transfer functionality works
- [ ] Mint functionality works (creator only)
- [ ] Balance checker works
- [ ] Token explorer displays correctly
- [ ] Candid UI accessible and functional
- [ ] All error handling works properly

## 🎉 **SUCCESS INDICATORS**

Your deployment is successful when:

✅ **Frontend URL is publicly accessible**
✅ **Internet Identity login works on mainnet**
✅ **First user becomes token creator**
✅ **All token operations work correctly**
✅ **UI updates in real-time after transactions**
✅ **Multiple users can interact with the system**
✅ **Candid UI shows all backend methods**

## 🚀 **SHARING YOUR APPLICATION**

Once deployed, you can share your frontend URL publicly:
```
https://<your-canister-id>.icp0.app
```

Users can:
- Access without any setup
- Login with their Internet Identity
- Interact with your token system
- Transfer tokens between accounts
- View the token explorer

Your EduCoin token system will be live on the Internet Computer mainnet! 🌟
