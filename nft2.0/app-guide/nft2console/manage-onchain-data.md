---
description: Guidance about How to manage NFT's onchain data.
---

# Manage onchain data

## 1. Write data

The **Write Data** feature allows you to:

* Customize your NFT's metadata.
* Update trait values (e.g., power, level, HP).
* Apply full NFT2.0 schema for complete metadata replacement.
* Batch-write data to a range of NFTs for fast updates (e.g., in games, loyalty systems, etc.).

### Step-by-Step Guide

#### Step 1: Navigate to Write NFT Data

Go to your dashboard and choose the **Write Data** feature from the NFT2.0 Console menu.

#### Step 2: Choose Data Input Mode

* Enter collection address
* **Single NFT Mode:** Input a specific `Token ID`.
* **Batch Mode:** Input a range `Start Token ID` → `End Token ID`. Enter a key and value that will be applied to all NFTs in the range.

#### Step 3: Select Key (Data Field)

The key dropdown will auto-display options:

* If the collection **has a schema**, it will show:
  * `nft2.0 schema`&#x20;
    * Used to **overwrite the entire metadata** of the NFT.
    * The data must follow the **standard NFT 2.0 structure**.
    * Ideal for advanced use cases where you want to replace the whole NFT profile (name, image, attributes, etc.).
  * All collection schema keys (e.g., `Power`, `Agility`, `Score`)&#x20;
    * Used to write metadata **field-by-field**.
    * Allows partial updates to specific traits without affecting the rest of the NFT data.
    * Great for dynamic updates like stats, progress, badges, etc.
* If the collection **doesn’t have a schema**, it will show:
  * `nft2.0 schema`
  * Default property keys from your Dapp schema (e.g., `Level`, `HP`, etc.)

#### Step 4: Enter Value

* If using `nft2.0 schema`: the URI must follow a valid IPFS format to ensure proper resolution and compatibility with NFT platforms and explorers.

**Example URI:**

```
https://darenft.myfilebase.com/ipfs/QmYyBnhjwMxKXbhJYqGWST2R23ryz3K6C91nti1ZvUd7M3
```

* If using a property key: enter a value. Make sure to enter the value in the correct format according to the selected key (text, number, etc.).

#### Step 5: Submit Transaction

Click the **Write Data** button and confirm the transaction in your connected wallet. Once confirmed, the data will be stored on-chain.

***

### Notes

* Batch writes apply the **same key-value** to all NFTs in the selected range.
* Writing `nft2.0 schema` **replaces** the entire metadata for the NFT.
* Writing a property key only updates that specific trait without affecting others.
* You can write data multiple times to the same NFT.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Write data</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Write batch NFT data</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Select key</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption><p>NFT data</p></figcaption></figure>
