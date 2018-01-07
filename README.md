# wg_utils 
utilities for Wireguard 

```
./wg_init 
Usage : ./wg_init DEV IP_CIDR:PORT PRIV_KEY_FILE_PATH WG_DIRECTIVES 

WG directives are : 
[fwmark <mark>] [peer <base64 public key> [remove] [preshared-key <file path>] [endpoint <ip>:<port>] [persistent-keepalive <interval seconds>] [allowed-ips <ip1>/<cidr1>[,<ip2>/<cidr2>]...] ]...
```

```
./wg_add_peer 
Usage : ./wg_add_peer DEV PEER_PUB_KEY ENDPOINT_IP:PORT ALLOWED_IPS WG_DIRECTIVES 

WG directives are : 
[ [remove] [preshared-key <file path>] [persistent-keepalive <interval seconds>] ...] 
```

```
./wg_service 
Usage : ./wg_service CONF_FILE ARGS 

CONF_FILE should point to a Wireguard configuration file 
ARGS are one of : start | no option ; save ; status | show ; down | stop ; restart ; reload 
```

TODO : 

1. wg_service : add iptables processing section; it will be able to process [IPTABLES_<table>] defined in CONF_FILE (or in $(/usr/bin/dirname ${CONF_FILE})/peers_$(/bin/basename ${CONF_FILE} .conf) ) 
2. wg_service : add check argument 
2. add sysvinit and systemd service files

