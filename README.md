# Scopyleft site generator

Clone the repo, init submodules:

```
$ git checkout sources
$ git submodule init
$ git submodule update
$ cd master
$ git branch
master
* sources
$ git co master
$ cd ..
```

Create a Python virtualenv:

```
$ virtualenv --no-site-packages `pwd`/env  # OR mkvirtualenv --no-site-packages scopyleft
$ pip install -r requirements.txt
$ source enb/bin/activate
```

From the `sources` branch, serve the site locally:

```
$ ./builder.py serve --debug
```

To build the static site into the `master` submodule:

```
$ ./builder.py build
```

Update and deploy to the `master` branch:

```
$ cd master # hint: it's a submodule, hence the trick
$ git branch
* master # double check you're on the master branch!
$ git ci -a -m"updated new version"
$ git push
```

It's automatically pushed online at [scopyleft.fr](http://scopyleft.fr) thanks to github pages.
