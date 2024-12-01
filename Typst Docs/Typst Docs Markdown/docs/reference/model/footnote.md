  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Model ](/docs/reference/model/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Footnote ](/docs/reference/model/footnote/)

#  ` footnote ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

A footnote.

Includes additional remarks and references on the same page with footnotes. A
footnote will insert a superscript number that links to the note at the bottom
of the page. Notes are numbered sequentially throughout your document and can
break across multiple pages.

To customize the appearance of the entry in the footnote listing, see [ `
footnote.entry ` ](/docs/reference/model/footnote/#definitions-entry) . The
footnote itself is realized as a normal superscript, so you can use a set rule
on the [ ` super ` ](/docs/reference/text/super/ "`super`") function to
customize it. You can also apply a show rule to customize only the footnote
marker (superscript number) in the running text.

##  Example

    
    
    Check the docs for more details.
    #footnote[https://typst.app/docs]
    

![Preview](/assets/docs/Rux1n4IPwOkOpn1s57WxpAAAAAAAAAAA.png)

The footnote automatically attaches itself to the preceding word, even if
there is a space before it in the markup. To force space, you can use the
string ` #  " "  ` or explicit [ horizontal spacing
](/docs/reference/layout/h/) .

By giving a label to a footnote, you can have multiple references to it.

    
    
    You can edit Typst documents online.
    #footnote[https://typst.app/app] <fn>
    Checkout Typst's website. @fn
    And the online app. #footnote(<fn>)
    

![Preview](/assets/docs/xECSHtr0VhzFh5onpw48GQAAAAAAAAAA.png)

_Note:_ Set and show rules in the scope where ` footnote ` is called may not
apply to the footnote's content. See [ here
](https://github.com/typst/typst/issues/1467#issuecomment-1588799440) for more
information.

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

footnote  (

numbering  :  [ str ](/docs/reference/foundations/str/) [ function
](/docs/reference/foundations/function/) ,  [ label
](/docs/reference/foundations/label/) [ content
](/docs/reference/foundations/content/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` numbering `

[ str ](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to number footnotes.

By default, the footnote numbering continues throughout your document. If you
prefer per-page footnote numbering, you can reset the footnote [ counter
](/docs/reference/introspection/counter/ "counter") in the page [ header
](/docs/reference/layout/page/#parameters-header) . In the future, there might
be a simpler way to achieve this.

Default: ` "1"  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set footnote(numbering: "*")
    
    Footnotes:
    #footnote[Star],
    #footnote[Dagger]
    

![Preview](/assets/docs/CVlSBedIWhhzGwE8LefQmwAAAAAAAAAA.png)

###  ` body `

[ label ](/docs/reference/foundations/label/) or  [ content
](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The content to put into the footnote. Can also be the label of another
footnote this one should point to.

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` entry ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

An entry in a footnote list.

This function is not intended to be called directly. Instead, it is used in
set and show rules to customize footnote listings.

footnote  .  entry  (

[ content ](/docs/reference/foundations/content/) ,  separator  :  [ content
](/docs/reference/foundations/content/) ,  clearance  :  [ length
](/docs/reference/layout/length/) ,  gap  :  [ length
](/docs/reference/layout/length/) ,  indent  :  [ length
](/docs/reference/layout/length/) ,

)  -> [ content ](/docs/reference/foundations/content/)

    
    
    #show footnote.entry: set text(red)
    
    My footnote listing
    #footnote[It's down here]
    has red text!
    

![Preview](/assets/docs/OQcOLIwIWFG81ucXxeuiVwAAAAAAAAAA.png)

_Note:_ Footnote entry properties must be uniform across each page run (a page
run is a sequence of pages without an explicit pagebreak in between). For this
reason, set and show rules for footnote entries should be defined before any
page content, typically at the very start of the document.

####  ` note `

[ content ](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The footnote for this entry. It's location can be used to determine the
footnote counter state.

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #show footnote.entry: it => {
      let loc = it.note.location()
      numbering(
        "1: ",
        ..counter(footnote).at(loc),
      )
      it.note.body
    }
    
    Customized #footnote[Hello]
    listing #footnote[World! ð]
    

![Preview](/assets/docs/pITXewKM6sSB5ed44fUp7wAAAAAAAAAA.png)

####  ` separator `

[ content ](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The separator between the document body and the footnote listing.

Default: ` line  (  length  :  30%  +  0pt  ,  stroke  :  0.5pt  )  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set footnote.entry(
      separator: repeat[.]
    )
    
    Testing a different separator.
    #footnote[
      Unconventional, but maybe
      not that bad?
    ]
    

![Preview](/assets/docs/2BZbfiOf16u6fje-JM2KhwAAAAAAAAAA.png)

####  ` clearance `

[ length ](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The amount of clearance between the document body and the separator.

Default: ` 1em  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set footnote.entry(clearance: 3em)
    
    Footnotes also need ...
    #footnote[
      ... some space to breathe.
    ]
    

![Preview](/assets/docs/jGI_-Yxsz0NqX0MjmZS_qQAAAAAAAAAA.png)

####  ` gap `

[ length ](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The gap between footnote entries.

Default: ` 0.5em  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set footnote.entry(gap: 0.8em)
    
    Footnotes:
    #footnote[Spaced],
    #footnote[Apart]
    

![Preview](/assets/docs/3sggupXU7L_bO6KYRBDWHQAAAAAAAAAA.png)

####  ` indent `

[ length ](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The indent of each footnote entry.

Default: ` 1em  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set footnote.entry(indent: 0em)
    
    Footnotes:
    #footnote[No],
    #footnote[Indent]
    

![Preview](/assets/docs/-zkE_ejQDpF6KTPTlZZ3gwAAAAAAAAAA.png)

[ ![â](/assets/icons/16-arrow-right.svg) Figure  Previous page
](/docs/reference/model/figure/) [ ![â](/assets/icons/16-arrow-right.svg)
Heading  Next page  ](/docs/reference/model/heading/)

