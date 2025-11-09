# 📝 TodoList dApp - Blockchain Todo Manager

A decentralized todo list application built on Ethereum Sepolia testnet that allows users to create and manage tasks permanently on the blockchain.

## 📋 Table of Contents
- [Overview](#overview)
- [Contract Details](#contract-details)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [How to Use](#how-to-use)
- [Smart Contract Functions](#smart-contract-functions)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Assignment Details](#assignment-details)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## 🎯 Overview

This project is a decentralized application (dApp) that demonstrates the integration of a Solidity smart contract with a web-based frontend. Users can create, view, and manage their todo tasks directly on the Ethereum blockchain, ensuring immutability and transparency.

## 🔗 Contract Details

- **Contract Address**: `0xd9145CCE52D386f254917e481eB44e9943F39138`
- **Network**: Sepolia Testnet (Chain ID: 11155111)
- **Compiler Version**: Solidity ^0.8.17
- **Deployment Tool**: Remix IDE
- **View on Etherscan**: [Contract Link](https://sepolia.etherscan.io/address/0xd9145CCE52D386f254917e481eB44e9943F39138)

## ✨ Features

### Smart Contract Features
- ✅ Add new tasks with descriptions
- ✅ Toggle task completion status
- ✅ Retrieve individual task details
- ✅ Get total task count for any user
- ✅ Get all tasks at once
- ✅ Event emission for task creation and updates
- ✅ Per-user task isolation

### Frontend Features
- 🔗 MetaMask wallet integration
- 📝 Add tasks to blockchain with transaction confirmation
- ✅ Toggle task completion status
- 📊 Real-time task count display
- 🕒 Timestamp display for each task
- 🎨 Modern, responsive UI design
- ⚠️ Error handling and user feedback
- 🔄 Automatic page updates after transactions
- 🌐 Network validation (Sepolia testnet)

## 🛠️ Technologies Used

### Backend (Smart Contract)
- **Solidity** v0.8.17 - Smart contract programming language
- **Remix IDE** - Contract development and deployment
- **OpenZeppelin** - Security patterns and best practices

### Frontend
- **HTML5** - Structure and semantic markup
- **CSS3** - Styling with gradients and animations
- **JavaScript (ES6+)** - Frontend logic and Web3 integration
- **Ethers.js v5.6** - Ethereum blockchain interaction library
- **MetaMask** - Wallet connection and transaction signing

### Blockchain
- **Ethereum Sepolia Testnet** - Test network for deployment
- **Etherscan** - Blockchain explorer for verification

## 🚀 Setup Instructions

### Prerequisites
1. **Install MetaMask**
   - Download from [metamask.io](https://metamask.io/)
   - Create a new wallet or import existing one
   - Save your seed phrase securely

2. **Switch to Sepolia Testnet**
   - Open MetaMask
   - Click on network dropdown
   - Select "Sepolia Test Network"
   - If not visible, enable "Show test networks" in settings

3. **Get Sepolia ETH**
   - Visit Sepolia faucet: [sepoliafaucet.com](https://sepoliafaucet.com/)
   - Or use [Google Cloud Faucet](https://cloud.google.com/application/web3/faucet/ethereum/sepolia)
   - Enter your wallet address and request test ETH
   - Wait for confirmation (usually 1-2 minutes)

### Installation Steps

1. **Clone or Download the Repository**
   ```bash
   git clone <your-repository-url>
   cd todolist-dapp
   ```

2. **Project Files**
   - Ensure you have the following files:
     - `SmartContract.sol` - The Solidity smart contract
     - `index.html` - The frontend interface
     - `README.md` - This file
     - `screenshots/` - Folder containing UI screenshots

3. **Open the Application**
   - Simply open `index.html` in your web browser
   - No build process or server required
   - Works with Chrome, Firefox, Brave, or Edge

## 📖 How to Use

### Step 1: Connect Your Wallet
1. Open `index.html` in your browser
2. Click the "Connect MetaMask" button
3. Approve the connection in MetaMask popup
4. Ensure you're on Sepolia testnet
5. Your wallet address will be displayed once connected

### Step 2: Add a Task
1. Type your task description in the input field
2. Click "Add Task" button
3. Confirm the transaction in MetaMask
4. Wait for blockchain confirmation (10-30 seconds)
5. Your task will appear in the list below

### Step 3: Toggle Task Status
1. Find your task in the list
2. Click "Mark Complete" to mark as done
3. Confirm the transaction in MetaMask
4. Task will update with completion status
5. Click again to mark as incomplete

### Step 4: View Task Details
- Each task shows:
  - Description
  - Task number
  - Creation timestamp
  - Completion status
  - Toggle button

## 🔧 Smart Contract Functions

### Write Functions (Require Gas)

#### `addTask(string _description)`
- **Description**: Creates a new task on the blockchain
- **Parameters**: 
  - `_description` (string) - The task description
- **Returns**: None
- **Events**: Emits `TaskCreated` event
- **Gas Cost**: ~50,000 - 100,000 gas

#### `toggleTask(uint256 _index)`
- **Description**: Toggles the completion status of a task
- **Parameters**: 
  - `_index` (uint256) - The index of the task to toggle
- **Returns**: None
- **Events**: Emits `TaskStatusUpdated` event
- **Gas Cost**: ~30,000 - 50,000 gas

### Read Functions (Free)

#### `getTaskCount(address _user)`
- **Description**: Returns the total number of tasks for a user
- **Parameters**: 
  - `_user` (address) - The user's wallet address
- **Returns**: `uint256` - Number of tasks
- **Gas Cost**: Free (view function)

#### `getTask(address _user, uint256 _index)`
- **Description**: Retrieves details of a specific task
- **Parameters**: 
  - `_user` (address) - The user's wallet address
  - `_index` (uint256) - The task index
- **Returns**: 
  - `description` (string) - Task description
  - `completed` (bool) - Completion status
  - `timestamp` (uint256) - Creation time
- **Gas Cost**: Free (view function)

#### `getAllTasks(address _user)`
- **Description**: Returns all tasks for a user at once
- **Parameters**: 
  - `_user` (address) - The user's wallet address
- **Returns**: `Task[]` - Array of all tasks
- **Gas Cost**: Free (view function)

## 📁 Project Structure

```
todolist-dapp/
├── SmartContract.sol          # Solidity smart contract code
├── index.html                 # Frontend HTML with CSS and JS
├── README.md                  # Project documentation (this file)
└── screenshots/               # UI and transaction screenshots
    ├── 1-initial-page.png     # dApp interface before connection
    ├── 2-metamask-connect.png # MetaMask connection popup
    ├── 3-add-task.png         # Adding task transaction
    ├── 4-tasks-displayed.png  # Tasks list with data
    └── 5-toggle-task.png      # Toggling task status
```

## 📸 Screenshots

### 1. Initial Page
The main interface showing the dApp before wallet connection.

### 2. MetaMask Connection
MetaMask popup requesting permission to connect to the dApp.

### 3. Adding Task
Transaction confirmation when adding a new task to the blockchain.

### 4. Tasks Displayed
List of tasks showing descriptions, timestamps, and completion status.

### 5. Toggle Task Status
Updating task completion status with blockchain transaction.

## 🎓 Assignment Details

- **Course**: MG3012 - Blockchain Technology for Business
- **Program**: BSFT - 5th Semester (Fall 2025)
- **Instructor**: Dr. Usama Arshad
- **Assignment**: Assignment 2 - Mini dApp Development
- **Deadline**: November 9, 2025, 23:59 PKT
- **Student Wallet**: `0x78c0931023c303ed9846bccd0b11f7c5878707ba`

### Assignment Requirements Met ✅

#### Smart Contract (5 marks)
- ✅ 3-5 functions implemented (6 functions total)
- ✅ At least one read function (3 read functions)
- ✅ At least one write function (2 write functions)
- ✅ Deployed on Sepolia testnet
- ✅ Connected with MetaMask

#### Frontend - HTML/CSS (3 marks)
- ✅ Headings (h1, h2, h3)
- ✅ Paragraphs (multiple p tags)
- ✅ Lists (ul, li elements)
- ✅ Links (Etherscan link)
- ✅ Buttons (Connect, Add, Toggle)
- ✅ Images (status indicators)
- ✅ Internal CSS styling
- ✅ Modern, responsive design

#### Frontend - JavaScript (4 marks)
- ✅ Script tag with ethers.js
- ✅ MetaMask connection logic
- ✅ Read data from blockchain
- ✅ Write data to blockchain
- ✅ Display transaction results
- ✅ Error handling
- ✅ Network validation

#### Functionality & Wallet Interaction (4 marks)
- ✅ Successful wallet connection
- ✅ Transaction signing and confirmation
- ✅ Real-time UI updates
- ✅ Event handling
- ✅ User feedback system

#### Documentation (3 marks)
- ✅ Comprehensive README.md
- ✅ Setup instructions
- ✅ Usage guide
- ✅ Screenshots included
- ✅ Contract address provided
- ✅ GitHub repository ready

#### Bonus Points
- ⭐ Contract verified on Etherscan (optional)
- ⭐ Enhanced UI with animations
- ⭐ Additional `getAllTasks()` function
- ⭐ Real-time transaction status updates

## 🐛 Troubleshooting

### MetaMask Not Connecting
- **Solution**: Refresh the page and ensure MetaMask is unlocked
- Check that you're on Sepolia testnet
- Try disconnecting and reconnecting MetaMask

### Transaction Failed
- **Solution**: Ensure you have enough Sepolia ETH for gas fees
- Check that you're connected to the correct network
- Try increasing gas limit in MetaMask settings

### Tasks Not Loading
- **Solution**: Wait a few seconds for blockchain confirmation
- Refresh the page after transaction confirmation
- Check console for error messages (F12 in browser)

### "Invalid Index" Error
- **Solution**: This means the task doesn't exist
- Make sure you're viewing tasks from the correct wallet
- Task indices start from 0

### Wrong Network Error
- **Solution**: Switch to Sepolia testnet in MetaMask
- Click on network dropdown and select "Sepolia Test Network"

## 📞 Support

If you encounter any issues:
1. Check the browser console for error messages (Press F12)
2. Verify your MetaMask is connected to Sepolia testnet
3. Ensure you have sufficient Sepolia ETH
4. Confirm the contract address is correct
5. Try refreshing the page

## 🔐 Security Notes

- Never share your private key or seed phrase
- This is deployed on testnet - not for real ETH
- Always verify contract address before interacting
- Test thoroughly before any mainnet deployment
- Keep your MetaMask updated

## 📝 License

This project is licensed under the MIT License.

## 🙏 Acknowledgments

- Dr. Usama Arshad - Course Instructor
- Ethereum Foundation - Blockchain technology
- MetaMask Team - Wallet infrastructure
- Remix IDE - Development environment
- OpenZeppelin - Smart contract patterns

---

**Developed by**: [Muhammad Afzaal Asghar]  
**Student ID**: [23i-5533]  
**Contact**: [i235533@isb.nu.edu.pk]  
**GitHub**: [https://github.com/muhafzaala/Mini-Dapp/upload]  
**Date**: November 2025

---

© 2025 TodoList dApp. Built for MG3012 - Blockchain Technology for Business.
