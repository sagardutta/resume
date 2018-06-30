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
* We are running a NGINX docker container which server our static website
 -  we have mounted the folder containing resume on the docker container as a volume
 -  so whenever we change the resume.html on docker host nginx container serving the content will get the updates
* We have installed a webhook receiver on the digitalocean droplet to receive webhooks
  -  The webhook on the droplet is configured to download the raw resume html on receiving a webhook and replacing the existing resume.html on docker host
  - once this html on docker host is refreshed the same change will make it to the container
* We have configured github to send a webhook on every push or commit to github


# Pipeline in action

* Change is pushed to Github
* Github triggers a webhook on digitalocean droplet
* Upon invoking, Webhook downloads the latest resume.html from github and replaces the old content
* As soon as the html is refreshed, it makes its way to the container
* Once you refresh the web page, we see the changes checked into github
