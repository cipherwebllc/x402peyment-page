# X402 Payment Page

Web3 wallet-connect payment page for X402 payment system.

## Pricing Plans

### USDC (Base Mainnet)
| Plan | Price | Description |
|------|-------|-------------|
| 🎫 Single | 0.1 USDC | 1 time use |
| 📅 Daily | 1 USDC | 30 uses per day |
| ⭐ Pro | 9 USDC | 30 days unlimited (準備中) |

### JPYC (Polygon Mainnet)
| Plan | Price | Description |
|------|-------|-------------|
| 🎫 Single | 15 JPYC | 1 time use |
| 📅 Daily | 150 JPYC | 30 uses per day |
| ⭐ Pro | 1500 JPYC | 30 days unlimited (準備中) |

> **Note:** Pro plan is currently in preparation and will be available after Postgres integration.

## Features

- 🦊 **MetaMask Integration** - One-click wallet connection
- 🔄 **Auto Network Switch** - Automatically switches to Base or Polygon
- 💳 **Multiple Plans** - Choose from Single, Daily, or Pro plans
- 💱 **Dual Currency** - Pay with USDC (Base) or JPYC (Polygon)
- ✅ **Transaction Verification** - Real-time confirmation
- 📱 **Responsive Design** - Works on desktop and mobile
- 🎨 **Beautiful UI** - Modern gradient design

## Deployment

### Option 1: Vercel (Recommended)

1. **Install Vercel CLI:**
   ```bash
   npm i -g vercel
   ```

2. **Deploy:**
   ```bash
   cd payment-page
   vercel --prod
   ```

3. **Copy the URL:**
   ```
   https://your-project-name.vercel.app
   ```

4. **Set environment variable in Railway:**
   ```bash
   PAYMENT_PAGE_URL=https://your-project-name.vercel.app
   ```

### Option 2: Netlify

1. **Install Netlify CLI:**
   ```bash
   npm i -g netlify-cli
   ```

2. **Deploy:**
   ```bash
   cd payment-page
   netlify deploy --prod
   ```

3. **Copy the URL and set in Railway**

### Option 3: GitHub Pages

1. **Create a new repository** (e.g., `x402-payment`)

2. **Push payment page:**
   ```bash
   cd payment-page
   git init
   git add .
   git commit -m "Initial payment page"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/x402-payment.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to repository Settings
   - Pages → Source: main branch
   - Wait for deployment

4. **Copy URL:** `https://YOUR_USERNAME.github.io/x402-payment/`

## Configuration

### Smart Contract Addresses

**Base Mainnet (USDC)**
- **USDC Contract:** `0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913`
- **Network:** Base Mainnet (Chain ID: 8453)

**Polygon Mainnet (JPYC)**
- **JPYC Contract:** `0x431D5dfF03120AFA4bDf332c61A6e1766eF37BDB`
- **Network:** Polygon Mainnet (Chain ID: 137)

**Common**
- **Receiver Address:** `0x52d4901142e2b5680027da5eb47c86cb02a3ca81`

### Customization

Edit `index.html` to customize:
- Colors and styling (CSS variables)
- Contract addresses
- Payment amount
- Network settings

## Usage

1. **Get Base ETH:**
   - Bridge ETH to Base via https://bridge.base.org/
   - Or purchase from an exchange that supports Base

2. **Get USDC on Base:**
   - Bridge USDC to Base or use an exchange

3. **Make Payment:**
   - Open: `index.html?user=YOUR_USER_ID`
   - Or with preset: `index.html?user=YOUR_USER_ID&currency=jpyc&plan=pro`
   - Available currencies: `usdc`, `jpyc`
   - Available plans: `single`, `daily`, `pro`
   - Select currency, plan and connect MetaMask
   - Send payment
   - Verify transaction on https://basescan.org/ or https://polygonscan.com/

## How It Works

1. User opens payment page with `?user=USER_ID` parameter
2. Clicks "Connect MetaMask"
3. MetaMask prompts to switch to Base Mainnet (if needed)
4. User clicks "Send 0.1 USDC"
5. MetaMask confirms transaction
6. Page shows success message
7. User returns to Discord/chat
8. Sends transaction hash or "支払いました"
9. Bot verifies payment on blockchain
10. User receives credit

## Security

- ✅ No private keys stored
- ✅ Client-side only (no backend)
- ✅ User controls wallet connection
- ✅ Transaction signed by user's wallet
- ✅ Verified on blockchain

## Troubleshooting

**"Please install MetaMask"**
- Install MetaMask browser extension

**"Please switch to Base Mainnet"**
- Allow MetaMask to switch networks automatically
- Or manually add Base network

**"Transaction failed"**
- Check you have enough ETH for gas
- Check you have at least 0.1 USDC
- Try again with higher gas

## License

MIT
