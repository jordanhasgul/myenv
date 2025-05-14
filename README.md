# myenv

To setup your environment, follow these steps:

### 1. Install dependencies

* Run the following commands:

```bash
> sudo apt update && sudo apt upgrade
> sudo apt install -y build-essentials, curl, git-all, openssh-client, gpg
```

### 2. Generate SSH Key

* Run the following commands:

```bash
> ssh-keygen -t ed25519 -b 4096 -C "jkhasgul@gmail.com"
> cat ~/.ssh/id_ed225519.pub
```

* Add the SSH key here: https://github.com/settings/ssh/new. 

### 3. Generate GPG Key

* Run the following commands:

```bash
> gpg --quick-gen-key "Jordan Hasgul <jkhasgul@gmail.com>" rsa4096 default never
> gpg --armor --export $(gpg --list-secret-keys --keyid-format=long | grep "^sec" | sed -E 's#^sec[[:space:]]+[^/]+/([^[:space:]]+).*#\1#g')
```

* Add the GPG key here: https://github.com/settings/gpg/new.

### 4. Install Task and run the Taskfile.yml

* Run the following commands:

```bash
> git clone git@github.com:jordanhasgul/myenv.git
> /bin/bash -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b /usr/local/bin
> cd myenv && task setup-myenv
```
