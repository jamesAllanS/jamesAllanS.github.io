# Generate SSH keys

The following steps walk you through how to:

- Generate SSH keys
- Add the public key generated in step 1 to your Git repository
- Confirm the above steps have been completed successfully

Generate SSH keys:
```bash
ssh-keygen -t rsa -C "email@goeshere.com"
```
`Enter file in which to save the key`: Press Enter
`Enter passphrase`: enter passphrase
`Enter same passphrase again`: enter passphrase again

After completing the above steps, the location of your public key is shown in the terminal window. If the currently logged in user is 'bob' the location of your public key would be `/home/bob/.ssh/id_rsa.pub`

Copy and import public key to GitHub:

```bash
cat /home/bob/.ssh/id_rsa.pub
```

Copy the whole public key that is now displayed in your terminal window to the clipboard

Go to https://github.com and sign in
Click the user icon in the top right corner of the screen and select Settings
Click SSH and GPG keys
Click New SSH key
Enter a title, paste the public key copied to the clipboard in the first bullet point, and click Add SSH key

Confirm the above steps:

```bash
ssh -T git@github.com
```


`Hi ! You've successfully authenticated, but GitHub does not provide shell access.`


The only hiccup you may encounter is when you attempt to SSH to GitHub. This link will provide some assistance -

https://help.github.com/articles/error-agent-admitted-failure-to-sign/
