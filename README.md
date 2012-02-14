Transparent HTTP proxy
======================

A basic transparent HTTP proxy that can sit between a client and HTTP servers,
proxying requests from the client and rewriting the returned resource.

Much inspiration taken from
[sergio-proxy](https://code.google.com/p/sergio-proxy/).

It is enabled on the gateway (in my case for a single client) by a simple
iptables rule:

    iptables -t nat -A PREROUTING -s $CLIENT_IP -p tcp --dport 80 -j REDIRECT --to-port 8080
