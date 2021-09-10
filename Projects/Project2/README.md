# Project 2 - NOT FINALIZED

Note: any time you see repository, assume your GitHub repo for this course, not the one we made in Project 1 manually on the AWS instance.

## Objectives:

- Protect files with secret information (in this case, an API key)
- Deploy a project using basic tools (GitHub & git)
- Build projects locally, then deploy them to your AWS instance
- Explore long term solutions to serving content that don't involve leaving your machine on or connected to the terminal 24/7

## Part 1 - Discord Bot Local

1. Create a folder in your repository called `Discord-Bot`
2. Create a `README.md` file in this folder.
3. [Follow this guide](https://realpython.com/how-to-make-a-discord-bot-python/) to create a Discord bot in a Discord server you control.

- The code for the bot can run either from your personal machine OR run it on the Linux AWS system.
- I created a fresh Discord server to play around in. You are welcome to do this in any Discord server you have admin privledges or create your own (it's free)
- Put your `python` code in the `Discord-Bot` folder

4. Modify the bot code to do either of the following:

- outputs quotes based on a command of your choice
  - note that this _must_ be a different command and set of quotes from the demo
- outputs pictures based on a command of your choice
  - see `!corgme` in the Department server under Discussion. Please spam #cute-pets only

5. Update the `README.md` with documentation. Use each bulleted item as a header (see [markdown-demo](../../markdown-demo.md)):

- Description
  - What the code does
  - What commands the bot can use, and what they do.
- How to use an API key
  - You may assume the user has created a Discord API key; you do not need to details how to do this to the user
  - Where does the key need to be located? Is this an environment variable? How did it get "loaded" into the system?
- Dependencies
  - Is `python` required? What version? How do you install `discord.py`?

## Part 2 - Discord Bot Production

Clone your repo and run your code on the AWS instance.

Make tweaks locally (such as adding another quote)

Use `pull`s to have the changes deploy to "production"

## The Research Part

For both projects, especially the Discord bot, you may have realized that it is lame that it only runs when you run the program.

In the real world, things are "always on", not waiting for Bob to turn his PC on and make sure the program is running.

Research some possible solutions that would solve this, and discuss why you think it would work.


## Guided Questions

You don't need to answer these as part of your project.  They serve as hints to figure out the project.

## Submission

1. Commit and push your changes to your repository.  Verify that these changes show in your course repository, https://github.com/WSU-kduncan/ceg3120-YOURGITHUBNAME

2. In Pilot, paste the link to your project folder.  Sample link: https://github.com/WSU-kduncan/ceg3120-YOURGITHUBUSERNAME/blob/main/Projects/Project2