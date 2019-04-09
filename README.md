# SpectrumxMN
Autoscript to make SpectrumXMN

You will need a fresh VPS running Ubuntu Linux 16.04.6 x64 with atleast 1 GB RAM and 15 GBs free space
1. log into your VPS console and download the file: 
```
git clone https://github.com/SPECTRUMXCOIN/SpectrumxMN.git
cd SpectrumxMN
```
2. Change the permissions:
```
chmod +x script.sh
```
3. Prepare the windows wallet:
- Go to debug console and type:
```
getnewaddress MN1
```
- Send 25000 SPE to this address and let atleast confirm by 16 conformations
- Get the MN key using the command below in your wallets console and make a note of this
```
masternode genkey
```
4. Back to vps and execute the file reemn.sh:
```
sudo ./script.sh
```
5. When the script asks for your masternode key enter the key you saved before.
6. When this has finished it will show info related to your masternode take note of your VPS_IP:PORT 

7. Go back to your windows wallet console and get masternode outputs:
```
masternode outputs
```
The result will be something like this: you will only need to note between "" 
```
txhash: "7a1ebb4baadf9ff39bbbfc2d58fd57ff15b65a5096069c8b232d3d312fb4xxxx",
outputidx: 1
```
8. Open the masternode conf file in tools and input the data you have noted i the order below:
```
MN1 IP:PORT masternodekey masternodeouputs txnumber
EXAMPLE: 38.25.122.251:34441 7NEGGttKZojkAzViEYXXXxKTFdAtC2uSiMg8NSFqYVBtN6mYdU 7a1ebb4baadf9ff39bbbfc2d58fd57ff15b65a5096069c8XXX3fb4cb5c 1
```
9. Save masternode.conf file reopen wallet, wait for sync and in masternodes tab click START ALL
10. Atleast 22 blocks to be confirmed and start to work

Enjoy :)
