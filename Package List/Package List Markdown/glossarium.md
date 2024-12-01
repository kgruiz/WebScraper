#  glossarium

0.5.1

Glossarium is a simple, easily customizable typst glossary.

Featured  Package

> [!TIP] Glossarium is based in great part of the work of [ SÃ©bastien
> dâHerbais de Thun ](https://github.com/Dherse) from his master thesis
> available at: [ https://github.com/Dherse/masterproef
> ](https://github.com/Dherse/masterproef) . His glossary is available under
> the MIT license [ here
> ](https://github.com/Dherse/masterproef/blob/main/elems/acronyms.typ) .

Glossarium is a simple, easily customizable typst glossary inspired by [ LaTeX
glossaries package ](https://www.ctan.org/pkg/glossaries) . You can see
various examples showcasing the different features in the ` examples ` folder.

![Screenshot](https://github.com/typst/packages/raw/main/packages/preview/glossarium/0.5.1/.github/example.png)

##  Manual

##  Fast start

    
    
    #import "@preview/glossarium:0.5.1": make-glossary, register-glossary, print-glossary, gls, glspl
    #show: make-glossary
    #let entry-list = (
      (
        key: "kuleuven",
        short: "KU Leuven",
        long: "Katholieke Universiteit Leuven",
        description: "A university in Belgium.",
      ),
      // Add more terms
    )
    #register-glossary(entry-list)
    // Your document body
    #print-glossary(
     entry-list
    )
    

###  Import and setup

This manual assume you have a good enough understanding of typst markup and
scripting.

For Typst 0.6.0 or later import the package from the typst preview repository:

    
    
    #import "@preview/glossarium:0.5.1": make-glossary, register-glossary, print-glossary, gls, glspl
    

For Typst before 0.6.0 or to use **glossarium** as a local module, download
the package files into your project folder and import ` glossarium.typ ` :

    
    
    #import "glossarium.typ": make-glossary, register-glossary, print-glossary, gls, glspl
    

After importing the package and before making any calls to ` gls ` , ` print-
glossary ` or ` glspl ` , please _**MAKE SURE** _ you add this line

    
    
    #show: make-glossary
    

> _WHY DO WE NEED THAT ?_ : In order to be able to create references to the
> terms in your glossary using typst ref syntax ` @key ` glossarium needs to
> setup some [ show rules ](https://typst.app/docs/tutorial/advanced-styling/)
> before any references exist. This is due to the way typst works, there is no
> workaround.
>
> Therefore I recommend that you always put the ` #show: ... ` statement on
> the line just below the ` #import ` statement.

###  Registering the glossary

First we have to define the terms. A term is a [ dictionary
](https://typst.app/docs/reference/types/dictionary/) as follows:

Key  |  Type  |  Required/Optional  |  Description   
---|---|---|---  
` key ` |  string  |  required  |  Case-sensitive, unique identifier used to reference the term.   
` short ` |  string  |  semi-optional  |  The short form of the term replacing the term citation.   
` long ` |  string or content  |  semi-optional  |  The long form of the term, displayed in the glossary and on the first citation of the term.   
` description ` |  string or content  |  optional  |  The description of the term.   
` plural ` |  string or content  |  optional  |  The pluralized short form of the term.   
` longplural ` |  string or content  |  optional  |  The pluralized long form of the term.   
` group ` |  string  |  optional  |  Case-sensitive group the term belongs to. The terms are displayed by groups in the glossary.   
      
    
    #let entry-list = (
      // minimal term
      (
        key: "kuleuven",
        short: "KU Leuven"
      ),
      // a term with a long form and a group
      (
        key: "unamur",
        short: "UNamur",
        long: "Namur University",
        group: "Universities"
      ),
      // a term with a markup description
      (
        key: "oidc",
        short: "OIDC",
        long: "OpenID Connect",
        description: [
          OpenID is an open standard and decentralized authentication protocol promoted by the non-profit
          #link("https://en.wikipedia.org/wiki/OpenID#OpenID_Foundation")[OpenID Foundation].
        ],
        group: "Acronyms",
      ),
      // a term with a short plural
      (
        key: "potato",
        short: "potato",
        // "plural" will be used when "short" should be pluralized
        plural: "potatoes",
        description: [#lorem(10)],
      ),
      // a term with a long plural
      (
        key: "dm",
        short: "DM",
        long: "diagonal matrix",
        // "longplural" will be used when "long" should be pluralized
        longplural: "diagonal matrices",
        description: "Probably some math stuff idk",
      ),
    )
    

Then the terms are passed as a list to ` register-glossary `

    
    
    #register-glossary(entry-list)
    

###  Printing the glossary

Now, you can display the glossary using the ` print-glossary ` function.

    
    
    #print-glossary(entry-list)
    

By default, the terms that are not referenced in the document are not shown in
the glossary, you can force their appearance by setting the ` show-all `
argument to true.

You can also disable the back-references by setting the parameter ` disable-
back-references ` to ` true ` .

By default, group breaks use ` linebreaks ` . This behaviour can be changed by
setting the ` user-group-break ` parameter to ` pagebreak() ` , or `
colbreak() ` , or any other function that returns the ` content ` you want.

You can call this function from anywhere in your document.

###  Referencing terms.

Referencing terms is done using the key of the terms using the ` gls `
function or the reference syntax.

    
    
    // referencing the OIDC term using gls
    #gls("oidc")
    // displaying the long form forcibly
    #gls("oidc", long: true)
    
    // referencing the OIDC term using the reference syntax
    @oidc
    

####  Handling plurals

You can use the ` glspl ` function and the references supplements to pluralize
terms. The ` plural ` key will be used when ` short ` should be pluralized and
` longplural ` will be used when ` long ` should be pluralized. If the `
plural ` key is missing then glossarium will add an âsâ at the end of the
short form as a fallback.

    
    
    #glspl("potato")
    

Please look at the examples regarding plurals.

####  Overriding the text shown

You can also override the text displayed by setting the ` display ` argument.

    
    
    #gls("oidc", display: "whatever you want")
    

##  Final tips

I recommend setting a show rule for the links to that your readers understand
that they can click on the references to go to the term in the glossary.

    
    
    #show link: set text(fill: blue.darken(60%))
    // links are now blue !
    

###  How to add

Copy this into your project and use the import as  ` glossarium `

    
    
    #import "@preview/glossarium:0.5.1"

![Copy](/assets/icons/16-copy.svg)

Check the docs for  [ more information on how to import packages
](https://typst.app/docs/reference/scripting/#packages) .

###  About

Author  s  :

     slashformotion  & Dherse 
License:

     MIT 
Current version:

     0.5.1 
Last updated:

     October 28, 2024 
First released:

     July 31, 2023 
Archive size:

     10.5 kB [ ![Size icon](/assets/icons/16-download.svg) ](https://packages.typst.org/preview/glossarium-0.5.1.tar.gz)
Repository:

     [ GitHub ](https://github.com/typst-community/glossarium)

###  Where to report issues?

This  package  is a project of  slashformotion and Dherse  .  Report issues on
[ their repository ](https://github.com/typst-community/glossarium) .  You can
also try to ask for help with this  package  on the  [ Forum
](https://forum.typst.app) .

Please report this  package  to the Typst team using the  [ contact form
](https://typst.app/contact) if you believe it is a safety hazard or infringes
upon your rights.

###  Version history

Version  |  Release Date   
---|---  
0.5.1  |  October 28, 2024   
[ 0.5.0 ](https://typst.app/universe/package/glossarium/0.5.0/) |  October 14, 2024   
[ 0.4.2 ](https://typst.app/universe/package/glossarium/0.4.2/) |  October 7, 2024   
[ 0.4.1 ](https://typst.app/universe/package/glossarium/0.4.1/) |  May 29, 2024   
[ 0.4.0 ](https://typst.app/universe/package/glossarium/0.4.0/) |  April 29, 2024   
[ 0.3.0 ](https://typst.app/universe/package/glossarium/0.3.0/) |  April 8, 2024   
[ 0.2.6 ](https://typst.app/universe/package/glossarium/0.2.6/) |  January 29, 2024   
[ 0.2.5 ](https://typst.app/universe/package/glossarium/0.2.5/) |  December 3, 2023   
[ 0.2.4 ](https://typst.app/universe/package/glossarium/0.2.4/) |  November 16, 2023   
[ 0.2.3 ](https://typst.app/universe/package/glossarium/0.2.3/) |  October 30, 2023   
[ 0.2.2 ](https://typst.app/universe/package/glossarium/0.2.2/) |  September 16, 2023   
[ 0.2.1 ](https://typst.app/universe/package/glossarium/0.2.1/) |  September 3, 2023   
[ 0.2.0 ](https://typst.app/universe/package/glossarium/0.2.0/) |  August 19, 2023   
[ 0.1.0 ](https://typst.app/universe/package/glossarium/0.1.0/) |  July 31, 2023   
  
Typst GmbH did not create this  package  and cannot guarantee correct
functionality of this  package  or compatibility with any version of the Typst
compiler or app.

