# xbridge.conf

* Under the ```[Main]``` heading, edit to suit your requirements:

  * ```ExchangeWallets=``` Add/remove coin heading's here
  * ```LogPath=``` Change file path to desired location 

* Under the ```[COIN]``` heading, edit to suit your individual wallet's RPC configuration:

  * ```Address=``` Edit this field to your individual labelled receive addresses
  * ```Username=``` Username must match RPCuser in the coin's ".conf"
  * ```Password=``` Password must match RPCpassword in the coin's ".conf"

* This master xbridge.conf will be updated as coins are added


## DX COMPATIBLE COINS

```
[Main]
ExchangeWallets=BTC,SYS,LTC,DGB,DASH,DYN,SEQ,otherwallet1,otherwallet2
FullLog=true
LogPath=C:\Users\PCusername\AppData\Roaming\blocknet\log
ExchangeTax=300

[RPC]
Enable=false
UserName=rpc1
Password=rpc1
UseSSL=false
Port=8080

[BTC]
Title=Bitcoin
Ip=127.0.0.1
Port=8332
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=0
ScriptPrefix=5
SecretPrefix=128
COIN=100000000
MinimumAmount=0
DustAmount=0
CreateTxMethod=BTC
MinTxFee=0
BlockTime=600
Address= BTC TEST ADDRESS
GetNewKeySupported=false
ImportWithNoScanSupported=false
TxVersion=1
FeePerByte=200

[SYS]
Title=SysCoin
Ip=127.0.0.1
Port=8370
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=0
ScriptPrefix=5
SecretPrefix=128
COIN=100000000
MinimumAmount=0
DustAmount=0
CreateTxMethod=BTC
MinTxFee=0
BlockTime=60
Address= SYS TEST ADDRESS
GetNewKeySupported=false
ImportWithNoScanSupported=false
TxVersion=1
FeePerByte=200

[LTC]
Title=Litecoin
Address= LTC TEST ADDRESS
Ip=127.0.0.1
Port=9332
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=48
ScriptPrefix=5
SecretPrefix=176
COIN=100000000
MinimumAmount=0
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=true
FeePerByte=200
MinTxFee=60000
TxVersion=1
BlockTime=60

[DASH]
Title=Dash
Address= DASH TEST ADDRESS
Ip=127.0.0.1
Port=9998
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=76
ScriptPrefix=16
SecretPrefix=204
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=true
MinTxFee=60000
BlockTime=150
FeePerByte=200

[DYN]
Title=Dynamic
Address= DYN TEST ADDRESS
Ip=127.0.0.1
Port=31350
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=30
ScriptPrefix=10
SecretPrefix=140
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=10000
BlockTime=128
FeePerByte=200

[VIA]
Title=ViaCoin
Address=VIA TEST ADDRESS
Ip=127.0.0.1
Port=5222
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=71
ScriptPrefix=33
SecretPrefix=199
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=24
FeePerByte=200

[DGB]
Title=Digibyte
Address= DGB TEST ADDRESS
Ip=127.0.0.1
Port=14022
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=30
ScriptPrefix=5
SecretPrefix=128
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=true
MinTxFee=100000
BlockTime=60
FeePerByte=200

[VTC]
Title=Vertcoin
Address=VTC TEST ADDRESS
Ip=127.0.0.1
Port=5888
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=71
ScriptPrefix=5
SecretPrefix=199
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=150
FeePerByte=200
```

## COMMUNICATES BUT TX FAILS
```
[SEQ]
Title=Sequence
Address= SEQ TEST ADDRESS
Ip=127.0.0.1
Port=16663
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=63
ScriptPrefix=64
SecretPrefix=170
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=100000
BlockTime=60
FeePerByte=200

[BAY]
Title=BitBay
Address= BAY TEST ADDRESS
Ip=127.0.0.1
Port=19915
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=25
ScriptPrefix=85
SecretPrefix=153
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=true
MinTxFee=10000
BlockTime=64
FeePerByte=200

[STRAT]
Title=Stratis
Address= STRAT TEST ADDRESS
Ip=127.0.0.1
Port=26174 
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=63
ScriptPrefix=125
SecretPrefix=191
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=true
MinTxFee=60000
BlockTime=60
FeePerByte=200

[DOGE]
Title=Dogecoin
Address= DOGE TEST ADDRESS
Ip=127.0.0.1
Port=22555 
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=30
ScriptPrefix=22
SecretPrefix=158
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=60
FeePerByte=200

[FTC]
Title=Feathercoin
Address= FTC TEST ADDRESS
Ip=127.0.0.1
Port=9337
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=14
ScriptPrefix=5
SecretPrefix=142
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=60
FeePerByte=200

[QRK]
Title=Quarkcoin
Address=QRK TEST ADDRESS
Ip=127.0.0.1
Port=8372
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=58
ScriptPrefix=9
SecretPrefix=186
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=30
FeePerByte=200
```

## NOT TESTED
```
[XST]
Title=Stealthcoin
Address=XST TEST ADDRESS
Ip=127.0.0.1
Port=46502
Username= YOUR USERNAME
Password=YOUR PASSWORD
AddressPrefix=62
ScriptPrefix=85
SecretPrefix=190
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=true
MinTxFee=100000
BlockTime=60
FeePerByte=200

[BLK]
Title=Blackcoin
Address=BLK TEST ADDRESS
Ip=127.0.0.1
Port=15715
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=25
ScriptPrefix=85
SecretPrefix=153
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=30
FeePerByte=200

[BRK]
Title=Breakoutcoin
Address=BRK TEST ADDRESS
Ip=127.0.0.1
Port=50542
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=19
ScriptPrefix=1
SecretPrefix=147
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=300
FeePerByte=200

[BRX]
Title=Breakoutstake
Address=BRX TEST ADDRESS
Ip=127.0.0.1
Port=50542
Username= YOUR USERNAME
Password= YOUR PASSWORD
AddressPrefix=19
ScriptPrefix=1
SecretPrefix=147
COIN=100000000
MinimumAmount=0
TxVersion=1
DustAmount=0
CreateTxMethod=BTC
GetNewKeySupported=false
ImportWithNoScanSupported=false
MinTxFee=60000
BlockTime=300
FeePerByte=200
```
