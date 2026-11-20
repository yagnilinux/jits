# cook

The Sidewinder Linux package manager. POSIX sh.

```
cook [-r root] [a|r|u|s|l] [pkg]...

  a  add       Install a package and its dependencies.
  r  remove    Remove a package.
  u  update    Sync the repo and upgrade everything.
  s  search    Search the repo.
  l  list      List installed packages.
```

Needs `wget`, `tar` and `sha256sum`. [busybox](https://busybox.net) has all three.

The repo comes from `COOK_REPO`, `<root>/etc/cook/repo` or `/etc/cook/repo`.

Manual: https://sidewinder-linux.codeberg.page/cook.html

CDDL 1.1, see LICENSE.
