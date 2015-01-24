## APT
------

Ansible role which executes `apt-get` update to ensure your local APT package
cache is up to date. In the same time, it also cleans all the packages which are
no longer needed.

##### Defaults

> In order to overwrite de defaults use the appropiate variables in your playbook.

| Variable                 | Value   | Overwritten by    |
|:-------------------------|:--------|:------------------|
| `apt_cache_valid_time`   | `3600`  | `apt.cache_time`  |
| `apt_install_recommends` | `false` | `apt.recommended` |
| `apt_install_sugggets`   | `false` | `apt.suggested`   |

Usage example:

``` yaml

- apt:
    cache_time: 300
    recommended: true
    suggested: true

```

> Please note that the purpose of this role is not to give you an over the top
> configuration. It's purpose is merely to get you up and running.
