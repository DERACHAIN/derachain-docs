---
description: Guidance on How to register Dapp's data schema
---

# Register data schema

## 1. Overview <a href="#overview" id="overview"></a>

In traditional web2 games, game data such as game characters, game items and other game assets are created, updated and stored by the Game Provider. That means the assets can "die" when the game itself is no longer on service. However, in web3 games, players can truly OWN their game assets - in the form of Non-Fungible Tokens. Game data like character properties or item characteristics will be stored on blockchain as metadata of the NFTs, instead of in some whatever game server.

When players play your game, in-game data will regularly be updated into NFT metadata, which could be triggered by the player or the game system. The Protocol will inquire the in-game data from the Game Provider and push it on blockchain as game metadata of the NFT.

The article guides you to set up the data schema of the game assets.

## 2. Define metadata schema <a href="#define-metadata-schema" id="define-metadata-schema"></a>

### 2.1 Add default schema

Navigate to **Console** > **Dashboard** > **NFT Data Schema**. Here you can see the data schema of your game. For now, each Game ID can define only 01 data schema.\


<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>Add schema</p></figcaption></figure>

Data schema is defined in format of JSON, to list out all the game properties of the NFTs and their data type. This is to validate the payload whenever the NFT is updated with your game metadata. You can define one-by-one property in the "View as List" form, then Console will generate the JSON schema for you.

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Add default schema</p></figcaption></figure>

Or you can also write your own schema in JSON in "View as JSON" form.

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Add by JSON</p></figcaption></figure>

A valid data schema should look like:

```json
{
  "type": "object",
  "properties": {
    "LEVEL": {
      "type": "integer",
      "description": "hero level "
    },
    "ATK": {
      "type": "number",
      "description": "attack point",
      "minimum": 0,
      "maximum": 100
    },
    "DEF": {
      "type": "number",
      "description": "defence point",
      "minimum": 0,
      "maximum": 100
    },
    "HP": {
      "type": "integer",
      "description": "health point"
    }
  }
}
```

**Save Profile**

* Once all fields are completed, click the **“Save”** button to submit your profile.
* Your information will be stored and made publicly visible on DareProtocol.

**Submit your data on-chain**

Once your **NFT data schema** is successfully saved, the next step is to **submit your data on-chain** to complete the **NFT data schema** creation process.

1. **Return to the Dashboard**
   * After saving your **NFT data schema**, head back to the **Account** page from the left-hand menu.
2. **Click "Create Data Registry"**
   * You’ll now see a **“Create data registry”** button become active at the bottom of the Account section.
   * Click this button to begin the on-chain submission process.
3. **Sign the Transaction in Wallet**
   * Your connected wallet will prompt you to **sign a transaction**.
   * Confirm the signature to finalize the creation of your **NFT data schema** on the DareProtocol blockchain.

### 2.2 Add collection schema

After adding the **default schema**, users can also define a **collection schema** for any specific collection.

The process of adding a collection schema is almost identical to adding the default schema. The only additional step is to **enter the address of the collection** you want to assign the schema to.

**Steps Recap:**

1. Navigate to the **NFT Data Schema** section.
2. Choose **Add Collection Schema**.
3. Enter the **collection address** where this schema should be applied.
4. Input your desired schema (just like the default one).
5. Save and update.
6. Submit data on-chain

Now your schema is tied to a specific collection, allowing you more flexibility and customization!

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Add collection schema</p></figcaption></figure>
