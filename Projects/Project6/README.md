# Project 6 - NOT FINALIZED

- [Objectives](#Objectives)
- [Submission](#Submission)
- [Extra Credit](#Extra-Credit)
  - dockerize the discord bot
  - store the API key in a volume
- [Rubric](Rubric.md)

## Objectives

- Containerize an application with Docker
- Automate the project pipeline with GitHub Actions
- Explore usage of webhooks to keep production up to date

## Project Overview

For this project, you'll need access to a public repo. I'm going to guess that your class repo may not be in a state where it should be made public (remember those Discord API keys?), so in Pilot you will find a new invite link to a public repo for this course. Completion of each milestone **by the date specificied for the milestone** will get you 1 pt of extra credit per milestone met. To qualify, you must submit your project to the Dropbox for Project 6 in Pilot.

## Part 1 - Dockerize it

- **Milestone Participation due 11/19**

- Create new GitHub repo (link to create located in Pilot in Content -> Project 6)
- In a folder named `website`, add the contents of your website
  - this can be a site you created in another class, pet project of yours, or just a vanilla html file
- Install Docker
  - You can install Docker in WSL2 or in an EC2 instance. You'll need your Project 6 repo on wherever you are working
- Create a container image that will run a webserver and contains your "website"
  - you can use apache2 or nginx as the webserver
- Create a Dockerfile with instructions on how to build the image
- Add site content & Dockerfile to repo

## Part 2 - GitHub Actions & DockerHub

- **Milestone Participation due 11/29**

- Create DockerHub account: https://hub.docker.com/ (select Free tier if prompted)
- Create Public Repository in DockerHub
- Set GitHub Secrets named DOCKER_USERNAME and DOCKER_PASSWORD with your respective information filled out.
- Set up GitHub Actions workflow to build and push docker image to DockerHub
  - Use workflow templated here: https://docs.github.com/en/actions/guides/publishing-docker-images#publishing-images-to-docker-hub

## Part 3 - Deployment

- **Milestone due**

- Create `README.md` in main folder of your repo that details the following:
  - Project Overview
  - Run Project Locally
    - how you installed docker + dependencies (WSL2, for example)
    - how to build the container
    - how to run the container
    - how to view the project (open a browser...go to ip and port...)
  - Configure AWS CLI
    - need AWS IAM user with admin credentials
    - how you installed
    - how to configure
  - Create DockerHub public repo
    - process to create
  - Configure GitHub Secrets
    - what credentials are needed - DockerHub credentials (do not state your credentials)
    - set secrets and secret names
  - Configure GitHub Workflow
    - variables to change (repository, etc.)

## Extra Credit - Docker Pull

- Documentation to perform the following:
  - How to pull image with `docker pull`, what repo is the image in, requirements of the repo (public vs. private)
  - Run the pulled image locally, using your system or a system on AWS as the host.

## Extra Credit - [Docke]Rise of the Discord Bot

- Dockerize your python bot - place in repo in folder named `Discord-Bot`
  - Add instructions to handle API key from Discord. Maybe have a docker copy that gets a .env file from their path (this need to exist to build and run image)
  - Your API key may be the most challenging piece of this project extra credit. GitHub secrets might be handy.
  - Be sure to site your sources if you model off of an example / other documentation

## Submission

In your GitHub repository, select the green `Code` button then select `Download ZIP`. Upload this zip file to Pilot.

In the `Comment` area in the Pilot Dropbox, copy URL / link to the repository corresponding to the project you are submitting
