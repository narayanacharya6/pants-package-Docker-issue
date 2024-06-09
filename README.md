This repo is for investigating an issue with the Pants package command.

Trying
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