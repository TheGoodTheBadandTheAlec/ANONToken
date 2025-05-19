# ANONToken

**OG Ethereum Privacy Primitive · Fully Decentralized · No zk · Linea Native**

ANONToken is a censorship-resistant ERC-20 dApp deployed on the Linea Sepolia Testnet. It allows users to unlink their everyday wallet (like MetaMask) from real-world spending (e.g., MetaMask Card) by minting and burning a token. ETH is sent to a newly generated, anonymous wallet — no bridges, no relayers, no zk required.

> 🔗 **App:** [immense-honey-brief.on-fleek.app](https://immense-honey-brief.on-fleek.app)  
> 🧱 **Contract:** `0xAfEAE83BD71E44d4291E95D621B10f3d3ff29a28` (Linea Sepolia)

---

## 🔐 How It Works

### 1. Mint
- Send `0.00000001 ETH` (testnet price) to mint 1 ANON token.
- Tokens are standard ERC-20 and transferable.

### 2. Burn for Privacy
- Frontend generates a stealth address and private key (never leaves your browser).
- You sign a hash that binds wallet, burnId, contract, chainId, and entropy.
- ETH is sent to the stealth wallet after a randomized delay.

### 3. Receive
- When 50 users have burned, a user triggers the withdrawal processor.
- ETH is sent anonymously to your stealth address.
- You import your key to access the funds — unlinking identity from source wallet.

---

## 💡 Why ANONToken?

| Feature           | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **No zk Required** | No SNARKs, no relayers, no bridge logic — pure Ethereum-based unlinkability. |
| **Random Delays** | Withdrawals unlock between 1–12 hours later to break timing analysis.       |
| **Full Decentralization** | No admin keys, no upgrades — immutable code.                          |
| **Zero Protocol Fees** | 0% fee (on testnet) — only gas is paid.                                 |
| **Gas Pooling**   | Withdrawals are paid from a shared gas pool with overage refunds.           |
| **Self-Custody**  | Only you hold the stealth private key — full control, no servers.           |

---

## 🧪 Testnet Instructions

1. **Connect Wallet**
   - Use MetaMask or [Rabby Wallet (desktop)](https://rabby.io/)
   - Connect to **Linea Sepolia** testnet

2. **Mint Token**
   - Visit [the dApp](https://immense-honey-brief.on-fleek.app)
   - Click **"Mint 1 ANON"** to receive your token

3. **Burn Token**
   - Click **"Burn 1 ANON"**
   - A new private key is generated and saved as `.txt`
   - Burn request is queued for anonymous withdrawal

4. **Withdraw ETH**
   - Once 50 burns are submitted, a user triggers `processWithdrawals()`
   - ETH is sent to the stealth address
   - You import the key to spend it privately

---

## ⚙️ Smart Contract Details

| Parameter             | Value                                      |
|-----------------------|--------------------------------------------|
| **Mint Price**        | `0.00000001 ETH` (testnet)                 |
| **Burn Delay**        | Randomized between 1–12 hours              |
| **Min Anonymity Set** | 50 burns required per batch                |
| **Fee**               | `0%` (all ETH sent to users minus gas)     |
| **Retry Limit**       | 7 attempts before fallback to fee sink     |
| **Gas Estimation**    | EWMA with 12.5% buffer                     |
| **Gas Refund**        | Last burner in the batch triggers withdraw & is reimbursed |

---

## 🛠 Developer

- **Frontend:** Static HTML + JS (no server)
- **Private Keys:** Generated with `ethers.Wallet(randomBytes(32))`
- **Security:** Signature-based authorization, no contracts allowed
- **Gas Pool:** Pooled ETH for each 50-user batch

---

## ⚠️ Disclaimer

This is a **testnet-only** deployment. Do not use with mainnet ETH.  
Losing your stealth private key = losing access to your ETH.  
This system is experimental, use at your own risk.

---

## 🧬 License

MIT © 2025 — CountFuckula.com
