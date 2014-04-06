Heroku buildpack: Git
============================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpack)
which downloads and builds specified version of git.

Usage
-----

Example usage:

    $ heroku create --stack cedar --buildpack https://github.com/abhishekmunie/heroku-buildpack-git.git
    ...

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack... cloning with git...done
    -----> Git app detected
    -----> Downloading Git ... done
    -----> Installing Git...
    ...
           done
    -----> Discovering process types
    ...

The buildpack will detect your app as Git if it has the file `_git.cfg` in the `root`.

This can be used in combination with [ddollar/heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi)
in order to support more complex use-cases where you need a specific version of git.

Configuring Buildpack
---------------------

Buildpack reads its configuration from `_git.cfg`

    git_version="<git_version>"

Hacking
-------

To modify this buildpack, fork it on Github. Push up changes to your fork, then
create a test app with `--buildpack <your-github-url>` and push to it.