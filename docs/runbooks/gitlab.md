# Gitlab

## Gotchas

1. Multi-line variables must have `/n` for new lines and then have `echo -e $VAR` to interpolate them properly

## Setup Gitlab Runners

1. Run `sudo vim /srv/gitlab-runner/config/config.toml` to edit the config file
1. Run the following to create a gitlab-runner

    ```
    sudo docker run -d --name gitlab-runner1 --restart always \
      -v /srv/gitlab-runner/config:/etc/gitlab-runner \
      -v /var/run/docker.sock:/var/run/docker.sock \
      gitlab/gitlab-runner:latest
    ```

1. Run `sudo docker run --rm -it -v /srv/gitlab-runner/config:/etc/gitlab-runner gitlab/gitlab-runner register`
