# open port 80 to an internal web server

```console
echo "rdr pass inet proto tcp from any to any port 80 -> 127.0.0.1 port 8080" | sudo pfctl -ef -
```

show current forwarding rules

```console
sudo pfctl -s nat
```

disable

```console
sudo pfctl -F all -f /etc/pf.conf
```
