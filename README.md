# MacBook for Developers
Some opinionated tips and tricks on how to use MacBook more efficiently as Software Engineer migrating from Windows to MacBook.

## Package manager - Brew
We all know apt and yum from Linux world, on MacBook the equivalent is `Brew`. It is not official part of iOS, so we have to install it separately. Just visit [official page](https://brew.sh/) and install it using provided one liner.

Now we can install packages similar as on Linux.

```
brew install wget
```


## Terminal
The integrated terminal is good enough if one is not using it quite often, but as a Developer or DevOps, you probably spend quite some time there. Instead of integrated terminal we can use `iTerm2` terminal which bring us split screens and more. Install it using newly obtained Brew!

```
brew install --cask iterm2
```

Now, find it using Launchpad, note that the name is just iTerm without 2 at the end.

Most common shortcuts that I use are:
- `Command + D` to split terminal horizontally
- `Command + Shift + D` to split terminal vertically
- `Command + W` to close part of terminal  

### Terminal prompt
We usually want to customize our shell prompt. This helps us with identifying on which branch are we currently working, on which Kubernetes cluster is currently selected and so on.

I used to use `oh-my-zsh`, but I lately found more lightweight alternative called `starship`. I suggest you go check it out on [official page](https://starship.rs/).
Oh, and installation? Again with Brew! Just do not forget to add init script to Zsh shell config file. Yes, Zsh is now default shell on MacBook, replacing Bash.

### Terminal autocomplete
I like `zsh-autosuggestions` that suggest commands based on my history. Again, Brew is your friend.


## Living with different versions of tools - Mise
Quite often we want to use different versions of tooling in different repos. Like different versions of Python, Terraform and so on. We could use helpers for each tool like `tfenv`, but I like more general solution - `Mise`. Check it out on [their Github](https://github.com/jdx/mise).

It supports global versions and versions per repo specified in `mise.toml` file. It is super practical if whole team is using it, as then correct versions are selected each time one moves into certain repo folder.

I use Brew for packages that I always want to have up to date and Mise for packages where versions matter, like default Python version or in certain repo.


## Docker containers - Colima
I am not a great fan of Docker Desktop, also there is license to be bought if used in company, so I rather use Colima and Docker client. Check it out at [Github](https://github.com/abiosoft/colima). It spawns Linux virtual machine in the background where Docker daemon is running and then we communicate with it using Docker client on MacBook.

```
brew install colima
brew install docker
```

```
colima start
```

After that Docker commands work our of the box!


## Virtual machines - UTM
For greater segmentation we usually want to use Virtual machines and not containers. Like when VPNing to some capture the flag competition, working with malware or just running software from questionable sources.

We can get UTM from [GitHub](https://github.com/utmapp/UTM).

In my Documents I have folder `iso` with ISO images that I use as install media.

## Text Editor - VSCode
For general development I like [VSCode](https://code.visualstudio.com/docs/setup/mac). Thing that I really like is moving to repo in terminal and opening it using `code .` command.
