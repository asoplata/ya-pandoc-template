# ya-pandoc-template
Yet Another Pandoc Template - a very simple system for quick cross-format Pandoc translation

## What is this even?

It's just a Makefile built around the amazing [Pandoc](http://pandoc.org/)
document converter that transforms all Markdown (`.md` filetype) files in the
current directory into one of several *stylized* document formats, customized
using Pandoc's support for custom templates. This includes

- -> stylized LaTeX Beamer presentations (via `templates/custom.beamer`),
- -> stylized LaTeX manuscripts (via `templates/custom.latex`),
- -> stylized double-column LaTeX manuscripts (via
  `templates/custom-double.latex`), and
- -> stylized HTML presentations using
  [reveal.js](https://github.com/hakimel/reveal.js) (via arguments to Pandoc)

## Installation

1. Install the necessary software:
    - Install [Pandoc](http://pandoc.org/)
    - Install the Pandoc extension
      [pandoc-citeproc](https://github.com/jgm/pandoc-citeproc) (TODO this
      may not be necessary?)
    - Install LaTeX if you don't have it already. Some ways to get it include
      [TeX Live](https://www.tug.org/texlive/) and
      [MiKTeX](https://miktex.org/).
    - Install [GNU Make](https://www.gnu.org/software/make/) if you don't
      have it already.
         - Linux likely already has it installed. For OS X you might have to
           install Xcode Command Line Tools from [Apple's developer
           site](https://developer.apple.com/downloads). For Windows,
           installing Make as part of the [Cygwin
           environment](https://www.cygwin.com/) is probably the easiest way
           to get it.
    - Install [the reveal.js library](https://github.com/hakimel/reveal.js/)
      into a folder at `$HOME/.pandoc/revealjs`. This may not be necessary,
      but in the past, I couldn't get reveal.js to be used out of the box.

2. Clone a copy of this repo, e.g.

    git clone https://github.com/asoplata/ya-pandoc-template.git

3. Copy the `templates` folder to your `$HOME/.pandoc` folder.

4. Copy the `Makefile` file to the same folder that contains your Markdown
   files. Note that you will have to do this for every project you want to
   use these templates in...but that means you now have a consistent, easy,
   and reproducible way to build all your documents!

5. Now you're ready to [Use](#Usage) the templates!

## Usage

- Once you've got the following in your folder:
    1. your Markdown files
    2. the Makefile from this repo
    3. (optional) a `bibliography.bib` BibTeX file

- Then, open a terminal in the folder and type **one** of the following commands
  based on what kind of output you want:

```{bash}
    make beamer
    make beamer_bib
    make html
    make html_bib
    make manuscript
    make manuscript_bib
    make manuscript_double
    make manuscript_double_bib
```

- Note: Just to be clear, this builds every Markdown file in the directory where the
  Makefile is run **into a single resulting document**.

#### BibTeX usage

- The "recipes" that end in `_bib` mean that BibTeX will be also be run.
  However, if you want BibTeX support, be aware:
    1. you need to include a `bibliography.bib` file in the current folder,
       and
    2. the build process will **fail** if you do not have a file of that type
       present.

## Examples

At [@edeno](https://github.com/edeno)'s forceful insistence, I have included
some examples of what the outputs look like in the `examples` folder.

## Customization / styling

If you want to see where and what I've stylized, including where you can easily
make your own changes, search the template files for the string
"ya-pandoc-template".

## Acknowledgements

- This would have been impossible without some great blog posts on using Pandoc
  for academia:
    - [http://kieranhealy.org/blog/archives/2014/01/23/plain-text/](http://kieranhealy.org/blog/archives/2014/01/23/plain-text/)
    - [http://jeromyanglim.blogspot.com/2012/07/beamer-pandoc-markdown.html](
http://jeromyanglim.blogspot.com/2012/07/beamer-pandoc-markdown.html)
    - I'm definitely forgetting some, but virtually none of the original
      implementation of this is original. This is NOT MY ORIGINAL IDEA.

- That said, Copyright Boston University 2017, License GPLv3 (when I figure out
  how to declare that correctly).

- If you want a much more serious, feature-rich approach to this kind of thing
  (or are frustrated by the limitations of this), I suggest the Pandoc fork
  [ScholDoc](https://github.com/timtylin/scholdoc) which is the engine for
  [ScholarlyMarkdown](http://scholarlymarkdown.com/).

## Postscript

This supersedes my earlier [Acadoc](https://github.com/asoplata/acadoc) method.
