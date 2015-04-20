### Install on OSX

(In the future there will be brew package)

1. Download binary for your system (modify v0.1.14 with latest release number):
	```bash
	sudo wget -O /usr/local/bin/gitlab-ci-multi-runner https://github.com/ayufan/gitlab-ci-multi-runner/releases/download/v0.1.14/gitlab-ci-multi-runner-darwin-amd64
	```

1. Give it permissions to execute:
	```bash
	sudo chmod +x /usr/local/bin/gitlab-ci-multi-runner
	```

1. The rest of commands execute as user who will run the runner

1. Setup the runner
	```bash
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
  shell

  INFO[0037] Runner registered successfully. Feel free to start it, but if it's running already the config should be automatically reloaded!
  ```


1. Start the runner
	```bash
	$ gitlab-ci-multi-runner run
	```

1. Voila! Runner has been started and will monitor for builds.

*NOTE* At this moment it is not possible to install the runner as a service, contributions are welcome. This means that you will have to start the runner manually after reboot.

#### Updating

1. Make sure that the runner is stopped.

1. Download binary for your system from https://github.com/ayufan/gitlab-ci-multi-runner/releases and replace runner's executable:
	```bash
	wget -O /usr/local/bin/gitlab-ci-multi-runner https://github.com/ayufan/gitlab-ci-multi-runner/releases/download/v0.1.14/gitlab-ci-multi-runner-darwin-amd64
	```

1. Give it permissions to execute:
	```bash
	chmod +x /usr/local/bin/gitlab-ci-multi-runner
	```

1. Run the service:
	```bash
	gitlab-ci-multi-runner run
	```
