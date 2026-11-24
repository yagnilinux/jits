# rag

light it. blackout's package manager, in POSIX sh.

```
rag [-r root] a|b|r|u|s|l|f [pkg]...

  a  add       install a bottle and what it needs
  b  build     build it from source, whatever your mix says
  r  remove    remove it
  u  update    sync, then upgrade or rebuild what changed
  s  search    search the crate, or list it all with no word
  l  list      what's installed
  f  fuel  what a bottle can be built with, and what you get
```

A bottle is a package recipe in the crate. Its fuel are the options it knows.
Your mix, `/etc/rag/mix`, says which ones you want:

```
*                 -doc
sys/qoltils       -yt
editors/scrawl      sha256:<sum of the source>
utils/pfetch      @latest
media/ffmpeg      =6.1-3
```

`+name` and `-name` pick fuel, `=version` holds a package, `sha256:` checks the source
against your own sum, `@latest` builds from upstream's git instead of the pinned version.

When your mix matches a bottle's defaults, rag installs the prebuilt package. When it
doesn't, it builds from source with `musl-cc`. Bottles with a `binonly` file only come prebuilt.

Needs `curl` or `wget`, `tar`, `lzfse` and `sha256sum`, plus `git` for `@latest`.

The repo comes from `RAG_REPO`, `<root>/etc/rag/repo` or `/etc/rag/repo`.

Apps install as one folder in `~/apps` (`/apps` as root), or `<root>/apps` with `-r`.
Moving the folder out uninstalls them.

Manual: https://yagnilinux.github.io/rag.html

CDDL 1.1, see LICENSE.
