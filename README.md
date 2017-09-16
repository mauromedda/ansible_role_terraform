ansible_role_terraform
======================

This is a simple ansible role to install terraform into a RedHat-like 7+ box.


Requirements
------------

This module hasn't specific requirements just Ansible.

Role Variables
--------------

```yaml
terraform_version: 0.10.5
```
 * terraform_version: Specify the terraform version to install

```yaml
terraform_dist_file: "terraform_{{terraform_version}}_linux_amd64.zip"
```
 * terraform_dist_file: Terraform distribution archive

```yaml
terraform_repo_url: "https://releases.hashicorp.com/terraform/{{terraform_version}}/{{ terraform_dist_file }}"
```
 * terraform_repo_url: Terraform distribution URL. Used to fetch the Terraform binary

```yaml
terraform_base_install_dir: /opt/hashicorp/terraform
```

 * terraform_base_install_dir: Root of the Terraform installation

```yaml
terraform_bin: /usr/bin/terraform
```
 * terraform_bin: Terraform binary location

```yaml
terraform_requirements:
  - unzip
```

 * terraform_requirements: Terraform playbook requirements

```yaml
terraform_purge_old: true
```

 * terraform_purge_old: Delete the oldest version installed in the system. Default: true

```yaml
terraform_cleanup: true
```
 * terraform_cleanup: Remove the Terraform distribution archive. Default: true



Example Playbook
----------------

```yaml
---
- hosts: localhost
  become: true
    connection: local

      roles:
          - mauromedda.ansible_role_terraform
```

Usage
-----

[![Terraform_role](https://asciinema.org/a/kTZCGC3aQeioJBN22wyqU1zoo.gif)](https://asciinema.org/a/kTZCGC3aQeioJBN22wyqU1zoo?autoplay=1&preload=1&speed=3)


License
-------

BSD

Author Information
------------------

Author: Mauro Medda 
