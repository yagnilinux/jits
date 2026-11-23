# introit

The YAGNI Linux package manager. POSIX sh.

```
introit [-r root] [a|r|u|s|l] [pkg]...

  a  add       Install a package and its dependencies.
  r  remove    Remove a package.
  u  update    Sync the repo and upgrade everything.
  s  search    Search the repo.
  l  list      List installed packages.
```

Needs `wget`, `tar` and `sha256sum`. [busybox](https://busybox.net) has all three.

The repo comes from `INTROIT_REPO`, `<root>/etc/introit/repo` or `/etc/introit/repo`.

Manual: https://requiem-linux.codeberg.page/introit.html

CDDL 1.1, see LICENSE.
