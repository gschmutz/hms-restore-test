# `docker exec` web console

A web UI to docker exec from the browser  

**[Documentation](https://github.com/bitbull-team/docker-exec-web-console)** | **[GitHub](https://github.com/bitbull-team/docker-exec-web-console)**

## How to enable?

```
platys init --enable-services DOCKER_EXEC_WEBCONSOLE
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:28375>.

You can select the container to exec into passing its id directly via `cid` query parameter ( eg. `http://192.168.1.112: 28375?cid=<container id>` ) or in the prompt that will show at page load.

You can pass the command to execute passing it via `cmd` query parameter ( eg. `http://192.168.1.112:28375?cid=<container id>&cmd=/bin/sh` ), otherwise it default to `/bin/bash`.
=======
Navigate to <http://10.156.72.251:28375>.

You can select the container to exec into passing its id directly via `cid` query parameter ( eg. `http://10.156.72.251: 28375?cid=<container id>` ) or in the prompt that will show at page load.

You can pass the command to execute passing it via `cmd` query parameter ( eg. `http://10.156.72.251:28375?cid=<container id>&cmd=/bin/sh` ), otherwise it default to `/bin/bash`.
>>>>>>> Stashed changes
