//

For the full list of supported coins see the Google Doc spreadsheet below:

https://docs.google.com/spreadsheets/d/1JVO5sg0-stWtXDoLG_lLVSt_z6aMJ7pwRv9Wf4hVJTQ/edit#gid=0

Thanks to @jcash in Slack for compiling the list and to the community testing members!

//

XBRIDGE.CONF

// Under the [Main] heading, only use .conf’s and wallets vetted by the Dev team

// Some wallets have been tested and traded through the testnet community, others are still work in progress

// This master xbridge.conf will be updated as coins are added/vetted by the Dev team

// Highlighted green sections need to be changed to match your individual wallet’s RPC configuration

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
