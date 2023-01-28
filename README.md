# MIT 6.419x Report Templates

## Usage

1. Install jupyter-book, etc:
   ```pip3 install -r requirements.txt```
2. Replace "Full Name" with your name in `_config.yml`
3. Replace `username` with your edX username in each `HW_ModuleX.md` file
4. Check that the questions match those on edX and report an issue on GitHub
   otherwise.
5. Answer questions (see `intro.md` for how to use MyST Markdown and add plots,
   etc)
6. Build the Jupyter Book with `jupyter book build .`
   1. or `jupyter book build --builder pdflatex .` (untested)
   2. or `jupyter book build --builder pdfhtml .` (untested)

## Tips

If you're on Linux and want to continuously rebuild the book when any changes
occur, you could use:

    while :; do watch -gn .1 stat -c %Z * && jupyter book build .; sleep 0.1; done

## ToDo

1. Test building directly to PDF (likely just requires some dependencies to be
   installed).
2. Add a CSS file to format the book correctly:
   1. Align username with title.
   2. Don't let pages break up answer blocks.
3. Use Markdown substitutions (`{{author}}`) to eliminate the need to manually
   find and replace your username. I could not get these to work.
