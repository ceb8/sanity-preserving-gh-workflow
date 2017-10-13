# sanity-preserving-gh-workflow
A command-line script to make it easier to have a github forking workflow that keeps me from getting confused about which "master", "upstream", "origin", etc. that I'm working on.

The key elements are:
1. Have the local clone "master" branch only point to the master branch of the "upstream" repository (i.e., not my fork)
2. In my github fork, never have a "master" branch - instead call it something else like "staging".
3. Never use remote names "origin" and "upstream" when there's a fork.  Therein lies madness (git his no intrinsic concept of "upstream", and github only marginally does).  Instead, just have all the remote names match the github user/organization names.

The script in this repo will ensure those are met when you clone a new repo.  Just put the script somewhere in your `PATH` and run it with the "upstream" repo provided as the command line argument.  For example, to clone and fork *this* repo, you'd do:
```
$ sane_fork_and_clone eteq/sanity-preserving-gh-workflow
```
once that's done you'll have a `sanity-preserving-gh-workflow` directory inside wherever you ran it, with remotes named "eteq" and "{your user name}", and the local master will point to "eteq". You can use ``sane_fork_and_clone --help`` to see the additional command-line options.
