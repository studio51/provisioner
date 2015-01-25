Ansible role which executes `apt-get` update to ensure your local APT package
cache is up to date. In the same time, it also cleans all the system packages
which are no longer needed.

> Please note that the purpose of this role is not to give you an over the top
> configuration. It's purpose is to merely to get you up and running and give
> you the following:

  * APT Cache latest updates
  * Control over `recommended` and `suggested` settings
  * Control over `unattended upgrades`
  * Additional packages required by your app

##### Defaults

> In order to overwrite the role defaults, use the appropiate variables in your
> playbook.

| Variable                  | Value   | Overwritten by            |
|:--------------------------|:--------|:--------------------------|
| `apt_reset_source_list`   | `true`  | `apt_reset_source`        |
| `apt_cache_valid_time`    | `3600`  | `apt_cache_time`          |
| `apt_install_recommends`  | `false` | `apt_recommended`         |
| `apt_install_sugggets`    | `false` | `apt_suggested`           |
| `apt_auto_remove`         | `true`  | `apt_remove_dependencies` |
| `apt_auto_clean`          | `false` | `apt_clean_packages`      |
| `apt_unattended_upgrades` | `yes`   | `apt_security_updates`    |

###### Usage example:

> In your app/playbooks/example.yml add the following(s)

``` yaml

apt_reset_source: false
apt_cache_time: 3000
apt_recommended: false
apt_suggested: false
apt_remove_dependencies: true
apt_clean_packages: false
apt_security_updates: true

```

##### Packages:

By default, the role installs the most common APT packages:

``` yaml

- python-apt
- curl
- libcurl4-openssl-dev
- libxslt-dev
- libxml2-dev
- sendmail

```

For adding additional packages, please use `apt_packages` variable in your playbook.

###### Usage example:

``` yaml

apt_packages:
  - foo
  - bar
  - daz

```

#### Pool requests are welcomed!
