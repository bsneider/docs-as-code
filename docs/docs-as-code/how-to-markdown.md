# How to Markdown

- [How to Markdown](#how-to-markdown)
  - [Benefits](#benefits)
  - [Markdown quick start](#markdown-quick-start)
  - [Install a markdown editor (VSCODE) No admin required](#install-a-markdown-editor-vscode-no-admin-required)
  - [Install markdown vscode plugins](#install-markdown-vscode-plugins)
  - [Install Git](#install-git)
  - [Clone your repo, using the terminal (Powershell, or Terminal if MAC) like a pro](#clone-your-repo-using-the-terminal-powershell-or-terminal-if-mac-like-a-pro)
    - [Windows](#windows)
    - [Mac](#mac)

## Benefits

- Easy documentation review via pull requests
- Definitive sign-off on changes by key members via pull requests
- Documentation can live close to the thing it documents
- Searchability across code and docs is in one place
  - Especially with GitHub
- Harder to have abandoned unhelpful pages - Less general docs clutter
- Pages are less likely to be out of date when close to the thing they document
- Users are notified via email or teams (if configured) when changes occur
- The chance of users sneaking in changes, or sneaking past updating the docs is lessened

## Markdown quick start

NOTE: This is a one time setup per machine. Expected time to finish this tutorial is 2 hours for a non-technical user.

NOTE2: Markdown can be edited directly in the Stash website interface, without the need for an additional markdown editor and understanding of git.

## Install a markdown editor (VSCODE) No admin required

- [VSCode download page](https://code.visualstudio.com/download)
  - Click the big button for your OS (operating system)
  - remember VSCODE is your friend :)

## Install markdown vscode plugins

- [yzhang.markdown-all-in-one](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [bierner.markdown-emoji](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-emoji)
- [davidanson.vscode-markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [Markdown Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown)
  - Makes it super easy just use the classic `ctrl + shift + p` and start typing docs and it remembers markdown syntax so don't you have to!
- [hediet.vscode-drawio](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)

## Install Git

- [Git windows install](https://git-scm.com/download/win)
- [Git mac install](https://git-scm.com/download/mac)
- [Git linux install](https://git-scm.com/download/linux)

## Clone your repo, using the terminal (Powershell, or Terminal if MAC) like a pro

Note, don't worry, if you are non-technical. After following this tutorial, you may get the feeling you are now a hacker.... That will soon pass lol.

1. Clone the repo to your local machine
2. Enter the new folder it was cloned into
3. Open VSCode

### Windows

```powershell
git clone https://github.com/bsneider/docs-as-code.git
cd docs-as-code
code .
```

### Mac

```bash
git clone https://github.com/bsneider/docs-as-code.git
cd docs-as-code
code .
```

If `code .` does not open vscode, then can follow these [steps](https://code.visualstudio.com/docs/setup/mac) to get it added in "PATH". Otherwise, click the vscode icon and follow the onscreen prompts to find the newly cloned repo called skunkworks.
