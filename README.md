# MIT 6.419x Report Templates

## Usage

1. Install jupyter-book, and all other packages you might need:
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

### Including code in the footer

A lot of these questions require many lines of code to load and pre-process
the data before the real action happens. You may want to display such code at
the end of the report, but still have it run at the beginning. To do that, we
duplicate the code at the start and end of the report, using
`:tags: ["remove-input"]` at the start to hide the code, but still run it, and
`:tags: ["remove-output"]` at the end to show the code, but not run it.

## Tips

If you're on Linux and want to continuously rebuild the book when any changes
occur, you could use:

    while :; do watch -gn .1 stat -c %Z * && jupyter book build .; sleep 0.1; done

If you have a lot of code blocks that take a long time to run, you may want to
prototype your report in a Jupyter Notebook first. Recompiling a Jupyter Book
will run every code cell from scratch, so can take 10+ minutes for ML-heavy
code. You may be able to build the Jupyter Book directly from your `.ipynb`
instead of converting it to markdown first: See the initial commit of this Git
repository or search online for more details.

## ToDo

1. Test building directly to PDF (likely just requires some dependencies to be
   installed).
2. Add a CSS file to format the book correctly:
   1. Align username with title.
   2. Don't let pages break up answer blocks.
3. Use Markdown substitutions (`{{author}}`) to eliminate the need to manually
   find and replace your username. I could not get these to work.
4. Do citations the [proper way][https://jupyterbook.org/en/stable/content/citations.html].
