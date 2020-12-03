# HellenicCoin(HNC)  Node instractions

# Operating system:  Ubuntu Server 18.04 LTS
(Recomented 4vCPU 8 GB RAM)

# 1. Update your Ubuntu machine.

sudo apt-get update

sudo apt-get upgrade

# 2. Install the required dependencies.

sudo apt-get install libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libdb-dev libdb++-dev libminiupnpc-dev

# 3. Download & Extract the tar file.

wget "https://github.com/helleniccoin/HNC/raw/master/helleniccoin-daemon-linux.tar.gz" -O helleniccoin-daemon-linux.tar.gz

tar -xzvf helleniccoin-daemon-linux.tar.gz

# 4. Install the daemon.

sudo mv helleniccoind /usr/bin/

# 5. Create the config file.

mkdir $HOME/.helleniccoin

nano $HOME/.helleniccoin/helleniccoin.conf

# 6. Paste the following lines in helleniccoin.conf.

rpcuser=rpc_hellenic_coin

rpcpassword=a_very_strong_password

rpcallowip=127.0.0.1

rpcport=16341

tcpport=16342

listen=1

server=1

txindex=1

staking=0

daemon=1

addnode=165.232.34.187

addnode=144.126.204.48

addnode=167.71.73.49

# 7.  Start your node with the following command.

helleniccoind



# HellenicCoin node RPC commands

this is the full list of RPC commands, You can also extacted from the node if you type            helleniccoind --help


# Usage:
  helleniccoind [options]
  
  helleniccoind [options] <command> [params]  Send command to -server or helleniccoind
  
  helleniccoind [options] help                List commands
  
  helleniccoind [options] help <command>      Get help for a command

# Options:

  -?                     This help message
  
  -conf=<file>           Specify configuration file (default: helleniccoin.conf)
  
  -pid=<file>            Specify pid file (default: helleniccoind.pid)
  
  -datadir=<dir>         Specify data directory
  
  -wallet=<dir>          Specify wallet file (within data directory)
  
  -dbcache=<n>           Set database cache size in megabytes (default: 25)
  
  -dblogsize=<n>         Set database disk log size in megabytes (default: 100)
  
  -timeout=<n>           Specify connection timeout in milliseconds (default: 5000)
  
  -proxy=<ip:port>       Connect through SOCKS5 proxy
  
  -tor=<ip:port>         Use proxy to reach tor hidden services (default: same as -proxy)
  
  -dns                   Allow DNS lookups for -addnode, -seednode and -connect
  
  -port=<port>           Listen for connections on <port> (default: 13500 or testnet: 23500)
  
  -maxconnections=<n>    Maintain at most <n> connections to peers (default: 125)
  
  -addnode=<ip>          Add a node to connect to and attempt to keep the connection open
  
  -connect=<ip>          Connect only to the specified node(s)
  
  -seednode=<ip>         Connect to a node to retrieve peer addresses, and disconnect
  
  -externalip=<ip>       Specify your own public address
  
  -onlynet=<net>         Only connect to nodes in network <net> (IPv4, IPv6 or Tor)
  
  -discover              Discover own IP address (default: 1 when listening and no -externalip)
  
  -listen                Accept connections from outside (default: 1 if no -proxy or -connect)
  
  -bind=<addr>           Bind to given address. Use [host]:port notation for IPv6
  
  -dnsseed               Query for peer addresses via DNS lookup, if low on addresses (default: 1 unless -connect)
  
  -forcednsseed          Always query for peer addresses via DNS lookup (default: 0)
  
  -synctime              Sync time with other nodes. Disable if time on your system is precise e.g. syncing with NTP (default: 1)
  
  -banscore=<n>          Threshold for disconnecting misbehaving peers (default: 100)
  
  -bantime=<n>           Number of seconds to keep misbehaving peers from reconnecting (default: 86400)
  
  -maxreceivebuffer=<n>  Maximum per-connection receive buffer, <n>*1000 bytes (default: 5000)
  
  -maxsendbuffer=<n>     Maximum per-connection send buffer, <n>*1000 bytes (default: 1000)
  
  -upnp                  Use UPnP to map the listening port (default: 0)
  
  -paytxfee=<amt>        Fee per KB to add to transactions you send
  
  -mininput=<amt>        When creating transactions, ignore inputs with value less than this (default: 0.01)
  
  -testnet               Use the test network
  
  -debug=<category>      Output debugging information (default: 0, supplying <category> is optional)
If <category> is not supplied, output all debugging information.
  
<category> can be: addrman, alert, db, lock, rand, rpc, selectcoins, mempool, net, coinage, coinstake, creation, stakemodifier.
  
  -logtimestamps         Prepend debug output with timestamp
  
  -shrinkdebugfile       Shrink debug.log file on client startup (default: 1 when no -debug)
  
  -printtoconsole        Send trace/debug info to console instead of debug.log file
  
  -regtest               Enter regression test mode, which uses a special chain in which blocks can be solved instantly. This is intended for regression testing tools and app development.
  
  -rpcuser=<user>        Username for JSON-RPC connections
  
  -rpcpassword=<pw>      Password for JSON-RPC connections
  
  -rpcport=<port>        Listen for JSON-RPC connections on <port> (default: 16341 or testnet: 26341)
  
  -rpcallowip=<ip>       Allow JSON-RPC connections from specified IP address
  
  -rpcconnect=<ip>       Send commands to node running on <ip> (default: 127.0.0.1)
  
  -rpcwait               Wait for RPC server to start
  
  -rpcthreads=<n>        Set the number of threads to service RPC calls (default: 4)
  
  -blocknotify=<cmd>     Execute command when the best block changes (%s in cmd is replaced by block hash)
  
  -walletnotify=<cmd>    Execute command when a wallet transaction changes (%s in cmd is replaced by TxID)
  
  -confchange            Require a confirmations for change (default: 0)
  
  -alertnotify=<cmd>     Execute command when a relevant alert is received (%s in cmd is replaced by message)
  
  -upgradewallet         Upgrade wallet to latest format
  
  -keypool=<n>           Set key pool size to <n> (default: 100)
  
  -rescan                Rescan the block chain for missing wallet transactions
  
  -salvagewallet         Attempt to recover private keys from a corrupt wallet.dat
  
  -checkblocks=<n>       How many blocks to check at startup (default: 500, 0 = all)
  
  -checklevel=<n>        How thorough the block verification is (0-6, default: 1)
  
  -loadblock=<file>      Imports blocks from external blk000?.dat file
  
  -maxorphanblocksmib=<n> Keep at most <n> MiB of unconnectable blocks in memory (default: 40)
  
  -datacarriersize       Maximum size of data in data carrier transactions we relay and mine (default: 15000)

Block creation options:

  -blockminsize=<n>      Set minimum block size in bytes (default: 0)
  -blockmaxsize=<n>      Set maximum block size in bytes (default: 250000)

SSL options: (see the Bitcoin Wiki for SSL setup instructions)

  -rpcssl                                  Use OpenSSL (https) for JSON-RPC connections
  
  -rpcsslcertificatechainfile=<file.cert>  Server certificate file (default: server.cert)
  
  -rpcsslprivatekeyfile=<file.pem>         Server private key (default: server.pem)
  
  -rpcsslciphers=<ciphers>                 Acceptable ciphers (default: 
  TLSv1.2+HIGH:TLSv1+HIGH:!SSLv2:!aNULL:!eNULL:!3DES:@STRENGTH)



# Active wallet commands

addmultisigaddress <nrequired> <'["key","key"]'> [account]
  
addnode <node> <add|remove|onetry>
  
addredeemscript <redeemScript> [account]
  
backupwallet <destination>
  
burn <amount> [hex string]
  
burnwallet [hex string] [force]

checkkernel [{"txid":txid,"vout":n},...] [createblocktemplate=false]

checkwallet

createrawtransaction [{"txid":txid,"vout":n},...] {address:amount,...}

decoderawtransaction <hex string>
  
decodescript <hex string>
  
dumpprivkey <helleniccoinaddress>
  
dumpwallet <filename>
  
encryptwallet <passphrase>
  
getaccount <helleniccoinaddress>
  
getaccountaddress <account>
  
getaddednodeinfo <dns> [node]
  
getaddressesbyaccount <account>
  
getbalance [account] [minconf=1]

getbestblockhash

getblock <hash> [txinfo]
  
getblockbynumber <number> [txinfo]
  
getblockcount

getblockhash <index>
  
getblocktemplate [params]

getcheckpoint

getconnectioncount

getdifficulty

getinfo

getmininginfo

getnettotals

getnewaddress [account]

getnewpubkey [account]

getpeerinfo

getrawmempool

getrawtransaction <txid> [verbose=0]
  
getreceivedbyaccount <account> [minconf=1]
  
getreceivedbyaddress <helleniccoinaddress> [minconf=1]
  
getstakesubsidy <hex string>
  
getstakinginfo
  
getsubsidy [nTarget]

gettransaction <txid>
  
getwork [data]

getworkex [data, coinbase]

help [command]

importprivkey <helleniccoinprivkey> [label] [rescan=true]
  
importwallet <filename>
  
keypoolrefill [new-size]

listaccounts [minconf=1]

listaddressgroupings

listreceivedbyaccount [minconf=1] [includeempty=false]

listreceivedbyaddress [minconf=1] [includeempty=false]

listsinceblock [blockhash] [target-confirmations]

listtransactions [account] [count=10] [from=0]

listunspent [minconf=1] [maxconf=9999999]  ["address",...]

makekeypair [prefix]

move <fromaccount> <toaccount> <amount> [minconf=1] [comment]
  
ping

repairwallet

resendtx

reservebalance [<reserve> [amount]]
  
sendalert <message> <privatekey> <minver> <maxver> <priority> <id> [cancelupto]
  
sendfrom <fromaccount> <tohelleniccoinaddress> <amount> [minconf=1] [comment] [comment-to]
  
sendmany <fromaccount> {address:amount,...} [minconf=1] [comment]
  
sendrawtransaction <hex string>
  
sendtoaddress <helleniccoinaddress> <amount> [comment] [comment-to]
  
setaccount <helleniccoinaddress> <account>
  
settxfee <amount>
  
signmessage <helleniccoinaddress> <message>
  
signrawtransaction <hex string> [{"txid":txid,"vout":n,"scriptPubKey":hex,"redeemScript":hex},...] [<privatekey1>,...] 
  [sighashtype="ALL"]
  
stop
  
submitblock <hex data> [optional-params-obj]
  
validateaddress <helleniccoinaddress>
  
validatepubkey <helleniccoinpubkey>
  
verifymessage <helleniccoinaddress> <signature> <message>


