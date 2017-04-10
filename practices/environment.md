# Environment

## Use a special directoy for all development applications

A good method to create our development environment is to have a specific repository in which we will put our applications and others tools specific to the development.
This repository should be accessible from all users on the computer in the case than one of our teammate would need to access it.

Example: `C:\development`

That's only if you don't need this to be secured and only accessible for you only. But for such a critical project, the best would be to create a virtual secured disk to be mount only when working on it. To do so, I would sugest to use [VeraCrypt](https://veracrypt.codeplex.com/).

## Avoid minor revision in applications names

Avoid putting the full application's version in the name of the base installation directory. Like this, updating an application, or switching between applications inside an environment variable is made more easier.

As an example, we can take the Java JDK: when installing it, the installer try to set the directory name as `jdk1.8.0_101`. Which can be quite troublesome when we update the application as we will also need to update all environment variables or paths to it...
But, if when installing it, we force the installation's directory's name as `jdk1.8`, then, we won't have to change any environment variable or path. Also, if we need to swith between different kind of jdk version, we will just have to update the major part: from `jdk1.8` to `jdk1.6`.
