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

Now you should be able to use all regular expressions. Add `-E` to use repetition operators effectively.

- `.` matches **any** character
- `\d{}` matches a **digit**, but you need to use `-P` option
- `?` means the preceding item is **optional** and will be matched once if found
- `*` means that the preceding item will be matched **zero or more times**
- `+` means that the preceding item will be matched **one or more times**
- `{n}` means the preceding item is matched exactly *n* times, while `{n,}` means the item is matched *n* or more times. `{n,m}` means that the preceding item is matched at least *n*times, but not more than *m* times. `{,m}` means that the preceding item is matched, at the most, *m* times.

### Character Classes

* `[aeiou]` is a **list** of characters to match
* `[m-t]` is a **range** of characters to match
* You may add `{n,m}` to a list or range

#### Famous Character Classes

* `[:lower:]` class of lower-case alphabet letters: `[a-z]`
* `[:upper:]` class of upper-case alphabet letters: `[A-Z]`
* `[:alpha:]` class of all alphabetic characters (lower+upper case)
* `[:digit:]` class of 0 to 9 digits
* `[:alnum:]` is a combination of *alpha* and *digit* classes

## Source

[A Beginner’s Guide to Grep: Basics and Regular Expressions](https://opensourceforu.com/2012/06/beginners-guide-gnu-grep-basics/)

[Corey Schafer's YouTube Channel: Linux/Mac Terminal Tutorial: The Grep Command](https://www.youtube.com/watch?v=VGgTmxXp7xQ&feature=youtu.be&list=PL-osiE80TeTvGhHkpvfmKWOiIPF8UVy6c)

