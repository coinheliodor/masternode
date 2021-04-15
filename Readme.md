# MasternodeSetup

### Required:

1. heliodor Coin for Collateral <br>
(You can buy heliodor coin on the following exchange:) <br>
*** <br>
Exchange: https://crex24.com/...
<br>***

2. Download your Local Wallet: https://github.com/coinheliodor/heliodor/releases/tag/1001



3. You will need also VPS with Ubuntu 18.04

**VPS WALLET:**

1. After you longin on your VPS , with this command you will download masternode-installer.   
`wget https://raw.githubusercontent.com/coinheliodor/masternode/main/masternode-install.sh`  
 

2. With this command you will make masternode-install-ubuntu.sh executable.  
`sudo chmod +x masternode-install.sh` <br>



3. Now install your masternode.  
`./masternode-install.sh`




**LOCAL WALLET:**

Send the collateral
Open your wallet and wait until your wallet has downloaded the blockchain.

Go to “Tools”.
Click “Debug console”.
This is the console where you will execute all commands.

Create a new masternode private key.

```
createmasternodekey
```

Example output

5VatfYsdfsdfMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5

Show your collateral address.
```
getaccountaddress "MN1"
```

Example output

HVZLnPeH2Z7FoKfvn7VDwJ8jBmhnqKTM
```
Transfer the required amount of coins to the “collateral address” that you created using the command “getnewaddress "MN1"”.
```
Wait until the transaction has the required masternode confirmations.

Go to “Tools”.
Click “Debug console”.
Enter the following command.
```
getmasternodeoutputs
```
```
Example output


[
  {
    "txhash": "018dsas242ccbfd2555bcd9cff4532041752c911f39cb2sawgacc83ccfe0cf170444w",
    "outputidx": 1
  }
]
```

Modify the following line in your masternode.conf file and paste it into:
```
MN1 VPSIP:59485 5VatfYsdfsdfMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 018dsas242ccbfd2555bcd9cff4532041752c911f39cb2sawgacc83ccfe0cf170444w 1
```
MN01 - Alias for your masternode.

VPSIP- External IP address of your VPS.

59485 - The port for smnc 

5VatfYsdfsdfMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 - Masternode private key from the command “createmasternodekey”.

018dsas242ccbfd2555bcd9cff4532041752c911f39cb2sawgacc83ccfe0cf170444w - Value “txhash” from the command “getmasternodeoutputs”.

1 - Value “outputidx” from the command “getmasternodeoutputs”.


Save the file and close.

Close your wallet.

Restart your wallet! 
On Masternode tab in your wallet - Start the masternode!
