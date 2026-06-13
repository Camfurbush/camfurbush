# Useful Docker Commands

Page of useful docker snippets

```sh
docker run -it -v $(pwd):/root/development -v /var/run/docker.sock:/var/run/docker.sock golang -- /bin/bash
```