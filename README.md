# jits

Just install that shit. The YAGNI Linux package manager. POSIX sh.

```
jits [-r root] [a|r|u|s|l] [pkg]...

  a  add       Install a package and its dependencies.
  r  remove    Remove a package.
  u  update    Sync the repo and upgrade everything.
  s  search    Search the repo.
  l  list      List installed packages.
```

Needs `wget`, `tar` and `sha256sum`. [busybox](https://busybox.net) has all three.

The repo comes from `JITS_REPO`, `<root>/etc/jits/repo` or `/etc/jits/repo`.

Manual: https://yagni-linux.codeberg.page/docs.html#jits

CDDL 1.1, see LICENSE.
