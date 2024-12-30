# Reentrancy Bug in balanceOf Function

This repository contains a Solidity smart contract with a reentrancy bug in the `balanceOf` function.  The bug allows an attacker to manipulate the balance reporting of the contract, potentially leading to significant vulnerabilities.

## Vulnerability Details

The `balanceOf` function lacks a reentrancy guard, which exposes it to reentrancy attacks.  An attacker could write a malicious contract that calls `balanceOf` multiple times in a single transaction, potentially manipulating the reported balance before the state is updated.

## Reproduction Steps

1.  Deploy the contract found in `bug.sol`.
2.  Interact with the contract using a malicious contract that exploits the reentrancy vulnerability.

## Solution

The solution, found in `bugSolution.sol`, addresses this vulnerability by implementing a proper reentrancy guard using the Checks-Effects-Interactions pattern.

## Disclaimer

This repository is for educational purposes only.  Do not use this code in a production environment without thoroughly auditing and securing it.