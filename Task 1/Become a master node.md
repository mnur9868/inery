# Become a Master Node ( Master Approval )
> Make sure you have completed "Start a node" section before following this step ! Otherwise, you Will get problem during run this step !
# 1. Configuration
Configuring node with Inery Account name and server IP or DNS by opening config.json file
```
cd;
cd inery-node/inery.setup/tools/;
nano config.json
```
scroll down to MASTER ACCOUNT and replace placeholders
> INFO : Name can have maximum of 12 characters ASCII lowercase a-z, 1-5 and dot character "." but dot can't be at the end of string
```
"MASTER_ACCOUNT":
{
    "NAME": "AccountName",
    "PUBLIC_KEY": "PublicKey",
    "PRIVATE_KEY": "PrivateKey",
    "PEER_ADDRESS": "IP:9010",
    "HTTP_ADDRESS": "0.0.0.0:8888",
    "HOST_ADDRESS": "0.0.0.0:9010"
}
```
> • AccountName = Your Inery master account name \
• PublicKey = Your Public key of an account \
• PrivateKey = Your Private key of an account \
• IP = Your IP address or DNS of your server


Save it (ctrl+S), Type "Y" and exit (ctrl+X)
# 2. Start blockchain protocol
go to previous directory "inery-setup" and run ine.py script
```
cd ..;
chmod +x ine.py;
./ine.py --master
```
> If everything is setup properly, after executing above command you should be able to see replay of blocks, may be up to few hours until sync is finished. After blockchain is replayed you will see new created blocks.
Go to directory master.node and execute script ./start.sh
```
cd master.node;
chmod +x start.sh;
./start.sh
```
> ========= PLEASE WAIT AFTER YOUR BLOCK SYNC FIRST BEFORE RUN THIS COMMAND BELOW ============
# 3. Register and approve

After everything is setup, you have to register and after approve it your account as producer
## A. Create a wallet with password
In order for transaction to pass, you will need wallet activated To activate wallet, go to user directory and type command :
```
cd;  cline wallet create --file defaultWallet.txt
```
> Now you created your default wallet with password saved in "defaultWallet.txt" file in /root/ directory. 
### > REMEMBER ! RUN THIS CODE ONLY ONCE OR YOUR PASSWORD CHANGED AND YOU WILL CAN'T OPEN THE WALLET !
> If you accidentally run this code again, you must delete your wallet and Rerun 3.A step again !
```
cd; rm -rf inery-wallet
```
> WARNING : Run this code above only if your wallet can't open because wrong password !
## B. Unlock the wallet
```
cline wallet unlock --password YOUR_WALLET_PASSWORD
```
> Replace YOUR_WALLET_PASSWORD with acctual password
## C. Import your private key
After wallet is unlocked, import your account's private key
```
cline wallet import --private-key MASTER_PRIVATE_KEY
```
> replace MASTER_PRIVATE_KEY with private key of your account
Now, you can register and approve your account as Master (block producer)
## D. Register as producer by executing command:
```
 cline system regproducer ACCOUNT_NAME ACCOUNT_PUBLIC_KEY 0.0.0.0:9010
```
> Account_Name = Inery master account name
Account_PublicKey = Public key of an account
## E. Approve your account as producer by executing command:
```
 cline system makeprod approve ACCOUNT_NAME ACCOUNT_NAME
```
> Account_Name = Inery master account name
# If everything is done, you can do the next task 
Don't for get to claim on the dasboard account !



