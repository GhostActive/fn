# fn

*fn* (short for *filename*) is a utility script, written in bash, replacing special characters in strings to create proper file- or directory names.

## Installation and Deinstallation

**Installation**

Clone GitHub repository
```sh
git clone https://github.com/GhostActive/fn.git
```

Install `fn` to local file system
```sh
cd fn && chmod +x fn && sudo cp fn /usr/local/bin/fn
```

**Deinstallation**

```sh
sudo rm /usr/local/bin/fn
```

## Usage

```
$ fn -h
fn - converts a list of string arguments to proper file- or directory name

Usage: fn [OPTION]... [STRING]...

All non alphanumeric characters are replaced by '-' (dash). Multiple dashes in
the filename are reduced to single one, e.g '--' or '---' gets to '-'. Dashes
at the begin and the end of a name are removed, too.

Options
    -h, --help
            Prints this help message.

    -t      Appends current timestamp (format '%F-%H%M%S') to filename
            as suffix.

    -v      Show version number.

Examples
    $ fn Hello World
    Hello-World

    $ fn https://localhost:8443
    https-localhost-8443

    Writes wget's output to file named like given URL
    $ wget -O /tmp/$(fn -t $URL).html $URL
    ...
```
