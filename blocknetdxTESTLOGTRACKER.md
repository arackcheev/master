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
#### Issue #1: (re-test)
 * After a successful TX posting there is Block movement? (re-test to make sure). No coin movement. TX cancels.
 
 * See log below:
 
 * MAKER SEQ/SYS LOG:
```[I] 2017-Aug-07 23:54:16 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: resp 200 {"result":{"":54.99000000,"DX testaddress":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: resp 200 {"result":["BFvDdaevmnqYMAFz4a5WL5ck932eXEXA2y"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: resp 200 {"result":{"":0.32824477,"BitconnectTest":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["BitconnectTest"],"id":1}

[I] 2017-Aug-07 23:54:16 [0x3] HTTP: resp 200 {"result":["8djfkGB6Qrbhk312nkvNjgtLr75XbNmqEn"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:17 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:18 [0x1] rpc call <listunspent>
[I] 2017-Aug-07 23:54:18 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 23:54:18 [0x1] HTTP: resp 200 {"result":[{"txid":"958de869269727bcaab5b0d4e4f6a67b0c8e51bc2b48ccf180e2eaae9b18cb2e","vout":0,"address":"SkQagsidSefbB7rVWjG5RiNDXMbxMrUAk2","scriptPubKey":"76a914fd897bb31fd8f75ba966effe10ec63c3d28957a588ac","amount":69.79800000,"confirmations":7785,"spendable":true}],"error":null,"id":1}

[I] 2017-Aug-07 23:54:18 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:18 [0x2] broadcast message, command 22
[T] 2017-Aug-07 23:54:18 [0x2] received packet, command code <22>
[I] 2017-Aug-07 23:54:18 [0x2] unknown transaction Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc= processTransactionCancel
[I] 2017-Aug-07 23:54:18 [0x2] broadcast message, command 22
[T] 2017-Aug-07 23:54:18 [0x2] received packet, command code <22>
[I] 2017-Aug-07 23:54:18 [0x2] unknown transaction Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc= processTransactionCancel
[I] 2017-Aug-07 23:54:18 [0x2] broadcast message, command 4
[T] 2017-Aug-07 23:54:18 [0x2] received packet, command code <4>
[T] 2017-Aug-07 23:54:18 [0x2] [] processPendingTransaction
[I] 2017-Aug-07 23:54:19 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:19 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:19 [0x3] HTTP: resp 200 {"result":{"":0.06557233,"BTC Test":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:19 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["BTC Test"],"id":1}

[I] 2017-Aug-07 23:54:19 [0x3] HTTP: resp 200 {"result":["1MWH86khL7wXtXWiNMG5HGAb6d7FKgW6Rn"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:20 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:20 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:20 [0x3] HTTP: resp 200 {"result":{"":-0.02241300,"DashTest":0.52509466},"error":null,"id":1}

[I] 2017-Aug-07 23:54:20 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DashTest"],"id":1}

[I] 2017-Aug-07 23:54:20 [0x3] HTTP: resp 200 {"result":["XsxGNC4hxaa5m4JeVm3FT5eQNR7fYK3BxH"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":{"":-5215.01000000,"DX testaddress":5398.85437500},"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":["DKYuPPJdtUjnC7iPBVjrnWQAmDV8EygP7M"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":{"":1718.96232000,"DX testaddress":400.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":["D6m5WZM78ciTQygp2oLvfPubtEFZtgKjia"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":{"":26.37971541,"DynamicTest":1.70000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DynamicTest"],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":["DSHQkWfWvi1ZbTJvBULiENVbatPMbJKavh"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":{"":55.61562500,"DX testaddress":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":["6gEBq2VX5wB8qPhrXyZxuFndycFo9GwGq8"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":{"":-0.81499800,"GameCredits Test":1.90000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["GameCredits Test"],"id":1}

[I] 2017-Aug-07 23:54:21 [0x3] HTTP: resp 200 {"result":["GUn81fe2HDDLsdkQaepVmvPgrqHWkDKM6W"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:22 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:22 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:22 [0x3] HTTP: resp 200 {"result":{"":-7.01000000,"GUI":4.49000000,"LBRY Test":5.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:22 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["GUI"],"id":1}

[I] 2017-Aug-07 23:54:22 [0x3] HTTP: resp 200 {"result":["bGzkPgkR4WRK1XWDpPuE4GWqYgHpSW2U8o"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:22 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["LBRY Test"],"id":1}

[I] 2017-Aug-07 23:54:22 [0x3] HTTP: resp 200 {"result":["baepKENi7HzBDUZMAriDCm4Qti4wrhMbnX","bag1tekFFqR4aPBSxZpEXbZuFWvHn29Ykg"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:23 [0x2] broadcast message, command 4
[T] 2017-Aug-07 23:54:23 [0x2] received packet, command code <4>
[T] 2017-Aug-07 23:54:23 [0x2] [] processPendingTransaction
[I] 2017-Aug-07 23:54:23 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:23 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: resp 200 {"result":{"":-5.98299600,"LitecoinTest":7.25589846},"error":null,"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["LitecoinTest"],"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: resp 200 {"result":["Lb8EMPmqaR9GRt9FxMJrUC6Gs5gaami3Dh"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: resp 200 {"result":{"":87.96323000,"MUETest":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["MUETest"],"id":1}

[I] 2017-Aug-07 23:54:23 [0x3] HTTP: resp 200 {"result":["7V7qUsNWyV1dYxqZqMMaRuQ7osd3YXiQj7"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:24 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: resp 200 {"result":{"":1.71472737,"NamecoinTest":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["NamecoinTest"],"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: resp 200 {"result":["N2H6BXhNBkKriQQYCskKR1Y2GrmQzd9Wux"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: resp 200 {"result":{"":2.28646495,"DX testaddress":1.85000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:24 [0x3] HTTP: resp 200 {"result":["DSYh1dPSdVowvXtnkur2MQhvG8duwiSWxK"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:25 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:25 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:26 [0x3] HTTP: resp 200 {"result":{"":7.98000000,"PeercoinTest":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:26 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["PeercoinTest"],"id":1}

[I] 2017-Aug-07 23:54:26 [0x3] HTTP: resp 200 {"result":["PGr9Dn4tTKy9HdbZcBJ4KL6KHA9bi47Wxg"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":6.99700000,"QTUM Test":192.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["QTUM Test"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["QVjBfxGFWQTkbqQbGPPYqeNiA993Nn3eYj"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":0.00000000,"Redd Test":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["Redd Test"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["RfyiwaK7MzDucZ6rwVAHXhJJHBLAFtwHtu"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":-1080.200000,"DX testaddress":1149.80000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["SWaiTyjWpzVCyKhzxdfny7GU37fd8hd9wM"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":1.80000000,"DX testaddress":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["DX testaddress"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["SZiTPGoXMzgEZYnDof3wyTABU9dzyPcg7G"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":255.55737677,"SyscoinTest":106.54299700},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["SyscoinTest"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["1F9oHgid9n5qc8HUpNSFTWRLoXwKh3rxXJ"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":3.13415111,"ViacoinTest":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["ViacoinTest"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["VcCUQEERivG8bkQTMTeD53B514ibLJ2qbL"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":{"":3.51169404,"VertcoinTest":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["VertcoinTest"],"id":1}

[I] 2017-Aug-07 23:54:27 [0x3] HTTP: resp 200 {"result":["Viiqs1yXGheZLBm344om73YDuQp89b6Aup"],"error":null,"id":1}

[I] 2017-Aug-07 23:54:28 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:54:38 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 5
[I] 2017-Aug-07 23:54:39 [0x2] broadcast message, command 6
[T] 2017-Aug-07 23:54:39 [0x2] received packet, command code <6>
[T] 2017-Aug-07 23:54:39 [0x2] [] processTransactionHold
[I] 2017-Aug-07 23:54:39 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 7
[I] 2017-Aug-07 23:54:39 [0x2] received message to mzu6SGYcA/KSKUBuzNu1IGm82hY= command 8
[T] 2017-Aug-07 23:54:39 [0x2] received packet, command code <8>
[T] 2017-Aug-07 23:54:39 [0x2] [SYS] processTransactionInit
[I] 2017-Aug-07 23:54:40 [0x2] received message to YuUelEMs6SIR5JoM8rgrJ7N+80Y= command 8
[I] 2017-Aug-07 23:54:40 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 9
[I] 2017-Aug-07 23:54:40 [0x2] received message to ZeJf0khWF0TAJTceYpKKE1jOP08= command 10
[T] 2017-Aug-07 23:54:40 [0x2] received packet, command code <10>
[T] 2017-Aug-07 23:54:40 [0x2] [SEQ] processTransactionCreate
[I] 2017-Aug-07 23:54:40 [0x2] rpc call <listunspent>
[I] 2017-Aug-07 23:54:40 [0x2] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 23:54:40 [0x2] HTTP: resp 200 {"result":[{"txid":"958de869269727bcaab5b0d4e4f6a67b0c8e51bc2b48ccf180e2eaae9b18cb2e","vout":0,"address":"SkQagsidSefbB7rVWjG5RiNDXMbxMrUAk2","scriptPubKey":"76a914fd897bb31fd8f75ba966effe10ec63c3d28957a588ac","amount":69.79800000,"confirmations":7785,"spendable":true}],"error":null,"id":1}

[I] 2017-Aug-07 23:54:40 [0x2] USED FOR TX <958de869269727bcaab5b0d4e4f6a67b0c8e51bc2b48ccf180e2eaae9b18cb2e> amount 69.798 0 fee 0.001
[I] 2017-Aug-07 23:54:40 [0x2] rpc call <getinfo>
[I] 2017-Aug-07 23:54:40 [0x2] HTTP: req  getinfo {"method":"getinfo","params":[],"id":1}

[I] 2017-Aug-07 23:54:40 [0x2] HTTP: resp 200 {"result":{"version":1010000,"protocolversion":70000,"walletversion":60000,"balance":69.79800000,"newmint":0.000000,"stake":0.000000,"blocks":447606,"moneysupply":44878664.29835634,"timeoffset":-10,"connections":16,"proxy":"","difficulty":0.8992549089561864,"testnet":false,"keypoololdest":1498778027,"keypoolsize":999,"encrypted":true,"mintonly":false,"unlocked_until":2502167930,"paytxfee":0.000000,"relayfee":0.000100,"errors":""},"error":null,"id":1}

[I] 2017-Aug-07 23:54:40 [0x2] rpc call <getnewaddress>
[I] 2017-Aug-07 23:54:40 [0x2] HTTP: req  getnewaddress {"method":"getnewaddress","params":[],"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] HTTP: resp 200 {"result":"SgUfFxpayrMCENw1A8N6a9DydvrEGjdr2L","error":null,"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] rpc call <createrawtransaction>
[I] 2017-Aug-07 23:54:42 [0x2] HTTP: req  createrawtransaction {"method":"createrawtransaction","params":[[{"txid":"958de869269727bcaab5b0d4e4f6a67b0c8e51bc2b48ccf180e2eaae9b18cb2e","vout":0}],{"SoHEEPrjjMHWAKC2njt9bxcifRYbadHEtG":0.50100000,"SYJPJgnpePkdjqaAv5CttQq4QrW5sDunws":0.00300000,"SgUfFxpayrMCENw1A8N6a9DydvrEGjdr2L":69.29300000}],"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] HTTP: resp 200 {"result":"0100000008448959012ecb189baeeae280f1cc482bbc518e0c7ba6f6e4d4b0b5aabc27972669e88d950000000000ffffffff032077fc020000000017a9141d0ddf5f3275b139fd0e9e6a27be22cd146854a787e0930400000000001976a91478bbf9f1b3f368f0e153d08a0314cb997cd3d2f588ac20ba049d010000001976a914d26e758b8c1856a0dff3f16ee0a7a2d83e74309c88ac00000000","error":null,"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] rpc call <signrawtransaction>
[I] 2017-Aug-07 23:54:42 [0x2] HTTP: req  signrawtransaction {"method":"signrawtransaction","params":["0100000008448959012ecb189baeeae280f1cc482bbc518e0c7ba6f6e4d4b0b5aabc27972669e88d950000000000ffffffff032077fc020000000017a9141d0ddf5f3275b139fd0e9e6a27be22cd146854a787e0930400000000001976a91478bbf9f1b3f368f0e153d08a0314cb997cd3d2f588ac20ba049d010000001976a914d26e758b8c1856a0dff3f16ee0a7a2d83e74309c88ac00000000",null,null],"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] HTTP: resp 200 {"result":{"hex":"0100000008448959012ecb189baeeae280f1cc482bbc518e0c7ba6f6e4d4b0b5aabc27972669e88d95000000006b483045022100df4223686fed51a51eb505eb596f85868fc06111dd9685eeff2c2781a223924a022067ba53a71c920a424478aeb046b3719d3a11f2b5ed47269540cb1a5dd39968ee012103a88150c6e8499040ffb1306796dfbf1f7c61b4ef2bf9beeaf7d56ccf332e279cffffffff032077fc020000000017a9141d0ddf5f3275b139fd0e9e6a27be22cd146854a787e0930400000000001976a91478bbf9f1b3f368f0e153d08a0314cb997cd3d2f588ac20ba049d010000001976a914d26e758b8c1856a0dff3f16ee0a7a2d83e74309c88ac00000000","complete":true},"error":null,"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] rpc call <decoderawtransaction>
[I] 2017-Aug-07 23:54:42 [0x2] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["0100000008448959012ecb189baeeae280f1cc482bbc518e0c7ba6f6e4d4b0b5aabc27972669e88d95000000006b483045022100df4223686fed51a51eb505eb596f85868fc06111dd9685eeff2c2781a223924a022067ba53a71c920a424478aeb046b3719d3a11f2b5ed47269540cb1a5dd39968ee012103a88150c6e8499040ffb1306796dfbf1f7c61b4ef2bf9beeaf7d56ccf332e279cffffffff032077fc020000000017a9141d0ddf5f3275b139fd0e9e6a27be22cd146854a787e0930400000000001976a91478bbf9f1b3f368f0e153d08a0314cb997cd3d2f588ac20ba049d010000001976a914d26e758b8c1856a0dff3f16ee0a7a2d83e74309c88ac00000000"],"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] HTTP: resp 200 {"result":{"txid":"531e3293246020be22dd0ef8fc699f011212de4f9e6b3d66ac91576f03ef53c6","version":1,"locktime":0,"time":1502168072,"vin":[{"txid":"958de869269727bcaab5b0d4e4f6a67b0c8e51bc2b48ccf180e2eaae9b18cb2e","vout":0,"scriptSig":{"asm":"3045022100df4223686fed51a51eb505eb596f85868fc06111dd9685eeff2c2781a223924a022067ba53a71c920a424478aeb046b3719d3a11f2b5ed47269540cb1a5dd39968ee01 03a88150c6e8499040ffb1306796dfbf1f7c61b4ef2bf9beeaf7d56ccf332e279c","hex":"483045022100df4223686fed51a51eb505eb596f85868fc06111dd9685eeff2c2781a223924a022067ba53a71c920a424478aeb046b3719d3a11f2b5ed47269540cb1a5dd39968ee012103a88150c6e8499040ffb1306796dfbf1f7c61b4ef2bf9beeaf7d56ccf332e279c"},"sequence":4294967295}],"vout":[{"value":0.50100000,"n":0,"scriptPubKey":{"asm":"OP_HASH160 1d0ddf5f3275b139fd0e9e6a27be22cd146854a7 OP_EQUAL","hex":"a9141d0ddf5f3275b139fd0e9e6a27be22cd146854a787","reqSigs":1,"type":"scripthash","addresses":["SoHEEPrjjMHWAKC2njt9bxcifRYbadHEtG"]}},{"value":0.300000,"n":1,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 78bbf9f1b3f368f0e153d08a0314cb997cd3d2f5 OP_EQUALVERIFY OP_CHECKSIG","hex":"76a91478bbf9f1b3f368f0e153d08a0314cb997cd3d2f588ac","reqSigs":1,"type":"pubkeyhash","addresses":["SYJPJgnpePkdjqaAv5CttQq4QrW5sDunws"]}},{"value":69.29300000,"n":2,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 d26e758b8c1856a0dff3f16ee0a7a2d83e74309c OP_EQUALVERIFY OP_CHECKSIG","hex":"76a914d26e758b8c1856a0dff3f16ee0a7a2d83e74309c88ac","reqSigs":1,"type":"pubkeyhash","addresses":["SgUfFxpayrMCENw1A8N6a9DydvrEGjdr2L"]}}]},"error":null,"id":1}

[I] 2017-Aug-07 23:54:42 [0x2] rpc call <getnewaddress>
[I] 2017-Aug-07 23:54:42 [0x2] HTTP: req  getnewaddress {"method":"getnewaddress","params":[],"id":1}

[I] 2017-Aug-07 23:54:43 [0x2] HTTP: resp 200 {"result":"SkTB9Z46inVFREpX219fnkLn9bMD5adtbi","error":null,"id":1}

[I] 2017-Aug-07 23:54:43 [0x2] rpc call <decoderawtransaction>
[I] 2017-Aug-07 23:54:43 [0x2] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["0100000001c653ef036f5791ac663d6b9e4fde1212019f69fcf80edd22be20602493321e5300000000c0483045022100f1b9868b84fd3465099ecc141bdec19d0ebf20c3ccfc7158cd846ebc74ac05cf022038893e622eaf965127732408b5b5c4a0a09b1ecfd2ac86433fedded3b8071ce501210259b37f4503eb6aaf336d9e64e64b011ca16aae0c5c06741febbd4d4d10c76ea3514c52630378d406b17576a914058af851c7712077d31df9bea6ffc0547e71d07a88ac6776a914df6fb3fa67ed77def98294e48b0804abfc5478fa88ada914f2e87f7223d118d523c13b5cd932d1484e3e230b8768feffffff0180f0fa02000000001976a914fe0714b32d7a0e5f2c5e77fbef4eb5a55cb135d688ac78d40600"],"id":1}

[I] 2017-Aug-07 23:54:43 [0x2] HTTP: resp 500 {"result":null,"error":{"code":-22,"message":"TX decode failed"},"id":1}

[I] 2017-Aug-07 23:54:43 [0x2] error: {"code":-22,"message":"TX decode failed"}
[I] 2017-Aug-07 23:54:43 [0x2] decode signed transaction error, transaction canceled processTransactionCreate
[I] 2017-Aug-07 23:54:43 [0x2] cancel transaction <a7b6be72bb3ada0bcafcbc476702cc5916d910f51331f7575132cbc25a20af63>
```

 * TAKER LOG:
```
[I] 2017-Aug-07 22:54:23 [0x1] HTTP: resp 200 {"result":[{"txid":"0f85c55d26e2d7b07e0bce816499ff1661e6b269e389529c8fee18a32643be1b","vout":2,"address":"Sbxd4x4FnJzbFGdapFKoiMxh4zBxRqyztX","v2address":"1Ffd37H73woPixr8GpLjATp8RCxXcNs8y4","account":"","scriptPubKey":"76a914a0dfa62eb2485183e2b75d8d6ba80852d3f6e38a88ac","amount":68.97999200,"confirmations":23409,"spendable":true,"solvable":true},{"txid":"1b429eceb7fde8ec155c43aeb9fb6ab9f814767c9ff4bc070a819a2a86fd519b","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23993,"spendable":true,"solvable":true},{"txid":"80651921aa40eba9dbe3a563530752a4d343d314e55e867c3628622f6a33ecbb","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23937,"spendable":true,"solvable":true},{"txid":"36f590f2f707de7e13941a46eca16b88fc9af364fbe97d60271e987bd5de95d0","vout":2,"address":"SfWjtYYg9RR95CuNUjpGaeny82x685NyHG","v2address":"1KDjrhmXR4DwYu7uwJqC2keQUFifKCF7VU","account":"","scriptPubKey":"76a914c7db07e4420d6ff99bfc6127a417bee51e58963a88ac","amount":3.68719360,"confirmations":24720,"spendable":true,"solvable":true},{"txid":"b75d742be3b652bd9f618e61fc2b1e11903298bcfac26929c50e2976d509abe6","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23874,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Aug-07 22:54:23 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:24 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:25 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:27 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:28 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:28 [0x1] rpc call <listunspent>
[I] 2017-Aug-07 22:54:28 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 22:54:28 [0x1] HTTP: resp 200 {"result":[],"error":null,"id":1}

[I] 2017-Aug-07 22:54:29 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:30 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:30 [0x4] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[I] 2017-Aug-07 22:54:30 [0x4] HTTP: resp 200 {"result":{"":0.00000000,"ppcTEST":0.00000000},"error":null,"id":1}

[I] 2017-Aug-07 22:54:30 [0x4] HTTP: req  getaddressesbyaccount {"method":"getaddressesbyaccount","params":["ppcTEST"],"id":1}

[I] 2017-Aug-07 22:54:30 [0x4] HTTP: resp 200 {"result":["PLjyQTB6mk4NdPps6Da7Zo8FdKfx8N5cfv"],"error":null,"id":1}

[I] 2017-Aug-07 22:54:30 [0x1] rpc call <listunspent>
[I] 2017-Aug-07 22:54:30 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 22:54:30 [0x1] HTTP: resp 200 {"result":[{"txid":"0f85c55d26e2d7b07e0bce816499ff1661e6b269e389529c8fee18a32643be1b","vout":2,"address":"Sbxd4x4FnJzbFGdapFKoiMxh4zBxRqyztX","v2address":"1Ffd37H73woPixr8GpLjATp8RCxXcNs8y4","account":"","scriptPubKey":"76a914a0dfa62eb2485183e2b75d8d6ba80852d3f6e38a88ac","amount":68.97999200,"confirmations":23409,"spendable":true,"solvable":true},{"txid":"1b429eceb7fde8ec155c43aeb9fb6ab9f814767c9ff4bc070a819a2a86fd519b","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23993,"spendable":true,"solvable":true},{"txid":"80651921aa40eba9dbe3a563530752a4d343d314e55e867c3628622f6a33ecbb","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23937,"spendable":true,"solvable":true},{"txid":"36f590f2f707de7e13941a46eca16b88fc9af364fbe97d60271e987bd5de95d0","vout":2,"address":"SfWjtYYg9RR95CuNUjpGaeny82x685NyHG","v2address":"1KDjrhmXR4DwYu7uwJqC2keQUFifKCF7VU","account":"","scriptPubKey":"76a914c7db07e4420d6ff99bfc6127a417bee51e58963a88ac","amount":3.68719360,"confirmations":24720,"spendable":true,"solvable":true},{"txid":"b75d742be3b652bd9f618e61fc2b1e11903298bcfac26929c50e2976d509abe6","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23874,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Aug-07 22:54:31 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 22:54:31 [0x2] broadcast message, command 6
[T] 2017-Aug-07 22:54:31 [0x2] received packet, command code <6>
[T] 2017-Aug-07 22:54:31 [0x2] [] processTransactionHold
[I] 2017-Aug-07 22:54:31 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 7
[I] 2017-Aug-07 22:54:31 [0x2] received message to mzu6SGYcA/KSKUBuzNu1IGm82hY= command 8
[I] 2017-Aug-07 22:54:31 [0x2] received message to YuUelEMs6SIR5JoM8rgrJ7N+80Y= command 8
[T] 2017-Aug-07 22:54:31 [0x2] received packet, command code <8>
[T] 2017-Aug-07 22:54:31 [0x2] [SEQ] processTransactionInit

[I] 2017-Aug-07 22:54:36 [0x2] broadcast message, command 22
[T] 2017-Aug-07 22:54:36 [0x2] received packet, command code <22>
```

 * SERVICE  NODE:
```[I] 2017-Aug-07 23:54:09 [0x2] broadcast message, command 3
[T] 2017-Aug-07 23:54:09 [0x2] received packet, command code <3>
[T] 2017-Aug-07 23:54:09 [0x2] [] processTransaction
[I] 2017-Aug-07 23:54:09 [0x2] received transaction Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc=
    from SWaiTyjWpzVCyKhzxdfny7GU37fd8hd9wM
             SEQ : 500000
    to   1F9oHgid9n5qc8HUpNSFTWRLoXwKh3rxXJ
             SYS : 500000
[T] 2017-Aug-07 23:54:09 [0x2] createTransaction
[I] 2017-Aug-07 23:54:09 [0x2] 47c9aa6320c3d67630df0c57547c2649978ed98be7cd912cc8c758d7714475d3
[I] 2017-Aug-07 23:54:09 [0x2] 81d4afe1193838faaf2559bac6a09199f93c0a7ce9eeb8bff5a9789284ef8522
[I] 2017-Aug-07 23:54:09 [0x2] transaction created, id Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc=
[I] 2017-Aug-07 23:54:09 [0x2] broadcast message, command 22
[T] 2017-Aug-07 23:54:09 [0x2] received packet, command code <22>
[I] 2017-Aug-07 23:54:09 [0x2] delete pending transaction <a7b6be72bb3ada0bcafcbc476702cc5916d910f51331f7575132cbc25a20af63>
[I] 2017-Aug-07 23:54:09 [0x2] Nothing to add to transactions history
[I] 2017-Aug-07 23:54:09 [0x2] unknown transaction Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc= processTransactionCancel
[I] 2017-Aug-07 23:54:09 [0x2] broadcast message, command 22
[T] 2017-Aug-07 23:54:09 [0x2] received packet, command code <22>
[I] 2017-Aug-07 23:54:09 [0x2] delete pending transaction <a7b6be72bb3ada0bcafcbc476702cc5916d910f51331f7575132cbc25a20af63>
[I] 2017-Aug-07 23:54:09 [0x2] Nothing to add to transactions history
[I] 2017-Aug-07 23:54:09 [0x2] unknown transaction Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc= processTransactionCancel
[I] 2017-Aug-07 23:54:29 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 5
[T] 2017-Aug-07 23:54:29 [0x2] received packet, command code <5>
[T] 2017-Aug-07 23:54:29 [0x2] [] processTransactionAccepting
[I] 2017-Aug-07 23:54:29 [0x2] received accepting transaction 9xX0LvuBbHmaylsJedv50879jIdjryBawssyUVf3MRM=
    from 1c5Sqp8uHydjsQmg9Qrt2oL5pzRMqNdcD
             SYS : 500000
    to   SWJuj94678vkagEV8JkmL3j7gerb1AwSJq
             SEQ : 500000
[T] 2017-Aug-07 23:54:29 [0x2] acceptTransaction
[I] 2017-Aug-07 23:54:29 [0x2] 81d4afe1193838faaf2559bac6a09199f93c0a7ce9eeb8bff5a9789284ef8522
[I] 2017-Aug-07 23:54:29 [0x2] 47c9aa6320c3d67630df0c57547c2649978ed98be7cd912cc8c758d7714475d3
[T] 2017-Aug-07 23:54:29 [0x2] tryJoin
[I] 2017-Aug-07 23:54:29 [0x2] transactions joined, new id <1331f7575132cbc25a20af63878cfdced3f9db79095bca9a796c81fb2ef415f7>
[I] 2017-Aug-07 23:54:29 [0x2] send xbcTransactionHold 
[I] 2017-Aug-07 23:54:29 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 7
[T] 2017-Aug-07 23:54:29 [0x2] received packet, command code <7>
[T] 2017-Aug-07 23:54:29 [0x2] [] processTransactionHoldApply
[I] 2017-Aug-07 23:54:29 [0x2] confirm transaction state <trJoined> from 1c5Sqp8uHydjsQmg9Qrt2oL5pzRMqNdcD
[I] 2017-Aug-07 23:54:29 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 7
[T] 2017-Aug-07 23:54:29 [0x2] received packet, command code <7>
[T] 2017-Aug-07 23:54:29 [0x2] [] processTransactionHoldApply
[I] 2017-Aug-07 23:54:29 [0x2] confirm transaction state <trJoined> from SWaiTyjWpzVCyKhzxdfny7GU37fd8hd9wM
[I] 2017-Aug-07 23:54:29 [0x2] send xbcTransactionInit to 1F9oHgid9n5qc8HUpNSFTWRLoXwKh3rxXJ
[I] 2017-Aug-07 23:54:29 [0x2] send xbcTransactionInit to SWJuj94678vkagEV8JkmL3j7gerb1AwSJq
[I] 2017-Aug-07 23:54:30 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 9
[T] 2017-Aug-07 23:54:30 [0x2] received packet, command code <9>
[T] 2017-Aug-07 23:54:30 [0x2] [] processTransactionInitialized
[I] 2017-Aug-07 23:54:30 [0x2] confirm transaction state <trHold> from SWJuj94678vkagEV8JkmL3j7gerb1AwSJq
[I] 2017-Aug-07 23:54:31 [0x2] received message to 9xX0LvuBbHmaylsJedv50879jIc= command 9
[T] 2017-Aug-07 23:54:31 [0x2] received packet, command code <9>
[T] 2017-Aug-07 23:54:31 [0x2] [] processTransactionInitialized
[I] 2017-Aug-07 23:54:31 [0x2] confirm transaction state <trHold> from 1F9oHgid9n5qc8HUpNSFTWRLoXwKh3rxXJ
[I] 2017-Aug-07 23:54:31 [0x2] send xbcTransactionCreate to SWaiTyjWpzVCyKhzxdfny7GU37fd8hd9wM
[I] 2017-Aug-07 23:54:34 [0x2] broadcast message, command 22
[T] 2017-Aug-07 23:54:34 [0x2] received packet, command code <22>
[I] 2017-Aug-07 23:54:34 [0x2] delete pending transaction <a7b6be72bb3ada0bcafcbc476702cc5916d910f51331f7575132cbc25a20af63>
[I] 2017-Aug-07 23:54:34 [0x2] Nothing to add to transactions history
[I] 2017-Aug-07 23:54:34 [0x2] unknown transaction Y68gWsLLMlFX9zET9RDZFlnMAmdHvPzKC9o6u3K+tqc= processTransactionCancel
```

#### Possible Solution(s):
 * User configuration parameter error
 
 
#### Dev Feedback/Status Update:
 * Contacted DYN/SEQ source to see if we can get assitance on SEQ. Possibly SEQ isn't CLTV but DYN is? 

## BitBay [BAY]

## Stratis [STRAT]

 * TAKER LOG STRAT/SYS:
```
[I] 2017-Aug-07 23:02:13 [0x1] rpc call <listunspent>
[I] 2017-Aug-07 23:02:13 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 23:02:13 [0x1] HTTP: resp 200 {"result":[{"txid":"0f85c55d26e2d7b07e0bce816499ff1661e6b269e389529c8fee18a32643be1b","vout":2,"address":"Sbxd4x4FnJzbFGdapFKoiMxh4zBxRqyztX","v2address":"1Ffd37H73woPixr8GpLjATp8RCxXcNs8y4","account":"","scriptPubKey":"76a914a0dfa62eb2485183e2b75d8d6ba80852d3f6e38a88ac","amount":68.97999200,"confirmations":23415,"spendable":true,"solvable":true},{"txid":"1b429eceb7fde8ec155c43aeb9fb6ab9f814767c9ff4bc070a819a2a86fd519b","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23999,"spendable":true,"solvable":true},{"txid":"80651921aa40eba9dbe3a563530752a4d343d314e55e867c3628622f6a33ecbb","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23943,"spendable":true,"solvable":true},{"txid":"36f590f2f707de7e13941a46eca16b88fc9af364fbe97d60271e987bd5de95d0","vout":2,"address":"SfWjtYYg9RR95CuNUjpGaeny82x685NyHG","v2address":"1KDjrhmXR4DwYu7uwJqC2keQUFifKCF7VU","account":"","scriptPubKey":"76a914c7db07e4420d6ff99bfc6127a417bee51e58963a88ac","amount":3.68719360,"confirmations":24726,"spendable":true,"solvable":true},{"txid":"b75d742be3b652bd9f618e61fc2b1e11903298bcfac26929c50e2976d509abe6","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23880,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Aug-07 23:02:13 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:14 [0x2] broadcast message, command 4
[T] 2017-Aug-07 23:02:14 [0x2] received packet, command code <4>
[T] 2017-Aug-07 23:02:14 [0x2] [] processPendingTransaction
[I] 2017-Aug-07 23:02:14 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:15 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:16 [0x1] rpc call <listunspent>
[I] 2017-Aug-07 23:02:16 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 23:02:16 [0x1] HTTP: resp 200 {"result":[],"error":null,"id":1}

[I] 2017-Aug-07 23:02:16 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:17 [0x1] rpc call <listunspent>
[I] 2017-Aug-07 23:02:17 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Aug-07 23:02:17 [0x1] HTTP: resp 200 {"result":[{"txid":"0f85c55d26e2d7b07e0bce816499ff1661e6b269e389529c8fee18a32643be1b","vout":2,"address":"Sbxd4x4FnJzbFGdapFKoiMxh4zBxRqyztX","v2address":"1Ffd37H73woPixr8GpLjATp8RCxXcNs8y4","account":"","scriptPubKey":"76a914a0dfa62eb2485183e2b75d8d6ba80852d3f6e38a88ac","amount":68.97999200,"confirmations":23415,"spendable":true,"solvable":true},{"txid":"1b429eceb7fde8ec155c43aeb9fb6ab9f814767c9ff4bc070a819a2a86fd519b","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23999,"spendable":true,"solvable":true},{"txid":"80651921aa40eba9dbe3a563530752a4d343d314e55e867c3628622f6a33ecbb","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23943,"spendable":true,"solvable":true},{"txid":"36f590f2f707de7e13941a46eca16b88fc9af364fbe97d60271e987bd5de95d0","vout":2,"address":"SfWjtYYg9RR95CuNUjpGaeny82x685NyHG","v2address":"1KDjrhmXR4DwYu7uwJqC2keQUFifKCF7VU","account":"","scriptPubKey":"76a914c7db07e4420d6ff99bfc6127a417bee51e58963a88ac","amount":3.68719360,"confirmations":24726,"spendable":true,"solvable":true},{"txid":"b75d742be3b652bd9f618e61fc2b1e11903298bcfac26929c50e2976d509abe6","vout":1,"address":"ShAF9TmFCTQtRzTcsZjyr63VKyT5wBzXWS","v2address":"1LsF7cz6U6DguggAL8kuJBtvgCDfCUupFW","account":"","scriptPubKey":"76a914d9eaf849d0363217ca31ceec0fd49083edfc734c88ac","amount":0.00300000,"confirmations":23880,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Aug-07 23:02:17 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:17 [0x2] broadcast message, command 6
[T] 2017-Aug-07 23:02:17 [0x2] received packet, command code <6>
[T] 2017-Aug-07 23:02:17 [0x2] [] processTransactionHold
[I] 2017-Aug-07 23:02:18 [0x2] received message to PZ5Ysd+z7dmw7X/WBU/BhuHi3LY= command 7
[I] 2017-Aug-07 23:02:18 [0x2] received message to mzu6SGYcA/KSKUBuzNu1IGm82hY= command 8
[I] 2017-Aug-07 23:02:18 [0x2] received message to hZZ8n1wUVk5ovfBorWjrgRRyamQ= command 8
[T] 2017-Aug-07 23:02:18 [0x2] received packet, command code <8>
[T] 2017-Aug-07 23:02:18 [0x2] [STRAT] processTransactionInit
[I] 2017-Aug-07 23:02:18 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:18 [0x2] received message to PZ5Ysd+z7dmw7X/WBU/BhuHi3LY= command 9
[I] 2017-Aug-07 23:02:19 [0x2] received message to iEF9gS1tMT/o2QNkz6bF9iAtfOU= command 10
[I] 2017-Aug-07 23:02:19 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:20 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:21 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:22 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:23 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:24 [0x4] listaccounts exception couldn't connect to server
[I] 2017-Aug-07 23:02:24 [0x2] broadcast message, command 22
[T] 2017-Aug-07 23:02:24 [0x2] received packet, command code <22>
```

 * TAKER LOG:
 


## Feathercoin [FTC]
#### Issue #1:
 * After a successful TX FTC/SYS posting and TX acceptance there is Block movement
 * TX maker sends FTC out successfully
 * TX taker sends SYS out successfully
 * TX maker receives SYS successfully
 * TX taker does not receive FTC
 * DX status stays in a "Created" state
 * FTC stuck in P2SH Hash
  
 * See DX taker log below:
```
[I] 2017-Jul-19 23:37:53 [0x1] HTTP: resp 200 {"result":[{"txid":"be236a295aa95b32463f1267db33e6d0362ceaf90dc7408b9b7c45dd7dd49a1a","vout":2,"address":"SdwKvVYhvmjTkBLwVqRn9VZUgE7wQQjciG","v2address":"1HeKtemZCQYGDsZUxQShbbQv2StWd4Ld3m","account":"","scriptPubKey":"76a914b6912c123c0d59a41ebe4b64f269f0208f67e8af88ac","amount":6.84975060,"confirmations":21,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Jul-19 23:37:56 [0x1] rpc call <listunspent>
[I] 2017-Jul-19 23:37:56 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Jul-19 23:37:56 [0x1] HTTP: resp 200 {"result":[],"error":null,"id":1}

[I] 2017-Jul-19 23:37:58 [0x1] rpc call <listunspent>
[I] 2017-Jul-19 23:37:58 [0x1] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Jul-19 23:37:58 [0x1] HTTP: resp 200 {"result":[{"txid":"be236a295aa95b32463f1267db33e6d0362ceaf90dc7408b9b7c45dd7dd49a1a","vout":2,"address":"SdwKvVYhvmjTkBLwVqRn9VZUgE7wQQjciG","v2address":"1HeKtemZCQYGDsZUxQShbbQv2StWd4Ld3m","account":"","scriptPubKey":"76a914b6912c123c0d59a41ebe4b64f269f0208f67e8af88ac","amount":6.84975060,"confirmations":21,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Jul-19 23:37:58 [0x2] broadcast message, command 6
[T] 2017-Jul-19 23:37:58 [0x2] received packet, command code <6>
[T] 2017-Jul-19 23:37:58 [0x2] [] processTransactionHold
[I] 2017-Jul-19 23:37:59 [0x2] received message to 28Ak0xS0UisRNdop9yMk8EgC8mM= command 7
[I] 2017-Jul-19 23:37:59 [0x2] received message to mzu6SGYcA/KSKUBuzNu1IGm82hY= command 8
[I] 2017-Jul-19 23:37:59 [0x2] received message to jMKzbKvkDXW5fiiWYwOEtFIL+KM= command 8
[T] 2017-Jul-19 23:37:59 [0x2] received packet, command code <8>
[T] 2017-Jul-19 23:37:59 [0x2] [FTC] processTransactionInit
[I] 2017-Jul-19 23:38:00 [0x2] received message to 28Ak0xS0UisRNdop9yMk8EgC8mM= command 9
[I] 2017-Jul-19 23:38:00 [0x2] received message to G1/UQy13ZjZMUCXII6qg2ptDsio= command 10
[I] 2017-Jul-19 23:38:02 [0x2] received message to 28Ak0xS0UisRNdop9yMk8EgC8mM= command 11
[I] 2017-Jul-19 23:38:02 [0x2] received message to BqJFBZbkQOd9Tl1BTmBVPUVXH+k= command 12
[T] 2017-Jul-19 23:38:02 [0x2] received packet, command code <12>
[T] 2017-Jul-19 23:38:02 [0x2] [SYS] processTransactionCreate
[I] 2017-Jul-19 23:38:02 [0x2] rpc call <getrawtransaction>
[I] 2017-Jul-19 23:38:02 [0x2] HTTP: req  getrawtransaction {"method":"getrawtransaction","params":["19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120"],"id":1}

[I] 2017-Jul-19 23:38:02 [0x2] HTTP: resp 500 {"result":null,"error":{"code":-5,"message":"No information available about transaction"},"id":1}

[I] 2017-Jul-19 23:38:02 [0x2] error: {"code":-5,"message":"No information available about transaction"}
[I] 2017-Jul-19 23:38:02 [0x2] no tx found 19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120 checkDepositTx
[I] 2017-Jul-19 23:38:37 [0x4] HTTP: req  listaccounts {"method":"listaccounts","params":[],"id":1}

[T] 2017-Jul-19 23:38:47 [0x4] received packet, command code <12>
[T] 2017-Jul-19 23:38:47 [0x4] [SYS] processTransactionCreate
[I] 2017-Jul-19 23:38:47 [0x4] rpc call <getrawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  getrawtransaction {"method":"getrawtransaction","params":["19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120"],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":"0100000001155e9e7a67eb94377530165aa545ef77a32229ceab4d7429baf9b5842a47923c020000006b483045022100f47f416f536d7597799443156d8656364ef7352634ee11d42e798f1b20e9888c022047877527e063a17111438f6385ab255832bdbf22843a1daaf016b97677361350012102da627285caa431d03d3debe52014de2cbff725710811adef6e00dd5fbe71e702ffffffff03a0751e0d0000000017a9140c3d594595d7bd76da26cad95017d94c80a9b59687e0930400000000001976a914746dfc1d408c391217b7803a575ccbda64c5f17a88ac4438986c010000001976a9141e00d9eca85a10371f9b68c102abd28a53a96f1388ac00000000","error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <decoderawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["0100000001155e9e7a67eb94377530165aa545ef77a32229ceab4d7429baf9b5842a47923c020000006b483045022100f47f416f536d7597799443156d8656364ef7352634ee11d42e798f1b20e9888c022047877527e063a17111438f6385ab255832bdbf22843a1daaf016b97677361350012102da627285caa431d03d3debe52014de2cbff725710811adef6e00dd5fbe71e702ffffffff03a0751e0d0000000017a9140c3d594595d7bd76da26cad95017d94c80a9b59687e0930400000000001976a914746dfc1d408c391217b7803a575ccbda64c5f17a88ac4438986c010000001976a9141e00d9eca85a10371f9b68c102abd28a53a96f1388ac00000000"],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":{"txid":"19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120","version":1,"locktime":0,"vin":[{"txid":"3c92472a84b5f9ba29744dabce2922a377ef45a55a1630753794eb677a9e5e15","vout":2,"scriptSig":{"asm":"3045022100f47f416f536d7597799443156d8656364ef7352634ee11d42e798f1b20e9888c022047877527e063a17111438f6385ab255832bdbf22843a1daaf016b9767736135001 02da627285caa431d03d3debe52014de2cbff725710811adef6e00dd5fbe71e702","hex":"483045022100f47f416f536d7597799443156d8656364ef7352634ee11d42e798f1b20e9888c022047877527e063a17111438f6385ab255832bdbf22843a1daaf016b97677361350012102da627285caa431d03d3debe52014de2cbff725710811adef6e00dd5fbe71e702"},"sequence":4294967295}],"vout":[{"value":2.20100000,"n":0,"scriptPubKey":{"asm":"OP_HASH160 0c3d594595d7bd76da26cad95017d94c80a9b596 OP_EQUAL","hex":"a9140c3d594595d7bd76da26cad95017d94c80a9b59687","reqSigs":1,"type":"scripthash","addresses":["32ojXRrg7Ni1tTZWGB3dPNHkHLb25Bnxa3"]}},{"value":0.00300000,"n":1,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 746dfc1d408c391217b7803a575ccbda64c5f17a OP_EQUALVERIFY OP_CHECKSIG","hex":"76a914746dfc1d408c391217b7803a575ccbda64c5f17a88ac","reqSigs":1,"type":"pubkeyhash","addresses":["6pM4vep2jBP5FaWZQ2zqB7nsjtdKthxiU4"]}},{"value":61.16882500,"n":2,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 1e00d9eca85a10371f9b68c102abd28a53a96f13 OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9141e00d9eca85a10371f9b68c102abd28a53a96f1388ac","reqSigs":1,"type":"pubkeyhash","addresses":["6gU65RVP4EDWHk6S2cEU5Ktx8cJ8pMVuFZ"]}}]},"error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <listunspent>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  listunspent {"method":"listunspent","params":[],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":[{"txid":"be236a295aa95b32463f1267db33e6d0362ceaf90dc7408b9b7c45dd7dd49a1a","vout":2,"address":"SdwKvVYhvmjTkBLwVqRn9VZUgE7wQQjciG","v2address":"1HeKtemZCQYGDsZUxQShbbQv2StWd4Ld3m","account":"","scriptPubKey":"76a914b6912c123c0d59a41ebe4b64f269f0208f67e8af88ac","amount":6.84975060,"confirmations":21,"spendable":true,"solvable":true}],"error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] USED FOR TX <be236a295aa95b32463f1267db33e6d0362ceaf90dc7408b9b7c45dd7dd49a1a> amount 6.84975 2 fee 0.000588
[I] 2017-Jul-19 23:38:47 [0x4] rpc call <getinfo>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  getinfo {"method":"getinfo","params":[],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":{"version":130200,"sysversion":"2.1.3","protocolversion":70031,"walletversion":130000,"balance":6.84975060,"blocks":291854,"timeoffset":0,"connections":8,"proxy":"","difficulty":5851781325.22578,"testnet":false,"keypoololdest":1500090143,"keypoolsize":100,"unlocked_until":1500530167,"paytxfee":0.00000000,"relayfee":0.00001000,"errors":""},"error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <getnewaddress>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  getnewaddress {"method":"getnewaddress","params":[],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":"SRoUmdSqqAn3vooEgUvtLSCJ7Keb1BwY4z","error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <createrawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  createrawtransaction {"method":"createrawtransaction","params":[[{"txid":"be236a295aa95b32463f1267db33e6d0362ceaf90dc7408b9b7c45dd7dd49a1a","vout":2}],{"3LcqCWqnhVaBzEheMdCKB7upiEEqWfTcx9":1.15044700,"SYk6CvoYvJ3NzopHQWomqTnDfMtPRoUHqj":0.00345000,"SRoUmdSqqAn3vooEgUvtLSCJ7Keb1BwY4z":5.69526560}],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":"01000000011a9ad47ddd457c9b8b40c70df9ea2c36d0e633db67123f46325ba95a296a23be0200000000ffffffff035c71db060000000017a914cf9fc609114aaaf86b8a5bc9ad004fe8e753e09587a8430500000000001976a9147d988480ac150b80711b4cee3ee4e60c7f3eb79988ac2049f221000000001976a9143173b865d64712ebfb6fc0b300adeaf66c8a931e88ac00000000","error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <signrawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  signrawtransaction {"method":"signrawtransaction","params":["01000000011a9ad47ddd457c9b8b40c70df9ea2c36d0e633db67123f46325ba95a296a23be0200000000ffffffff035c71db060000000017a914cf9fc609114aaaf86b8a5bc9ad004fe8e753e09587a8430500000000001976a9147d988480ac150b80711b4cee3ee4e60c7f3eb79988ac2049f221000000001976a9143173b865d64712ebfb6fc0b300adeaf66c8a931e88ac00000000",null,null],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":{"hex":"01000000011a9ad47ddd457c9b8b40c70df9ea2c36d0e633db67123f46325ba95a296a23be020000006b483045022100e715a83d47d6967c7ec87e52054c848ac29f1d508423fa5b5cba074759295c6f022070b61a655af33d46dd19f0911f91176a8a0d4f6dfc3a512e7de0e3512276dc3d0121035cfabd99f7435b0692c5e315094a84f94a8d62129def067a9ce7b746a4367dceffffffff035c71db060000000017a914cf9fc609114aaaf86b8a5bc9ad004fe8e753e09587a8430500000000001976a9147d988480ac150b80711b4cee3ee4e60c7f3eb79988ac2049f221000000001976a9143173b865d64712ebfb6fc0b300adeaf66c8a931e88ac00000000","complete":true},"error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <decoderawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["01000000011a9ad47ddd457c9b8b40c70df9ea2c36d0e633db67123f46325ba95a296a23be020000006b483045022100e715a83d47d6967c7ec87e52054c848ac29f1d508423fa5b5cba074759295c6f022070b61a655af33d46dd19f0911f91176a8a0d4f6dfc3a512e7de0e3512276dc3d0121035cfabd99f7435b0692c5e315094a84f94a8d62129def067a9ce7b746a4367dceffffffff035c71db060000000017a914cf9fc609114aaaf86b8a5bc9ad004fe8e753e09587a8430500000000001976a9147d988480ac150b80711b4cee3ee4e60c7f3eb79988ac2049f221000000001976a9143173b865d64712ebfb6fc0b300adeaf66c8a931e88ac00000000"],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":{"txid":"5fb6bd8bec46933610d959e57fc0c5d5823fab1b790050713b51f2bd18501c29","hash":"5fb6bd8bec46933610d959e57fc0c5d5823fab1b790050713b51f2bd18501c29","size":258,"vsize":258,"version":1,"locktime":0,"vin":[{"txid":"be236a295aa95b32463f1267db33e6d0362ceaf90dc7408b9b7c45dd7dd49a1a","vout":2,"scriptSig":{"asm":"3045022100e715a83d47d6967c7ec87e52054c848ac29f1d508423fa5b5cba074759295c6f022070b61a655af33d46dd19f0911f91176a8a0d4f6dfc3a512e7de0e3512276dc3d[ALL] 035cfabd99f7435b0692c5e315094a84f94a8d62129def067a9ce7b746a4367dce","hex":"483045022100e715a83d47d6967c7ec87e52054c848ac29f1d508423fa5b5cba074759295c6f022070b61a655af33d46dd19f0911f91176a8a0d4f6dfc3a512e7de0e3512276dc3d0121035cfabd99f7435b0692c5e315094a84f94a8d62129def067a9ce7b746a4367dce"},"sequence":4294967295}],"vout":[{"value":1.15044700,"n":0,"scriptPubKey":{"asm":"OP_HASH160 cf9fc609114aaaf86b8a5bc9ad004fe8e753e095 OP_EQUAL","hex":"a914cf9fc609114aaaf86b8a5bc9ad004fe8e753e09587","reqSigs":1,"type":"scripthash","addresses":["3LcqCWqnhVaBzEheMdCKB7upiEEqWfTcx9"]}},{"value":0.00345000,"n":1,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 7d988480ac150b80711b4cee3ee4e60c7f3eb799 OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9147d988480ac150b80711b4cee3ee4e60c7f3eb79988ac","reqSigs":1,"type":"pubkeyhash","addresses":["1CT6B62QBvrBUW2ps5phHZdf1aexe4AxmY"]}},{"value":5.69526560,"n":2,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 3173b865d64712ebfb6fc0b300adeaf66c8a931e OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9143173b865d64712ebfb6fc0b300adeaf66c8a931e88ac","reqSigs":1,"type":"pubkeyhash","addresses":["15WUjnfh6oarQW1n93wonY3jTYRADq6HeG"]}}]},"error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <getnewaddress>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  getnewaddress {"method":"getnewaddress","params":[],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":"SQ9vBZmKJgYoVKAmzt2jUVYDv4F7zapc1D","error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <decoderawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["0100000001291c5018bdf2513b715000791bab3f82d5c5c07fe559d910369346ec8bbdb65f00000000c0483045022100e733e467f1c14006cd9c7a50ef55425e05456e16e9d19e0c5d529ac9f737dc0502200315ac375148811485d10810cbc5a0f962a441e0fe134b139cb22a3062482fbd01210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937514c5263030e7404b17576a914b660441b56cafecf963d8af40d6934f052332a5688ac6776a914d6577360b733df22ddaa814de974eeca61dd6e4f88ada914a5750179a3f25e2edb59d9234991107132dfda2b8768feffffff015cc2da06000000001976a9141f61005d5f10b0f2962b72e47b69877c328ccc5a88ac0e740400"],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":{"txid":"47782e694f0f1a1e4297e4cf4b02d064ba0cfcb1ee04d655df4e041b720f1c36","hash":"47782e694f0f1a1e4297e4cf4b02d064ba0cfcb1ee04d655df4e041b720f1c36","size":277,"vsize":277,"version":1,"locktime":291854,"vin":[{"txid":"5fb6bd8bec46933610d959e57fc0c5d5823fab1b790050713b51f2bd18501c29","vout":0,"scriptSig":{"asm":"3045022100e733e467f1c14006cd9c7a50ef55425e05456e16e9d19e0c5d529ac9f737dc0502200315ac375148811485d10810cbc5a0f962a441e0fe134b139cb22a3062482fbd[ALL] 0300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937 1 63030e7404b17576a914b660441b56cafecf963d8af40d6934f052332a5688ac6776a914d6577360b733df22ddaa814de974eeca61dd6e4f88ada914a5750179a3f25e2edb59d9234991107132dfda2b8768","hex":"483045022100e733e467f1c14006cd9c7a50ef55425e05456e16e9d19e0c5d529ac9f737dc0502200315ac375148811485d10810cbc5a0f962a441e0fe134b139cb22a3062482fbd01210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937514c5263030e7404b17576a914b660441b56cafecf963d8af40d6934f052332a5688ac6776a914d6577360b733df22ddaa814de974eeca61dd6e4f88ada914a5750179a3f25e2edb59d9234991107132dfda2b8768"},"sequence":4294967294}],"vout":[{"value":1.14999900,"n":0,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 1f61005d5f10b0f2962b72e47b69877c328ccc5a OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9141f61005d5f10b0f2962b72e47b69877c328ccc5a88ac","reqSigs":1,"type":"pubkeyhash","addresses":["13rv9izAaKMby1PKTT3evbPfGH1hD5x6mZ"]}}]},"error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] rpc call <sendrawtransaction>
[I] 2017-Jul-19 23:38:47 [0x4] HTTP: req  sendrawtransaction {"method":"sendrawtransaction","params":["01000000011a9ad47ddd457c9b8b40c70df9ea2c36d0e633db67123f46325ba95a296a23be020000006b483045022100e715a83d47d6967c7ec87e52054c848ac29f1d508423fa5b5cba074759295c6f022070b61a655af33d46dd19f0911f91176a8a0d4f6dfc3a512e7de0e3512276dc3d0121035cfabd99f7435b0692c5e315094a84f94a8d62129def067a9ce7b746a4367dceffffffff035c71db060000000017a914cf9fc609114aaaf86b8a5bc9ad004fe8e753e09587a8430500000000001976a9147d988480ac150b80711b4cee3ee4e60c7f3eb79988ac2049f221000000001976a9143173b865d64712ebfb6fc0b300adeaf66c8a931e88ac00000000"],"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] HTTP: resp 200 {"result":"5fb6bd8bec46933610d959e57fc0c5d5823fab1b790050713b51f2bd18501c29","error":null,"id":1}

[I] 2017-Jul-19 23:38:47 [0x4] deposit B 5fb6bd8bec46933610d959e57fc0c5d5823fab1b790050713b51f2bd18501c29
[I] 2017-Jul-19 23:38:47 [0x2] received message to mzu6SGYcA/KSKUBuzNu1IGm82hY= command 18

[I] 2017-Jul-19 23:39:43 [0x2] received message to 28Ak0xS0UisRNdop9yMk8EgC8mM= command 19
[I] 2017-Jul-19 23:39:43 [0x3] listaccounts exception couldn't connect to server
[I] 2017-Jul-19 23:39:44 [0x2] received message to jMKzbKvkDXW5fiiWYwOEtFIL+KM= command 20
[T] 2017-Jul-19 23:39:44 [0x2] received packet, command code <20>
[T] 2017-Jul-19 23:39:44 [0x2] [FTC] processTransactionConfirmB
[I] 2017-Jul-19 23:39:44 [0x2] rpc call <decoderawtransaction>
[I] 2017-Jul-19 23:39:44 [0x2] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["01000000012001abc2f72a375da7394913569bc44dfb35e33018b0acce2e58d1d04194051900000000e12103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768ffffffff0100ef1c0d000000001976a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac00000000"],"id":1}

[I] 2017-Jul-19 23:39:44 [0x2] HTTP: resp 200 {"result":{"txid":"9a8c7e58418d5f9963e56354dfeeba652d46079e322ecb0726ed80fbfd7a3a94","version":1,"locktime":0,"vin":[{"txid":"19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120","vout":0,"scriptSig":{"asm":"03ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba83 304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001 0300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937 0 63032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768","hex":"2103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768"},"sequence":4294967295}],"vout":[{"value":2.20000000,"n":0,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 8cc2b36cabe40d75b97e2896630384b4520bf8a3 OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac","reqSigs":1,"type":"pubkeyhash","addresses":["6rZidRyTTcnxWcD1ChEBiuTVkjU991dhjd"]}}]},"error":null,"id":1}

[I] 2017-Jul-19 23:39:44 [0x2] rpc call <sendrawtransaction>
[I] 2017-Jul-19 23:39:44 [0x2] HTTP: req  sendrawtransaction {"method":"sendrawtransaction","params":["01000000012001abc2f72a375da7394913569bc44dfb35e33018b0acce2e58d1d04194051900000000e12103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768ffffffff0100ef1c0d000000001976a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac00000000"],"id":1}

[I] 2017-Jul-19 23:39:44 [0x2] HTTP: resp 500 {"result":null,"error":{"code":-25,"message":""},"id":1}

[I] 2017-Jul-19 23:39:44 [0x2] error: {"code":-25,"message":""}
[I] 2017-Jul-19 23:39:44 [0x2] payment B not send, no deposit tx, move to pending

[T] 2017-Jul-19 23:40:47 [0x4] received packet, command code <20>
[T] 2017-Jul-19 23:40:47 [0x4] [FTC] processTransactionConfirmB
[I] 2017-Jul-19 23:40:47 [0x4] rpc call <decoderawtransaction>
[I] 2017-Jul-19 23:40:47 [0x4] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["01000000012001abc2f72a375da7394913569bc44dfb35e33018b0acce2e58d1d04194051900000000e12103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768ffffffff0100ef1c0d000000001976a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac00000000"],"id":1}

[I] 2017-Jul-19 23:40:47 [0x4] HTTP: resp 200 {"result":{"txid":"9a8c7e58418d5f9963e56354dfeeba652d46079e322ecb0726ed80fbfd7a3a94","version":1,"locktime":0,"vin":[{"txid":"19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120","vout":0,"scriptSig":{"asm":"03ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba83 304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001 0300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937 0 63032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768","hex":"2103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768"},"sequence":4294967295}],"vout":[{"value":2.20000000,"n":0,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 8cc2b36cabe40d75b97e2896630384b4520bf8a3 OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac","reqSigs":1,"type":"pubkeyhash","addresses":["6rZidRyTTcnxWcD1ChEBiuTVkjU991dhjd"]}}]},"error":null,"id":1}

[I] 2017-Jul-19 23:40:47 [0x4] rpc call <sendrawtransaction>
[I] 2017-Jul-19 23:40:47 [0x4] HTTP: req  sendrawtransaction {"method":"sendrawtransaction","params":["01000000012001abc2f72a375da7394913569bc44dfb35e33018b0acce2e58d1d04194051900000000e12103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768ffffffff0100ef1c0d000000001976a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac00000000"],"id":1}

[I] 2017-Jul-19 23:40:47 [0x4] HTTP: resp 500 {"result":null,"error":{"code":-25,"message":""},"id":1}

[I] 2017-Jul-19 23:40:47 [0x4] error: {"code":-25,"message":""}
[I] 2017-Jul-19 23:40:47 [0x4] payment B not send, no deposit tx, move to pending

[T] 2017-Jul-19 23:41:46 [0x3] received packet, command code <20>
[T] 2017-Jul-19 23:41:46 [0x3] [FTC] processTransactionConfirmB
[I] 2017-Jul-19 23:41:46 [0x3] rpc call <decoderawtransaction>
[I] 2017-Jul-19 23:41:46 [0x3] HTTP: req  decoderawtransaction {"method":"decoderawtransaction","params":["01000000012001abc2f72a375da7394913569bc44dfb35e33018b0acce2e58d1d04194051900000000e12103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768ffffffff0100ef1c0d000000001976a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac00000000"],"id":1}

[I] 2017-Jul-19 23:41:46 [0x3] HTTP: resp 200 {"result":{"txid":"9a8c7e58418d5f9963e56354dfeeba652d46079e322ecb0726ed80fbfd7a3a94","version":1,"locktime":0,"vin":[{"txid":"19059441d0d1582eceacb01830e335fb4dc49b56134939a75d372af7c2ab0120","vout":0,"scriptSig":{"asm":"03ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba83 304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001 0300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937 0 63032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768","hex":"2103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768"},"sequence":4294967295}],"vout":[{"value":2.20000000,"n":0,"scriptPubKey":{"asm":"OP_DUP OP_HASH160 8cc2b36cabe40d75b97e2896630384b4520bf8a3 OP_EQUALVERIFY OP_CHECKSIG","hex":"76a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac","reqSigs":1,"type":"pubkeyhash","addresses":["6rZidRyTTcnxWcD1ChEBiuTVkjU991dhjd"]}}]},"error":null,"id":1}

[I] 2017-Jul-19 23:41:46 [0x3] rpc call <sendrawtransaction>
[I] 2017-Jul-19 23:41:46 [0x3] HTTP: req  sendrawtransaction {"method":"sendrawtransaction","params":["01000000012001abc2f72a375da7394913569bc44dfb35e33018b0acce2e58d1d04194051900000000e12103ea6ae03740204bde7dc08f2fc8a0b23a5bf94ab3eac5b2b3d21be19f3d93ba8347304402205c6287bd3b8d130b4d6361267894031d99380b877340cd96520216c40952568d02206448b78814423e08255d75f51c2544747ca0897a87a374dd59ae46dd8d0061b001210300287d2cc237d6b3508e7d06a2804843fe2f405534631b71176354283fc5e937004c5263032d911bb17576a914d6577360b733df22ddaa814de974eeca61dd6e4f88ac6776a914b660441b56cafecf963d8af40d6934f052332a5688ada914a5750179a3f25e2edb59d9234991107132dfda2b8768ffffffff0100ef1c0d000000001976a9148cc2b36cabe40d75b97e2896630384b4520bf8a388ac00000000"],"id":1}

[I] 2017-Jul-19 23:41:46 [0x3] HTTP: resp 500 {"result":null,"error":{"code":-25,"message":""},"id":1}

[I] 2017-Jul-19 23:41:46 [0x3] error: {"code":-25,"message":""}
[I] 2017-Jul-19 23:41:46 [0x3] payment B not send, no deposit tx, move to pending
```

#### Possible Solution(s):
 * User configuration parameter error
 
#### Dev Feedback/Status Update:

*

## Quarkcoin [QRK]

## Blackcoin [BLK]

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

## Potcoin [POT]

## Peercoin [PPC]

## Bitconnect [BCC]

## Groestlcoin [GRS]

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
  
