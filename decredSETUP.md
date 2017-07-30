Go to: https://github.com/decred/decred-release/releases/tag/v1.0.5

Download: dcrinstall-windows-amd64-v1.0.5.exe

Run the .exe

Find the directory. Should be: `C:\Users\<NAME>\decred\ `

---

* Open 3 cmd prompt windows.
  * On all 3 change the directory to the source:
	  `cd C:\Users\<NAME>\decred`
    
## First cmd prompt window:

* On the first one copy and paste below and hit enter.

  * `dcrd --notls --rpcuser=CHANGE --rpcpass=CHANGE --minrelaytxfee=0.01 --rpclisten=127.0.0.1`

* It will connect and download the blockchain. Leave this running in the background.


## Second cmd prompt window:

* Type: `dcrwallet --create`

* Create/enter a password. It wont display anything. 

* Type it again for confirm it. 

* Click no on addition security and no on an exisiting wallet.

* Copy your seed and Hex into a document and save it.

* Type: `OK`  (capital letters)

* Your wallet should be created successfully!

## Third cmd prompt window:

* Type and enter:

`dcrwallet --username=CHANGE --password=CHANGE --noclienttls --noservertls --walletpass public --dcrdusername=CHANGE --dcrdpassword=CHANGE --txfee=0.01`
(enter the same user/pass as the above RPC for both)

  * Enter your password. It should rescan blocks and eventually connect to blocks.
  
  * Leave running in the background.

## Back to Second cmd prompt window:

* Type: 

`dcrctl -u CHANGE -P CHANGE --wallet --notls walletpassphrase <password> 1000000`

(-u and -P is your user/pass from above. <password> is your wallet password, but don’t use the <> symbols)

* It should take you back to the directory.

* Type: 

`dcrctl -u CHANGE -P CHANGE --wallet --notls createnewaccount "testDECRED"`

(“testDECRED” is what I am calling this labelled address, use the quotation marks and label it what you want)

* It should take you back to the directory. 

* Type:

	`dcrctl -u CHANGE -P CHANGE --wallet --notls getnewaddress "testDECRED"`
  
  (getnewaddress " " is whatever you wrote on the above command)

* This should output your labelled address.

* Go to your xbridge and edit the parameters to match this address, rpc user/pass etc…

* Run xbridge.

