# ATLAS Latex

ATLAS LaTeX class, style files and templates to typeset notes and papers.
See ChangeLog or Git log for history of changes.

*Responsible:* Ian Brock (Ian.Brock@cern.ch)

--------------------------------------------

### Included files

The following template main files exist:

- `atlas-document.tex`: Generic ATLAS document 
- `atlas-document-texmf.tex`: Generic ATLAS document for a central atlaslatex installation 
- `atlas-draft-cover.tex`: Make a standalone cover for an ATLAS draft
- `atlas-preprint-cover.tex`: Make a standalone cover for an ATLAS CERN preprint
- `atlas-auxmat.tex`:	A front page for auxiliary material  
  
The ATLAS document class (`atlasdoc.cls`) and style files can be found in 
the latex directory. The following main style files exist:
- `atlasbiblatex.sty`:		Reference style adjustments for biblatex
- `atlascover.sty`:		Make a cover (CONF note, CERN preprint, ATLAS draft)
- `atlascontribute.sty`:	List of contributors (and authors) for a document
- `atlaspackage.sty`:		Standard packages used in ATLAS documents
- `atlasphysics.sty`:		Useful definitions. This file simply inputs others.

Options can be used to specify which should be included.

Documentation can be found in the doc directory.
  - `atlas-paper.pdf`:		Guide to the content and style of ATLAS papers
  - `atlas-latex.pdf`:		Guide to the use of the ATLAS document templates and styles
  - `atlas-bibtex.pdf`:		Guide to references and BibTeX in ATLAS
  - `atlas-physics.pdf`:	Symbols defined in atlasphysics.sty
  - `atlas-tables.pdf`:	Some guidelines and help for tables  

More detailed information about the package can be found under:

https://twiki.cern.ch/twiki/bin/view/AtlasProtected/PubComLaTeX  

### How to use

The general idea is that, for each document, this package should be cloned into a new directory.
It is assumed that all style files are in a directory latex, which is a subdirectory of 
the one in which the main document sits.

The latex subdirectory can of course be a link to a central style directory.

You can use the `\ATLASLATEXPATH` variable to specify an arbitrary directory.  

To make a new document give the command:
```
  make new [BASENAME=mydocument] [TEXLIVE=YYYY]
```


The TeX Live version is set to 2016 by default.
This version number should be fine for newer versions of TeX Live 
and also for an up-to-date MikTeX 2.9 installation. The command `make help` gives you a bit more assistance on which make targets exist.

#### Running on lxplus
The most common FAQ I get is why atlaslatex does not just compile "out of the box"?
If you are running on lxplus for it to work, you MUST set your PATH correctly:
```
  export PATH=/afs/cern.ch/sw/XML/texlive/latest/bin/x86_64-linux:$PATH
```

A users guide to the templates can be found in `doc/atlas_latex.pdf`. You can produce
this document yourself (and thus test that your LaTeX setup is working)
by giving the commands:
```
  cd doc/atlas_latex
  make
```

or
```
  cd doc/atlas_latex
  pdflatex atlas_latex
  biber    atlas_latex
  pdflatex atlas_latex
  pdflatex atlas_latex
```


Three other make targets are:
  - `make clean`:				Cleans up intermediate files
  - `make cleanpdf`:				Remove output pdf file
  - `make cleanall`:			Also cleans up output pdf file
