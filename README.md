### GENERATING SSH KEYS

IN YOUR TERMINAL, BEGIN AT ROOT FOLDER (~)
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

WHEN YOU SEE...  
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519):* 
```
[Press enter]
```
> Enter passphrase (empty for no passphrase):
```
[Type a passphrase, or press enter to skip]
```
> Enter same passphrase again:
```
[Type passphrase again]
```

START THE SSH AGENT
```
eval "$(ssh-agent -s)"
```

OPEN FILE **(WINDOWS USERS SKIP)**
```
open ~/.ssh/config
```

IF FILE DOES NOT EXIST **(WINDOWS USERS SKIP)**
```
> The file /Users/you/.ssh/config does not exist.
touch ~/.ssh/config
```

OPEN FILE **(WINDOWS USERS SKIP)**
```
open ~/.ssh/config
```
PASTE INTO TEXT EDITOR **(WINDOWS USERS SKIP)**
```
Host *  
  AddKeysToAgent yes  
  UseKeychain yes  
  IdentityFile ~/.ssh/id_ed25519  
```
SAVE AND CLOSE THE FILE **(WINDOWS USERS SKIP)**

BACK IN TERMINAL: ADD TO KEYCHAIN
```
ssh-add -K ~/.ssh/id_ed25519
```
---

### ADDING SSH TO GITHUB

COPY PUBLIC KEY **(MAC)**
```
pbcopy < ~/.ssh/id_ed25519.pub
```
COPY PUBLIC KEY **(WINDOWS)**
```
clip < ~/.ssh/id_ed25519.pub
```

ON GITHUB:  
FOLLOW THESE INSTRUCTIONS AND PASTE IN COPIED KEY FROM ABOVE STEP  
https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

---
### CONNECT TO YOUR REPO

ON GITHUB:  
FOLLOW THESE INSTRUCTIONS TO SET UP A REPO  
https://docs.github.com/en/get-started/quickstart/create-a-repo

IN YOUR TERMINAL:
```
cd into your project folder
```
```
git remote set-url origin [your ssh url]
git branch -M main
git add .
git commit -m "your first commit"
git push -u origin main
```
