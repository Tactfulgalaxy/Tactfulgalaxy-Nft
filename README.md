 A Gas-Efficient NFT Minting Project
A decentralized NFT project built on ERC-721, allowing users to mint, transfer, and update NFTs with efficient on-chain metadata storage. This project includes two types of NFTs:

BasicNft → Simple ERC-721 NFT with an IPFS-stored image.
MoodNft → Fully on-chain dynamic NFT that changes based on user interaction.
Built using Foundry for fast development, testing, and deployment.

📌 Features
✅ Mint NFTs with unique metadata and images.
✅ On-chain metadata for MoodNft (dynamically changes).
✅ Gas-efficient implementation using OpenZeppelin standards.
✅ Compatible with OpenSea & other marketplaces.
✅ Foundry-based testing & deployment.

🔗 Smart Contract Overview
BasicNft.sol – Simple NFT Contract
Function	Description
mintNFT(string memory tokenUri)	Mints an NFT with an IPFS metadata URI
tokenURI(uint256 tokenId)	Returns the metadata URL for a given token
getTokenCounter()	Returns the number of NFTs minted
MoodNft.sol – Dynamic NFT Contract
Function	Description
mintNft()	Mints a Mood NFT (default mood: Happy)
flipMood(uint256 tokenId)	Allows the owner to change the NFT’s mood
tokenURI(uint256 tokenId)	Returns on-chain encoded metadata
📌 Standard: ERC-721
📌 Chain: Ethereum, Polygon, Arbitrum (EVM-compatible)
📌 Marketplace Compatibility: OpenSea, Blur, LooksRare

🚀 Quick Start
1️⃣ Install Foundry
sh
Copy
Edit
curl -L https://foundry.paradigm.xyz | bash
foundryup
2️⃣ Clone & Install Dependencies
sh
Copy
Edit
git clone https://github.com/Tactfulgalaxy/MyNFT-Project.git
cd MyNFT-Project
forge install
3️⃣ Compile & Deploy
sh
Copy
Edit
forge build
forge create --rpc-url $RPC_URL --private-key $PRIVATE_KEY src/BasicNft.sol:BasicNft
forge create --rpc-url $RPC_URL --private-key $PRIVATE_KEY src/MoodNft.sol:MoodNft
(Replace $RPC_URL & $PRIVATE_KEY with your values)

4️⃣ Mint an NFT
Mint BasicNft
sh
Copy
Edit
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY \
    "0xYourContractAddress" "mintNFT(string)" "ipfs://your-metadata-uri"
Mint MoodNft
sh
Copy
Edit
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY \
    "0xYourMoodNftAddress" "mintNft()"
5️⃣ Flip Mood (For MoodNft)
sh
Copy
Edit
cast send --rpc-url $RPC_URL --private-key $PRIVATE_KEY \
    "0xYourMoodNftAddress" "flipMood(uint256)" 0
🧪 Running Tests
sh
Copy
Edit
forge test -vvv
✅ Ensures correct minting, metadata retrieval, ownership checks, and state updates.

🎨 OpenSea & Metadata Example
Example metadata.json for BasicNft (stored on IPFS):

json
Copy
Edit
{
  "name": "MyNFT #1",
  "description": "A unique NFT from MyNFT Project.",
  "image": "ipfs://QmExampleHash",
  "attributes": [
    { "trait_type": "Background", "value": "Blue" },
    { "trait_type": "Rarity", "value": "Legendary" }
  ]
}
For MoodNft, metadata is fully on-chain and changes dynamically.

📜 License
Licensed under MIT.

👨‍💻 Author: TactfulGalaxy 🌌

🔥 Deploy & Mint NFTs on-chain today! 🚀#   T a c t f u l g a l a x y - N f t  
 #   T a c t f u l g a l a x y - N f t  
 