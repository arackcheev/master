# Blocknet DX Test Log Tracking

The purpose of this document is to identify DX errors through testing of new coins on the exchange whether it be on test-net or main-net. The chart below will be a general summary of the progress. After the general summary will be sections of each coin with the issues at hand and the progress of the resolution. There is no particular order in which coins are looked at first. 

This is community based testing and the information will be relayed to the developers of Blocknet for further assistance.

## General Summary

| COIN  | CLTV? | JSON RPC? | DX COMM? | TX POSTED? | BLOCK MOVEMENT? | MAKER RECEIVE COIN? | TAKER RECEIVE COIN? | STATUS or COMMENTS |
|:-------:|:-------:|:-----------:|:----------:|:------------:|:-----------------:|:---------------------:|:---------------------:|----------------------|
| SEQ   |YES    |YES        |YES       |YES         |YES              |NO                   |NO                   |                      |
| BAY   |YES    |YES        |YES       |YES         |NO               |NO                   |NO                   |                      |
| STRAT |       |YES        |YES       |YES         |                 |                     |                     |                      |
| FTC   |       |YES        |YES       |YES         |YES              |YES                  |NO                   |                      |
| QRK   |       |YES        |YES       |YES         |                 |                     |                     |                      |
| BLK   |       |YES        |YES       |YES         |NO               |                     |                     |                      |
| XST   |       |YES        |YES       |YES         |                 |                     |                     |                      |
| BRK   |       |YES        |YES       |NO          |                 |                     |                     |'INVALID TX ADDRESS ON TX POST'                      |
| BRX   |       |YES        |YES       |NO          |                 |                     |                     |'INVALID TX ADDRESS ON TX POST'                      |
| SWIFT |       |YES        |          |            |                 |                     |                     |                      |
| POT   |       |YES        |YES       |            |                 |                     |                     |                      |
| PPC   |       |YES        |YES       |            |                 |                     |                     |                      |
| BCC   |       |YES        |          |            |                 |                     |                     |                      |
| GRS   |       |YES        |YES       |            |                 |                     |                     |                      |
| DCR   |       |YES        |YES       |            |                 |                     |                     |                      |
| XC    |       |YES        |          |            |                 |                     |                     |                      |
| ETH   |       |           |          |            |                 |                     |                     |                      |
| ZEC   |       |           |          |            |                 |                     |                     |                      |
| SIA   |       |           |          |            |                 |                     |                     |                      |
| BCN   |       |           |          |            |                 |                     |                     |                      |
| NXT   |PROBABLE|PROBABLE  |          |            |                 |                     |                     |NOT LOOKED INTO YET   |

# NON - LOGGED COINS

 * Stealth [XST] >> TX decode failed
 * Emercoin [EMC] >> TX decode failed
 * Ioncoin [ION] >> TX decode failed
 * Verge [XVG] >> TX decode failed
 * Gulden [NLG] >> Labelled address wont show up >> Forced address in a TX >> Stays in HOLD

## Sequence [SEQ]
#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVXzZlRi1vWjBZUUE)
    
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVTTRNS2gycTZwV1E)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVaTdNai12bzNSd2s)
 
#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 * Contacted DYN/SEQ source to see if we can get assitance on SEQ. Possibly SEQ isn't CLTV but DYN is? 

## BitBay [BAY]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVSG12b2dDaWdPcEk)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVY1JsZm56dFNBakk)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVZXY1VUFDUzNDbms)
 
#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Stratis [STRAT]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVSDdHZW9UVGZEeDg)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVeHNjYURadjRFaUE)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVMXdLS0dERGVzbHc)
 
#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Feathercoin [FTC]
#### Issue #1 (code 5 no info about tx) & (code 25) :
 * After a successful TX FTC/SYS posting and TX acceptance there is Block movement
 * TX maker sends FTC out successfully
 * TX taker sends SYS out successfully
 * TX maker receives SYS successfully
 * TX taker does not receive FTC
 * DX status stays in a "Created" state
 * FTC stuck in P2SH Hash
  
  * See log's below:
 
    * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVamg4cVNNZG9VXzg)
  
    * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVcnVONE5iOTN2TXM)
  
    * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVWVR1UzR5LVpPTzg)
  
#### Possible Solution(s):
 * User configuration parameter error
 
#### Dev Feedback/Status Update:

*

## Quarkcoin [QRK]

#### Issue #1 (code 26 insufficient priority):
 * After a successful TX QRK/SYS posting and TX acceptance there is Block movement
 * TX maker sends QRK out successfully
 * TX taker sends SYS out successfully
 * TX maker receives SYS successfully
 * TX taker does not receive QRK
 * DX status stays in a "Created" state
 * QRK stuck in P2SH Hash
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVZ0JEdHhQejU3bmc)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVbEVoUFBDV2lTNVk)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVcmR4bGRJekF0aWs)

 #### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Blackcoin [BLK]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVeVFaSGRheG0zRHM)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVU1pWczhUM3g1eXM)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVSHFUbjRKZ2drdjg)
 
#### Possible Solution(s):
 * User configuration parameter error
 * Using new Lore client, not old QT client. Try old client?
  
#### Dev Feedback/Status Update:
 *  

## Potcoin [POT]

#### Issue #1:
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](
  
   * [Taker Log](
  
   * [Node Log](
 
#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Peercoin [PPC]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVVGZ4dkdYZWhGRTg)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVMG9SbUxKZnF5SEU)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVVFZnSm9WSGV1Rnc)

 #### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Bitconnect [BCC]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVbjRLNmRiU0FNcDA)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVamFTdEhUcnFGWE0)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVU3hMWjJqU3RvLWs)

 #### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Groestlcoin [GRS]

#### Issue #1:
 *  
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVQmY4TXJRZDVfajA)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVbm05Z01kWWl6WUk)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVSXNiNHpYYkFFd0U)

 #### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Decred [DCR]
#### Issue #1:
* Using CMD line wallet due to issues with Paymetheus
  * See CMD line setup here: https://github.com/Aderks/master/blob/master/decredSETUP.md

* Achieve resp 200 on Decred but with errors:

```
[I] 2017-Jul-30 09:48:57 [0x2] HTTP: resp 200 {"result":{"default":0,"imported":0,"testDECRED":0},"error":null,"id":1}
[I] 2017-Jul-30 09:48:57 [0x2] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["default"],"id":1}

[I] 2017-Jul-30 09:48:57 [0x2] HTTP: resp 200 {"result":null,"error":null,"id":1}
[I] 2017-Jul-30 09:48:57 [0x2] result not an array 
[I] 2017-Jul-30 09:48:57 [0x2] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["imported"],"id":1}

[I] 2017-Jul-30 09:48:57 [0x2] HTTP: resp 200 {"result":null,"error":{"code":-4,"message":"account not found"},"id":1}
[I] 2017-Jul-30 09:48:57 [0x2] error: {"code":-4,"message":"account not found"}
[I] 2017-Jul-30 09:48:57 [0x2] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["testDECRED"],"id":1}

[I] 2017-Jul-30 09:48:57 [0x2] HTTP: resp 200 {"result":["Dse7q6T1ZACC8SqMwMvSKkYGtF16RXXY9Ec"],"error":null,"id":1}
```

* With the error Block calls/recieves wallet and balance information from Decred
* Most likely the reason for Issue #2

#### Issue #2:
* When creating a new TX, and hit Post, we get a "invalid TX address"

* Decred uses a 35 character address, whereas the majority of others use 34 and sometimes 33 character addresses

 * Attempts were made to decompress base58 and remove the last 4 bytes for checksum, and the 2nd byte for color byte
 * With the removal of the 2nd byte of HEX, we then converted back to Base 58 and forced a TX off that address, see below:
 
```
[I] 2017-Jul-30 01:58:23 [0x1] HTTP: resp 200 {"result":[{"txid":"0f85c55d26e2d7b07e0bce816499ff1661e6b269e389529c8fee18a32643be1b","vout":2,"address":"Sbxd4x4FnJzbFGdapFKoiMxh4zBxRqyztX","v2address":"1Ffd37H73woPixr8GpLjATp8RCxXcNs8y4","account":"","scriptPubKey":"76a914a0dfa62eb2485183e2b75d8d6ba80852d3f6e38a88ac","amount":68.97999200,"confirmations":11232,"spendable":true,"solvable":true},{"txid":"1b429eceb7fde8ec155c43aeb9fb6ab9f814767c9ff4bc070a819a2a86fd519b","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":11816,"spendable":true,"solvable":true},{"txid":"80651921aa40eba9dbe3a563530752a4d343d314e55e867c3628622f6a33ecbb","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":11760,"spendable":true,"solvable":true},{"txid":"36f590f2f707de7e13941a46eca16b88fc9af364fbe97d60271e987bd5de95d0","vout":2,"address":"SfWjtYYg9RR95CuNUjpGaeny82x685NyHG","v2address":"1KDjrhmXR4DwYu7uwJqC2keQUFifKCF7VU","account":"","scriptPubKey":"76a914c7db07e4420d6ff99bfc6127a417bee51e58963a88ac","amount":3.68719360,"confirmations":12543,"spendable":true,"solvable":true},{"txid":"b75d742be3b652bd9f618e61fc2b1e11903298bcfac26929c50e2976d509abe6","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":11697,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Jul-30 01:58:26 [0x1] rpc call <listunspent>
[I] 2017-Jul-30 01:58:26 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Jul-30 01:58:26 [0x1] HTTP: resp 200 {"result":null,"error":null,"id":1}
[I] 2017-Jul-30 01:58:26 [0x1] result not an array 
[I] 2017-Jul-30 01:58:26 [0x1] rpc::listUnspent failedgetAccountBalance
[I] 2017-Jul-30 01:58:32 [0x1] rpc call <listunspent>
[I] 2017-Jul-30 01:58:32 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Jul-30 01:58:32 [0x1] HTTP: resp 200 {"result":[{"txid":"0f85c55d26e2d7b07e0bce816499ff1661e6b269e389529c8fee18a32643be1b","vout":2,"address":"Sbxd4x4FnJzbFGdapFKoiMxh4zBxRqyztX","v2address":"1Ffd37H73woPixr8GpLjATp8RCxXcNs8y4","account":"","scriptPubKey":"76a914a0dfa62eb2485183e2b75d8d6ba80852d3f6e38a88ac","amount":68.97999200,"confirmations":11232,"spendable":true,"solvable":true},{"txid":"1b429eceb7fde8ec155c43aeb9fb6ab9f814767c9ff4bc070a819a2a86fd519b","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":11816,"spendable":true,"solvable":true},{"txid":"80651921aa40eba9dbe3a563530752a4d343d314e55e867c3628622f6a33ecbb","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":11760,"spendable":true,"solvable":true},{"txid":"36f590f2f707de7e13941a46eca16b88fc9af364fbe97d60271e987bd5de95d0","vout":2,"address":"SfWjtYYg9RR95CuNUjpGaeny82x685NyHG","v2address":"1KDjrhmXR4DwYu7uwJqC2keQUFifKCF7VU","account":"","scriptPubKey":"76a914c7db07e4420d6ff99bfc6127a417bee51e58963a88ac","amount":3.68719360,"confirmations":12543,"spendable":true,"solvable":true},{"txid":"b75d742be3b652bd9f618e61fc2b1e11903298bcfac26929c50e2976d509abe6","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":11697,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Jul-30 01:58:32 [0x2] broadcast message, command 6
[T] 2017-Jul-30 01:58:32 [0x2] received packet, command code <6>
[T] 2017-Jul-30 01:58:32 [0x2] [] processTransactionHold
[I] 2017-Jul-30 01:58:33 [0x2] received message to GsEm68N/jr65zMlWWO/RXTpS6b4= command 7
```
* Stays in 'Hold' state, due to unrecognized forced address
  
#### Possible Solution(s):

* Need block to recognize 35 character long addresses or somehow decompress the address to be usable

#### Dev Feedback/Status Update:

* 

## GameCredits [GAME]

#### Issue #1 (code 25):
 * After a successful TX GAME/SYS posting and TX acceptance there is Block movement
 * TX maker sends GAME out successfully
 * TX taker sends SYS out successfully
 * TX maker receives SYS successfully
 * TX taker does not receive GAME
 * DX status stays in a "Created" state
 * GAME stuck in P2SH Hash
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVZW4yMzByeHltc28)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVLXZNOEcza2hrVDQ)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVUWpqTzByYmRiQ1E)
 
#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  

## Reddcoin [RDD]

#### Issue #1 (code 26):
 * After a successful TX RDD/SYS posting and TX acceptance there is Block movement
 * TX maker sends RDD out successfully
 * TX taker sends SYS out successfully
 * TX maker receives SYS successfully
 * TX taker does not receive RDD
 * DX status goes into "Cancelled" state
 * RDD stuck in P2SH Hash
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVdlNJLXVyZUpwOVk)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVazhPcmRTWVhEUms)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVSl9ZZzV2ejR5YVU)
 
#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *  
 
## Cloakcoin [CLOAK]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVVnBVcFdHQ2pOX2s)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVMkVNeU41SEplMzA)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVaV9BV1BGVjJiamc)

 #### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 *   
 
## CLAMcoin [CLAMS]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVWE1CcHljeTc5SEk)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVYTRwWHY0bWVwU2s)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVTVlNSGdKNjZCUW8)

 #### Possible Solution(s):
 * User configuration parameter error
 
 #### Dev Feedback/Status Update:
 *
 
## LEOcoin [LEO]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVSWdLNjJhMmVkbms)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVZlF5blNtdWx3NzA)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVSVkxVEN0dkk3Q3c)

 #### Possible Solution(s):
 * User configuration parameter error
 
 #### Dev Feedback/Status Update:
 *
 
## Nubits [NBT]

#### Issue #1 (code 22 TX decode failed):
 * After a successful TX posting there is Block movement. No coin movement after accepted TX. TX cancels.
 
 * See log's below:
 
   * [Maker Log](https://drive.google.com/open?id=0By-umY3NmpLVUWV0eW0tYUxEZUk)
  
   * [Taker Log](https://drive.google.com/open?id=0By-umY3NmpLVYWNBbThfRmhfSzQ)
  
   * [Node Log](https://drive.google.com/open?id=0By-umY3NmpLVOTZ2dDBjeVdoNnc)

 #### Possible Solution(s):
 * User configuration parameter error
 
 #### Dev Feedback/Status Update:
 *

---
---
# Future Coin's

## Stealthcoin [XST]
#### Issue #1:
* Waiting on new windows client w/ updated CLTV codework 

#### Possible Solution(s):
* Wait for release of new wallet client, then begin testing

#### Dev Feedback/Status Update:
* Forthcoming...

## Breakoutcoin [BRK]

## Breakoutstake [BRX]

## Bitswift [SWIFT]
#### Issue #1:
* No CLTV support yet

#### Possible Solution(s):
* CLTV is currently being implemented into BitSwift
* Once new wallet is out testing can begin

#### Dev Feedback/Status Update:
* Forthcoming...

## XCurrency [XC]
#### Issue #1:
* Unsure if Xcurrency has CLTV support yet

#### Possible Solution(s):
* Get confirmation on CLTV support
* Download and test trade

#### Dev Feedback/Status Update:
* New wallet with codebase in the future

## Ethereum [ETH]
#### Issue #1:
* Not support by Blocknet yet

#### Possible Solution(s):
* Modify code to support ETH and ERC20 coins

#### Dev Feedback/Status Update:
* Forthcoming...

## Zcash [ZEC]

#### Issue #1:
* Not support by Blocknet yet

#### Possible Solution(s):
* Modify code to support ZEC

#### Dev Feedback/Status Update:
* Forthcoming...
  
## Siacoin [SIA]
#### Issue #1:
* Haven't tested yet, might not be supported by Blocknet yet

#### Possible Solution(s):
* Modify code to support SIA

#### Dev Feedback/Status Update:
* 

## Bytecoin [BCN]
#### Issue #1:
* Haven't tested yet, might not be supported by Blocknet yet

#### Possible Solution(s):
* Modify code to support BCN and other CryptoNote based coins

#### Dev Feedback/Status Update:
* 

## Nxt [NXT]
#### Issue #1:
* NXT has its own CLTV/API, but it's different from Bitcoin based coins

#### Possible Solution(s):
* Need to modify Block API to understand NXT API
* Once block can talk with NXT tests can be conducted

#### Dev Feedback/Status Update:

*   
