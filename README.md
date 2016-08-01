# iptables-blocklist
get abusive IPs from blocklist.de and block it through iptables

Thanks to hints from: http://stackoverflow.com/questions/27696067/how-to-quickly-add-rules-to-iptables-from-blocklists

## usage

prepare ipset
```
ipset create BlockAddress hash:ip hashsize 4096
````

add the script to cron

```
0 0 */2 * * root /usr/local/bin/blockip
```

add this to ferm INPUT block:
`mod set set BlockAddress src DROP;`

---

TODO:
handle IPv6
handle other sources
