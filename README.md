ANONToken
The first privacy primitive on Linea. Fully decentralized. No zk. No relayers. No bridges.

ANONToken is a censorship-resistant ERC-20 protocol that lets users unlink their everyday crypto wallet from real-world spending, such as a MetaMask Card. By minting and then burning a single token, users receive ETH into a freshly generated stealth address — fully anonymized, without any centralized server or third-party control.

🌐 Testnet App (Linea Sepolia)
🛠 Built for Linea · Open-source · OG Ethereum ethos

🔐 How It Works
Mint

Send exactly 0.00000001 ETH (testnet price) to mint 1 ANON.

Tokens are standard ERC-20 and transferable, but only burners receive the anonymous ETH.

Burn for Privacy

The frontend generates a fresh stealth wallet (private key never leaves the browser).

You sign a commitment off-chain (binding wallet + contract + chain + entropy).

One transaction sends ETH to the stealth address after a randomized delay (1–12h).

Withdraw

Once 50 burns accumulate, one user triggers a randomized, anonymized payout.

Funds land in the stealth address. You import the private key to access them.

🧱 Key Features
Feature	Description
Privacy Model	Burn-based unlinkability; randomized queue delays; no zk needed.
Chain	Linea Sepolia (testnet).
Frontend	Fully browser-based, no backend. Keys generated locally.
Fees	0% protocol fee (testnet); gas-only model.
Security	Immutable contract, capped retry logic, no owner/admin keys.
Gas Optimization	Uses EWMA gas oracle logic with capped reimbursement.

🧪 How to Use (Testnet)
Setup

Connect via Rabby Desktop or MetaMask to Linea Sepolia

Get Sepolia ETH here

Mint

Visit: ANONToken dApp

Click “Mint 1 ANON” to send 0.00000001 ETH and receive a token.

Burn

Click “Burn 1 ANON”

App generates a fresh stealth key + signature

Submits burn tx + gas prepayment

Wait 1–12 hours until batch of 50 burns is processed

Withdraw

Import the stealth key in MetaMask or Rabby

Your ETH appears post-randomized delay (fully unlinkable to source)

🛡 Smart Contract
Address (Sepolia): 0xAfEAE83BD71E44d4291E95D621B10f3d3ff29a28

Token Symbol: ANON

Decimals: 18

Mint Price: 0.00000001 ETH

Anonymity Set: 50

Delay: Randomized between 1 – 12 hours

Reentrancy Protection: Enabled

Gas Refund: Caller of processWithdrawals() is reimbursed from pooled ETH

📁 Key Files
File	Description
index.html	Main frontend UI
script.js	All wallet, mint, burn, and stealth logic
ANONToken.sol	Solidity contract with gas pool batching, retry limits, and anonymity logic
style.css	Fully dark, Linea-themed visual style with responsive components

⚠️ Disclaimer
This is a testnet deployment. ETH and ANON tokens on Linea Sepolia have no real value. Keep your private key safe. No one can recover your ETH if you lose the stealth key.

🧬 License
MIT © 2025
