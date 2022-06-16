# Testing

Please ignore

```py
import requests

s = requests.Session()
r = s.get(url)

if r.status_code == 200:
    filename = [
        json.loads(j.split('=')[1])
        for j in [
            i.strip()
            for i in r.headers['content-disposition'].split(';')
        ] if j[:9] == "filename="
    ][0]
    print(filename)
```
