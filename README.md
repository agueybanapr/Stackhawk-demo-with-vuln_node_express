# Vulnerable Node Express

This is a vulnerable Node Express service meant to be used as a target for security testing tools.
All code in this repository is for testing purposes only.

## I am currently using it to test [Stackhawk](https://stackhawk.com) DAST CI/CD & Github Actions solutions as a POC to hopefully add it to our security tools stack.

```DELETE ME```
## Build and Run

### Install NPM Dependencies
```shell script
npm install
```

### Initialize SQLite DB
```shell
node bootstrapdb.js
```

### Run
```shell script
DEBUG=myapp:* npm start
```
## 
## Build and Run with Docker

### Build Docker Image
```shell script
docker build --tag stackhawk/nodeexpressvulny .
```
##
### Run Docker Container
```shell script
docker run --rm --publish 3000:3000 --name nodeexpressvulny stackhawk/nodeexpressvulny
```

### Build and Run in Docker Compose
```shell script
docker-compose up --build --detach
```

## Known Vulnerabilities
* SQL Injection via search box. - `item%' union all select * from user; -- ` 
* Cross Site Scripting via search box. - `<script>alert("hey guy");</script>`
