Git Remote Branch
=================

This tool makes it easier to work with git branches and tags by wrapping remote and local operations in one command.

Usecase: Branching
------------------

A typical use-case is to create a branch in in your local git checkout and to push the changes to a remote with the same name, e.g. here on GitHub. You'd then do something like this:

```sh
# Create the branch
$ git branch implement-closures
$ git checkout implement-closures

# Hack away...
$ ...

# Finally, push it and set up tracking
$ git push -u origin master:refs/heads/implement-closures
$ git fetch origin
$ git branch --track implement-closures origin/implement-closures
```

The `grb` command can help you do this with less typing:

```sh
# Create branch, push it, set up tracking, finally switch there
$ grb create implement-closures
```

Usecase: Tagging
----------------

Another use-case is to create a release of a software asset by tagging. You'd type the following in your shell:

```sh
$ git tag -a v1.5.6 -m '- Release v1.5.6'
$ git push origin v1.5.6
```

The `grb` command folds this together in a simple command:

```sh
$ grb tag v1.5.6
```

All supported commands
----------------------

### grb create
Create a branch

```sh
$ grb create <branch-name> # Parent: "master"
$ grb create <branch-name> <parent-branch-name>
```

### grb track
Track an existing remote branch

```sh
$ grb track <remote-branch-name>
```

### grb remove
Remove a branch

```sh
$ grb remove <branch-name>
```

### grb tag
Create a tag

```sh
$ grb tag <tag-name>
```

### grb untag
Remove a tag

```sh
$ grb untag <tag-name>
```
