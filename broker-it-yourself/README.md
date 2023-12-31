# Broker it yourself
Build a peer-to-peer exchange for non-custodial trading of Aptos assets for cash.

## Quest Overview
Look no further, OvermindSwap is here! Or maybe its OvermindPay? This decentralized platform allows trades to be fulfilled and disputes managed in a completely peer-to-peer way. Learn how to operate your own fiat to crypto platform using the AptosToken and think about the types of disputes which may arise and resolution mechanisms.
This quest was created to serve as fuel for your entrepreneurial spirit. There are many product functionalities and security checks not yet in place.

## Recommended Concepts
- AptosCoin: manage digital assets securely and fairly
- SimpleMap and Vector: track offers and global state
- Optionally, Generics: if you want to easily add more currencies to the platform, learning about generics is important

## Quest Features
- init(): 
  - Initialize a resource account as the platform that manages all trades.
  - Register the resource account with AptosCoin in order to allow APT token movement through the resource account
  - Initialize the State resource and move it to the resource account to track global state.
- create_offer():
  - Get the offerID through the inline helper function get_next_offer_id.
  - Update the global state with new offer.
  - If the offer is a sale, check offer creator's AptosCoin balance and lock the appropriate amount of tokens in the resource account.
  - Emit an event upon successful offer creation.
- accept_offer():
  - Assert that offer state allows acceptance.
  - Add counterparty address.
  - If it is a buy offer, check buyers coin balance and lock their tokens.
  - Emit an event upon successful acceptance of offer.
- complete_offer():
  - Assert that the offer is accepted and not disputed.
  - Either party in the offer may mark complete
  - Emit an event that offer completion was raised.
  - If both parties have marked completion. Remove the offer from global state and transfer the APT tokens.
  - Emit another event to track the transfer.
- cancel_offer():
  - Only the offer creator may cancel an offer while it is not under dispute.
  - Remove the offer from the global listing. 
  - If the offer was a sell offer, unlock creator's tokens
  - Emit a cancel event.
- open_dispute():
  - Either party can open a dispute if they are offer participants.
  - Set disput flag to true and emit an event.
- resolve_dispute():
  - Only the arbiter listed in the offer may resolve a dispute.
  - The arbiter may:
  - Terminate the offer and give locked tokens to creator
  - Terminate the offer and give locked tokens to counterparty
  - Close the dispute without taking any action
  - Mark the dispute as resolved by emitting an event
