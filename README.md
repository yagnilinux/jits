# snares

The YAGNI Linux package manager. POSIX sh.

```
snares [-r root] [a|r|u|s|l] [pkg]...

  a  add       Install a package and its dependencies.
  r  remove    Remove a package.
  u  update    Sync the repo and upgrade everything.
  s  search    Search the repo.
  l  list      List installed packages.
```

Needs `wget`, `tar` and `sha256sum`. [busybox](https://busybox.net) has all three.

The repo comes from `SNARES_REPO`, `<root>/etc/snares/repo` or `/etc/snares/repo`.

Apps (packages marked `app` in the index) install as one folder in `~/apps` (`/apps` as root),
or `<root>/apps` with `-r`. Removing the folder uninstalls them.

Manual: https://fiordland-linux.codeberg.page/snares.html

CDDL 1.1, see LICENSE.
