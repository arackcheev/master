# BLOCKNET
![alt text](https://github.com/Aderks/master/blob/master/pictures/block.PNG "Logo Title Text 1")

The Internet Of Blockchains

## Blocknet Decentralised Exchange Service Node Setup

**These instructions are to run as a servive node for the Blocknet Decentralised Exchange.** 

* Blocknet’s DX uses the xbridgep2p™ blockchain router technology to enable users to exchange tokens and assets, and to utilise smart contracts between blockchains.

## Overview
Setup requires an integration between the Blocknet wallet and the wallets of coins you want as currency pairs. At this stage, nothing is automated and the UI on the new Blocknet wallet will be used until the final UI is complete. Configuration is by manually creating (or editing) .conf files: 

 * blocknetdx.conf
 
 * servicenode.conf

 * xbridge.conf

 * configuration file for each currency you want to support

Integration is via the wallets’ RPC APIs. For security reasons we recommend that wallets all run on a single box and communicate over localhost (127.0.0.1), though wallets may also be run on multiple machines and connect via IP address. General documentation on JSON RPC features is available @ https://en.bitcoin.it/wiki/Running_Bitcoin.

## Requirements
* Two computers with the latest Blocknet client installed, encrypted, fully synced
   * One computer will be the Service Node Server which will need to be running 24/7
      * This guide will refer this computer as the " SNODE SERVER "
   * The other computer will be the client computer where the 5000 Block is locked. This doesn't need to run 24/7.
      * This guide will refer this computer as the " CLIENT "

* Your Public IP address or a VPS/VPN IP address

* 5000.000 Block to be locked into a service node address (the 5000 Block cannot stake while it is locked)

* The latest wallet of each currency you want to support on your service node (fully synced, encrypted)

* Properly configured .conf files each wallet


## Service Node Setup

* Download the latest wallet release on 2 computers or VPS 
   * [GitHub Releases](https://github.com/BlocknetDX/BlockDX/releases)
   
* On each computer let the wallet fully sync. Once that is complete encrypt both wallets with a password of your choice
   * If you are testing please use `testnet=1` or `-testnet` for `blocknetdx-qt.exe`
   
### CLIENT Computer Wallet Setup   
   
* Navigate the top toolbar to: `Tools > Debug console`
   * Type `getaccountaddress <name>` (This generates a public address key for your service node. Create a unique service node name.)
      * Ex: `getaccountaddress snode01`
      
   * Type `servicenode genkey` (This generates and ouputs your service node private key)
   
   * Take note of these generated outputs as they will be needed in the configuration files
   
* Whichever wallet your funds are located in send exactly 5000.00 Block (tBlock if on testnet) to the public address you created on the previous step
   * The address needs to have EXACTLY 5000.00 Block (tBLock) to work properly
   * When you send the 5000 Block, ensure "Send as zero-fee transaction if possible" is checked off
   
* Wait for the CLIENT computer to receive and confirm the 5000 Block TX

* Once the TX is fully confirmed navigate back to: `Tools > Debug console`
   * Type `servicenode ouputs` (This outputs the servicenode TX information needed in the `servicenode.conf`)
   
   * Take note of these generated outputs as they will be needed in the configuration files
   
* Go to [Google](www.google.com) and search "whats my ip". Your Public IP address will be displayed. Take note of this address as it will be needed in the configuration files.
   * Main-net users use IP_address:?????
   * Test-net users use IP_address:41474
   
* Navigate to your Blocknet data directory (default is: `%appdata%/roaming/blocknetdx/`)
   * Create/edit the `servicenode.conf` file (`/blocknetdx/testnet4/` for testnet users)
   
   * There should be an example of how the configuration needs to be in this file: (You can delete this after yours is typed in)
     * ex: `mn1 127.0.0.2:41474 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0`   
   
   * Enter your generated information from above in the format showed in the example:
   ```
   snode01 <your_public_IP:41474> <your_servicenode_private_key> <collateral_TX_ouput> <TX_ouput_index>
   ```
   
   * Save the `servicenode.conf` and restart the wallet. Fully unlock the wallet.
   
### SNODE Computer Wallet Setup

* Navigate to your Blocknet data directory (default is: `%appdata%/roaming/blocknetdx/`)
   * Create/edit the `blocknetdx.conf` file
     * If you are testnet `blocknetdx.conf` needs to stay in `%appdata%/roaming/blocknetdx/` and NOT in the `/testnet4/` folder
     
   * Type the following information into your `blocknetdx.conf` file:
   
   ```
   staking=0
   servicenode=1
   servicenodeaddr=<your_public_IP:41474>
   servicenodeprivkey=<your_servicenode_private_key>
   ```
   
   * Save the `blocknetdx.conf` and restart the wallet. Fully unlock the wallet.
   
### Starting Service Node(s)

* On the CLIENT computer navigate to the "Servicenodes" button on the GUI. If the setups were done correctly you should see all of your "Aliases"

* Click your Alias (ex: snode01), and then at the bottom click "Start alias" button on the GUI.
   * You should see a successful popup window. The status of your node should be "ENABLED" and show an "Active time"
   
![alt text](https://github.com/Aderks/master/blob/master/pictures/snode_alias.PNG "Logo Title Text 1")    
   
* At this time your Service Node is running successfully. You can close off the CLIENT computer Blocknet wallet if you want.   
   
* The CLIENT computer will receive the " Servicenode Rewards "


### Status Checks

* On the SNODE SERVER navigate the top toolbar to: `Tools > Debug console`
   * Type `servicenode debug` (This will output a message "Servicenode successfully started")
   
   * Type `servicenode status` (This will ouput your service node information and a successful message at the end of it)
   
![alt text](https://github.com/Aderks/master/blob/master/pictures/snode_status.PNG "Logo Title Text 1")    
   
* If you did not receive "Servicenode successfully started" proceed to the next "Troubleshooting section"

* If you received a "Servicenode successfully started" proceed to the next step of this setup
   
   
### Troubleshooting

* Ensure your `servicenode.conf` information is correct to your settings

* Ensure you dont have "< >" in any of the configuration files : (ex: `servicenodeaddr=<your_public_IP:41474>` should be `servicenodeaddr=127.0.0.1:41474`. "127.0.0.1 is an example IP address")
   * Ensure you are using the correct IP PORT #
     * Main-net=????? Test-net=41474

* Ensure on the CLIENT computer you only have a `servicenode.conf`, the `blocknetdx.conf` is not needed on the CLIENT computer
   * For testnet ensure `servicenode.conf` is located in `/testnet4/`

* Ensure on the SNODE SERVER computer you only have a `blocknetdx.conf`, the `servicenode.conf` is not needed on the SNODE SERVER computer
   * For testnet ensure `blocknetdx.conf` is located in `/blocknetdx/` and not `/testnet4/`
   * If you are a tester there will be a CMD line startup guide so you don't have to edit this configuration when you switch from main-net and test-net
   
* Ensure your configuration files are not `servicenode.conf.txt`

* Ensure the 5000 block is exactly 5000 block, no more or no less & ensure it is confirmed

* Ensure you wallets are fully sync'd and fully unlocked   
   
---

## Setup  .conf Files for the Wallets of Your Trading Coins:
The wallet of each coin you want to trade needs to be configured with a username/password and an allow from IP, if you’re using only a local machine use IP:127.0.0.1

 * To see a list of various wallet configurations go to: [Wallet Configurations](https://github.com/BlocknetDX/blocknet-docs/blob/master/walletsCONF.md)

 * Download the latest wallet, let it sync up fully, then close the wallet.

 * Click the START button on your desktop, where it says “Search program and files” then type “%appdata%” and the “Roaming” directory should pop up. Click on “Roaming” or hit enter.

 * Find your wallet’s designated data directory folder, ex: Bitcoin

 * If you don’t have a .conf file started you will need to open up Notepad to create one.

 * Copy and paste the following (this can be added to what is already present in file if you have “addnodes” or other configurations in here already):

```
server=1
listen=1
rpcuser=yourusername
rpcpassword=yourpassword
rpcallowip=127.0.0.1
enableaccounts=1 (required for BitBay and Syscoin; probably fine for other wallets)
staking=0 (required for BitBay and Syscoin; probably fine for other wallets)
```

 * Change `rpcuser` and `rpcpassword` to something unique to you. For security reasons you should have a different RPC username and password for each wallet. 

 * If you’re using a single machine use IP: `127.0.0.1`

 * When you are done, click File, Save as, Type in: “bitcoin.conf”.
    * Ensure the file is not “bitcoin.conf.txt”

 * Save it and then place the .CONF into its corresponding wallet folder.
    * For this example: %Appdata%/Roaming/Bitcoin 

 * Remember what you wrote for the username, password, and IP.

 * Create an identical .CONF file for each wallet you are going to be using on the decentralised exchange.
    * Ensure `rpcuser` and `rpcpassword` are different on each wallet for security purposes
 
---

## Configure Trading Coin Addresses
In each trading coin’s wallet, create a new address and label it something informative, like “DX address”. (xbridge expects a labelled receive address)

 * To create a new address, go to your wallet’s “receive” tab and click “new address”

 * To label an address, you may either right-click on it or click the “label” field.
 
 ![alt text](https://github.com/Aderks/master/blob/master/pictures/labelledaddress.PNG "Logo Title Text 1") 

 * This needs to be done for all wallets being used.


## Setup xbridge.conf

The Blocknet’s Xbridge technology is integrated into the latest client release. See [GitHub](https://github.com/BlocknetDX/BlockDX) for the source code.

 * To see the full list of coin .conf's see: [xbridge.conf](https://github.com/BlocknetDX/blocknet-docs/blob/master/xbridgeCONF.md)

 * Create/edit an `xbridge.conf` file and place the following configuration file in the blocknet wallet data directory (for Windows) C:\Users\[yourusername]\AppData\Roaming\blocknetdx\

 * Note: to avoid crashes or failed trades, please edit your `xbridge.conf` to feature only and all the coins you wish to have on your service node

 * Paste the RPC usernames and passwords you created for each currency pair into the “Username” and “Password” fields.
 
 * Paste the address of the "labelled receive address" you created for each currency pair.

 * If the port is unknown on the currency pair you want, you will need to find the port the wallet is using on Localhost. Here is a working method to do so:

    * Open Task Manager and go to the “details” tab
    * Locate the relevant wallet and make a note of its PID.
    * Run Command Prompt and type `netstat -ano | field “[PID]”.D]`
    * Look for an entry like the following: `TCP	0.0.0.0:9332   0.0.0.0:0     LISTENING   	5336`

 * The number after the colons in the IP address is the port to use (here, “9332”). Type it into `xbridge.conf` at the `Port=` line.

 * Note: wallets open different ports to connect to peers over the internet, and other ports on localhost for various purposes. The port you are looking for is a four-digit number after either the zero address (0.0.0.0) or localhost (127.0.0.1). The other ports use five-digit numbers.
 
 * Note: there may be more than one port open for your coin. In such cases, try the first one, and if it doesn’t work, try the next one.

 * Save the File (if you just edited the existing file, just click save, if you made a new file then click file, save as, and in the file name type: “xbridge.conf”).
    * Ensure the file is not “xbridgep2p.conf.txt”

 * Place this file into the Blocknet data directory folder: "C:\Users\[yourusername]\AppData\Roaming\blocknetdx\"

 * You will be coming back to this to edit it in the future to add future coins, and change `RPCusername` `RPCpassword` `Port` `Address` 
 
 * Do not change the other settings in the .CONF file unless you are conducting tests.
 

## Startup
 * Start the currency pair(s) you are running on your service node
    * Ensure the wallet is fully sync'd and unlocked

 * Start the Blocknet wallet on the SNODE SERVER computer after starting the other wallets.
 

## Verify communication between wallets.
In order to ensure that the xbridge client is communicating with your wallets and the .conf files are setup properly, on the Blocknet wallet, click the GUI “XBridge” tab  and then click the “Toggle to log” button.

As the wallet starts up, you’ll see the DX initialise using the values you entered into your `xbridge.conf` file:

![alt text](https://github.com/Aderks/master/blob/master/pictures/dx_start.PNG "Logo Title Text 1") 

 * Wait until you see “HTTP: resp 200” messages on the console. This signifies that the wallets are communicating over RPC and setup has been successful.
 
![alt text](https://github.com/Aderks/master/blob/master/pictures/resp200.PNG "Logo Title Text 1") 

 * Note: If, amidst the “HTTP: resp 200” messages, you see a message similar to `[I] 2017-Apr-19 17:48:31 [0x2],listaccounts exception couldn't connect to server`, then it is likely that at least one of your specified trading wallets have not been run.

 * Note: If you fail to get “HTTP: resp 200” messages, it’s possible that the ports assigned to wallets differ from those specified in your .conf file. To check this, open Command Prompt, type `netstat -an`, and take a look which ports are being used over localhost (127.0.0.1), or sometimes over 0.0.0.0.
 
 
## Problem Diagnosis
* To verify that each wallet is communicating with xbridge make sure the created receive addresses for each wallet is listed in the address book. If this part fails, close your wallets and review their configuration files. 

* Verify the ports are actually open. You may use Command Prompt to do so by typing in `netstat -an` and reviewing the print. Check that the ports you specified in the .conf files (ex: 8332 for Bitcoin) are open over localhost (127.0.0.1).

* Check that no OS-based firewall is blocking communication. You may do this through your firewall’s interface.

* Check the progress of RPC communication in C:\Users\yourusername\AppData\Roaming\blocknetdx\log

* Check the progress of CLTV-based coin exchange steps in C:\Users\yourusername\AppData\Roaming\blocknetdx\log-tx

* Check on general wallet events in C:\Users\yourusername\AppData\Roaming\walletname\testnet\debug.log
