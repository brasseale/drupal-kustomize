
# Drupal on Kubernetes using Kustomize
This project utilizes Kustomize to deploy a base project consisting of Drupal and a Mariadb OR Postgres database. Both Drupal and the database chosen are resilient through restarts utilizing persistent volume storage.

---
## Features   

- Deploys MariaDB or Postgres to Kubernetes easily
- Liveness/Readiness probes to ensure in the event of failures, resiliency is maintained.
- Persistent storage capable pods

___
## How to deploy:

### Base Build and Deploy
`$ kustomize build base | kubectl apply -f -`

### Deploy overlay using Postgres for DB 
`$ kustomize build overlays/postgres | kubectl apply -f -`

---
## Enable Proxy

`$ kubectl port-forward service/drupal 65432:80`

*Navigate to [localhost:65432](http://localhost:65432) to start Drupal install*   

--- 
## Install Drupal
Choose database type "*Mysql, Mariadb, Percona server, or equivalent*" if deploying "**base**", otherwise choose "Postgres" if deploying "**overlays/postgres**". 

**Setup Variables:**   
```
Database Name: drupal-database
Database User: root 
Database Pass: dbpass 
```

**Advanced Options**
```   
Host: drupal-db
Port: 3306 (maridb), 5432 (postgres)
```

**Save and Continue** to install Drupal.

---
## TODOs:


- [ ] Create way to clean up deployment envs for overlays.
- [ ] Look into robust way to have Drupal handle environment variables for common site settings.
- [ ] Research alternative ways to patch container settings that don't involve specific JSON6902 replacements... currently, its a little clumsy and hard to read.
    