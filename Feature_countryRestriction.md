| Function | Visibility | Modifiers | Description |
|----------|------------|-----------|-------------|
| `batchRestrictCountries(uint16[] calldata _countries)` | External | N/A | Adds countries restriction in batch |
| `batchUnrestrictCountries(uint16[] calldata _countries)` | External | N/A | Removes countries restriction in batch |
| `addCountryRestriction(uint16 _country)` | Public | `onlyOwner` | Adds country restriction |
| `removeCountryRestriction(uint16 _country)` | Public | `onlyOwner` | Removes country restriction |
| `isCountryRestricted(uint16 _country)` | Public | N/A | Returns true if country is restricted |
| `complianceCheckOnCountryRestrictions(address /*_from*/, address _to, uint256 /*_value*/)` | Public | N/A | Checks the compliance status of a transaction based on the receiver's country restriction |
| `_transferActionOnCountryRestrictions(address _from, address _to, uint256 _value)` | Internal | N/A | State update post-transfer (no action) |
| `_creationActionOnCountryRestrictions(address _to, uint256 _value)` | Internal | N/A | State update post-minting (no action) |
| `_destructionActionOnCountryRestrictions(address _from, uint256 _value)` | Internal | N/A | State update post-burning (no action) |
