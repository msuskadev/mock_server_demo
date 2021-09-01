
1. Official WireMock docker Image: https://hub.docker.com/r/rodolpheche/wiremock/

2. Running WireMock cotainer:

```bash
$ docker run -d -p 8080:8080 -v /c/MyProjects/EC/MockServer-PoC/stubs:/home/wiremock rodolpheche/wiremock
```

or

```bash 
$ docker run -d -p 8080:8080 --mount type=bind,source=/c/MyProjects/EC/MockServer-PoC/stubs,target=/home/wiremock rodolpheche/wiremock
```

3. Path to directory with Docer Desktop Volumes:
```
\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes
```

## Demo Agenda
1. Simple request

```
GET http://{{server}}:{{port}}/users
```

2. Simple request with basic validation

```
GET http://{{server}}:{{port}}/users?first_name=adam
```

❗ WireMock supports matching of requests to stubs and verification queries using the following attributes:
* URL
* HTTP Method
* Query parameters
* Headers
* Basic authentication (a special case of header matching)
* Cookies
* Request body
* Multipart/form-data

2. Pagination

❗ USE OFFSET = 1, 3, 5, 7, 9 

3. Delay

```
GET http://{{server}}:{{port}}/users/delay
```

4. Validation authentication

```
POST http://{{server}}:{{port}}/users
```


6. 500 Status

```
GET http://{{server}}:{{port}}/fault
```

7. Devops:

    * create Dockerfile
    * define CI/CD pipieline
