# EbroVault: A Tokenized Vault Solution

## Overview
EbroVault is a smart contract-based tokenized vault system that leverages the ERC-4626 standard to enable efficient and flexible asset management. The project includes a custom vault contract (`TokenVault`) and a fungible token contract (`SICKESTToken`) to demonstrate seamless integration of deposit, withdrawal, and yield accrual functionalities.

---

## Project Structure

### 1. `TokenVault.sol`
The `TokenVault` contract is an implementation of the ERC-4626 standard for tokenized vaults. It enables users to deposit assets, earn yield, and withdraw their holdings with accrued interest.

#### Key Features:
- **Deposits:** Users can deposit a specified amount of ERC-20 tokens and receive vault shares in return.
- **Withdrawals:** Users can withdraw their assets along with an additional 10% yield.
- **Shareholder Management:** Tracks and manages each user's deposited assets.

#### Functions:
- `_deposit(uint _assets)`: Allows users to deposit ERC-20 tokens into the vault.
- `_withdraw(uint _shares, address _receiver)`: Allows users to withdraw their deposited assets plus accrued yield.
- `totalAssets()`: Returns the total assets managed by the vault.
- `totalAssetsOfUser(address _user)`: Returns the balance of a specific user.

### 2. `sickesttoken.sol`
The `SICKESTToken` contract is an ERC-20 token implementation using OpenZeppelin's library. It serves as the asset for the `TokenVault` and supports minting functionalities.

#### Key Features:
- **Minting:** Allows authorized accounts to mint new tokens.
- **Standard ERC-20 Compliance:** Supports standard ERC-20 functionalities with 18 decimals.

---

## Features

### TokenVault
- **ERC-4626 Compliance:** Utilizes the standardized vault interface for asset management.
- **Yield Calculation:** Provides a fixed 10% yield on withdrawals.
- **Flexible User Management:** Tracks user shares and validates transactions.

### SICKESTToken
- **Custom Token:** A mintable ERC-20 token designed to integrate seamlessly with the vault.
- **Decentralized Asset:** Serves as the core asset for deposits and withdrawals.

---

## Prerequisites

### Tools and Dependencies
- **Solidity Compiler (0.8.20 or higher)**
- [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts)
- [Solmate ERC-4626 Library](https://github.com/transmissions11/solmate)

### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/EbroVault.git
   ```
2. Install dependencies using a package manager like [Foundry](https://getfoundry.sh/) or [Hardhat](https://hardhat.org/).

---

## Usage

### Deployment
1. Deploy `SICKESTToken`:
   - Use a deployment script or manual deployment tools like Remix to deploy `SICKESTToken`.
2. Deploy `TokenVault`:
   - Pass the `SICKESTToken` contract address as the `_asset` parameter.
   - Provide a name and symbol for the vault shares.

### Interaction
- **Deposit:**
  Call `_deposit` with the desired asset amount to receive vault shares.
- **Withdraw:**
  Call `_withdraw` with the desired share amount to redeem assets plus yield.

---

## Example Workflow
1. Mint SICKEST tokens for the user using `mint`.
2. Deposit the tokens into the vault using `_deposit`.
3. Withdraw tokens from the vault using `_withdraw`.

---

## Directory Structure
```plaintext
.
├── TokenVault.sol        # ERC-4626 compliant vault contract
├── sickesttoken.sol      # ERC-20 token implementation
└── README.md             # Project documentation
```

---

## Future Enhancements
- Support for additional ERC-20 tokens.
- Dynamic yield strategies based on market conditions.
- Improved governance mechanisms for vault management.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Acknowledgments
- [OpenZeppelin](https://openzeppelin.com/) for secure and robust smart contract libraries.
- [Solmate](https://github.com/transmissions11/solmate) for the ERC-4626 implementation.
- The Ethereum community for continuous innovation in decentralized finance.

