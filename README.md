#### GENERATING SSH KEYS

```
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```

```
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519): [Press enter]
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

```
eval "$(ssh-agent -s)"
```
```
open ~/.ssh/config
```

```
> The file /Users/you/.ssh/config does not exist.
touch ~/.ssh/config
```

```
open ~/.ssh/config
```
PASTE: 

Host *  
  AddKeysToAgent yes  
  UseKeychain yes  
  IdentityFile ~/.ssh/id_ed25519  

```
ssh-add -K ~/.ssh/id_ed25519
```
---

#### ADDING SSH TO GITHUB

COPY PUBLIC KEY
```
pbcopy < ~/.ssh/id_ed25519.pub
```
https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
