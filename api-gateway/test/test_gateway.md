### Send request without SSL Termination
```bash
curl -k http://localhost:8444/api/f1/drivers?year=2019 | jq && echo
```

### Send request with SSL Termination
```bash
curl -k https://localhost:8443/api/f1/drivers?year=2019 | jq && echo
```

### Get response header in result
```bash
curl -k -v https://localhost:8443/get | jq && echo
```

### API key authentication
```bash
curl -k -H "x-api-key:P5FcvLwkyN7eethF" https://localhost:8443/post | jq && echo
```

### Key-Value store API key authentication
```bash
curl -k -H "x-kv-api-key:2j1PM5rwgt1" https://localhost:8443/anything | jq && echo
```

### Rate limit
```bash
for i in {1..10}; do curl -k https://localhost:8443/get | jq && echo; done
```

### JWT authentication
```bash
TOKEN="eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyLCJ1aWQiOjIyMn0.L7cAao32jKJGKEgdWyfKzDn6FC-3baJv6Rl1E6lGwY0" ; curl -k -H "Authorization: Bearer $TOKEN" https://localhost:8443/drivers | jq && echo
```
