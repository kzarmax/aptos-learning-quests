# Longswords & Dragons
Breed mythical creatures and refine weaponry

## Quest Overview
In a land far far away, there exist ferocious creatures and legendary weapons. Each dragon and sword have been digitalised in an NFT - from the sharpness of a sword to the breeding time of a dragon. Dragons and longswords can be created in the fantasy world through providing existing NFT collections. In this ever-after land, two dragons multiply through breeding. Respect breeding times for successful hatching! Longswords, on the other hand, are upgraded in a forge which consumes 2 - 10 pieces of original equipment. This is only the start to an epic adventure...
​
## Recommended Concepts
- TokenV2: standard for NFTs
- SimpleMap: to manage collections of beast and steel
- Timestamp: for successful hatching of creatures
- bcs​ and aptos_hash: for those who wish to learn the cryptographic ways of monster breeding and equipment improvement  
​
## Quest Features
- create_dragon_collection() / create_dragon():
  - Create a new collection of monsters
  - Define their starting characteristics
  - Let the Breeder know about the new monster race
  - Create a new monster token based on available collection
- create_sword_collection() / create_sword():
  - Supply a new collection of Equipment
  - Check the combine amount is met to forge a new equipment
  - Create a new Equipment token from provided collection
- breed_dragons():
  - Signer of the transaction must be the owner of the NFTs
  - NFTs must be from the same collection
  - Blocks transfer of the NFTs for amount of time specified while creating the collection
- hatch_dragon():
  - Unlocks monsters locked for breeding if the breeding finished
  - Signer of the transaction must be the owner of the NFTs
  - Creates a new monster NFT with combined properties and transfers it to the owner
- combine_swords():
  - Burns amount of equipment tokens specified while creating the collection
  - Tokens must be from the same collection
  - Signer of the transaction must be the owner of the NFTs
  - Creates a new equipment token with combined properties
