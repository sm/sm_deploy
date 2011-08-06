# Deploy BDSM Extension

This extension is used to deploy

## Description

  BDSM Deployment management extension

## Usage

  bdsm deploy <action> \[arguments\]

## Actions

  $(actions)

## Deployment Steps:

1. update_repository
2. deploy:
  a. stage
  b. configure
  c. symlink
  d. replace_current
  e. cleanup
  f. record

## Hooks

For each step there are two hooks one that is run before ('before_' prefix)
and one that is run after ('after_' prefix).

Each hook is the name of a step listed above prefixed with either before_ or
after_.  For example around steps a - f there is a 'before_deploy' and an
'after_deploy'

If you want to execute a task before the code is moved in place but after
everything is setup in the staging area, use 'before_replace_current' hook.

## Notes

If any one of the deployment steps fail, then the deploy should fail as well.
If this is not the case please let me know right away and provide a gist of
'bdsm --trace deploy' so that I can inspect where the failure is occurring.

## Prerequisites

* git
* curl
* rsync
* subversion / mercurial (if the application's repository uses them).

## Resources

* [Online Documentation](http://extensions.beginrescueend.com/deploy/)
* [Pivotal Tracker](https://www.pivotaltracker.com/projects/26822)

