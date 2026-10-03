Q1: pwd gave me /mnt/c/Users/sanch. This is my actual Windows user folder  (C:\Users\sanch) but WSL shows it through /mnt/c since that's how it 
mounts the C drive. Basically WSL and Windows are looking at the same folder, just different naming.

Q2: When I ran ls -a I suddenly saw a bunch of stuff I hadn't seen before- .copilot, .ms-ad, .python_history, .vscode, .vscode-shared. None of 
that showed up with regular ls. Turns out anything that starts with a dot counts as "hidden" in Linux and normal ls just skips past it without 
telling you it exists. -a basically means show literally everything, hidden or not.

Q3: I picked this line from ls -l: -rwxrwxrwx 1 ankitplaksha ankitplaksha 6412 Jan 27 2025 -1.14-windows.xml
The very first character is "-" which tells you it's a regular file (if it was a folder it'd be "d" instead). After that you get 9 more 
characters split into 3 groups of 3 - these are permissions for the owner, the group, and everyone else, and rwx means read/write/execute is allowed for all of them here.

Q4: This worked without cd because I was already sitting in my home  folder, and coding-cafe happens to be right there inside it. So 
coding-cafe/week02 only worked because of where I currently was standing - that makes it a relative path, not absolute. If I'd typed the whole 
thing from root, like ~/coding-cafe/week02, that would be absolute and it wouldn't matter where I was standing, it'd always work.

Q5: mv actually did two separate things here even though it's one command. First time I used it, it moved README-backup.md out of 
coding-cafe and into week01 - same name, new location. Second time, once I was already inside week01, I used mv again but this time just to 
rename it to old-readme.md, so the location stayed the same but the name changed. Kind of interesting that there's no separate "rename" command in 
Linux, it's literally the same mv doing both jobs depending on how you use it.

Q6: Ran echo $PATH and counted the folders separated by colons, got around 21 total. A chunk of them were the usual linux system folders 
like /usr/bin and /bin, but a good number were windows paths too, like /mnt/c/Windows/System32, since apparently WSL pulls the windows PATH in 
as well.

Q7: python3 is sitting at /usr/bin/python3, this is the system-wide one.

Q8: This would probably be different for someone else on a different machine, since PATH order depends on what's installed and in what 
sequence it got added. Even on the same lab computer two people could have installed things differently over time so their PATH order wouldn't match exactly.

Q9: Typed pyton3 by mistake and got "command 'pyton3' not found", with the shell actually suggesting python3 instead which was helpful. Makes 
sense once you think about it - the shell just checks every single folder in PATH looking for something named exactly pyton3, and since I 
spelled it wrong nothing matches that name even though python3 (spelled right) is sitting right there on PATH the whole time.

Q10: Ran ls first after making .venv and it wasn't there. Ran ls -a right after and there it was. Reason is the same as Q2 basically - .venv starts 
with a dot so it's hidden by default, plain ls just doesn't show it unless you force it with -a.

Q11: Once I ran source .venv/bin/activate my prompt changed and now has (.venv) sitting right at the start before my username. Just a visual way 
of telling me I'm inside the virtual environment right now.

Q12: Before activating, which python3 gave /usr/bin/python3. After activating it, same command instead gave 
/home/ankitplaksha/coding-cafe/.venv/bin/python3. So activate isn't installing some new python, it's just quietly changing my PATH so that 
the venv's own bin folder gets checked before /usr/bin does, and since shell stops at the first match it finds, it grabs the venv one first now.

Q13: Ran pip list before and after installing requests and honestly they looked identical both times. Turns out requests and all its dependencies 
(certifi, charset-normalizer, idna, urllib3) were already sitting in the venv before I even ran the install command, so it just told me 
"Requirement already satisfied" instead of installing anything fresh.

Q14: After deactivate, which python3 went right back to /usr/bin/python3, same as before I ever touched the venv. So deactivate is just undoing 
whatever PATH change activate made, putting things back the way they were.

Q15: Looked this up in man ls - the -h flag stands for human-readable and it just makes file sizes way easier to read, showing something like 1K, 
234M, 56G instead of some long number of raw bytes. Basically instead of seeing 6412 you'd see 6.4K, saves you doing the math in your head.

Q16: Ran python3 and pressed Ctrl+C first - it printed KeyboardInterrupt but I was still stuck at the >>> prompt, still inside python. Then 
pressed Ctrl+D and that actually closed python completely, dropped me straight back to my normal shell prompt. So Ctrl+C just interrupts/stops 
something without leaving, while Ctrl+D is more like telling it "I'm 
done, exit now".
