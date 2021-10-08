# web_requests_python_notes

## POST Web Request with Python using requests module

```python
import json, requests

payload = '[{"key": "value"}]'

proxies = {
"http_proxy": "http://...",
"https_proxy": "http://...",
"no_proxy": "localhost, 127.0.0.1, ..."
}

rest_endpoint = "rest/<method_name>" 
url = "http://localhost:5000" # software port 5000 is default for flask for example

with requests.post(url=url, json = json.loads(payload), proxies = proxies) as response:
  print(response.text, response.status_code)
```

## POST Web Request via curl
```bash
url='http://localhost:5000'
payload='[{"key": "value"}]'
curl -X POST $url -H 'Content-Type: application/json' -d $payload
# curl --request POST $url --header 'Content-Type: application/json' --data $payload
```
