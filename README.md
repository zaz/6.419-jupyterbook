# MIT 6.419x Report Templates

## Installation

    git clone https://gitlab.com/MITx-community/data-science/6.419/report-template-jupyterbook.git reports
    cd reports
    pip3 install -r requirements.txt
    git submodule update --init --recursive --remote

The 1st line downloads this repository.  The 2nd moves into the repository.
The 3rd line ensures you have all of the Python package requirements listed
in requirements.txt. The 4th line downloads the datasets for this course.

**Note:** The last 2 lines will download gigabytes of data.  Please open an
issue on GitHub if the datasets here no longer match those given on edX.

## Usage

1. Replace "Full Name" with your name in `_config.yml`
2. Replace `username` with your edX username in each `HW_ModuleX.md` file
3. Check that the questions match those on edX and open an issue on GitHub
   otherwise.
4. Answer questions (see `intro.md` for how to use MyST Markdown and add plots,
   etc)
5. Build the Jupyter Book with `jupyter book build .`
   1. or `jupyter book build --builder pdflatex .` (untested)
   2. or `jupyter book build --builder pdfhtml .` (untested)

### Including code in the footer

A lot of these questions require many lines of code to load and pre-process
the data before the real action happens. You may want to display such code at
the end of the report, but still have it run at the beginning. To do that, we
duplicate the code at the start and end of the report, using
`:tags: ["remove-input"]` at the start to hide the code, but still run it, and
omitting `{code-block}` at the end to show the code, but not run it.

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

## More Resources

Feel free to contribute and add things to the
[GitLab MITx Data Science][1]
repository list.

- [R Markdown](https://github.com/upfl0/MITx-6.419x) — upfl0
- [LaTeX](https://www.overleaf.com/read/ytcwypvhnzyd) — wkuang1

## ToDo

1. Test building directly to PDF (likely just requires some dependencies to be
   installed).
2. Add a CSS file to format the book correctly:
   1. Align username with title.
   2. Don't let pages break up answer blocks.
3. Use Markdown substitutions (`{{author}}`) to eliminate the need to manually
   find and replace your username. I could not get these to work.
4. Do citations the [proper way][2].


 [1]: https://gitlab.com/MITx-community/data-science/
 [2]: https://jupyterbook.org/en/stable/content/citations.html
