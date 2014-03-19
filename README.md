Git Remote Branch
=================

This tool makes it easier to work with git branches and tags by wrapping remote and local operations in one command.

Usecase
-------

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

