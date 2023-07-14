# Slice the JPEG
Adding fungibility to NFT object tokens and creating a platform to sell the fractions.

## Quest Overview
Fractionalize your NFTs and trade those fractions with AptosCoin. Explore adding fungibility through the Metadata object resource and deep dive into digital asset management through the use of refs and property maps. You are responsible for setting the price of the fractions, called SplitTokens, tracking supply and user balances on your very own Fractional Marketplace.
The Overmind Marketplace keeps things thrilling by allowing owners of a high enough percentage of fractionals to perform a call and buy out the remainder of the fractionals needed to grab the original NFT. The rest of the fractional holders may now only redeem their fractions for AptosCoin - you snooze, you loose!

## Recommended Concepts
- fungible_asset: to transform your singular NFT into tradeable pieces and manageable its tokenomics - total and circulating supply
- primary_fungible_store:​ to govern the fungible pieces by providing a deterministic store resource in user accounts
- property_map:​ to track key marketplace data such as price of fractions and origin NFT metadata
- Object standard:​ with a special focus on manipulating refs. 

## Quest Features
- init_module():
  - Create a resource account and initialize the global State resource.
  - Register AptosCoin for resource account to accept payments in AptosCoin.
  - Move the State resource to the resource account
- split():
  - Send the original NFT to the resource account
  - Call create_split_token_as_fungible_token helper function to create the fractional tokens for the original
  - Create the fractional object address and constructor_ref
  - Create Property Map tracking original token and fractional tokenomics
  - Create the primary fungible store for SplitTokens
  - Generate mint and burn refs for the SplitToken
  - Move the SplitToken resource under the created object address.
  - Mint the total supply of fractionals to the original NFT creator account
- redeem():
  - Assert that the owner attempting to redeem has amassed the total supply of all fractionals and is now redeeming for the original NFT.
  - Burn all fractionals.
  - Transfer original NFT to owner of fractionals.
- call():
  - Assert that the amount of SplitToken fractionals owned by the user exceeds the call_threshold and is eligible to perform a call.
  - Assert that the user owns enough AptosTokens to buy out the remainder of the fractional supply.
  - User pays the call_price for all remainder fractional supply
  - Burn user's fractionals and transfer original NFT to user.
- exchange_split_tokens_for_call_payment():
  - Assert original NFT has been redeemed already and so, owners of fractionals can only redeem their SplitTokens for AptosCoins.
  - Resource account pays user the call_price for the fractionals they own.
  - Burn all fractionals owned by user. 
