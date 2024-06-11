### StandardToken Contract

The StandardToken contract is an ERC20-compliant token with additional functionalities such as burning and minting. It inherits from the ERC20 and Ownable contracts from the OpenZeppelin library. Below is an overview of its features:

#### Overview

- **Solidity Version:** 0.8.0
- **License:** MIT
- **Imports:**
  - `ERC20Burnable.sol`: Provides functionality to burn tokens.
  - `Ownable.sol`: Provides functionality to restrict certain operations to the contract owner.

#### Constructor

- `constructor(uint256 initialSupply)`: Initializes the token with the specified initial supply upon deployment. The token is named "StandardCoin" with the symbol "STC".

#### Functions

1. `mint(address to, uint256 amount)`: Allows the contract owner to mint new tokens and assign them to a specified address.

2. `burn(uint256 amount)`: Allows token holders to burn a specified amount of their own tokens, reducing the total supply.

3. `transfer(address recipient, uint256 amount)`: Overrides the ERC20 `transfer` function to include custom logic if necessary. In this implementation, it simply transfers tokens from the sender to the recipient.

#### Usage

To use the StandardToken contract:
1. Deploy the contract with an initial supply of tokens.
2. Optionally, mint additional tokens using the `mint` function.
3. Users can transfer tokens to other addresses using the `transfer` function.
4. Token holders can burn their own tokens using the `burn` function.

#### Example

```solidity
// Deploy the contract with an initial supply of 1,000 tokens
StandardToken token = new StandardToken(1000);

// Mint 500 tokens and assign them to a specific address
token.mint(addressToMint, 500);

// Transfer tokens from one address to another
token.transfer(recipientAddress, amount);

// Burn tokens (only the token holder can burn their own tokens)
token.burn(amount);
```
