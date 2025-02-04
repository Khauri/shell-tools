# Shell Tools

A collection of simple shell utilties that I use in my day-to-day life.

Most are POSIX complicant and should work in any shell

### Installation

Download them, copy-paste them into existing scripts, or have ChatGPT generate them for you when you're writting your own shell scripts. I do not care.

### How do I install all of them at once

The easiest thing to do is clone the repo somewhere on your computer

```sh
git clone [this-repo]
```

Then add the location to your PATH.

On MacOS and some linux distros you can create a new file in `/etc/paths.d`

```sh
echo $PWD | sudo tee /etc/paths.d/shell-tools
```

## Licence

tl;dr: Do whatever you want