# BLOCKNET
![alt text](https://github.com/Aderks/master/blob/master/pictures/block.PNG "Logo Title Text 1")

The Internet Of Blockchains

## Blocknet Decentralised Exchange Trader Setup Guide

**These instructions are to trade on the Blocknet Decentralised Exchange** 

* Blocknet’s DX uses the xbridgep2p™ blockchain router technology to enable users to exchange tokens and assets, and to utilise smart contracts between blockchains.

## Overview
Setup requires an integration between the Blocknet wallet and the wallets of coins you want to trade with. At this stage, nothing is automated and the UI on the new Blocknet wallet will be used until the final UI is complete. Configuration is by manually creating (or editing) .conf files: 

 * xbridge.conf

 * configuration file for each currency you want to support

Integration is via the wallets’ RPC APIs. For security reasons we recommend that wallets all run on a single box and communicate over localhost (127.0.0.1), though wallets may also be run on multiple machines and connect via IP address. General documentation on JSON RPC features is available at https://en.bitcoin.it/wiki/Running_Bitcoin.

## Requirements

* Latest Blocknet client installed, encrypted, fully synced

* Latest wallet of each currency you want to trade with (fully synced, encrypted)

     * Currency you want to trade with needs to be sent to a labelled receive address on each wallet 

* Properly configured .conf files for each wallet

---

## Setup  .conf Files for the Trading Wallets
The wallet of each coin you want to trade with needs to be configured with a username/password and an allow from IP, if you’re using only a local machine use IP:127.0.0.1

 * To see the full list of compatible wallet configurations go to: [Wallet Configurations](https://github.com/BlocknetDX/blocknet-docs/blob/master/walletsCONF.md)

 * Download the latest wallet, let it sync up fully, then close the wallet

 * Click the START button on your desktop, where it says “Search program and files” then type “%appdata%” and the “Roaming” directory should pop up. Click on “Roaming” or hit enter

 * Find your wallet’s designated data directory folder, ex: Bitcoin

 * If you don’t have a .conf file started you will need to open up Notepad to create one.

 * Navigate to [Wallet Configurations](https://github.com/BlocknetDX/blocknet-docs/blob/master/walletsCONF.md) and copy/paste the configuration information for the wallet you are running. (this can be added to what is already present in file if you have “addnodes” or other configurations already):
   * Ex: bitcoin.conf
   
   ```
   server=1
   listen=1
   rpcuser=yourusername
   rpcpassword=yourpassword
   rpcallowip=127.0.0.1
   ```
   
   * Ensure the configuration is correct. Do not assume the configurations are the same for each wallet.

 * Change `rpcuser` and `rpcpassword` to something unique to you. For security reasons you should have a different RPC username and password for each wallet

 * If you’re using a single machine use IP: `127.0.0.1`

 * When you are done, click File, Save as, Type in: `bitcoin.conf`
    * Ensure the file is not `bitcoin.conf.txt`

 * Save it and then place the .conf into its corresponding wallet folder
    * For this example: %Appdata%/Roaming/Bitcoin 

 * Remember what you wrote for the username, password, and IP

 * Create .conf files for each wallet you are going to be using on the decentralised exchange.
    * Ensure `rpcuser` and `rpcpassword` are different on each wallet for security purposes
 
---

## Configure Coin Addresses
In each wallet, create a new address and label it something informative, like “DX address” (xbridge expects a labelled receive address)

 * To create a new address, go to your wallet’s “receive” tab and click “new address”

 * To label an address, you may either right-click on it or click the “label” field.
 
 ![alt text](https://github.com/BlocknetDX/blocknet-docs/blob/master/pictures/labelledaddress.PNG "Logo Title Text 1") 

 * Send the funds you want to trade with to the labelled address
 
 * This needs to be done for all the wallets you want to trade with
 
---

## Setup xbridge.conf

The Blocknet’s Xbridge technology is integrated into the latest client release. See [GitHub](https://github.com/BlocknetDX/BlockDX) for the source code.

 * To see the full list of coin .conf's see: [xbridge.conf](https://github.com/BlocknetDX/blocknet-docs/blob/master/xbridgeCONF.md)

 * Create/edit an `xbridge.conf` file and place the following configuration file in the blocknet wallet data directory (for Windows) C:\Users\[yourusername]\AppData\Roaming\blocknetdx\

 * Note: to avoid crashes or failed trades, please edit your `xbridge.conf` to feature only and all the coins you wish to trade with

 * Paste the RPC usernames and passwords you created for each currency pair into the “Username” and “Password” fields
 
 * Paste the address of the "labelled receive address" you created for each currency pair
 
 * Ensure the rest of the configuration matches [xbridge.conf](https://github.com/BlocknetDX/blocknet-docs/blob/master/xbridgeCONF.md) for each coin

 * Save the File (if you just edited the existing file, just click save, if you made a new file then click file, save as, and in the file name type: `xbridge.conf`
    * Ensure the file is not `xbridge.conf.txt`

 * Place this file into the Blocknet data directory folder: "C:\Users\[yourusername]\AppData\Roaming\blocknetdx\"

 * You will be coming back to this to edit it in the future to add future coins, and change `RPCusername` `RPCpassword` `Port` `Address` 
 
 * Do not change the other settings in the .conf file unless you are on testnet conducting tests.
 
---

## Startup Sequence
 * Start the currency pair(s) you are trading with
    * Ensure every wallet is fully sync'd and unlocked

 * Start the Blocknet wallet after starting the other wallets.
     
---

## Verify communication between wallets.
In order to ensure that the xbridge client is communicating with your wallets and the .conf files are setup properly, navigate to the Blocknet data dir: C:\Users\yourusername\AppData\Roaming\blocknetdx\

   * Open the "log" folder. Open up the log file with the current date/time. Ex: `xbridgep2p_20170831T181856.log`
   * Each log file will update until the client instance is close. If a new client instance is opened a new log file will be created.

As the wallet starts up, you’ll see the DX initialise using the values you entered into your `xbridge.conf` file:

![alt text](https://github.com/BlocknetDX/blocknet-docs/blob/master/pictures/dxstart.PNG "Logo Title Text 1") 

 * Wait until you see “HTTP: resp 200” messages. This signifies that the wallets are communicating over RPC and setup has been successful. Ensure each wallet you are running displays a “HTTP: resp 200” and displays your labelled receive address name.
 
 ![alt text](https://github.com/BlocknetDX/blocknet-docs/blob/master/pictures/resp_200.PNG "Logo Title Text 1") 

 * Note: If, amidst the “HTTP: resp 200” messages, you see a message similar to `[I] 2017-Apr-19 17:48:31 [0x2],listaccounts exception couldn't connect to server`, then it is likely that at least one of your specified trading wallets have not been run.

 * Note: If you fail to get “HTTP: resp 200” messages, it’s possible that the ports assigned to wallets differ from those specified in your .conf file. To check this, open Command Prompt, type `netstat -an`, and take a look which ports are being used over localhost (127.0.0.1), or sometimes over 0.0.0.0.
 
--- 
 
## Place an Order
Once you’ve confirmed that the wallets are communicating and setup has been successful, do the following:

   * In the “BlocknetDX” tab of the Blocknet wallet, click on the “New Transaction” button. A new window will open:

   * Click on the “Address book” icon. This opens up a new window that displays the addresses you created in each currency pair wallet. 

      * Note: If you do not see these addresses, it means that your wallets are not communicating over RPC.

      * Note: It may take up to about 30 seconds for xbridgep2p to connect with your wallets, but once startup has completed it will populate your currency pair addresses.

      * Note: Do not manually paste an address into the “from” and “to” fields. Select addresses that xbridgep2p has been given by your currency pair wallets.

---

## Problem Diagnosis
* To verify that each wallet is communicating with xbridge make sure the created receive addresses for each wallet is listed in the address book. If this part fails, close your wallets and review their configuration files.

* If you made changes to any .conf file you need to close and restart that wallet, including Blocknet 

* Verify the ports are actually open. You may use Command Prompt to do so by typing in `netstat -an` and reviewing the print. Check that the ports you specified in the .conf files (ex: 8332 for Bitcoin) are open over localhost (127.0.0.1).

* Ensure all .conf files are configured properly. These configurations are very case-sensitive. Any wrong data entered in them could be causing the issues.

* Check that no OS-based firewall is blocking communication. You may do this through your firewall’s interface.

* Check the xbridge log for any errors in: C:\Users\yourusername\AppData\Roaming\blocknetdx\log

* Check on general wallet events in C:\Users\yourusername\AppData\Roaming\walletname\debug.log

---

## Security Tips
(With thanks to threepwood)

Since our technology essentially makes you your own exchange, here are some tips on how to keep your money safe.

   * The Blocknet’s team will never ask for your private keys or coins. Do not get fooled by impersonators.
Exchanges

   * Always move your coins from exchange to your private wallet.

   * Use long and random password.

   * Set up 2FA on logins and any withdrawals.

   * Disable password recovery via SMS/phone service. Disable all password recovery options for maximum security.

   * Recovery passwords are fine but keep them printed and offline.

   * Make sure your stored emails do not contain any extra information such as passwords or social security numbers.

   * Use different email addresses where possible. This limits the ability for hackers to run their automated "Forgot my password" links. 
   
   * Online Activity / Personal Information Disclosure. Do not promote your coin count etc online.

   * Limit your online public persona. This can attract unwanted attention which can make you a target.

   * Disable any online accounts you no longer use.

   * Assume hacking groups are building up social profiles on yourself. Your interests, time you are usually online, who you interact with.

   * Hacking groups use automated scripts so if those resources are exhausted they will try to social engineer your contacts.

   * Hacking groups are experts at social engineering. They have done this thousands of times.

   * Do not open random links and files provided in Slack, etc.

   * Do not fall for sob stories (Boohoo I lost all my coins) without proper due diligence.

   * Take multiple backups of your private keys regularly.

   * Verify backup by importing keys to the client.

   * Store your backups in M-DISC or in paper format.

   * Use dedicated wallet / staking PC and make it your safe haven. DO NOT USE IT FOR ANY OTHER ONLINE ACTIVITIES.

   * Encrypt your hard drives.

   * Use open source where possible.

   * Keep your software updated.

   * Do not install software from unknown 3rd party actors.

   * Use network level segmentation and mitigate attack surface against your wallet PC.
