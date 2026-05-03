<div align="center">

<br/>

```
  ████████╗██╗███╗   ███╗███████╗██╗      ██████╗  ██████╗██╗  ██╗
  ╚══██╔══╝██║████╗ ████║██╔════╝██║     ██╔═══██╗██╔════╝██║ ██╔╝
     ██║   ██║██╔████╔██║█████╗  ██║     ██║   ██║██║     █████╔╝ 
     ██║   ██║██║╚██╔╝██║██╔══╝  ██║     ██║   ██║██║     ██╔═██╗ 
     ██║   ██║██║ ╚═╝ ██║███████╗███████╗╚██████╔╝╚██████╗██║  ██╗
     ╚═╝   ╚═╝╚═╝     ╚═╝╚══════╝╚══════╝ ╚═════╝  ╚═════╝╚═╝  ╚═╝
```

**Schedule future OZONE transfers with cryptographic time-locks.**  
*Non-custodial · Decentralized · On-chain 24/7*

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-5de0c8.svg?style=flat-square)](https://choosealicense.com/licenses/mit/)
[![Network](https://img.shields.io/badge/Network-Ozone%20Mainnet-a78bfa?style=flat-square)](https://ozonechain.io)
[![Chain ID](https://img.shields.io/badge/Chain%20ID-10121-5de0c8?style=flat-square)](https://ozonescan.com)
[![Contract](https://img.shields.io/badge/Contract-Verified-00c896?style=flat-square)](https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.20-363636?style=flat-square&logo=solidity)](https://soliditylang.org)
[![Fee](https://img.shields.io/badge/Service%20Fee-1%25-f59e0b?style=flat-square)]()

<br/>

[**→ Live App**](https://yourdomain.com) · [**→ Contract on OzoneScan**](https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1) · [**→ Ozone Chain**](https://ozonechain.io)

<br/>

---

</div>

## Overview

**TimeLock** is a decentralized, non-custodial OZONE transfer scheduler built on **Ozone Mainnet**. Lock native OZONE coins into a smart contract for any recipient — they can only claim after your chosen unlock date. The sender can cancel and get refunded at any point before unlock.

No admin keys. No upgradeable proxies. No custody. Just math and time.

```
Sender  ──[scheduleTransfer]──▶  Smart Contract  ──[claimTransfer]──▶  Recipient
                                       │
                               locked until unlockTime
                                       │
                  Sender  ◀──[cancelTransfer]──┘  (before unlock only)
```

<br/>

## Features

| Feature | Details |
|---|---|
| **Time-locked transfers** | Lock OZONE for any recipient until a future timestamp |
| **Non-custodial** | Only recipient can claim · Only sender can cancel |
| **Cancel & refund** | Sender gets 99% back if cancelled before unlock |
| **Fee preview** | See exact fee + net amount before confirming |
| **Live stats** | Total transfers & OZONE locked shown on page load |
| **Transfer lookup** | Look up any transfer by ID without connecting wallet |
| **Max lock** | Up to 5 years from schedule date |
| **Service fee** | 1% flat, taken at schedule time, non-refundable |
| **Gas** | 1 Gwei on Ozone Mainnet |

<br/>

## Contract

```
Address   0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1
Network   Ozone Mainnet
Chain ID  10121
Compiler  Solidity v0.8.20+commit.a1b79de6
EVM       London
License   MIT
Status    Verified ✓ (OzoneScan)
```

> [View on OzoneScan →](https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1)

<br/>

## How It Works

```
1. Connect Wallet
   └─ MetaMask on Ozone Mainnet (Chain ID 10121)

2. Schedule Transfer
   └─ Enter recipient address, OZONE amount, unlock date
   └─ Contract takes gross amount; 1% fee deducted; net locked

3. Funds Lock On-Chain
   └─ OZONE held in contract until unlockTime passes
   └─ Sender can cancel anytime before unlock (99% refund)

4. Recipient Claims
   └─ After unlock, recipient calls claimTransfer()
   └─ Net OZONE sent directly to their wallet
```

<br/>

## Contract Interface

<details>
<summary><strong>Read Functions</strong></summary>

| Function | Signature | Description |
|---|---|---|
| `getTransfer` | `0xc16fe907` | Full details for a transfer ID |
| `getTransfersBySender` | `0x4e94cef9` | All transfer IDs sent by an address |
| `getTransfersByRecipient` | `0xf2270d72` | All transfer IDs incoming to an address |
| `getTransferDetailsBySender` | `0x04783fb7` | Full structs for all sent transfers |
| `getTransferDetailsByRecipient` | `0xefebbdd7` | Full structs for all received transfers |
| `isClaimable` | `0x89610a09` | Returns true if transfer can be claimed |
| `isCancellable` | `0x2d3a6329` | Returns true if transfer can be cancelled |
| `timeUntilUnlock` | `0x1b934ce5` | Seconds remaining until unlock |
| `previewFee` | `0x35e856f2` | Returns `(fee, netAmount)` for a gross amount |
| `totalTransfers` | `0x3bf47720` | Total number of transfers ever scheduled |
| `contractBalance` | `0x8b7afe2e` | Total OZONE currently locked in contract |
| `totalFeesCollected` | `0x60c6d8ae` | Cumulative fees collected |
| `FEE_BPS` | `0xbf333f2c` | Fee in basis points (100 = 1%) |
| `BPS_DENOMINATOR` | `0xe1a45218` | Denominator for BPS calculation (10000) |
| `MAX_LOCK_DURATION` | `0x4f1bfc9e` | Maximum lock duration in seconds |
| `MIN_AMOUNT` | `0xddbcb5fa` | Minimum transferable amount |
| `feeRecipient` | `0x46904840` | Address receiving fees |
| `owner` | `0x8da5cb5b` | Contract owner address |
| `pendingOwner` | `0xe30c3978` | Pending owner (two-step ownership transfer) |

</details>

<details>
<summary><strong>Write Functions</strong></summary>

| Function | Signature | Description |
|---|---|---|
| `scheduleTransfer(address recipient, uint256 unlockTime)` | `0xdd1f7776` | Create a time-locked transfer (payable) |
| `claimTransfer(uint256 transferId)` | `0x0a7920c5` | Claim an unlocked transfer (recipient only) |
| `cancelTransfer(uint256 transferId)` | `0x59caecb5` | Cancel before unlock (sender only, 99% refund) |
| `transferOwnership(address newOwner)` | `0xf2fde38b` | Initiate ownership transfer |
| `acceptOwnership()` | `0x79ba5097` | Accept pending ownership |
| `updateFeeRecipient(address newFeeRecipient)` | `0xf160d369` | Update fee collection address (owner only) |

</details>

<details>
<summary><strong>Events</strong></summary>

```solidity
event TransferScheduled(
    uint256 indexed transferId,
    address indexed sender,
    address indexed recipient,
    uint256 grossAmount,
    uint256 netAmount,
    uint256 fee,
    uint256 unlockTime
);

event TransferClaimed(
    uint256 indexed transferId,
    address indexed recipient,
    uint256 netAmount,
    uint256 timestamp
);

event TransferCancelled(
    uint256 indexed transferId,
    address indexed sender,
    uint256 refundAmount,
    uint256 timestamp
);
```

</details>

<br/>

## Running Locally

> **Important:** MetaMask will not inject into `file://` pages. You must serve this over `http://localhost`.

**Option 1 — Python (no install needed)**
```bash
cd ~/Downloads
python3 -m http.server 8080
# Open: http://localhost:8080/timelocked-transfer.html
```

**Option 2 — Node.js**
```bash
npx serve ~/Downloads
# Open: http://localhost:3000/timelocked-transfer.html
```

**Option 3 — VS Code**  
Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension → right-click the HTML file → *Open with Live Server*

<br/>

## Network Setup

Add **Ozone Mainnet** to MetaMask manually if not already added:

| Field | Value |
|---|---|
| Network Name | Ozone Mainnet |
| RPC URL | `https://node1.ozonechain.io` |
| Chain ID | `10121` |
| Currency Symbol | `OZONE` |
| Block Explorer | `https://ozonescan.com` |

Or click **Switch Network** in the app — it will add it automatically.

<br/>

## Tech Stack

```
Frontend     Vanilla HTML · CSS · JavaScript (no framework)
Fonts        Instrument Serif + Geist Mono
Web3         ethers.js v6.7.0
Contract     Solidity 0.8.20
Network      Ozone Mainnet (EVM-compatible, PoS)
Explorer     OzoneScan (Blockscout)
```

<br/>

## Security Notes

- **Non-custodial:** The contract never has admin access to funds. Only the sender and recipient have privileged actions on their own transfers.
- **No upgradeability:** The contract is not upgradeable. What is deployed is what runs.
- **Two-step ownership:** Ownership transfers use a `pendingOwner` pattern to prevent accidental transfers.
- **Fee is final:** The 1% fee is deducted at schedule time. Cancellations refund 99% of the gross amount.
- **Time validation:** Unlock time must be in the future and within 5 years of the schedule date.

<br/>

## Fee Structure

```
You send:          100.000000 OZONE  (gross)
Service fee (1%):    1.000000 OZONE  → feeRecipient
Recipient gets:     99.000000 OZONE  (net, locked until unlockTime)

On cancel (before unlock):
Refund to sender:   99.000000 OZONE  (fee is non-refundable)
```

<br/>

## Project Structure

```
timelocked-transfer/
├── timelocked-transfer.html   # Complete single-file dApp (HTML + CSS + JS)
├── README.md                  # This file
└── contracts/
    └── TimeLockedTransfer.sol # Smart contract source (Solidity 0.8.20)
```

<br/>

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/your-feature`
3. Commit your changes: `git commit -m 'feat: add your feature'`
4. Push to the branch: `git push origin feat/your-feature`
5. Open a Pull Request

<br/>

## Links

| Resource | URL |
|---|---|
| Live App | https://yourdomain.com |
| Contract | https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1 |
| Ozone Chain | https://ozonechain.io |
| OzoneScan | https://ozonescan.com |
| Ozone Staking | https://staking.ozonescan.com |

<br/>

---

<div align="center">

MIT License · Built on [Ozone Mainnet](https://ozonechain.io) · Contract verified on [OzoneScan](https://ozonescan.com)

</div>
