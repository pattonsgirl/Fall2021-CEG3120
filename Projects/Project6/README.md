# Project 6

- [Objectives](#Objectives)
- [Project Overview](#Project-Overview)
- [Part 1 - Dockerize it](#Part-1---Dockerize-it)
- [Part 2 - GitHub Actions and DockerHub](#Part-2---GitHub-Actions-and-DockerHub)
- [Part 3 - Deployment](#Part-3---Deployment)
- [Submission](#Submission)
- [Extra Credit - Automate Deployment](#Extra-Credit---Automate-Deployment)
- [Extra Credit - Rise of the Discord Bot](#Extra-Credit---Rise-of-the-Discord-Bot)
- [Rubric](Rubric.md)

## Objectives

- Containerize an application with Docker
- Automate the project pipeline with GitHub Actions
- Explore usage of webhooks to keep production up to date

## Project Overview

For this project you will be creating a fresh repository - the link is in Pilot under Content - Projects - Project 6. This is the repo you will be using for this project.

You will notice that each part has "Milestone" labels and dates. This project is not due until 12/8. Completion of each milestone **by the date specificied for the milestone** will get you 1 pt of extra credit per milestone date met. To qualify, you must submit your project to the Dropbox for Project 6 in Pilot.

## Part 1 - Dockerize it

- **Milestone Participation due 11/22**

### Tasks

- Create new GitHub repo (link to create located in Pilot in Content -> Project 6)
- In a folder named `website`, add the contents of your website
  - this can be a site you created in another class, pet project of yours, or just a vanilla html file
- Install Docker
  - You can install Docker in WSL2 or in an EC2 instance. You'll need your Project 6 repo on wherever you are working
- Create a container image that will run a webserver and contains your "website"
  - you can use apache2 or nginx as the webserver
- Create a Dockerfile with instructions on how to build the image
- Add site content & Dockerfile to repo

### Documentation

- Create `README.md` in main folder of your repo that details the following:
- Project Overview
- Run Project Locally
  - how you installed docker + dependencies (WSL2, for example)
  - how to build the container
  - how to run the container
  - how to view the project (open a browser...go to ip and port...)

## Part 2 - GitHub Actions and DockerHub

- **Milestone Participation due 12/3**

### Tasks

- Create DockerHub account: https://hub.docker.com/ (select Free tier if prompted)
- Create Public Repository in DockerHub
- Set GitHub Secrets named DOCKER_USERNAME and DOCKER_PASSWORD with your respective information filled out.
- Set up GitHub Actions workflow to build and push docker image to DockerHub
  - Use workflow templated here: https://docs.github.com/en/actions/guides/publishing-docker-images#publishing-images-to-docker-hub

### Documentation

- Update `README.md` in main folder of your repo to include:

- Create DockerHub public repo
  - process to create
- Allow DockerHub authentication via CLI using Dockhub credentials
- Configure GitHub Secrets
  - what credentials are needed - DockerHub credentials (do not state your credentials)
  - set secrets and secret names
- Configure GitHub Workflow
  - variables to change (repository, etc.)

### Resources

- [GitHub Actions - Docker Docs](https://docs.docker.com/ci-cd/github-actions/)

## Part 3 - Deployment

- **Milestone Participation due 12/6**

### Tasks

- For this piece, you can use your backend pool of webservers from the project 5 or just another EC2 instance.
- Install docker on the instance
- Pull your project image
- Run the container - bind it to the host's port 80

### Documentation

- Update `README.md` in main folder of your repo to include:
- Pulling the image
- Running the container

## Submission

1. Commit and push your changes to your repository. Verify that these changes show in your course  
   repository.

   - Your repo should contain:
   - `README.md`
   - `website` folder with website pages
   - `Dockerfile`
   - GitHub action yml file

2. In Pilot, paste the link to your project folder.

## Extra Credit - Automate Deployment

Here's the deal. DockerHub and GitHub and many other things offer these things called "webhooks". Think very basic triggers that can notify when actions happen (actions in the lowercase sense, GitHub Actions are their own thing). The goal is to automate deploying updates. I am including some resources that may (or may not) be good directions to check out. I will accept either of the following strategies:

1. Use a GitHub webhook to trigger an update script to pull changes on the server
   - [How to Automatically Deploy from GitHub to server using webhook](https://betterprogramming.pub/how-to-automatically-deploy-from-github-to-server-using-webhook-79f837dcc4f4)
2. Use DockerHub webhooks to pull an updated image
   - [Build CI/CD Pipelines Using Docker](https://circleci.com/blog/build-cicd-piplines-using-docker/)
   - [docker hook - GitHub repo](https://github.com/schickling/docker-hook)
   - [docker image puller - GitHub repo](https://github.com/tuxity/docker-image-puller)

The [Webhook](https://github.com/adnanh/webhook) package has the most potential usefulness.

## Extra Credit - Rise of the Discord Bot

- Dockerize your python bot. Place in repo in folder named `Discord-Bot`. Include the following:
  - the docker bot code & api
  - the Dockerfile that builds the image
  - a `README.md` file that contains documentation on how the project works
- The hard part here is dealing with the secret. It shouldn't exist in the image we send around - then anyone would have it. It should only exist on servers we trust running the container.
- My recommended method here will be to create a folder that we share with the running container - this is known as a mount or a volume.
