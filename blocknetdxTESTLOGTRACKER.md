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


## Sequence [SEQ]

### Issue #1: (re-test)
 * After a successful TX posting there is Block movement? (re-test to make sure). No coin movement. TX cancels.
 
 * See log below:

### Possible Solution(s):
 * Error code: ... 
 
### Dev Feedback/Status Update:

* 

## BitBay [BAY]

## Stratis [STRAT]

## Feathercoin [FTC]

## Quarkcoin [QRK]

## Blackcoin [BLK]

## Stealthcoin [XST]
### Issue #1:
* Waiting on new windows client w/ updated CLTV codework 

### Possible Solution(s):
* Wait for release of new wallet client, then begin testing

### Dev Feedback/Status Update:
* Forthcoming...

## Breakoutcoin [BRK]

## Breakoutstake [BRX]

## Bitswift [SWIFT]
### Issue #1:
* No CLTV support yet

### Possible Solution(s):
* CLTV is currently being implemented into BitSwift
* Once new wallet is out testing can begin

### Dev Feedback/Status Update:
* Forthcoming...

## Potcoin [POT]

## Peercoin [PPC]

## Bitconnect [BCC]

## Groestlcoin [GRS]

## Decred [DCR]

### Issue #1:
* Using CMD line wallet due to issues with Paymetheus

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

### Issue #2:
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
  
### Possible Solution(s):

* Need block to recognize 35 character long addresses or somehow decompress the address to be usable

### Dev Feedback/Status Update:

* 

## XCurrency [XC]
### Issue #1:
* Unsure if Xcurrency has CLTV support yet

### Possible Solution(s):
* Get confirmation on CLTV support
* Download and test trade

### Dev Feedback/Status Update:
* 

## Ethereum [ETH]
### Issue #1:
* Not support by Blocknet yet

### Possible Solution(s):
* Modify code to support ETH and ERC20 coins

### Dev Feedback/Status Update:
* Forthcoming...

## Zcash [ZEC]

### Issue #1:
* Not support by Blocknet yet

### Possible Solution(s):
* Modify code to support ZEC

### Dev Feedback/Status Update:
* Forthcoming...
  
## Siacoin [SIA]
### Issue #1:
* Haven't tested yet, might not be supported by Blocknet yet

### Possible Solution(s):
* Modify code to support SIA

### Dev Feedback/Status Update:
* 

## Bytecoin [BCN]
### Issue #1:
* Haven't tested yet, might not be supported by Blocknet yet

### Possible Solution(s):
* Modify code to support BCN and other CryptoNote based coins

### Dev Feedback/Status Update:
* 

## Nxt [NXT]

### Issue #1:
* NXT has its own CLTV/API, but it's different from Bitcoin based coins

### Possible Solution(s):
* Need to modify Block API to understand NXT API
* Once block can talk with NXT tests can be conducted

### Dev Feedback/Status Update:

* 
  
