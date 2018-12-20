# The `grep` command

[TOC]

## Fundamentals

Find string inside an specific file:

```bash
grep "Abner Castro" info.txt
```

Basic options:

- `-w` for **whole words**
- `-i` for **case insensitive**
- `-n` for **line number**
- `-B` see # number of lines  **before**
- `-A` see # number of lines **after**
- `-C` see # number of lines **around**
- `-r` search **recursively** inside subdirectories.
- `-l` just **list** which files contain a match
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

