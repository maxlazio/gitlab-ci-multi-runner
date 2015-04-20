### Install and initial configuration (For Debian, Ubuntu and CentOS)

1. Add package to apt-get or yum (**THESE REPOSITORIES ARE TEMPORARY AND ARE SUBJECT TO CHANGE**)
  ```bash
  # For Debian/Ubuntu
  curl https://packagecloud.io/install/repositories/ayufan/gitlab-ci-multi-runner/script.deb | sudo bash

  # For CentOS
  curl https://packagecloud.io/install/repositories/ayufan/gitlab-ci-multi-runner/script.rpm | sudo bash
  ```

1. Install `gitlab-ci-multi-runner`
  ```bash
  # For Debian/Ubuntu
  apt-get install gitlab-ci-multi-runner

  # For CentOS
  yum install gitlab-ci-multi-runner
  ```

1. (OPTIONAL) If you want to use runnner in Docker install it:
  ```bash
  curl -sSL https://get.docker.com/ | sh
  ```

1. Setup the runner
  ```bash
  $ cd ~gitlab_ci_multi_runner
  $ gitlab-ci-multi-runner setup
  ```

  Provide the answers to questions asked by the setup screen:

  ```
  Please enter the gitlab-ci coordinator URL (e.g. http://gitlab-ci.org:3000/ )
  https://ci.gitlab.org/

  Please enter the gitlab-ci token for this runner
  xxx

  Please enter the gitlab-ci description for this runner
  my-runner
  INFO[0034] fcf5c619 Registering runner... succeeded

  Please enter the executor: shell, docker, docker-ssh, ssh?
  docker

  Please enter the Docker image (eg. ruby:2.1):
  ruby:2.1
  INFO[0037] Runner registered successfully. Feel free to start it, but if it's running already the config should be automatically reloaded!
  ```

1. Runner should be started already and you are ready to build your projects!

#### Updating

1. To install the latest version, simply execute:

  ```bash
  # For Debian/Ubuntu
  apt-get update
  apt-get install gitlab-ci-multi-runner

  # For CentOS
  yum install gitlab-ci-multi-runner
  ```
