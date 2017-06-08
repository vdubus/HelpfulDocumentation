# Git

## Installation

To begin with, we would need first to install
[Git for Windows](https://git-for-windows.github.io/).

## Integration

### PowerShell Integration with [Posh-Git](https://github.com/dahlbyk/posh-git)

We can integrate Git inside of **PowerShell** with **Posh-Git**.  
To do so, and for complete integration, we shoud open the **PowerShell**
console as an admin and execute this command to install **Posh-Git**:

```
PowerShellGet\Install-Module posh-git
```

Then, to enable it so that each time you open the console it is available, do:

```
Add-PoshGitToProfile
```

You will find more information on
[Posh-Git](https://github.com/dahlbyk/posh-git) website.

## UI

### [GitKraken](https://www.gitkraken.com/)

A **freeware** UI only for **non-commercial use**. You need to register yourself.  
With this one, you don't need to install **Git** on your computer.

### [GitExtension](https://gitextensions.github.io/)

An **OpenSource** UI.  
It will ask you to install **Git** to work.

### [SourceTree](https://www.sourcetreeapp.com/)

A **freeware** UI. You just need to register to their website.  
It will ask you to install **Git** to work.  
One of the best.

### [GitHub Desktop](https://desktop.github.com/)

A **freeware** UI to be use with **GitHub projects**.  
You won't need to install **Git**.

## Configuration

### Editor

It is possible to [associating text editors](https://help.github.com/articles/associating-text-editors-with-git/) like **Atom** or **Notepad++** with **Git**, so they can be used to edit commits.

### GPG

#### Why

It is possible to sign you commit with a GPG key.  
I would suggest you to read the [Git horro story](https://mikegerwitz.com/papers/git-horror-story) first so that you know why you should sign your commits.

#### configuration

Check the
[GPG documentation from GitHub](https://help.github.com/articles/signing-commits-with-gpg/) for more information on how to enable this.

Here the list of global information which interract with the GPG functionality:

-   `gpg.program` - The program used to sign your commits.
-   `commit.gpgsign` - `true` to enforce the signature for all commit.
-   `user.email` - Your e-mail address which will be used to find the GPG key associated with it.
-   `user.signingkey` - The GPG signature key to use. Needed if you have multiple key for your e-mail.

I would recommand you to define these properties on **global** in the git configuration so that they are used by default by all git projects.

On windows, I would recommand you to define the full path to the gpg executable so that each progamme can correctly ask you your GPG password.

Example:

```shell
git config --global --add gpg.program "C:\Program Files (x86)\GNU\GnuPG\gpg2.exe"
```

You can also configure a different GPG key per project by overriding `user.email` and `user.signingkey` on the **local** git configuration.

```shell
git config --local --add user.email <YourOtherEMailAddress>
git config --local --add user.signingkey <YourOtherGPGKey>
```

## More Information

### Prefer `git rebase` over `git merge`

-   [We use ‘git rebase’ and so should you](https://medium.com/@sellarafaeli/we-use-git-rebase-and-so-should-you-be89d1932a14)
-   [Getting solid at Git rebase vs. merge](https://delicious-insights.com/en/posts/getting-solid-at-git-rebase-vs-merge/)
-   [Git rebase -i belong to us](https://medium.com/@sellarafaeli/git-rebase-i-belong-to-us-4d7010387683)
