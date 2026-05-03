<div align="center">

<br/>

```
 ███████████  ███                           █████                         █████     
▒█▒▒▒███▒▒▒█ ▒▒▒                           ▒▒███                         ▒▒███      
▒   ▒███  ▒  ████  █████████████    ██████  ▒███         ██████   ██████  ▒███ █████
    ▒███    ▒▒███ ▒▒███▒▒███▒▒███  ███▒▒███ ▒███        ███▒▒███ ███▒▒███ ▒███▒▒███ 
    ▒███     ▒███  ▒███ ▒███ ▒███ ▒███████  ▒███       ▒███ ▒███▒███ ▒▒▒  ▒██████▒  
    ▒███     ▒███  ▒███ ▒███ ▒███ ▒███▒▒▒   ▒███      █▒███ ▒███▒███  ███ ▒███▒▒███ 
    █████    █████ █████▒███ █████▒▒██████  ███████████▒▒██████ ▒▒██████  ████ █████
   ▒▒▒▒▒    ▒▒▒▒▒ ▒▒▒▒▒ ▒▒▒ ▒▒▒▒▒  ▒▒▒▒▒▒  ▒▒▒▒▒▒▒▒▒▒▒  ▒▒▒▒▒▒   ▒▒▒▒▒▒  ▒▒▒▒ ▒▒▒▒▒ 
```

**Schedule future OZONE transfers with cryptographic time-locks.**  
*Non-custodial · Decentralized · On-chain 24/7*

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-5de0c8.svg?style=flat-square)](LICENSE)
[![Network](https://img.shields.io/badge/Network-Ozone%20Mainnet-a78bfa?style=flat-square&logo=ethereum&logoColor=white)](https://ozonechain.com)
[![Chain ID](https://img.shields.io/badge/Chain%20ID-10121-5de0c8?style=flat-square)](https://ozonescan.com)
[![Contract Verified](https://img.shields.io/badge/Contract-Verified%20%E2%9C%93-00c896?style=flat-square)](https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.20-363636?style=flat-square&logo=solidity&logoColor=white)](https://soliditylang.org)
[![EVM](https://img.shields.io/badge/EVM-London-f59e0b?style=flat-square)](https://ethereum.org)
[![Fee](https://img.shields.io/badge/Fee-1%25%20Flat-f87171?style=flat-square)]()
[![Gas](https://img.shields.io/badge/Gas-1%20Gwei-9ca3af?style=flat-square)]()
[![GitHub Pages](https://img.shields.io/badge/Deployed-GitHub%20Pages-222?style=flat-square&logo=github&logoColor=white)](https://gr4nth1k.github.io/TimeLockedTransfer/)

<br/>

[**→ Live App**](https://gr4nth1k.github.io/TimeLockedTransfer/) &nbsp;·&nbsp; [**→ Contract on OzoneScan**](https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1) &nbsp;·&nbsp; [**→ Ozone Chain**](https://ozonechain.com) &nbsp;·&nbsp; [**→ OzoneScan Explorer**](https://ozonescan.com)

<br/>

---

</div>

## What is TimeLock?

**TimeLock** is a decentralized, non-custodial OZONE transfer scheduler built on **Ozone Mainnet**. Lock native OZONE coins into a verified smart contract for any recipient — they can only claim after your chosen unlock date. The sender can cancel and receive a refund at any point before unlock.

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
| **Time-locked transfers** | Lock OZONE for any recipient until a future Unix timestamp |
| **Non-custodial** | Only the recipient can claim · Only the sender can cancel |
| **Cancel & refund** | Sender receives 99% back if cancelled before unlock |
| **Instant fee settlement** | 1% fee sent to `feeRecipient` at schedule time, not claim time |
| **Fee preview** | See exact fee and net amount before confirming in MetaMask |
| **Live stats** | Total transfers and OZONE locked load without wallet connection |
| **Transfer lookup** | Look up any transfer by ID — no wallet required |
| **Auto network switch** | App prompts MetaMask to add/switch to Ozone Mainnet automatically |
| **Max lock duration** | Up to 5 years from the schedule date |
| **Single-file dApp** | Entire frontend is one self-contained HTML file — zero build step |

<br/>

## Contract

```
Address    0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1
Bech32     ozone1s42xw8w406qz2n2cyl5h4aw2wwjm96lp0sl4ye
Network    Ozone Mainnet 3.0
Chain ID   10121
Compiler   Solidity v0.8.20+commit.a1b79de6
EVM        London
Optimizer  Disabled
License    MIT
Verified   OzoneScan — May 03 2026
Creator    0x4dc33362e43b692809efF2be548518f89Ac727ac
Deploy Tx  0x2e92b26c593f1ebcfdc64afac929ea3e6b9cac79447a21e6cabb2da55a3f1a4d
```

> [View on OzoneScan →](https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1)

<br/>

## How It Works

```
1. Connect Wallet
   └─ MetaMask on Ozone Mainnet (Chain ID 10121)
   └─ App auto-prompts network add/switch if needed

2. Schedule Transfer
   └─ Enter recipient address, OZONE amount, unlock date & time
   └─ 1% fee deducted and sent instantly to feeRecipient
   └─ Remaining net amount locked in contract until unlockTime

3. Funds Lock On-Chain
   └─ OZONE held in contract until unlockTime passes
   └─ Sender can cancel anytime before unlock (99% refund)
   └─ Fee is non-refundable even on cancel

4. Recipient Claims
   └─ After unlock, recipient visits the app
   └─ Clicks Claim on the Received tab
   └─ Net OZONE sent directly to their wallet in one transaction
```

<br/>

## Contract Interface

<details>
<summary><strong>Read Functions</strong></summary>

<br/>

| Function | Selector | Description |
|---|---|---|
| `getTransfer(uint256 transferId)` | `0xc16fe907` | Full details for a transfer ID |
| `getTransfersBySender(address)` | `0x4e94cef9` | All transfer IDs sent by an address |
| `getTransfersByRecipient(address)` | `0xf2270d72` | All transfer IDs incoming to an address |
| `getTransferDetailsBySender(address)` | `0x04783fb7` | Full structs for all sent transfers |
| `getTransferDetailsByRecipient(address)` | `0xefebbdd7` | Full structs for all received transfers |
| `isClaimable(uint256 transferId)` | `0x89610a09` | Returns true if transfer can be claimed now |
| `isCancellable(uint256 transferId)` | `0x2d3a6329` | Returns true if transfer can be cancelled |
| `timeUntilUnlock(uint256 transferId)` | `0x1b934ce5` | Seconds remaining until unlock |
| `previewFee(uint256 grossAmount)` | `0x35e856f2` | Returns `(fee, netAmount)` for a gross input |
| `totalTransfers()` | `0x3bf47720` | Total number of transfers ever scheduled |
| `contractBalance()` | `0x8b7afe2e` | Total OZONE currently locked in contract |
| `totalFeesCollected()` | `0x60c6d8ae` | Cumulative fees sent to feeRecipient |
| `FEE_BPS()` | `0xbf333f2c` | Fee in basis points — 100 = 1% |
| `BPS_DENOMINATOR()` | `0xe1a45218` | BPS denominator — 10000 |
| `MAX_LOCK_DURATION()` | `0x4f1bfc9e` | Maximum lock duration in seconds (5 years) |
| `MIN_AMOUNT()` | `0xddbcb5fa` | Minimum transferable gross amount |
| `feeRecipient()` | `0x46904840` | Address currently receiving fees |
| `owner()` | `0x8da5cb5b` | Contract owner address |
| `pendingOwner()` | `0xe30c3978` | Pending owner (two-step transfer pattern) |

</details>

<details>
<summary><strong>Write Functions</strong></summary>

<br/>

| Function | Selector | Access | Description |
|---|---|---|---|
| `scheduleTransfer(address recipient, uint256 unlockTime)` | `0xdd1f7776` | Anyone | Create a time-locked transfer — payable |
| `claimTransfer(uint256 transferId)` | `0x0a7920c5` | Recipient only | Claim funds after unlock time has passed |
| `cancelTransfer(uint256 transferId)` | `0x59caecb5` | Sender only | Cancel before unlock, receive 99% refund |
| `updateFeeRecipient(address newFeeRecipient)` | `0xf160d369` | Owner only | Update the fee collection address |
| `transferOwnership(address newOwner)` | `0xf2fde38b` | Owner only | Initiate two-step ownership transfer |
| `acceptOwnership()` | `0x79ba5097` | Pending owner | Complete the ownership transfer |

</details>

<details>
<summary><strong>Events</strong></summary>

<br/>

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

## Fee Structure

```
Schedule 100 OZONE
├──  1.000000 OZONE  (1%)  → feeRecipient wallet  ← sent instantly, same block
└── 99.000000 OZONE  (99%) → locked in contract   ← held until unlockTime

Recipient claims after unlock:
└── 99.000000 OZONE → recipient wallet

Sender cancels before unlock:
├── 99.000000 OZONE → refunded to sender
└──  1.000000 OZONE → already settled (non-refundable)
```

> The fee is transferred to `feeRecipient` **at the moment of scheduling** — not at claim or cancel time.

<br/>

## Running Locally

> **Important:** MetaMask blocks wallet injection into `file://` pages by browser security policy. You must serve the file over `http://localhost`. Alternatively, use the hosted [GitHub Pages version](https://gr4nth1k.github.io/TimeLockedTransfer/) — no setup needed.

**Option 1 — Python** *(no dependencies)*
```bash
cd ~/Downloads
python3 -m http.server 8080
# Open: http://localhost:8080/index.html
```

**Option 2 — Node.js**
```bash
npx serve ~/Downloads
# Open: http://localhost:3000/index.html
```

**Option 3 — VS Code**  
Install [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) → right-click `index.html` → *Open with Live Server*

<br/>

## Network Configuration

The app will prompt MetaMask to add Ozone Mainnet automatically via the **Switch Network** button. To add it manually:

| Field | Value |
|---|---|
| Network Name | `OZONE MAINNET 3.0` |
| RPC URL | `https://chain.ozonescan.com` |
| Chain ID | `10121` |
| Currency Symbol | `OZONE` |
| Block Explorer | `https://ozonescan.com` |

<br/>

## Tech Stack

```
Frontend        Vanilla HTML · CSS · JavaScript  (no framework, no build step)
Typography      Instrument Serif (display) + Geist Mono (monospace body)
Web3 Library    ethers.js v6.7.0 via CDN
Smart Contract  Solidity 0.8.20 · EVM London · MIT License
Blockchain      Ozone Mainnet — EVM-compatible Proof-of-Stake
Explorer        OzoneScan (powered by Blockscout)
Hosting         GitHub Pages
```

<br/>

## Security

- **Non-custodial** — The contract holds funds but has no owner-controlled withdrawal. Only the designated sender and recipient can act on their transfer.
- **No upgradeability** — The contract is not a proxy and cannot be upgraded. The deployed bytecode is final.
- **Two-step ownership** — Ownership transfers require the new owner to explicitly call `acceptOwnership()`, preventing accidental transfers to wrong addresses.
- **Fee is immutable per transfer** — The 1% rate is fixed at schedule time. Any future changes to `FEE_BPS` do not retroactively affect locked transfers.
- **Time-bounded locks** — Unlock time must be strictly in the future and within 5 years of the schedule date. No indefinite locks.
- **Verified source** — Contract source code is publicly verified on OzoneScan.

<br/>

## Project Structure

```
TimeLockedTransfer/
├── index.html    # Complete single-file dApp (HTML + CSS + JS, no dependencies)
├── README.md     # This file
└── LICENSE       # MIT License
```

<br/>

## Contributing

1. Fork this repository
2. Create a feature branch: `git checkout -b feat/your-feature`
3. Commit with a clear message: `git commit -m 'feat: describe your change'`
4. Push to your fork: `git push origin feat/your-feature`
5. Open a Pull Request against `main`

<br/>

## Links

| Resource | URL |
|---|---|
| Live App | https://gr4nth1k.github.io/TimeLockedTransfer/ |
| Contract | https://ozonescan.com/address/0x8554671dd57e80254D5827e97aF5CA73A5b2EBE1 |
| Deploy Tx | https://ozonescan.com/tx/0x2e92b26c593f1ebcfdc64afac929ea3e6b9cac79447a21e6cabb2da55a3f1a4d |
| Ozone Chain | https://ozonechain.com |
| OzoneScan | https://ozonescan.com |
| Ozone Staking | https://staking.ozonescan.com |
| Ozone Twitter | https://twitter.com/ozonechain |
| Ozone Telegram | https://t.me/ozonechainofficial |

<br/>

---

<div align="center">

MIT License &nbsp;·&nbsp; Built on [Ozone Mainnet 3.0](https://ozonechain.com) &nbsp;·&nbsp; Contract verified on [OzoneScan](https://ozonescan.com) &nbsp;·&nbsp; Hosted on [GitHub Pages](https://gr4nth1k.github.io/TimeLockedTransfer/)

</div>
