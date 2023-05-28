| Function | Description |
| -------- | ----------- |
| `setCompliance` | Sets the compliance contract of the token. Only the owner of the token smart contract can call this function. Calls `bindToken` on the compliance contract. Emits a `ComplianceAdded` event. |
| `forcedTransfer` | Force a transfer of tokens between two whitelisted wallets. If the `from` address does not have enough free tokens (unfrozen tokens) but has a total balance higher or equal to the `amount`, the amount of frozen tokens is reduced to have enough free tokens for the transfer. The remaining balance on the `from` account is 100% composed of frozen tokens post-transfer. Requires that the `to` address is a verified address. This function can only be called by a wallet set as an agent of the token. Emits a `TokensUnfrozen` event if the `_amount` is higher than the free balance of `_from` and a `Transfer` event. |
| `mint` | Mint tokens on a wallet. Improved version of the default mint method. Tokens can be minted to an address only if it is a verified address as per the security token. This function can only be called by a wallet set as an agent of the token. Emits a `Transfer` event. |
| `burn` | Burns tokens from the sender's account. The amount of tokens to burn must be less than or equal to the sender's balance. This function reduces the balance of the sender and the total supply of the token. Emits a `Transfer` event with the `to` address as the zero address to represent burning tokens. |
| `setRegistry` | Sets the registry contract address for the token. Only the owner of the token smart contract can call this function. |
| `getRoles` | Retrieves the roles assigned to the specified address. Returns an array of role IDs assigned to the address. |
| `setRole` | Sets or removes a role for an address. Only the owner of the token smart contract can call this function. Emits a `RoleSet` event. |
| `hasRole` | Checks if an address has a specific role. Returns a boolean indicating whether the address has the specified role. |
| `DEFAULT_ADMIN_ROLE` | Role identifier for the default admin role. |
| `MINTER_ROLE` | Role identifier for the minter role. |
| `PAUSER_ROLE` | Role identifier for the pauser role. |
| `TOKEN_DETAILS_ROLE` | Role identifier for the token details role. |
| `TRANSFER_ROLE` | Role identifier for the transfer role. |
| `freeze` | Freezes the token, preventing transfers. This function can only be called by a wallet with the pauser role. Emits a `Paused` event. |
| `unfreeze` | Unfreezes the token, allowing transfers. This function can only be called by a wallet with the pauser role. Emits an `Unpaused` event. |
