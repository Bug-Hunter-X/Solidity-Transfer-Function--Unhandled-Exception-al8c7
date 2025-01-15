# Solidity Transfer Function Bug
This repository demonstrates a common bug in Solidity transfer functions: insufficient balance handling.  The provided `transfer` function lacks robust error handling, leading to potential issues.

## Bug Description
The `transfer` function attempts to transfer tokens without checking if the sender has sufficient balance. If the `amount` exceeds `balanceOf[msg.sender]`, the transaction will revert with an error. However, the original code doesn't handle this explicitly leading to unexpected behavior.

## Solution
The solution includes proper checks using the `require` statement to verify sufficient balance before performing the transfer.  If the balance is insufficient, the transaction reverts gracefully with an informative error message.