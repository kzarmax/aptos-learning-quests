# Diamons Are For Clicking
Build an empire of efficient diamond clicking

# Quest Overview
Inspired by the popular Cookie Clicker web game, create a diamond mining empire by clicking and buying upgrades. Start with simply clicking 1 diamond at a time and progressively purchase upgrades which auto-mines a certain number of diamonds per minute. Work smart, not hard!

# Recommended Concepts
- Vector to store upgrades and read their properties  
- Signer​ to manage GameStore  
- Timestamp​ to track time between claiming diamonds

# Quest Features
- click():
  - Each click adds one diamond to the GameStore
- get_unclaimed_diamonds ():
  - get the minutes elapsed between now and the previous timestamp
  - loop through the upgrades vector to get all current upgrades and its multiplicative upgrade_amount
  - loop through the POWERUP_VALUES and get dpm (diamonds per minute
  - calculate total_upgrade_amount (dpm x upgrade_amount) for each upgrade
- claim ():
  - claim all unclaimed diamonds up to current time point
  - update GameStore states
- upgrade ():
  - player buys an upgrade to increase auto mining efficiency
  - check that player has enough diamonds currently to afford the upgrade, and possibly any multiplicative amounts
  - use base amount if no multiplier was specified
  - update the GameStore state
