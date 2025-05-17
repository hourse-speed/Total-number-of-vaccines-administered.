# VaccinationTracker Smart Contract

A simple Move smart contract on the Aptos blockchain to manage and track public vaccination campaigns.

## 📄 Description

This smart contract allows a public health authority (admin) to:
- Start a vaccination campaign with a target number.
- Record each vaccination event on-chain.

Each campaign stores:
- `total_vaccinated`: Number of people vaccinated so far.
- `target`: Total vaccination goal.

## 📦 Module

```move
module MyModule::VaccinationTracker
