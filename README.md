
Feel free to use our provisioner however it feels right for you or your project.
However, we do recommend the following setup as the provisioner has been created
with it in mind.

---

**The provisioner has been split in two parts:**

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

---

```
- playbooks
  - vars
    - development.yml
    - global.yml
    - production.yml
    - staging.yml
  - vagrant.yml
```

##### You will have to create this structure in the app' root folder.

> playbooks contain application specific configuration which will overwrite any
> role's configuration, if supported.
> In some cases, the playbook will also contain important variables that could
> break some of the provisioner roles, such as app names, users, locations etc..

**A note in the role' description will be added if the role requires a global or
environment specific variable. Se please read the role' `README.md` carefully.**

```
- playbooks
  - vars
    - ..

    As the name suggests, the vars folder contains variables that are required by a role.

    global.yml contains variables that apply to any environment whereas development.yml,
    staging.yml, and production.yml contains variables that apply only to that specific
    environment.
