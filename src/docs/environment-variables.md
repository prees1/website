---
layout: docs
title: Environment variables
---

# Environment variables

Environment variables that are set by AppVeyor for every build:

* `APPVEYOR` - `True` if build runs in AppVeyor environment
* `CI` - `True` if build runs in AppVeyor environment
* `APPVEYOR_API_URL` - AppVeyor Build Agent API URL
* `APPVEYOR_ACCOUNT_NAME` - account name
* `APPVEYOR_PROJECT_ID` - AppVeyor unique project ID
* `APPVEYOR_PROJECT_NAME` - project name
* `APPVEYOR_PROJECT_SLUG` - project slug (as seen in project details URL)
* `APPVEYOR_BUILD_FOLDER` - path to clone directory
* `APPVEYOR_BUILD_ID` - AppVeyor unique build ID
* `APPVEYOR_BUILD_NUMBER` - build number
* `APPVEYOR_BUILD_VERSION` - build version
* `APPVEYOR_BUILD_WORKER_IMAGE` - current build worker image the build is running on, e.g. `Visual Studio 2015` (also can be used as "tweak" environment variable to set build worker image)
* `APPVEYOR_PULL_REQUEST_NUMBER` - GitHub Pull Request number
* `APPVEYOR_PULL_REQUEST_TITLE` - GitHub Pull Request title
* `APPVEYOR_JOB_ID` - AppVeyor unique job ID
* `APPVEYOR_JOB_NAME` - job name
* `APPVEYOR_JOB_NUMBER` - job number, i.g. 1, 2, etc.
* `APPVEYOR_REPO_PROVIDER` - `github`, `bitbucket`, `kiln`, `vso` or `gitlab`
* `APPVEYOR_REPO_SCM` - `git` or `mercurial`
* `APPVEYOR_REPO_NAME` - repository name in format `owner-name/repo-name`
* `APPVEYOR_REPO_BRANCH` - build branch. For Pull Request commits it is **base** branch PR is merging into
* `APPVEYOR_REPO_TAG` - `true` if build has started by pushed tag; otherwise `false`
* `APPVEYOR_REPO_TAG_NAME` - contains tag name for builds started by tag; otherwise this variable is undefined
* `APPVEYOR_REPO_COMMIT` - commit ID (SHA)
* `APPVEYOR_REPO_COMMIT_AUTHOR` - commit author's name
* `APPVEYOR_REPO_COMMIT_AUTHOR_EMAIL` - commit author's email address
* `APPVEYOR_REPO_COMMIT_TIMESTAMP` - commit date/time
* `APPVEYOR_REPO_COMMIT_MESSAGE` - commit message
* `APPVEYOR_REPO_COMMIT_MESSAGE_EXTENDED` - the rest of commit message after line break (if exists)
* `APPVEYOR_SCHEDULED_BUILD` - `True` if the build runs by scheduler
* `APPVEYOR_FORCED_BUILD` (`True` or undefined) - builds started by "New build" button or from the same API
* `APPVEYOR_RE_BUILD` (`True` or undefined) - build started by "Re-build commit/PR" button of from the same API
* `PLATFORM` - platform name set on Build tab of project settings (or through `platform` parameter in `appveyor.yml`)
* `CONFIGURATION` - configuration name set on Build tab of project settings (or through `configuration` parameter in `appveyor.yml`)

## Tweak environment variables

* `APPVEYOR_ARTIFACT_UPLOAD_TIMEOUT` - artifact upload timeout in seconds. Default is 600 (10 minutes)
* `APPVEYOR_FILE_DOWNLOAD_TIMEOUT` - timeout in seconds to download arbirtary files using `appveyor DownloadFile` command. Default is 300 (5 minutes)
* `APPVEYOR_REPOSITORY_SHALLOW_CLONE_TIMEOUT` - timeout in seconds to download repository (GitHub, Bitbucket or VSTS) as zip file (shallow clone). Default is 1800 (30 minutes)
* `APPVEYOR_CACHE_ENTRY_UPLOAD_DOWNLOAD_TIMEOUT` - timeout in seconds to download or upload each cache entry. Default is 300 (5 minutes)
* `APPVEYOR_CACHE_SKIP_RESTORE` - set to `true` to disable cache restore
* `APPVEYOR_CACHE_SKIP_SAVE` - set to `true` to disable cache update
* `APPVEYOR_WAP_ARTIFACT_NAME` - custom name for WAP artifact (default is the same as project name)
* `APPVEYOR_BUILD_WORKER_IMAGE` - set build worker image for build to run on. Can be done only at build configuration level, not at build time
* `APPVEYOR_SKIP_FINALIZE_ON_EXIT` - if `appveyor exit` or `Exit-AppVeyor` build was called, exit build even without **Finalize** steps (`on_success`, `on_finish` scripts and build cache save)
* `APPVEYOR_SAVE_CACHE_ON_ERROR` - save build cache on build failure. By default build cache is being saved only during successful build **Finalize** steps
