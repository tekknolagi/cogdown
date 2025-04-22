# cogdown

Mostly an amalgamated version of [Ned Batchelder's
cog](https://github.com/nedbat/cog) library, with features added to succinctly
render graphviz in markdown.

## Usage

Add input like [example.md](example.md).

Run `python ./cogapp.py -r example.md` (`-r` is for in-place).

## Alternatives

* [pandoc-filter-graphviz](https://github.com/Hakuyume/pandoc-filter-graphviz)
  and other [pandoc filters](https://benjaminwuethrich.dev/2020-06-29-pbb-dot-graphs.html)
  (see also [panflute](https://github.com/sergiocorreia/panflute))
* [markdown-dot](https://github.com/jawher/markdown-dot)
