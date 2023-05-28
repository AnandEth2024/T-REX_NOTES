# this feature allows to put a maximum balance for an investor


## Smart Contract Functions

| Function Name                       | Visibility   | Description                                                                                                                                                                                                                                 |
|-------------------------------------|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `setMaxBalance(uint256 _max)`       | External     | Sets the maximum balance limit for an individual. Only the owner of the Compliance smart contract can call this function. Emits a `MaxBalanceSet` event.                                                                                |
| `complianceCheckOnMaxBalance(address _from, address _to, uint256 _value) returns (bool)` | Public       | Checks the compliance status of a transaction. Returns true if the transfer is allowed to be executed, and false if it exceeds the maximum balance threshold.                                                                         |
| `_transferActionOnMaxBalance(address _from, address _to, uint256 _value)` | Internal     | Updates the ONCHAINID-based balance of `_to` and `_from` post-transfer. Reverts if the post-transfer balance of `_to` exceeds the maximum balance. Internal function, can only be called from the functions of the Compliance smart contract. |
| `_creationActionOnMaxBalance(address _to, uint256 _value)`         | Internal     | Updates the ONCHAINID-based balance of `_to` post-minting. Reverts if the post-minting balance of `_to` exceeds the maximum balance. Internal function, can only be called from the functions of the Compliance smart contract.                |
| `_destructionActionOnMaxBalance(address _from, uint256 _value)`   | Internal     | Updates the ONCHAINID-based balance of `_from` post-burning. Internal function, can only be called from the functions of the Compliance smart contract.                                                                                   |

## Events

| Event Name                   | Description                                                                                                     |
|------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `MaxBalanceSet(uint256 _maxBalance)` | Emitted when the maximum balance has been set. `_maxBalance` is the maximum amount of tokens that a user can hold. |

## State Variables

| Variable Name               | Type       | Visibility | Description                                                                                                     |
|-----------------------------|------------|------------|-----------------------------------------------------------------------------------------------------------------|
| `maxBalance`                | uint256    | Public     | Maximum balance per investor ONCHAINID.                                                                         |
| `IDBalance`                 | mapping    | Public     | Mapping of balances per ONCHAINID.                                                                              |
