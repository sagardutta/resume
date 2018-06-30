# CI/CD Resume

* This is a simple setup to demonstrate CI/CD
* You have to realize this is not how CI/CD works in real organizations
* This project tries to demonstrate all the important concepts


## Concepts demonstrated

* Github push triggering a CI/CD
* There is no CI here since there is nothing to build
* CD is triggered using a webhook which deploys to a digitalocean droplet


## Components in CI/CD pipeline

* Github
* webhook
* Digitalocean droplet (this is what hosts your resume)

## What exactly happens in the pipeline

* The resume is just a html document with CSS
* Digitalocean droplet is running a docker host on ubuntu
* We are running a NGINX docker container which server for our static website
* We have configured the github  
