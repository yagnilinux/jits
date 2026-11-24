# snares

fiordland's package manager. POSIX sh.

```
snares [-r root] a|b|r|u|s|l|f [pkg]...

  a  add       install an egg and what it needs
  b  build     build it from source, whatever your crest says
  r  remove    remove it
  u  update    sync, then upgrade or rebuild what changed
  s  search    search the rookery, or list it all with no word
  l  list      what's installed
  f  feathers  what an egg can be built with, and what you get
```

An egg is a package recipe in the rookery. Its feathers are the options it knows.
Your crest, `/etc/snares/crest`, says which ones you want:

```
*                 -doc
sys/qoltils       -yt
editors/peck      sha256:<sum of the source>
utils/pfetch      @latest
media/ffmpeg      =6.1-3
```

`+name` and `-name` pick feathers, `=version` holds a package, `sha256:` checks the source
against your own sum, `@latest` builds from upstream's git instead of the pinned version.

When your crest matches an egg's defaults, snares installs the prebuilt package. When it
doesn't, it builds from source with `musl-cc`. Eggs with a `binonly` file only come prebuilt.

Needs `curl` or `wget`, `tar`, `lzfse` and `sha256sum`, plus `git` for `@latest`.

The repo comes from `SNARES_REPO`, `<root>/etc/snares/repo` or `/etc/snares/repo`.

Apps install as one folder in `~/apps` (`/apps` as root), or `<root>/apps` with `-r`.
Moving the folder out uninstalls them.

Manual: https://fiordland-linux.codeberg.page/missal.html#snares

CDDL 1.1, see LICENSE.
