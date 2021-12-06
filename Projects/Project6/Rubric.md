# Project 6 Rubric

## Repo contents:

- `README.md`
- `website` folder with website pages
- `Dockerfile`
- GitHub action yml file in `.github/workflows`

## docker basics + Dockerfile

- Create `README.md` in main folder of your repo that details the following:
- Project Overview
- Run Project Locally
  - how you installed docker + dependencies (WSL2, for example)
  - how to build the container
  - how to run the container
  - how to view the project (open a browser...go to ip and port...)

## GitHub Actions and DockerHub

- Create DockerHub public repo
  - process to create
- Allow DockerHub authentication via CLI using Dockhub credentials
- Configure GitHub Secrets
  - what credentials are needed - DockerHub credentials (do not state your credentials)
  - set secrets and secret names
- Configure GitHub Workflow
  - variables to change (repository, etc.)

## Deployment

- Update `README.md` in main folder of your repo to include:
- Pulling the image
- Running the container
