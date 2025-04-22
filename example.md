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

<!--[[[cog
dot("""
digraph G {
    rankdir=LR;
    YARV -> HIR;
    HIR -> LIR;
    LIR -> ASM;
}
""", out_file_name="sample.svg")
]]]-->
<!--[[[end]]]-->
