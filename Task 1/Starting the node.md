# TUTORIAL INERY TESTNET TASK 1 : Starting the node
You can show your support by following my intagram @Mr9868_idx
And also you can bought me a cup of cofeee, here is my USDT address
```
0xe494798560f5E0046C20848A99A02aF0311412e5
```
# Hardware spesification
  • Memory: 8 GB RAM \
  • CPU: 4 Core \
  • Disk: 250 GB SSD Storage \
  • Bandwidth: 250 Mbps 
# Recommended VPS shop :
  • Contabo \
  • Digital Ocean \
  • VULTR
> Make sure your spesification is match to the requirements otherwise your VPS Will be suspended
# 1. Update and upgrade your repository
```
sudo apt-get update - y && sudo apt-get upgrade && sudo apt install git && sudo apt install screen
```
# 2. Installing Dependencies
To install all required dependencies on ubuntu distribution open terminal and execute the following command:
```
sudo apt-get install -y make bzip2 automake libbz2-dev libssl-dev doxygen graphviz libgmp3-dev \
autotools-dev libicu-dev python2.7 python2.7-dev python3 python3-dev \
autoconf libtool curl zlib1g-dev sudo ruby libusb-1.0-0-dev \
libcurl4-gnutls-dev pkg-config patch llvm-7-dev clang-7 vim-common jq libncurses5
```
> Make sure your installation is done otherwise Will be a problem to the next step
# 3. Allow your firewall to open required port
```
sudo apt-get install firewalld -y
sudo systemctl start firewalld
sudo systemctl enable firewalld
sudo firewall-cmd --set-default-zone=public
sudo firewall-cmd --zone=public --add-port=22/tcp --permanent
sudo firewall-cmd --zone=public --add-port=8888/tcp --permanent
sudo firewall-cmd --zone=public --add-port=9010/tcp --permanent
sudo firewall-cmd --reload
sudo systemctl restart firewalld
```
Check if all required port is open
```
sudo firewall-cmd --list-all
```
If your port is already in use, you can following this step :
 • Get the process ID (pid)
Example The port 9010 is already in use
```
sudo lsof -i :9010
```
You Will see like this 
```
COMMAND     PID USER   FD   TYPE   DEVICE SIZE/OFF NODE NAME
nodine  3525695 root   21u  IPv4  2889492      0t0  TCP server:9010 (LISTEN)
```
  * Kill the proses by their pid.
Example i Will kill pid 3525695
```
sudo kill 3525695
```
  * After that, allow firewall and open your port again ( Step 3 )
# Download inery node package to your repository
```
 git clone  https://github.com/inery-blockchain/inery-node
```
after the installation complete, then
```
cd inery-node/inery.setup
```
Give ine.py script permission for execution with "chmod" command :
```
chmod +x ine.py
```
Export path to local os envirment for inery binaries
```
./ine.py --export
```
Script has written path to .bashrc file, now in order to work you paste this line in terminal, it will refresh envirmental path variable for current terminall session
```
cd; source .bashrc; cd -
```
Allright, if the step above is already done you can following the next step

