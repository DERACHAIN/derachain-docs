---
description: Guidance on How to create Dapp on NFT2.0 protocol
---

# Create Dapp

## 1. Creating a D-app Profile on NFT2Console

To start building your application on **DareProtocol**, you first need to create a **D-app Profile**. Follow the steps below to complete this process:

### Step 1: Connect Wallet & Access the Dashboard

* Visit **NFT2Console** and connect your wallet (Metamask or any EVM-compatible wallet).
* Once connected, the system will automatically register a **D-app Identity** for you on-chain.
*   From the Dashboard, you can begin creating your D-app profile by either:

    * Clicking the **"D-app Profile"** menu on the left sidebar,\
      **or**
    * Clicking the **"Create D-app profile"** button under the **Account Information** section.



    <figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Dashboard</p></figcaption></figure>

### Step 2: Fill in Your D-app Profile

On the profile creation screen, complete the following fields:

**Upload Profile Picture**

* Click the camera icon to upload an image that represents your D-app or game.
* Recommended format: JPG/PNG, under 2MB.

**D-app Name**

* Enter the official name of your D-app or project.

**About Game**

* Provide a brief description of your game or project.
* Keep it concise and highlight the key features or gameplay elements.

**Save Profile**

* Once all fields are completed, click the **“Save”** button to submit your profile.
* Your information will be stored and made publicly visible on DareProtocol.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>D-app Profile</p></figcaption></figure>

### Step 3: Submit Your D-app On-Chain

Once your **D-app Profile** is successfully saved, the next step is to **submit your data on-chain** to complete the D-app creation process.

1. **Return to the Dashboard**
   * After saving your D-app profile, head back to the **Account** page from the left-hand menu.
2. **Click "Create Data Registry"**
   * You’ll now see a **“Create data registry”** button become active at the bottom of the Account section.
   * Click this button to begin the on-chain submission process.
3. **Sign the Transaction in Wallet**
   * Your connected wallet will prompt you to **sign a transaction**.
   * Confirm the signature to finalize the creation of your D-app identity on the DareProtocol blockchain.
4.  **D-app Successfully Created**

    After completing the profile creation and signing the on-chain transaction, your D-app is now officially registered on the DareProtocol.

    **Account Information:**

    * **D-app Identity**\
      A unique identifier generated automatically when your wallet connects.
    *   **Registry URI**\
        A public IPFS link containing your D-app metadata.\
        Example:\
        `ipfs://QmYrWbByihwfev4vi96HVMLi3KbNi7rovfETtSpNcNaxn1`

        You can:

        * Click the **copy icon** to copy the link or click view detail data&#x20;
        * Click [**View on NFT2scan**](https://nft2scan.com/d-apps) to inspect your data on-chain

<figure><img src="../../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption><p>Create data registry</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption><p>Deploy data</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (4) (1).png" alt=""><figcaption><p><strong>D-app Successfully Created</strong></p></figcaption></figure>

## 2. Editing D-app Profile

On DareNFT Console, creators can freely update their D-app profile at any time. However, changes are **only stored off-chain until the user signs and submits them on-chain**.

**Steps to edit a D-app profile:**

1. **Go to `D-app Profile` from the sidebar menu**
   * You’ll see the current profile including:
     * Profile picture
     * D-app name
     * Description (About game)
2. **Click the `Edit` button** in the top right corner.
3. **Update any of the following fields:**
   * **Profile Picture**: Upload a new image if needed
   * **D-app Name**: Edit the name of your D-app (e.g., _Hunter_)
   * **About Game**: Update the description (e.g., _Max_)
4. **Click `Save`**
   * This will temporarily save your updates in the UI
5. **Go back to the `Account` page**
   * You’ll now see a next to `Update D-app profile`
   * This means your local profile has been updated, but not yet registered on-chain
6. **Click `Update data registry`**
   * This action triggers a wallet signature request
   * After confirmation, your new D-app data is uploaded to IPFS and registered on-chain
7. **View your changes**
   * Your new profile data will be available on-chain
   * `Registry URI` will update with a new IPFS hash
   * You can verify it via \[NFT2scan] or IPFS explorer

#### Notes:

* Changes are only made permanent **after signing the transaction via wallet**
* All updates are published via IPFS and visible in the `Registry URI`
* If you skip the final “Update data registry” step, your edits will **not** reflect on-chain

<figure><img src="../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption><p>D-app detail</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (6) (1).png" alt=""><figcaption><p>Edit D-app </p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Update Data registry</p></figcaption></figure>
