##🧱 Sui NFT Mint Contract
This repository contains a simple Sui smart contract for minting NFTs (Non-Fungible Tokens) on the Sui blockchain using Move language. The contract enables users to mint unique digital assets, each represented as an NFT, with customizable metadata such as name, description, and image URL.

##📦 Features
Mint NFTs with custom metadata

Store NFTs securely in the owner's wallet

Use object::transfer to transfer NFTs to users

Compliant with Sui standards for digital assets
##📄 Smart Contract Overview
module my_project::nft_minter {
    use sui::object;
    use sui::transfer;
    use sui::tx_context::{TxContext};
    use sui::balance;

    struct MyNFT has key {
        id: UID,
        name: String,
        description: String,
        url: String,
    }

    public entry fun mint_nft(
        name: String,
        description: String,
        url: String,
        ctx: &mut TxContext
    ) {
        let nft = MyNFT {
            id: object::new(ctx),
            name,
            description,
            url,
        };
        transfer::transfer(nft, tx_context::sender(ctx));
    }
}
##🛠️ Dependencies
Move language

Sui SDK & CLI
##
📃 License
MIT License

