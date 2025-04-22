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
* Maybe [python-liquid](https://github.com/jg-rp/liquid) or
  [liquidpy](https://github.com/pwwang/liquidpy) (or really any Liquid
  implementation where you could add a `{% dot %}` filter)
* Using a prelude:

  `python3 -m cogapp -p "$(cat prelude.py)" example.md`

  where `prelude.py` is

  ```python
  import subprocess
  import hashlib
  def dot(dot_source, out_file_name=None):
      input_bytes = dot_source.encode('utf-8')
      if out_file_name is None:
          out_file_name = hashlib.md5(input_bytes).hexdigest() + ".svg"
      subprocess.check_output(['dot', '-Tsvg', '-o', out_file_name], input=input_bytes)
      cog.out(f'<object data="{out_file_name}" type="image/svg+xml"></object>')
  ```
