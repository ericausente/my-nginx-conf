### Request: https://public.kushikimi.xyz/application1/

LB: 
```
  location /application1/ {
             proxy_pass https://www.kushikimi.xyz/api/;
             add_header Content-Type text/plain;
           }
```


Webserver:
```
### Proxied Request: https://www.kushikimi.xyz/api/
### Backend Server is configured as below: 
location /api/ {
        add_header Content-Type text/plain;
        return 200 "You are accessing $scheme://$host$uri";
    }
```

###############################################################################
### Testing from browser: https://public.kushikimi.xyz/application1/
### Output: You are accessing https://www.kushikimi.xyz/api/
###############################################################################



