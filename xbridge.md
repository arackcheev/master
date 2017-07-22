# XBRIDGE.CONF

-Under the [Main] heading, only use .conf’s and wallets vetted by the Dev team

-Some wallets have been tested and traded through the testnet community, others are still work in progress

-This master xbridge.conf will be updated as coins are added/vetted by the Dev team

-Highlighted green sections need to be changed to match your individual wallet’s RPC configuration

```
[Main]
ExchangeWallets=BTC,SYS,LTC,DGB,DASH,DYN,SEQ, [otherwallet1],[otherwallet2],etc…]
FullLog=true
LogPath= CHANGE FILE PATH TO DESIRED LOCATION or C:\Users\PCusername\AppData\Roaming\blocknet\log
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
