# DegenToken

DegenToken is a simple ERC-20 token written in Solidity, featuring additional functionality such as product listings, purchasing products, and ownership management. This token is designed for educational purposes and demonstrates basic concepts in Ethereum smart contract development.

## Table of Contents

1. [Overview](#overview)
2. [Token Details](#token-details)
3. [Products](#products)
4. [Functions](#functions)
5. [Usage](#usage)

## Overview

DegenToken is an ERC-20 token with the added functionality of listing products. It inherits from the OpenZeppelin ERC20 and Ownable contracts, providing standard token functionality and ownership management.

## Token Details

- **Name:** Degen
- **Symbol:** DGN
- **Decimals:** 18
- **Initial Supply:** Specified during contract deployment

## Products

DegenToken includes a product feature, allowing the owner to list products with names and prices. The initial deployment includes a set of example products:

1. Lamborghini Aventador - 10 DGN
2. Porsche GT - 30 DGN
3. Ferrari SP90 - 50 DGN
4. Rolls Royce - 25 DGN

## Functions

### `addProduct(string memory name, uint256 price) internal onlyOwner`

Adds a new product to the list. Only the owner can call this function.

### `getProduct(uint256 index) public view returns (string memory name, uint256 price)`

Returns the details of a specific product by index.

### `mint(uint256 amount) public onlyOwner`

Mints additional tokens. Only the owner can call this function.

### `burn(uint256 amount) public`

Burns a specified amount of tokens. Requires the amount to be greater than 10 and the caller to have a sufficient balance.

### `buyProduct(uint256 productIndex) public`

Allows users to purchase a product by index, burning the required tokens and emitting a `ProductPurchased` event.

### `transfer(address to, uint256 amount) public override returns (bool)`

Overrides the ERC-20 `transfer` function to include custom logic.

### `getAllProducts() public view returns (Product[] memory)`

Returns an array containing all listed products.

## Usage

1. Deploy the contract, specifying the initial token supply.
2. The owner can add products using the `addProduct` function.
3. Users can transfer tokens, burn tokens (if conditions are met), and purchase products using the respective functions.
4. The owner can mint additional tokens if needed.
