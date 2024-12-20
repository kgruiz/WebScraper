#  blinky

0.1.0

Typesets paper titles in bibliographies as hyperlinks.

This package permits the creation of Typst bibliographies in which paper
titles are typeset as hyperlinks. Hereâs an example (with links typeset in
blue):

![](https://raw.githubusercontent.com/alexanderkoller/typst-
blinky/main/examples/screenshot.png)

The bibliography is generated from a Bibtex file, and citations are done with
the usual Typst mechanisms. The hyperlinks are specified through DOI or URL
fields in the Bibtex entries; if such a field is present, the title of the
entry will be automatically typeset as a hyperlink.

See [ here ](https://github.com/alexanderkoller/typst-
blinky/tree/main/examples) for a full example.

##  Usage

Adding hyperlinks to your bibliography is a two-step process: (a) use a CSL
style with magic symbols (explained below), and (b) enclose the ` bibliography
` command with the ` link-bib-urls ` function:

    
    
    #import "@preview/blinky:0.1.0": link-bib-urls
    
    ... @cite something ... @cite more ...
    
    #let bibsrc = read("custom.bib")
    #link-bib-urls(bibsrc)[
      #bibliography("custom.bib", style: "./association-for-computational-linguistics-blinky.csl")
    ]
    

Observe that the Bibtex file ` custom.bib ` is loaded twice: once to load into
` link-bib-urls ` and once in the standard Typst ` bibliography ` command.
Obviously, this needs to be the same file twice. See under âAlternative
solutionsâ below why this canât be simplified further at the moment.

If a Bibtex entry contains a DOI field, the title will become a hyperlink to
the DOI. Otherwise, if the Bibtex entry contains a URL field, the title will
become a hyperlink to this URL. Otherwise, the title will be shown as normal,
without a link.

##  CSL with magic symbols

Blinky generates the hyperlinked titles through a regex show rule that
replaces a âmagic symbolâ with a [ link
](https://typst.app/docs/reference/model/link/) command. This âmagic
symbolâ is a string of the form ` !!BIBENTRY!<key>!! ` , where ` <key> ` is
the Bibtex citation key of the reference.

You will therefore need to tweak your CSL style to use it with Blinky.
Specifically, in every place where you would usually have the paper title,
i.e.

    
    
    

or similar, your CSL file now instead needs to print a decorated version of
the paperâs citation-key (= Bibtex key):

    
    
    

You can have more prefix before and suffix after the ` !!BIBENTRY! ` and ` !!
` , as in the example, but these magic symbols need to be there so Blinky can
find the places in the document where the hyperlinked title needs to be
inserted.

You can check the [ example CSL file
](https://github.com/alexanderkoller/typst-
blinky/blob/main/examples/association-for-computational-linguistics-
blinky.csl) to see what this looks like in practice; compare to [ the
unmodified original ](https://github.com/citation-style-
language/styles/blob/master/association-for-computational-linguistics.csl) .

##  Alternative solutions

The current mechanism in Blinky is somewhat heavy-handed: a Typst plugin uses
the [ biblatex ](https://github.com/typst/biblatex) crate to parse the Bibtex
file (independently of the normal operations of the ` bibliography ` command),
and then all occurrences of the magic symbol in the Typst bibliography are
replaced by the hyperlinked titles.

It would be great to replace this mechanism by something simpler, but it is
actually remarkably tricky to make bibliography titles hyperlinks with the
current version of Typst (0.11.1). All the alternatives that I could think of
donât work. Here are some of them:

  * Print the URL/DOI using the CSL style, and then use a regex show rule to convert it into a ` link ` around the title somehow. This does not work because most URLs contain a colon character (:), and these [ cause trouble with Typst regexes ](https://github.com/typst/typst/issues/86) . 
  * Make the CSL style output text of the form ` #link(url)[title] ` . This does not work because the content generated by CSL is not evaluated further by Typst. Also, Typst [ does not support show rules for the individual bibliography items ](https://github.com/typst/typst/issues/942) , which makes it tricky to call [ eval ](https://typst.app/docs/reference/foundations/eval/) on them. 
  * Create a show rule for ` link ` . Some CSL styles already generate ` link ` elements if a URL/DOI is present in the bib entry - one could consider replacing it with a ` link ` whose URL is the same as before, but the text is a link symbol or some such. However, a show rule for a link that generates another link runs into an infinite recursion; Typst made [ the deliberate decision ](https://github.com/typst/typst/pull/3327) to handle such recursions only for ` text ` show rules. 
  * The best solution would be to simply use an unmodified CSL file, but it is not clear to me how one would pick out the paper title from the bibliography in a general way. Iâm afraid that any solution that hyperlinks titles will require modifications to the CSL style. 

It would furthermore be desirable to hide the fact that we are reading the
same Bibtex file twice behind a single function call. However, code in a Typst
package [ resolves all filenames relative to the package directory
](https://github.com/typst/typst/issues/2126) , which means that the package
cannot access a bibliography file outside of the package directory. We may be
able to simplify this once [ #971 ](https://github.com/typst/typst/issues/971)
gets addressed.

###  How to add

Copy this into your project and use the import as  ` blinky `

    
    
    #import "@preview/blinky:0.1.0"

![Copy](/assets/icons/16-copy.svg)

Check the docs for  [ more information on how to import packages
](https://typst.app/docs/reference/scripting/#packages) .

###  About

Author  :

     [ Alexander Koller ](mailto:akoller@gmail.com)
License:

     MIT 
Current version:

     0.1.0 
Last updated:

     August 7, 2024 
First released:

     August 7, 2024 
Archive size:

     75.1 kB [ ![Size icon](/assets/icons/16-download.svg) ](https://packages.typst.org/preview/blinky-0.1.0.tar.gz)
Repository:

     [ GitHub ](https://github.com/alexanderkoller/typst-blinky)

###  Where to report issues?

This  package  is a project of  Alexander Koller  .  Report issues on  [ their
repository ](https://github.com/alexanderkoller/typst-blinky) .  You can also
try to ask for help with this  package  on the  [ Forum
](https://forum.typst.app) .

Please report this  package  to the Typst team using the  [ contact form
](https://typst.app/contact) if you believe it is a safety hazard or infringes
upon your rights.

###  Version history

Version  |  Release Date   
---|---  
0.1.0  |  August 7, 2024   
  
Typst GmbH did not create this  package  and cannot guarantee correct
functionality of this  package  or compatibility with any version of the Typst
compiler or app.

