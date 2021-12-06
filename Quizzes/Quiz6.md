# Quiz 6

1. From the following docker run command, identify the container's port
   docker run -dit --rm -p 4141:8080 myapp:3.1

   - 8080

2. From the following docker run command, identify the host's port
   docker run -dit --rm -p 4141:8080 myapp:3.1

   - 4141

3. I have an application that needs anaconda python. Using an image registry, like DockerHub, recommend a base image that would include anaconda python

   - `docker pull continuumio/anaconda3`

4. In a GitHub action, an \_\_\_\_ is one or more triggers that cause the workflow to run

   - event

5. T/F GitHub Action workflows must exist in the repository in the .github/workflows folder
   - True
