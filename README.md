# gitshots-MacOS
Take a photo each time you make a git commit. Use the binfile make a film out of it. Not configurable, targets MacOS. Inspired by https://github.com/gkalabin/git-shots.

## Prerequisites
  * imagesnap
  * ffmpeg

## Setup
Following steps assume that you have no local post-commit hooks. If you have - use your brain.
  * `brew install imagesnap`
  * `git clone`
  * switch to cloned directory
  * `cp -r .git-templates ~/.git-templates`
  * tell git where to find templates `git config --global init.templatedir '~/.git-templates'`
  * update your existing repos with `git init`
    * if `.git/post-commit` already exists in project `git init` will not update it
    * you will need to `rm` the file and rerun or merge it manually.
  * commits will now put a photo in `~/.gitshots` directory

## Making a film
  * requires `ffmpeg`
  * run `bin/make-film` will output `film_${timestamp}.mp4` to `~/.gitshots`
