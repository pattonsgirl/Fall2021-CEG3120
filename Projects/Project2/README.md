# Project 2 - NOT FINALIZED

Note: any time you see repository, assume your GitHub repo for this course, not the one we made in Project 1 manually on the AWS instance.

## Objectives:

- Protect files with secret information (in this case, an API key)
- Deploy a project using basic tools (GitHub & git)
- Build projects locally, then deploy them to your AWS instance
- Explore long term solutions to serving content that don't involve leaving your machine on or connected to the terminal 24/7

## The Story

A developer is handing a project off to you for deployment.  He has left you [documentation](https://realpython.com/how-to-make-a-discord-bot-python/) of how it works, the [core code](bot.py), and some changes to make before the project goes live.

Your job is to put the code into your repository (in GitHub classrooms) in a folder named `Discord-Bot`.  Read through the documentation and figure out:
  - how to generate an API key from Discord
  - where to store the API key for the project to run
  - keep the API key / secret information off GitHub
    - If you mess up, you'll need to create a new Discord API key, then tread carefully
    - TODO: instructions for untracking a tracked file
  - install the python packages needed to run the project
Run the project locally (your system, perhaps), first.  Next, clone it (your GitHub classrooms repo) to your AWS instance and run the project from there.

For the changes, you'll be customizing the bot to output your set of messages when a command of your choice is written on your Discord server.  To do this, you are going to create a `branch`, make your changes, test them, and then `merge` your changes with `main`

## Part 1

1. Create a folder in your repository called `Discord-Bot`
2. Get the core code from [bot.py](bot.py) and copy / paste in into a `.py` file in your repo
3. [Follow this guide](https://realpython.com/how-to-make-a-discord-bot-python/) to create a Discord bot in a Discord server you control.

- The code for the bot can run either from your personal machine OR run it on the Linux AWS system.
- I created a fresh Discord server to play around in. You are welcome to do this in any Discord server you have admin privledges or create your own (it's free)
- Put your `python` code in the `Discord-Bot` folder

5. Update the `README.md` with documentation. Use each bulleted item as a header (see [markdown-demo](../../markdown-demo.md)):

- Description
  - What the code does
  - What commands the bot can use, and what they do.
- How to use an API key
  - You may assume the user has created a Discord API key; you do not need to details how to do this to the user
  - Where does the key need to be located? Is this an environment variable? How did it get "loaded" into the system?
- Dependencies
  - Is `python` required? What version? How do you install `discord.py`?

## Part 2 - Discord Bot Modifications

1. Clone your repo and run your code on the AWS instance.

2. Create a `branch` and make one of the modifications to the code listed below:
  - outputs quotes based on a command of your choice
    - note that this _must_ be a different command and set of quotes from the demo
  - outputs pictures based on a command of your choice
    - see `!corgme` in the Department server under Discussion. Please spam #cute-pets only
  - Note: you are allowed to both, or pay around beyond just these, but at minimum one of these

3. Test your changes while on the `branch`.  When your changes are tested and working, `merge` your `branch` changes with `main`

## Part 3 - R&D (Research & Documentation)

For both projects, especially the Discord bot, you may have realized that it is lame that it only runs when you run the program.

In the real world, things are "always on", not waiting for Bob to turn his PC on and make sure the program is running.

Research some possible solutions that would solve this, and discuss why you think it would work.


## Guided Questions

You don't need to answer these as part of your project.  They serve as hints to figure out the project.

## Submission

1. Commit and push your changes to your repository.  Verify that these changes show in your course repository, https://github.com/WSU-kduncan/ceg3120-YOURGITHUBNAME

2. In Pilot, paste the link to your project folder.  Sample link: https://github.com/WSU-kduncan/ceg3120-YOURGITHUBUSERNAME/blob/main/Projects/Project2