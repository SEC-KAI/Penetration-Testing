# HTTP response observations

Observations from the accompanying HTTP response screenshots.

| Request shown | Result | Supported interpretation |
| --- | --- | --- |
| `curl -I 10.65.172.80:3000` | 200 OK; X-Powered-By: Express; connect.sid; HttpOnly | An HTTP service answered a HEAD request on port 3000 and advertised Express. |
| `curl -I 10.65.172.80/server:3000` | Failed to connect on port 80 | The suffix is inside the path, not the authority/port. |
| `curl -I 10.65.172.80:3000/nonexistent` | 404 Not Found; Express header | The server handled the request but did not provide the requested route. |

The 404 response also includes `Content-Security-Policy: default-src 'none'` and `X-Content-Type-Options: nosniff`. These are observations for this response, not evidence that all application routes have the same policy. No framework version or exploitability is established.
