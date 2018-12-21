# The `grep` command

[TOC]

## Fundamentals

Find string inside a specific file:

```bash
grep "Abner Castro" info.txt
```

Basic options:

- `-w` for **whole words**
- `-i` for **case insensitive**
- `-n` for **line number**
- `-v` for **inverted** search
- `-B` see # number of lines  **before**
- `-A` see # number of lines **after**
- `-C` see # number of lines **around**
- `-H` prints **filename** of files that matches the search
- `-r` search **recursively** inside subdirectories.
- `-l` just **list** which files contain a match, or use `--files-with-match`
- `-L` **list** files that **do not** contain match, or use `--files-without-match` 
- `-c` lists and displays the number of **occurrences** in each file

Search through every file in a directory

```shell
grep -win "Abner Castro" ./*.txt
```

But that won't search inside subdirectories. To do that, use the `-r` option.

## Using Pipes

Use `|` to pipe content into `grep`. For example, search `history` for a specific command:

```shell
history | grep "git commit" | grep "dotfile"
```

## Using Regular Expressions

Install GNU version of `grep` using Homebrew.

```shell
brew install grep
```

And now use `ggrep` to use GNU version. To use that version as default, pass `--with-default-names` when installing.

Now you should be able to use all regular expressions.

- `.` matches **any** character
- `\d{}` matches a **digit**, but you need to use `-P` option

## Source

[A Beginner’s Guide to Grep: Basics and Regular Expressions](https://opensourceforu.com/2012/06/beginners-guide-gnu-grep-basics/)

[Corey Schafer's YouTube Channel: Linux/Mac Terminal Tutorial: The Grep Command](https://www.youtube.com/watch?v=VGgTmxXp7xQ&feature=youtu.be&list=PL-osiE80TeTvGhHkpvfmKWOiIPF8UVy6c)

