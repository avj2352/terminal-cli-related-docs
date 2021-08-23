# Grep Related Code-snippets, Articles

![Logo](./design/grep-image.png)

## Important Links

- [EggHead Course](https://egghead.io/courses/use-grep-for-fast-search-from-the-command-line)
- [Grep CheatSheet](https://ryanstutorials.net/linuxtutorial/cheatsheetgrep.php)


## Basic Syntax

### Basic Syntax of using Grep

```sh
# Basic grep usage syntax

# grep "<search-query>" file-name

grep "#" grep-cheatsheet.md

# # Grep Related Code-snippets, Articles
# ## Important Links
# ## Basic Syntax

```

### Multiple Files

You can even search multiple files with same extension types

```sh
# Search Multiple files with same extension

grep "#." *.md

# README.md:# Articles on Terminal CLI
# grep-cheatsheet.md:# Grep Related Code-snippets, Articles
# grep-cheatsheet.md:## Important Links
# grep-cheatsheet.md:## Basic Syntax

```

### Recursive search

```sh
# Search recursively

grep -r "important"

```

### Show Line Numbers

```sh
# Shows line numbers
grep -n "#" readme.md
```

## Working with find

- The **find** is used to find files in a particular location. with respect to grep, its syntax is in reverse order

```sh
# find <location> -name "<search-query>"

find . -name "*.jsx"

```
### XARGS

- You can combine grep and find queries to make your search even powerful using **| (pipe)** & **"xargs"**

```sh
# Combine find and grep

find examples -name "*spec.js" | xargs grep "songs"

# Provides list of all spec files which contain the word / phrase songs

# also same as

grep -r --include "*spec.js" "songs"
```

How does it work ? All find queries get stored in the **stdin** & xargs uses grep to run it queries on them

## Git Grep

Use **git grep** to search files we actually care about

- _how is it different ?_ **git grep** simply ignores the files mentioned in the **.gitignore** which is really handy!

```sh
# ignore node_modules if mentioned in .gitignore
git grep -r --include "*spec.js" "songs"

```

## Highlighting Queries

Show search queries in color (highlighted)

```sh
grep -r --color bind
```

## Show Context

Context in grep means underlines

### After

Shows underlines AFTER every search

```sh
# shows 2 underlines AFTER search
grep -A2 --color "#" README.md
```

### Before

Shows underlines BEFORE every search

```sh
# shows 2 underlines BEFORE search
grep -B2 --color "#" README.md
```

### Before & After

Shows underlines Before & After every search

```sh
# shows 2 underlines Before & After search
grep -C2 --color "#" README.md
```

## RegEx

### Match one character

```sh
# Match single occurance of # in README.md
grep --color "#." README.md
# # Articles on Terminal CLI
```

### March 0 or atleast 1 occurance

If you'd like to find atleast one / no occurance of a character use **\?**

```sh
# 0 or 1 atleast occurance of http or https
grep --color "https\?" README.md
# includes http also
```

### March 1 or more (not 0!) occurances

If you'd like to find 1 to many occurance of a character use **\+**

> _This doesn't include no occurances !!_

```sh
# atleast 1 or more occurances of https
grep --color "https\+" README.md
# DOES NOT include http
```










 










