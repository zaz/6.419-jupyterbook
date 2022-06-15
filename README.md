# MIT 6.419x Report Templates

## Usage

1. Install jupyter-book, etc:
   ```pip3 install -r requirements.txt```
2. Replace `username` with your edX username in:
   1. `_toc.yml`,
   2. the filenames: `HW1_Module1_username.md`, etc,
   3. and inside the files themselves: `**Name:** username`
3. Check that the questions match those on edX and report an issue on GitHub
   otherwise.
4. Answer questions (see `intro.md` for how to use MyST Markdown and add plots,
   etc)
5. Build the Jupyter Book with `jupyter book build .`
   1. or `jupyter book build --builder pdflatex .` (untested)
   2. or `jupyter book build --builder pdfhtml .` (untested)

## Tips

If you're on Linux and want to continuously rebuild the book when any changes
occur, you could use:

    while :; do watch -gn .1 stat -c %Z * && jupyter book build .; sleep 0.1; done

## ToDo

1. Make font size of final PDF bigger: 11pt.
2. Test building directly to PDF (likely just requires some dependencies to be
   installed).
3. Improve CSS formatting.
4. Use Markdown substitutions (`{{author}}`) to eliminate the need to manually
   find and replace your username. I could not get these to work.
