* this feature allows to put a limit on the monthly deposits one can make on a given exchange
 *  It won't be possible for an investor to send more than the monthly limit of tokens on a given exchange



| **Function**                                     | **Description**                                                                                                                                 |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| `setExchangeMonthlyLimit`                        | Sets the limit of tokens allowed to be transferred monthly to a specific exchange ID.                                                          |
| `addExchangeID`                                  | Tags an ONCHAINID as an exchange ID.                                                                                                            |
| `removeExchangeID`                               | Untags an ONCHAINID as an exchange ID.                                                                                                          |
| `isExchangeID`                                   | Checks if an ONCHAINID belongs to an exchange.                                                                                                  |
| `getMonthlyCounter`                              | Returns the current monthly counter of an investor's transfers to a specific exchange.                                                         |
| `getMonthlyTimer`                                | Returns the current timer of an investor's transfers to a specific exchange.                                                                   |
| `getExchangeMonthlyLimit`                        | Returns the monthly limit set for a specific exchange.                                                                                         |
| `complianceCheckOnExchangeMonthlyLimits`         | Checks the compliance status of a transfer based on the monthly limits for transfers to exchange wallets.                                      |
| `_transferActionOnExchangeMonthlyLimits`         | Updates the state of the compliance feature after a transfer, if the receiver address is linked to an exchange ID and the sender is not an agent. |
| `_creationActionOnExchangeMonthlyLimits`         | Updates the state of the compliance feature after a minting.                                                                                    |
| `_destructionActionOnExchangeMonthlyLimits`      | Updates the state of the compliance feature after a burning.                                                                                    |
| `_increaseExchangeCounters`                      | Checks if the monthly cooldown must be reset, and if the transfer value has been exceeded, increases the user's ONCHAINID counters.              |
| `_resetExchangeMonthlyCooldown`                  | Resets the monthly cooldown for an investor's transfers to a specific exchange.                                                                 |
| `_isExchangeMonthFinished`                       | Checks if the current month has ended for an investor's transfers to a specific exchange.                                                      |
