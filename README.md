# Convert-Mardown-file-to-PDF-using-PANDOC
Using Pandoc to generate PDFs from Markdown
on a Mac running macOS 10.13.4

To install the needed components you can use Homebrew

Two Components are needed:
1. Pandoc
2. PDFLaTex

Install instructions:

Use Homebrew to install pandoc:

brew install pandoc

Then use Homebrew to install the PDFLaTex program.

brew install --cask basictex

You should now have all the needed components but it won't work until the pdflatex executable is available in your PATH environment variable. To configure this my technique is to sym link the executable to a directory already in my PATH.

ln -s -v /Library/TeX/texbin/pdflatex /usr/local/bin/pdflatex

Now if I enter which pdflatex on the command line the system responds:
/usr/local/bin/pdflatex

And now I'm able to generate a PDF from my Markdown file with this command

pandoc file.md -s -o file.pdf

Pandoc will take your Markdown file, tranform it to TeX and then run it through the PDFLaTex program to output a PDF file.
