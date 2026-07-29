#### Common Nginx headers
````
proxy_set_header Host $host;
proxy_set_header X-Real-IP $remote_addr;
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
proxy_set_header X-Forwarded-Proto $scheme;
````
-----

- Assuming we have a request-flow:

````
Client: 192.168.10.50
        |
        | HTTPS
        v
Nginx: 192.168.10.10
        |
        | HTTP
        v
Tomcat: 192.168.10.20:8080
````

- Tomcat see the request be a TCP connection that created by Nginx.

- If headers weren't setup, Tomcat will see:

````
Remote IP = 192.168.10.10
Protocol  = HTTP
Host      = maybe name of upstream
````

-> Tomcat didn't know:
- Real client = `192.168.10.50`
- Read protocol = `HTTPS`
- Origin domain = `app.demo.local`

##### Host $host

`proxy_set_header Host $host;`

-> `Host` header indicates which website or virtual host the client wants to access.

##### X-Real-IP $remote_addr

`proxy_set_header X-Real-IP $remote_addr`

`remote_addr` is IP of devices connects directly to Nginx.

E.g:

````
Client 192.168.10.50
        |
        v
      Nginx
````

-> `$remote_addr = 192.168.10.50`

Backend use this header to:
- Write access log.
- Audit.
- Rate limit in app-layer.
...

##### X-Forwarded-For $proxy_add_x_forwarded_for

- Very important when request go through many proxy-layers.

`X-Forwarded-For` records list IP of request.

E.g:

````
Client:        203.0.113.50
Load Balancer: 10.0.0.5
Nginx:         10.0.0.10
Tomcat:        10.0.0.20
````

-> Tomcat will receive:
`X-Forwarded-For: 203.0.113.50, 10.0.0.5`

##### X-Forwarded-Proto $scheme

- Is the protocol client use to connect to Nginx.

````
Client
  |
  | HTTPS
  v
Nginx
  |
  | HTTP
  v
Tomcat
````

-> Tomcat will know the origin connection is `HTTPS`.


