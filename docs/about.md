# About UniqVerse

## How we do it

We're using AI embedding models to convert content into vectorized form and place it into vector database. 
In this way, we index NFTs, registered through our platform as well as other popular NFT marketplaces.

When user want to check the authenticity of the content, we transform it with our AI model 
in the same way into vector know the distance to existing content.

There are two main use cases when user check the content:
1. User want to buy an NFT check if content is authentic, and it's not a duplicate of another NFT from our or other marketplaces.
2. User is a content creator and want to have a proof of uniqueness of his/her content.

When content creator find that his/her has a high rarity, 
he/she can create an NFT and register it on our platform to protect the intellectual property.

### Register new NFT flow

1. Save the content in IPFS/S3
2. Register an NFT with the content hash and add it into the content manager contract
3. Off-chain oracle listen for the events from content manager contract, when new NFT is registered:
   1. Uses AI model to create a vector
   2. Publish the vector in the IPFS/S3
   3. Publish the distance (rarity), and vector hash in the IPFS/S3
   4. Other oracles could check the published vector and if it's wrong, slash the publisher
4. After rarity publish and confirmation, user can use the NFT, for example, sell or rent rights for the content
