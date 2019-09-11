## CKWC

My own WireGuard configuration. Pretty much defaults except some tweaks and changes here and there. The setups are for your Server & Client.


## Config

The WireGuard default config directory is located under `/etc/wireguard`. 


## Generating keys

You can generate your public key and private key with command `wg genkey | tee prikey | wg pubkey > pubkey`.


## OpenWRT

Make sure you added your chnroute to the list, an example looks like this:
```
create chnroute hash:net family inet hashsize 4096 maxelem 65536
add chnroute 103.45.212.0/XX
...
..
.
```


## VPN

Getting the VPN running requires that you change `Address`, `PrivateKey` & `PublicKey`, `Endpoint` (IP:Port) + the `ListenPort` port is optional (Default is: 51820).

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

## Acknowledgements

In case you have some problems, there are multiple "auto-configuration" scripts avbl. but you usally don't need them, it's not hard to change port, keys and hostename - or is it?!

* [wireguard-mesh-configurator (github.com)](https://github.com/k4yt3x/wireguard-mesh-configurator) - WireGuard full mesh configuration generator.
* [easy-wg-quick (github.com)](https://github.com/burghardt/easy-wg-quick) - Creates Wireguard configuration for hub and peers with ease

