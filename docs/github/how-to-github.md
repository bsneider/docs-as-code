# How to Git Hub

- [How to Git Hub](#how-to-git-hub)
  - [Setting up GitHub with Enterprise](#setting-up-github-with-enterprise)
    - [Joining Enterprise Organization](#joining-enterprise-organization)
    - [GitHub account settings for using enterprise account](#github-account-settings-for-using-enterprise-account)
  - [Setting up SSH with GitHub](#setting-up-ssh-with-github)
    - [Generating an SSH key](#generating-an-ssh-key)
    - [Adding Public SSH key](#adding-public-ssh-key)
    - [Authorize the SSH key for use with SAML SSO](#authorize-the-ssh-key-for-use-with-saml-sso)

## Setting up GitHub with Enterprise

### Joining Enterprise Organization

**Note: Replace Org-Name with the name of your GitHub Organization**
**Note: Replace enterprise-name with the name of your email domain**
**Note2: Assumes use of and integration with Okta for SSO**

- In the email from GitHub you received, accept the invitation to your Organization
- Click the "Authenticate" button.
- If you instead get a 403 Forbidden error that mention Okta, ask the Engineering Team to add you to the GitHub Org-Name application in Okta.
- Next, you’ll be prompted for your GitHub user account – the one to be associated with the Org-Name organization in GitHub.
- If you have a personal GitHub account you want to use, just sign in using those GitHub credentials.

### GitHub account settings for using enterprise account

- Click on your photo (or the empty photo placeholder) to access your account’s settings.
- Under email, add your @enterprise-name.com email if it isn’t there.
- You’ve get an email at that address to verify you can access that email’s inbox. If you don’t see the verification email, ask IT Security Operations team if an email from noreply@github.com to you has been quarantined.
- Now, still in Setting, go to the bottom of the Notifications tab to “Custom Routing”, and edit the setting for Organization Org-Name to ensure it routes emails from that Organization to your @enterprise-name.com email address (and not a personal one).

## Setting up SSH with GitHub

### Generating an SSH key

- Open terminal (if in windows use WSL2 or Git Bash) to create an ssh key.
- Run ```ssh-keygen -t rsa```
- You will first be prompted for file to save the key. The default is shown. If you choose to provide a different directory, you will need to configure your git setup to consume that key location.
- When prompted for passphrase, simply press enter. If you used default, you will now have two keys in the following location (~/.ssh/id_rsa  ~/.ssh.id_rsa.pub).

### Adding Public SSH key

- Open Github, and navigate to <>Code tab in relevant repo.
- Click the green "Code" dropdown on the top right.
- In the dropdown, click the SSH tab
- Below the SSH address, click "add new SSH keys"
- Name your SSH key, then paste the SSH key for the id_rsa.pub file you created above into the "key" field. Click add key.

### Authorize the SSH key for use with SAML SSO

- Go to Settings -> SSH and GPG keys.
- Next to your SSH key, click enable SSO
- Add the organization you want to authorize the SSH key for and click Authorize.
  
    See [Github Docs](https://docs.github.com/en/github/authenticating-to-github/authenticating-with-saml-single-sign-on/authorizing-an-ssh-key-for-use-with-saml-single-sign-on) for additional documentation.
