How to Cite Datasets and Link to Publications
=============================================

The Digital Curation Centre (DCC) is a centre of expertise in digital information curation, with a focus on research data management. Among its activities is the publication of How-to Guides that provide working knowledge of curation topics. The guides are aimed at people in research or support posts who are new to managing and curating data. 

"How to Cite Datasets and Link to Publications" is a title in this series, and this is where it is maintained.


Branching policy
----------------

There are two main branches in use:

* **master** contains released versions (tags v2, v3...).
* **draft** is the working branch where the document is revised between releases.


Authoring convention
--------------------

The document is written in the flavour of Markdown used by [Pandoc](http://johnmacfarlane.net/pandoc/) to make it easy to generate alternative formats.

The references are generated from the bibliographic information in the `cite-datasets.bib` file, which is written in [biblatex](http://www.tex.ac.uk/tex-archive/help/Catalogue/entries/biblatex.html) format.


Compiling the document
----------------------

Turning the Markdown code into HTML and camera-ready PDF is quite involved, so it is recommended you use the provided Makefile. To use it as it stands you will need the following installed on your system:

* the Make utility
* Perl
* pandoc
* pandoc-citeproc
* a TeX distribution (for PDF output)
* the fonts [Charis SIL](http://scripts.sil.org/cms/scripts/page.php?item_id=CharisSIL_download) and [DejaVu Mono](http://dejavu-fonts.org/wiki/Download) (for PDF output, though you could choose different ones by editing the Makefile)

To generate both HTML and a preview PDF, simply run this command:

~~~~
make
~~~~

For just the HTML:

~~~~
make html
~~~~

For just the PDF:

~~~~
make pdf
~~~~

To clean up the auxiliary files:

~~~~
make clean
~~~~

To remove all generated files:

~~~~
make distclean
~~~~

For a camera-ready PDF, there is an additional target `dtp`. It may not be widely useful as it has some additional, difficult dependencies:

* [dcchowto.cls](https://github.com/alex-ball/dcchowto), which is undergoing thorough revision to make it more portable
* Gill Sans (light, regular and bold series) installed in the TeX system (for true fidelity, though it will fall back to more common fonts)
* a slightly hacked version of biblatex-apa (so it can be used with footnotes, but the regular version will work without error)
