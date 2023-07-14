# Capability Heist
Test your capabilities in Grand Theft Heist!

## Quest Overview
Explore the experimental capability module in Move through a bank heist. At each stage, there is a question to be answered which if answered correctly, provides the capability to perform the next leg of the heist. A complementary validator module is provided so you may compete with your friends and community to determine who deserves to be the real King of the Heist!

## Recommended Concepts
- Capability: Aptos' experimental module which allows capabilities to be created, managed and transferred
- aptos_hash: allows a secure, hashed submission to the validator module

## Quest Features
- Module capability_heist_core:
  - Contains the five capabilities of a successful bank heist
  - Initialize a resource account to manage the capabilities and designate the player as the Robber persona
  - For all five functions of the heist
    - Acquire the capability successfully from previous step
    - Assert the correct answer has been given for the current step
    - If correct, provide the capability to advance to the next step
- Module Validator:
  - There is no additional code required for this Module!
  - The validator checks for the correct hash of all answers and stores answers in a simple_map
  - There are some view functions - most important of which shows which addresses got all correct answers and deserve to be crowned King of the Heist!
