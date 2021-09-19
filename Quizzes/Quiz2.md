# Quiz 2

1. Files that should not be accidentally added for tracking should be listed in a ____ file in your git repository.  This will prevent them from showing up in the `git status` command as files that should be added for tracking, and will prevent them from being accidentally pushed to GitHub
    - .gitignore
    - a file with this specified name has contents specifying which files we do NOT want to track
    - git stash - hide your laundry under the bed: https://git-scm.com/docs/git-stash

2. T/F If you expose an OAuth token in a public repo on GitHub, GitHub will send you a warning message and contact the service that generated the token to revoke the token.
    - True

3. T/F The python package manager is named `apt`.
    - False
    - The python package manager is named `pip` or `pip3`
    - `apt` is the Ubuntu Linux package manager

4. I have a repo with a main branch.  I have made a new branch, changed to it, and edited bubbles.py  How can I merge my changes back into the main branch?
    - git checkout main
    - git merge other_branch
    - git push
    - Pull Requests were also a valid option
    - git rebase - Overwrite all content on one branch (any commits) with the content of another (all commits) https://git-scm.com/docs/git-rebase

5. I have changes on GitHub that don't exist in my local workspace (my cloned folder).  What command will get the content and update my workspace (repo folders and files)?
    - `git pull`
    - pull will both fetch and merge content from remote (GitHub) to my local repo.
    - commit creates a snapshot of my changes, locally.
    - push pushes content that exists locally to remote (GitHub)
    - add adds a file for tracking by git the program

