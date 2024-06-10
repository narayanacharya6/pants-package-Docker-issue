This repo is for investigating an issue with the Pants package command.

Trying with pants 2.20.0 and 2.21.0

```
pants package src/my-project:docker-base-image
```

results in a (possibly unrelated?) error

```
% pants package src/my-project:docker-base-image
11:32:58.94 [INFO] waiting for pantsd to start...
11:33:03.96 [INFO] pantsd started
11:33:04.19 [INFO] Initializing scheduler...
11:33:04.91 [INFO] Scheduler initialized.
11:33:09.18 [ERROR] 1 Exception encountered:

Engine traceback:
  in `package` goal

ValueError: An invalid variable was requested via the --test-extra-env-var mechanism: {PIP_EXTRA_INDEX_URL:
```

With pants 2.22.0a0 the error message is slightly different -

```
% pants package src/my-project:docker-base-image
11:18:55.26 [ERROR] Expected build_args to contain an 'add' element, a 'remove' element or both but found: {"PIP_EXTRA_INDEX_URL": String("<SOME_URL_HERE>")}


Use --print-stacktrace for more error details and/or -ldebug for more logs. 
See https://www.pantsbuild.org/2.22/docs/using-pants/troubleshooting-common-issues for common issues.
Consider reaching out for help: https://www.pantsbuild.org/community/getting-help
```
