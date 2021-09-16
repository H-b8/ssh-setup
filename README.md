#### GENERATING SSH KEYS

BEGIN AT ROOT FOLDER (~)
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

```
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519): [Press enter]
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

START THE SSH AGENT IN THE BACKGROUND
```
eval "$(ssh-agent -s)"
```

OPEN FILE
```
open ~/.ssh/config
```

IF FILE DOES NOT EXIST
```
> The file /Users/you/.ssh/config does not exist.
touch ~/.ssh/config
```

OPEN FILE
```
open ~/.ssh/config
```
PASTE INTO TEXT EDITOR: 
```
Host *  
  AddKeysToAgent yes  
  UseKeychain yes  
  IdentityFile ~/.ssh/id_ed25519  
```
SAVE AND CLOSE THE FILE

BACK IN TERMINAL: ADD TO KEYCHAIN
```
ssh-add -K ~/.ssh/id_ed25519
```
---

#### ADDING SSH TO GITHUB

COPY PUBLIC KEY
```
pbcopy < ~/.ssh/id_ed25519.pub
```
FOLLOW INSTRUCTIONS WHILE ON GITHUB WEBSITE
https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

---

#### CONNECT TO YOUR REPO

ON GITHUB: FOLLOW THESE INSTRUCTIONS TO SET UP A REPO
https://docs.github.com/en/get-started/quickstart/create-a-repo

IN YOUR TERMINAL:
```
cd into your project folder
```
```
git remote add origin git@github.com:H-b8/fgdfg.git
git branch -M main
git add .
git commit -m "your first commit"
git push -u origin main
```
