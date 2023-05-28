## Smart Contract: DayMonthLimits

This smart contract allows setting limits on transfer volumes on a daily and monthly basis. Investors are restricted from sending more tokens than the fixed limit per day or month.

### Functions

| Function                           | Visibility | Description                                                                                                                                                              |
|------------------------------------|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `setDailyLimit(uint256 _newDailyLimit)`      | External   | Sets the daily limit of tokens allowed to be transferred. Only the owner of the Compliance smart contract can call this function.                                       |
| `setMonthlyLimit(uint256 _newMonthlyLimit)`  | External   | Sets the monthly limit of tokens allowed to be transferred. Only the owner of the Compliance smart contract can call this function.                                   |
| `complianceCheckOnDayMonthLimits(address _from, address _to, uint256 _value) → bool` | Public     | Checks the compliance status of a transaction, ensuring that it doesn't exceed the daily and/or monthly limits. Returns `true` if the transfer is allowed, `false` otherwise. |
| `_transferActionOnDayMonthLimits(address _from, address _to, uint256 _value)`         | Internal   | Updates the state of the compliance feature post-transfer. Increments daily and monthly transfer counters.                                                              |
| `_creationActionOnDayMonthLimits(address _to, uint256 _value)`           | Internal   | Updates the state of the compliance feature post-minting. This feature doesn't require any state update after minting.                                                 |
| `_destructionActionOnDayMonthLimits(address _from, uint256 _value)`      | Internal   | Updates the state of the compliance feature post-burning. This feature doesn't require any state update after burning.                                                 |
| `_increaseCounters(address _userAddress, uint256 _value)`                 | Internal   | Increases the user's transfer counters. Resets the daily and monthly cooldowns if necessary.                                                                           |
| `_resetDailyCooldown(address _identity)`                            | Internal   | Resets the daily cooldown if the cooldown has reached the time limit of 1 day.                                                                                          |
| `_resetMonthlyCooldown(address _identity)`                          | Internal   | Resets the monthly cooldown if the cooldown has reached the time limit of 30 days.                                                                                      |
| `_isDayFinished(address _identity) → bool`                                  | Internal   | Checks if the day has finished since the cooldown has been triggered for the given identity.                                                                           |
| `_isMonthFinished(address _identity) → bool`                                | Internal   | Checks if the month has finished since the cooldown has been triggered for the given identity.                                                                         |

### Events

| Event                               | Description                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------------------|
| `DailyLimitUpdated(uint _newDailyLimit)`    | Emitted whenever the daily limit has been updated.                                               |
| `MonthlyLimitUpdated(uint _newMonthlyLimit)`| Emitted whenever the monthly limit has been updated.                                             |
