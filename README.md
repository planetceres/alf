<div align='center'>
<img src='alf-logo.svg' width=300>

Alf - Your Little Bash Alias Friend
==================================================

![Version](https://img.shields.io/badge/version-0.4.0-blue.svg)
[![Build Status](https://github.com/DannyBen/alf/workflows/Test/badge.svg)](https://github.com/DannyBen/alf/actions?query=workflow%3ATest)

</div>

---

Alf enhances your bash alias management.

Features
--------------------------------------------------

- Create aliases by using a config file
- Create aliases for sub-commands (for example, `g s` for `git status`)
- Synchronize your aliases across hosts or users by uploading your 
  config file to GitHub.


![Demo](/demo/cast.svg)

Alf was developed using the [Bashly Command Line Framework][bashly].



Installation
--------------------------------------------------

Install the `alf` executable script:

    $ bash <(curl -s https://raw.githubusercontent.com/DannyBen/alf/master/setup)

If you prefer to install manually, simply download the [alf](/alf) file,
place it somewhere in your path, and make it executable.

Note that alf requires bash 4.0 or higher (`brew install bash` for mac users).


Using with GitHub-hosted configuration (recommended)
--------------------------------------------------

The easiest way to use alf is to create a repository on github, call it 
`alf-conf`, and put an `alf.conf` file in it.

### 1. Create your own `alf-conf` repository  

- See the [alf.conf](alf.conf) file as a starting point, or
- Fork my [alf-conf][conf] repository

### 2. Connect alf to your repository

```shell
$ alf connect <your github user>
```

### 3. Save and source your aliases

```shell
$ alf save
$ source ~/.bash_aliases  # this normally already exists in your ~/.bashrc
```


Using without GitHub
--------------------------------------------------

If you want to try alf before creating your Github repo, use this method to
create your `bash_aliases` file from a local configuration file.

### 1. Create your `alf.conf` file

See the sample [alf.conf](alf.conf) file as a starting point.

### 2. Save and source your aliases

    $ alf save
    $ source ~/.bash_aliases


Additional usage patterns
--------------------------------------------------

```
$ alf --help
alf - Your Little Bash Alias Friend

Usage:
  alf [command] [options]
  alf [command] --help | -h
  alf --version | -v

Commands:
  connect    Connect to a remote git repository
  download   Perform git pull on the connected repo
  upload     Perform git commit and push on the connected repo
  generate   Generate aliases to stdout
  save       Generate aliases to ~/.bash_aliases
  edit       Open your alf.conf for editing
  which      Show the alias command
  upgrade    Upgrade alf to the latest version

Options:
  --help, -h
    Show this help

  --version, -v
    Show version number

Environment Variables:
  ALF_RC_FILE
    Path to alfrc file
    This file holds the location of the alf-conf repository
    Default: ~/.alfrc

  ALF_ALIASES_FILE
    Path to bash_aliases file
    This file will be generated when calling 'alf save'
    Default: ~/.bash_aliases
```

Related Projects
--------------------------------------------------

For a similar project, but for command shortcuts on a per-directory basis, 
see [opcode][opcode].


Contributing / Support
--------------------------------------------------

If you experience any issue, have a question or a suggestion, or if you wish
to contribute, feel free to [open an issue][issues].

---

[issues]: https://github.com/DannyBen/alf/issues
[conf]: https://github.com/DannyBen/alf-conf
[opcode]: https://github.com/DannyBen/opcode
[bashly]: https://github.com/dannyben/bashly