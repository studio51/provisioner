
Feel free to use our provisioner however it feels right for you or your project. 
However, we do recommend the following setup as the provisioner has been created
with it in mind.

---

The provisioner has been split in two parts:

```
- playbooks
  - vars
    - development.yml
    - global.yml
    - production.yml
    - staging.yml
  - vagrant.yml

```

> playbooks contain application specific configuration which will overwrite any
> role's configuration, if supported.
> In some cases, the playbook will also contain important variables that could
> break some of the provisioner roles, such as app names, users, locations etc..

**If a role requires such variables, a note will be added on the role's
description, so please read the `README.md` carrefully!**



```
- provisioner
  - roles
    - foo
    - bar
 
```

> The provisioner is the soul of your application, kind of. It should be
> treated as a VIP and no modification should be done to it.

> If there are any configurable parts of the role, they should be available for
> you to overwrite, please read the role description in that case.
