# cogdown

Mostly an amalgamated version of [Ned Batchelder's
cog](https://github.com/nedbat/cog) library, with features added to succinctly
render graphviz in markdown.

## Usage

Add input like:

```markdown
<!-- article.md -->
<!--[[[cog
dot("""
digraph G {
    rankdir=LR;
    YARV -> HIR;
    HIR -> LIR;
    LIR -> ASM;
}
""")
]]]-->
<!--[[[end]]]-->
```

Run `python ./cogapp.py -c -r article.md` (`-c` is for checksum, `-r` is for
in-place).
