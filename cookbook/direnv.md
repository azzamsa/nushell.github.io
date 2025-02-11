---
title: Direnv
---

# Direnv

Many people use [direnv](https://direnv.net) to load an environment upon entering a directory as well as unloading it when exiting the directory.
Configuring direnv to work with nushell requires nushell version 0.66 or later.

---

### Configuring direnv

To make direnv work with nushell the way it does with other shells requires us to use the hooks functionality in nushell:

```shell
let-env config = {
  hooks: {
    env_change: {
      PWD: [{
        code: "
          let direnv = (direnv export json | from json)
          let direnv = if ($direnv | length) == 1 { $direnv } else { {} }
          $direnv | load-env
        "
      }]
    }
  }
}
```

With that configuration in place, direnv should now work with nushell.
