# Web Application Security Testing with StackHawk DAST

## Overview

This repository serves as a Proof of Concept (POC) for integrating StackHawk's Dynamic Application Security Testing (DAST) solution into our Continuous Integration/Continuous Deployment (CI/CD) pipeline using GitHub Actions.   

## Purpose

The main objectives of this POC are:
- Evaluate StackHawk DAST for vulnerability detection in our web applications.
- Test the integration of StackHawk DAST with our CI/CD pipeline.
- Assess the feasibility of adding StackHawk to our company's security tools stack.

# Vulnerable Node Express

This is a vulnerable Node Express service meant to be used as a target for security testing tools.
All code in this repository is for testing purposes only.

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

## Build and Run with Docker

### Build Docker Image
```shell script
docker build --tag stackhawk/nodeexpressvulny .
```

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
