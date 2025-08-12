# 💰 **HOW TO GET CYCLES FOR MAINNET DEPLOYMENT**

You need cycles to deploy to the Internet Computer mainnet. Here's how to get them:

## 🎯 **QUICK SUMMARY**

- **Cycles needed**: ~1-2 trillion cycles (1-2 TC)
- **Cost**: Approximately $1-2 USD worth of ICP
- **Time**: 10-30 minutes to acquire and convert

## 🔄 **METHOD 1: BUY ICP AND CONVERT TO CYCLES (RECOMMENDED)**

### Step 1: Buy ICP
Buy ICP tokens on any major exchange:
- **Coinbase** (easiest for US users)
- **Binance**
- **Kraken**
- **Huobi**

*Amount needed: ~$2-5 USD worth of ICP*

### Step 2: Get Your DFX Principal Address
```bash
dfx identity get-principal
```
Copy this principal ID - this is your "wallet address" for ICP.

### Step 3: Send ICP to Your Principal
1. In your exchange, withdraw ICP
2. Paste your principal ID as the destination address
3. Send minimum 0.1 ICP (more is safer)

### Step 4: Check ICP Balance
```bash
export DFX_WARNING=-mainnet_plaintext_identity
dfx ledger --network ic balance
```

### Step 5: Convert ICP to Cycles
```bash
# Convert 0.5 ICP to cycles (should be plenty)
dfx cycles convert --amount 0.5 --network ic
```

### Step 6: Verify Cycles Balance
```bash
dfx cycles balance --network ic
```

You should see something like "0.5 TC" or more.

## 🎁 **METHOD 2: FREE CYCLES (LIMITED)**

### DFINITY Faucet (if available)
```bash
# Check if faucet is available
# Visit: https://faucet.dfinity.org/
```

*Note: Free faucets are often limited and may not always be available.*

### Developer Grants
If you're building something significant, you might qualify for:
- **DFINITY Developer Grants**
- **Internet Computer Ecosystem Fund**

## 💡 **COST BREAKDOWN**

### Deployment Costs (approximate):
- **Backend canister creation**: ~0.1 TC
- **Frontend canister creation**: ~0.1 TC
- **Backend deployment**: ~0.2 TC
- **Frontend deployment**: ~0.2 TC
- **Buffer for operations**: ~0.4 TC

**Total needed**: ~1 TC (costs about $1 USD)

### Ongoing Costs:
- **Query calls**: Free
- **Update calls**: ~0.0000001 TC each
- **Storage**: ~0.127 TC per GB per year
- **Compute**: ~0.0000004 TC per instruction

*Your token system will cost pennies per month to run!*

## ⚡ **QUICK START COMMANDS**

Once you have cycles:

```bash
# 1. Set environment
export DFX_WARNING=-mainnet_plaintext_identity

# 2. Check you have cycles
dfx cycles balance --network ic

# 3. Run automated deployment
./scripts/deploy-mainnet.sh
```

## 🔧 **TROUBLESHOOTING**

### "Insufficient balance" when converting
```bash
# Check your ICP balance first
dfx ledger --network ic balance

# You need at least 0.0001 ICP to convert
# Get more ICP from exchange if needed
```

### "No wallet configured" error
```bash
# Create a cycles wallet
dfx cycles create --network ic
```

### Can't find your principal
```bash
# Make sure you're using the correct identity
dfx identity whoami
dfx identity get-principal
```

## 🎯 **AFTER GETTING CYCLES**

Once you have 1+ TC, you can:

1. **Deploy to mainnet**: `./scripts/deploy-mainnet.sh`
2. **Get your public URL**: `https://<canister-id>.icp0.app`
3. **Share with the world**: Your app is live on Web3!

## 💰 **CYCLES MANAGEMENT TIPS**

### Monitor Usage:
```bash
# Check remaining cycles
dfx cycles balance --network ic

# Check canister status
dfx canister --network ic status fungible_token_backend
dfx canister --network ic status fungible_token_frontend
```

### Top Up When Needed:
```bash
# Add more cycles from your balance
dfx canister --network ic deposit-cycles 100000000000 fungible_token_backend
```

## 🌟 **ESTIMATED TIMELINE**

- **Exchange account setup**: 5-30 minutes
- **ICP purchase**: 1-10 minutes  
- **ICP transfer**: 5-30 minutes
- **Cycle conversion**: 1 minute
- **Deployment**: 5-10 minutes

**Total**: 15-80 minutes from start to live deployment!

---

**🎉 Once you have cycles, your EduCoin token system will be live on the Internet Computer for the world to use!**
