# Setup TortoiseHg for GitHub using Hg-git

## Clone Hg-git
* Homepage: [https://hg-git.github.io/]
* Primary [https://foss.heptapod.net/mercurial/hg-git]
* Mirror [https://github.com/schacon/hg-git]


## Generate SSH public key for Git and private key for TortoiseHg
General guide
[https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent]

1. Generate key pair from command prompt (WIN10)
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

2. Add your public key to Git account

3. Convert private key to ppk format

   1. Download puttygen [https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html]

   2. Run puttygen.exe

   [MENU] Conversions >> Import key

   [BUTTON] Save private key

## Setup TortoiseHg

Edit mercurial.ini: 

   * Enable bookmarks

   * Enter your hg-git path

   * Enter your private key path

   * Enter "git+ssh://" + your github repo ssh path 

```
[extensions]
bookmarks=
hggit = C:\[path to]\hg-git\hggit

[ui]
ssh = "C:\[path to]\TortoisePlink.exe" -ssh -i "C:\[path to]\private_key.ppk"

[paths]
default = git+ssh://git@github.com:[someone]/[repo].git
```

### Reference 
[https://www.codeproject.com/Articles/376058/Step-by-step-Setup-TortoiseHg-for-gitHub]

[https://stackoverflow.com/questions/2951011/how-to-let-tortoisehg-mercurial-on-windows-use-the-private-key-file-generated]
