## CKWC

My own WireGuard configuration. Pretty much defaults except some tweaks and changes here and there. The setups are for your Server & Client.


## Config

The WireGuard default config directory is located under `/etc/wireguard`. 


## Generating keys

You can generate your public key and private key with command `wg genkey | tee prikey | wg pubkey > pubkey`.


## VPN

Getting the VPN running requires that you change `Address`, `PrivateKey` & `PublicKey, `Endpoint` (IP:Port) + the `ListenPort` port is optional (Default is: 51820).

## Prerequisites (Server-side)

* WireGuard
* nmap (optional)
* socat (optional)
* iptables/ip6tables

```sh
./start-server.sh
```

## Prerequisites (Client-side)

```sh
export ENDPOINT=<...>
export REMOTE_HOSTNAME=192.168.128.1
export REMOTE_PORT=51820
./client.sh
```
