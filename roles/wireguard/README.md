# Wireguard

Setup a wireguard cluster for VPN access. Add all nodes into a group in your inventory.

## Server

A `server` is the node that your VPN clients will masquarade the IP as, must have one the cluster.

## Keys generation

By default the role will generate a new private key and public key for all hosts defined in the playbooks. It is also possible to use pre-defined `wg_privatekey` and `wg_pubkey`, simply define it a host variable file or inventory file.
