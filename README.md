# Terraform Beginner Bootcamp 2023

## Semantic Versioning  :mage:

This project is going to utilize semantic versioning for it's tagging. 
[semver.org](https://semver.org/)

The general format:

Given a version number  **MAJOR.MINOR.PATCH** , eg. `1.0.1`

- **MAJOR** version when you make incompatible API changes
- **MINOR** version when you add functionality in a backward compatible manner
- **PATCH** version when you make backward compatible bug fixes
Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.


## Install Terraform CLI 

### Considerations with Terraform CLI changes

This project is built against Ubuntu. Please consider checking your Linux Distribution and change accordingly to distribution needs. 

[How to check OS Version in Linux](https://www.cyberciti.biz/faq/how-to-check-os-version-in-linux-command-line/)
The Terraform CLI installation instructions have changed due to gpg keyring changes. So we ned to refer to the latest install CLI instructions via Terraform Documentation and change the scripting for install. 

[Install Terraform CLI Ubuntu/Debian](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

Example of checking
$cat /etc/os-release

````PRETTY_NAME="Ubuntu 22.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.3 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
````

### Refactoring into Bash Scripts 

While fixing the Terraform CLI gpg depraciation issues we noticed that bash scripts were a considerable amount more code. So we decided to create a bash script to install Terraform CLI.

This bash script is located here: [./bin/install_terraform_cli.sh](./bin/install_terraform_cli.sh)


- This will keep the Gitpod Task File[.gitpod.yml](.gitpod.ym) tidy. 
- This will allow us to debug easier and execute manually Terraform CLI install 
- This will allow better portability for other projects that need to install Terraform CLI.
