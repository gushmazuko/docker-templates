# Docker Templates
* [Traefik](https://github.com/gushmazuko/dockers_template/tree/master/traefik)
## Handy aliases
Add to `~/.aliasrc`
```bash
alias dc="docker-compose"
alias dex='docker exec -it '
alias dps='docker ps'
```
## DNS API
Add to `~/.aliasrc`
```bash
DNS_API="XXXXXXX"
alias dns-rec='_dns-rec() { curl -Ss "https://zonomi.com/app/dns/dyndns.jsp?host=$1&api_key=$DNS_API";}; _dns-rec'
alias dns-add='_dns-add() {curl -Ss "https://zonomi.com/app/dns/dyndns.jsp?action=SET&name=$1=$2&type=A&api_key=$DNS_API";}; _dns-add'
alias dns-del='_dns-del() { curl -Ss "https://zonomi.com/app/dns/dyndns.jsp?action=DELETE&name=$1&type=A&api_key=$DNS_API";}; _dns-del'
alias dns-get='_dns-get() { curl -Ss "https://zonomi.com/app/dns/dyndns.jsp?action=QUERY&name=**.dxside.net&api_key=$DNS_API" | grep name -A 3;}; _dns-get'
```

* dns-rec - Set current IP address to  `example.com`
```bash
dns-rec example.com
```

* dns-add - Set an IP Address (A) record: attribute `a.example.com to 10.0.0.1`
```bash
dns-add example.com 10.0.0.1
```

* dns-del - Delete an IP Address (A) record: `a.example.com`
```bash
dns-del a.example.com
```

* dns-get - Retrieve all records ending in `example.com`. e.g. letting you fetch all records in a DNS zone.
```bash
dns-get example.com
```
