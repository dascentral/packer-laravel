# Laravel AMI

This repository enables the automated creation of an AWS AMI running Ubuntu 22.04 LTS. The image is configured for the hosting of a Laravel application.

The code here is heavily influenced by [Chris Fidao](https://fideloper.com/), who published a free series on Packer at [Cloudcasts.io](https://cloudcasts.io/course/a-packer-primer).

## Installing Packer

See a full list of [Packer downloads](https://www.packer.io/downloads).

```bash
# for macOS users
brew tap hashicorp/tap
brew install hashicorp/tap/packer
```

## Validating the configuration

```bash
# validate the configuration
packer validate laravel.json
```

## Building the AMI

Replace `PROFILE` and `PASSWORD` with the relevant values for your use case.

```bash
# build the image
packer build -var "profile=PROFILE" -var "vault_pass=PASSWORD" laravel.json
```

## Resources

* [Cloudcasts](https://cloudcasts.io/)
* [Packer](https://www.packer.io/)
* [Ubuntu Amazon EC2 AMI Locator](https://cloud-images.ubuntu.com/locator/ec2/)

## Roadmap

* Add [Oh My Zsh](https://ohmyz.sh/) and preferred plugins
* Add [Certbot](https://certbot.eff.org/)
* Explore what else should come over from [ubuntu-dotfiles](https://github.com/dascentral/ubuntu-dotfiles)
