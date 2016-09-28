# CS-221-homework-markdown-template
A markdown template for homework in CS 221.

### Requirement
pandoc and latex environment

on Mac with [Homebrew](http://brew.sh) installed:
```bash
brew install pandoc
brew cask install mactex
```

### How to compile

In root folder of this repository run the following command:

```bash
pandoc -o homework.pdf homework.md --latex-engine=xelatex --template=./template.tex
```

You can also try add this alias in your `.zshrc` or `.bashrc` for easier compilation:

```bash
function md2pdft() {file=$1; filepath=${file%.*}; pandoc -o $filepath.pdf $filepath.md --latex-engine=xelatex --template="`pwd`/template.tex"; }
```

This command accepts one paramenter which is the location of the markdown file. It also assume that the template is at the same directory where this command run and have the name `template.tex`. For example, in the repository root folder run:

```bash
md2pdft homework.md
```

If you are using a Mac, the following alias may be helpful:

```bash
function md2pdfto() {file=$1; filepath=${file%.*}; pandoc -o $filepath.pdf $filepath.md --latex-engine=xelatex --template="`pwd`/template.tex"; open $filepath.pdf;}
```

This script automatically open the PDF generated with the default editor.
