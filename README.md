How to Cite Datasets and Link to Publications
=============================================

The Digital Curation Centre (DCC) is a centre of expertise in digital information curation, with a focus on research data management. Among its activities is the publication of How-to Guides that provide working knowledge of curation topics. The guides are aimed at people in research or support posts who are new to managing and curating data. 

"How to Cite Datasets and Link to Publications" is a title in this series, and this is where it is maintained.


Branching policy
----------------

There are two main branches in use:

* **master** is used for releases. Versions for review and quality assurance are tagged r1, r2, r3 and so on, while published versions are tagged v2, v3, v4 and so on. (The numbers in the two sequences are not intended to correspond.)
* **draft** is the working branch where the document is revised between releases.

Note that [Version 1 (2011-10-18)](http://www.dcc.ac.uk/webfm_send/865) and [Version 2 (2012-06-20)](http://www.dcc.ac.uk/webfm_send/525) were written using a different system and therefore their history is not recorded in this repository.

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
* the fonts [Charis SIL](http://scripts.sil.org/cms/scripts/page.php?item_id=CharisSIL_download) and [DejaVu Mono](http://dejavu-fonts.org/wiki/Download) (for preview PDF output, though you could choose different ones by editing the Makefile)

For a camera-ready PDF such as the DCC publishes, you will also need the class file `dcchowto.cls` installed to your TeX tree or in your working directory. Currently the only way of getting it is to generate it from the [`dcchowto` DTX file](https://github.com/alex-ball/dcchowto).

To generate both HTML and a camera-ready PDF, simply run this command:

~~~~
make
~~~~

For just the HTML:

~~~~
make html
~~~~

For just the camera-ready PDF:

~~~~
make dtp
~~~~

For a preview PDF:

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

