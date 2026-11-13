Ans(q1): The `--global` flag tells Git to apply these configuration settings (your name and email) to every repository on your entire user account system-wide.

If you leave it out, Git will only apply the settings locally to the specific repository you are currently working in. If you are not inside a Git repository yet, the command will fail with an error.

Ans(q2): What appeared: The .git folder. It only shows up with ls -a because the dot at the start makes it a hidden directory in Linux.
What's inside: It has all the configuration files and history for the repository. It includes things like the config file for local settings, an objects folder that stores the actual data/commits, and a HEAD file that tracks which branch you're currently on.

Ans(q3): Git is offering to track 3 items right now: README.md, week01/, and week02/. None of these look like things I didn't write, since they are just my lab files and folders

Ans(q4): Nothing actually disappeared on my terminal because the .venv/ folder wasn't showing up as untracked for me in Question 3 anyway. But according to the guide, the .venv/ folder should disappear from git status once the .gitignore file filters it out.

Ans(q5): It should be committed. If we don't commit the .gitignore file, other people working on the same repository won't have our ignore rules, and their workspace will get cluttered with tracked virtual environment files.

Ans(q6): The README.md file moved from the "Untracked files" heading to the "Changes to be committed" heading. In the three-places model, this means the file moved from my Working Directory into the Staging Area.



Ans(q7): Git printed the root commit ID 98a130c, the commit message, and a list of the tracked files it created. It said that 3 files were changed with 206 insertions.

Ans(q8):  The first seven characters are called the short SHA-1 hash (or short commit ID). They serve as a unique identifier to reference that specific commit.2
 
  Ans(q9): The four steps of the cycle are:
1. Edit or modify the files in the project.
2. Run git status to see what changed.
3. Run git add to move those changes into the staging area.
4. Run git commit -m "message" to permanently save the snapshot.

Ans(q10): the README.md file gets a special name and lives in the root directory because it acts as the landing page for the project. Platforms like GitHub look for this specific file automatically and display it right on the front page so anyone looking at the repository can immediately read what it is about. A generic file like notes.md won't trigger that automatic display

Ans(q11): Running gh auth login creates and stores a secure access token on my machine. It acts as a credential helper, so Git can securely talk to GitHub and verify who I am without asking for my password every single time I push.

Ans(q12): When I refreshed the page, the home screen displayed my repository files along with the formatted layout of my README.md file right at the bottom. This happens because GitHub automatically looks for a file named README.md in the root folder to render as the main front page overview for anyone looking at the project.

Ans(q13): No, pushing did not change my local history at all. The commit hashes (36e4dc8 and 98a130c) and messages are exactly the same as before. The only change is that it now shows origin/master in red text next to master, which just indicates that the online GitHub repository is now fully tracked and matching my local machine.

Ans(q14): A private repository safely exists on GitHub's cloud servers, but it is locked down so only the owner and specifically invited people (like our TAs) can see it. If a repository doesn't exist on GitHub at all, the code only lives locally on my machine, meaning there's no online backup and nobody else can access or grade it.
