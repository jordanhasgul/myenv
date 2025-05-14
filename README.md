# myenv

To setup your environment, follow these steps:

## Install dependencies

1. Run the following commands:

```bash
> sudo apt update && sudo apt upgrade
> sudo apt install -y build-essentials, curl, git-all, openssh-client, gpg
```

## Generate SSH Key

1. Run the following commands:

```bash
> ssh-keygen -t ed25519 -b 4096 -C "jkhasgul@gmail.com"
> cat ~/.ssh/id_ed225519.pub
```

2. Add the SSH key here: https://github.com/settings/ssh/new. 

## Generate GPG Key

1. Run the following commands:

```bash
> gpg --quick-gen-key "Jordan Hasgul <jkhasgul@gmail.com>" rsa4096 default never
> gpg --armor --export $(gpg --list-secret-keys --keyid-format=long | grep "^sec" | sed -E 's#^sec[[:space:]]+[^/]+/([^[:space:]]+).*#\1#g')
```

2. Add the GPG key here: https://github.com/settings/gpg/new.

## Install Task and run the Taskfile.yml

1. Run the following commands:

```bash
> sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b /usr/local/bin
> git clone git@github.com:jordanhasgul/myenv.git
> cd myenv && task setup-myenv
```
