# Shell Tools

A collection of simple shell utilties that I use in my day-to-day life.

Most are POSIX complicant and should work in any shell.

### Installation

Download them, copy-paste them into existing scripts, or have ChatGPT generate them for you when you're writting your own shell scripts. I do not care.

All files are standalone and do not depend on any other files or non POSIX dependencies, so you can download or copy just a single script if you want.

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

## Tools

### align

Align given text by some separator.

```sh
echo "shortKey: short\nlongKey: long" | align
# or
align <<EOF
shortKey: short
longerKey: long
EOF
```

Results in:

```txt
shortKey : short
longerKey: long
```

### cmdroute

Useful for creating subcommands in POSIX sh. 

Given a command name it will search the binary's location for subcommand scripts and automatically pass unused arguments to them.

A subcommand script is any script that starts with the given name and is followed by a `-`, `.` or `_`. 

For example, given the directory:
```sh
.
├── wait-for
├── wait-for-failure
├── wait-for-file
├── wait-for-port
├── wait-for-success
└── wait-for-tcp
```

With the contents of `wait-for` containing simply `cmdroute wait-for "@"`, the other scripts can be called with subcommand syntex, for example:

```sh
wait-for failure
```

TODO: In the near feature this will be combinable with other commands that will automatically construct usage documentation

### findcmd

Finds commands in any of the locations in your current $PATH that matches the provided regular expression

Examples:
```sh
# Find all commands where "find" appears in the name
findcmd find
# Find all commands ending with grep
findcmd grep$
```

### rawr

Random Argument WRangler

Picks a random line from a file and provides it as arguments to the given command.

`args.txt`
```txt
world
everyone
```

```sh
rawr args.txt echo hello
# prints either "hello world" or "hello everyone"
```

### trim, trim.end, trim.start

Trim white space from a string on both ends, the tail end, or the start end respectively

Note that each script is standalone and it is not necessary to copy/download all of them.

## Licence

tl;dr: Do whatever you want