# Vending Machine Smart Contract  

This repository contains a smart contract written in Solidity that simulates a vending machine's functionality on the Ethereum blockchain. The contract allows users to purchase snacks, while the owner manages inventory and handles the machine's balance.  

## Features  

1. **Owner-Only Actions:**  
   - Add new snacks to the vending machine.  
   - Restock existing snacks.  
   - View the vending machine's balance.  
   - Withdraw the machine's balance to the owner's account.  

2. **Public Access:**  
   - Anyone can purchase snacks by sending the required payment in ether.  

3. **Automated Operations:**  
   - The contract automatically deducts the snack quantity upon successful purchase.  
   - Ensures secure payment processing and inventory updates.  

## Contract Overview  

The vending machine maintains an inventory of snacks, represented by a `Snack` struct with the following properties:  
- `id`: A unique identifier for each snack.  
- `name`: The name of the snack.  
- `quantity`: The number of units available.  
- `price`: The cost per unit, specified in ether.  

The inventory is stored in two data structures:  
- `stock`: An array for general access and iteration.  
- `stock1`: A mapping for quick lookups by ID.  

### Functions  

1. **Adding Snacks**  
   - The owner can add new snacks by specifying a name, quantity, and price.  
   - Emits a `newSnackAdded` event upon successful addition.  

2. **Restocking Snacks**  
   - The owner can increase the quantity of an existing snack using its ID.  
   - Emits a `snackRestocked` event upon successful restock.  

3. **Purchasing Snacks**  
   - Users can buy snacks by providing the snack ID, quantity, and required payment.  
   - Ensures sufficient stock and correct payment before completing the transaction.  
   - Emits a `snackSold` event upon successful purchase.  

4. **Accessing Balance**  
   - The owner can view the vending machine's balance and withdraw funds.  

## Events  

- `newSnackAdded`: Triggered when a new snack is added to the inventory.  
- `snackRestocked`: Triggered when a snack's quantity is restocked.  
- `snackSold`: Triggered when a snack is successfully purchased.  

## Security  

The contract uses a `modifier` to restrict sensitive actions (like adding snacks, restocking, and withdrawing funds) to the owner. Payment validations ensure that purchases are completed securely.  

## Getting Started  

To deploy and interact with this contract, you'll need:  
1. A Solidity-compatible development environment (e.g., Remix, Hardhat).  
2. An Ethereum wallet for deploying and testing the contract.  
3. Ether for transactions on the blockchain.  

This smart contract provides a simple yet functional example of how blockchain technology can be applied to automate vending machine operations.
