# How to find .CONF Prefixes Instructions

1. Address Prefix

  1. Go to: http://lenschulwitz.com/base58
  2. Enter wallet address into Base 58 Decoder
  3. First 2 digits of HEX copy into: http://www.binaryhexconverter.com/hex-to-decimal-converter
  4. Decimal value = address prefix

2. Script Prefix

Go to wallet console
Type validateaddress <wallet address>
Copy pubkey
If it says something about locked wallet go `walletpassphrase <walletpassword> <pick a number in seconds> example: `walletpassphrase password 10000`
Type decodescript <enter copied pubkey from step 3>
Take the p2sh output and decode that to HEX on the base58 website
Then convert first 2 digits of hex. decimal value = script prefix

3. Secret Prefix

Go to wallet console
Type dumpprivkey <wallet address>
Copy the privkey. 
Decode the privkey to HEX on the base 58 website
Then convert first 2 digits of hex. decimal value = secret prefix

4.  RPC Port

Search wallet’s GitHub, official webpage, bitcointalk, general google searches
Try some of the website sources listed below on the next page
Under the wallets Debug or Tool menu, click the Peers tab. The IP address port is usually 1 below what is listed. This only works sometimes.
From command line (windows: `netstat -an` / linux: `netstat -anp`) That should show open ports (on windows it wont’ show the process, but there is a GUI that does)
