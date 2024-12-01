  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Layout ](/docs/reference/layout/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Page ](/docs/reference/layout/page/)

#  ` page ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

Layouts its child onto one or multiple pages.

Although this function is primarily used in set rules to affect page
properties, it can also be used to explicitly render its argument onto a set
of pages of its own.

Pages can be set to use ` auto  ` as their width or height. In this case, the
pages will grow to fit their content on the respective axis.

The [ Guide for Page Setup ](/docs/guides/page-setup-guide/) explains how to
use this and related functions to set up a document with many examples.

##  Example

    
    
    #set page("us-letter")
    
    There you go, US friends!
    

![Preview](/assets/docs/Gsn3vxGfYJJE0DFa5w6toQAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

page  (

paper  :  [ str ](/docs/reference/foundations/str/) ,  width  :  [ auto
](/docs/reference/foundations/auto/) [ length
](/docs/reference/layout/length/) ,  height  :  [ auto
](/docs/reference/foundations/auto/) [ length
](/docs/reference/layout/length/) ,  flipped  :  [ bool
](/docs/reference/foundations/bool/) ,  margin  :  [ auto
](/docs/reference/foundations/auto/) [ relative
](/docs/reference/layout/relative/) [ dictionary
](/docs/reference/foundations/dictionary/) ,  binding  :  [ auto
](/docs/reference/foundations/auto/) [ alignment
](/docs/reference/layout/alignment/) ,  columns  :  [ int
](/docs/reference/foundations/int/) ,  fill  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ color
](/docs/reference/visualize/color/) [ gradient
](/docs/reference/visualize/gradient/) [ pattern
](/docs/reference/visualize/pattern/) ,  numbering  :  [ none
](/docs/reference/foundations/none/) [ str ](/docs/reference/foundations/str/)
[ function ](/docs/reference/foundations/function/) ,  number-align  :  [
alignment ](/docs/reference/layout/alignment/) ,  header  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ content
](/docs/reference/foundations/content/) ,  header-ascent  :  [ relative
](/docs/reference/layout/relative/) ,  footer  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ content
](/docs/reference/foundations/content/) ,  footer-descent  :  [ relative
](/docs/reference/layout/relative/) ,  background  :  [ none
](/docs/reference/foundations/none/) [ content
](/docs/reference/foundations/content/) ,  foreground  :  [ none
](/docs/reference/foundations/none/) [ content
](/docs/reference/foundations/content/) ,  [ content
](/docs/reference/foundations/content/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` paper `

[ str ](/docs/reference/foundations/str/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

A standard paper size to set width and height.

This is just a shorthand for setting ` width ` and ` height ` and, as such,
cannot be retrieved in a context expression.

![](/assets/icons/16-arrow-right.svg) View options

Default: ` "a4"  `

![](/assets/icons/16-arrow-right.svg) View paper sizes

` "  a0  " ` , ` "  a1  " ` , ` "  a2  " ` , ` "  a3  " ` , ` "  a4  " ` , ` "
a5  " ` , ` "  a6  " ` , ` "  a7  " ` , ` "  a8  " ` , ` "  a9  " ` , ` "  a10
" ` , ` "  a11  " ` , ` "  iso-b1  " ` , ` "  iso-b2  " ` , ` "  iso-b3  " ` ,
` "  iso-b4  " ` , ` "  iso-b5  " ` , ` "  iso-b6  " ` , ` "  iso-b7  " ` , `
"  iso-b8  " ` , ` "  iso-c3  " ` , ` "  iso-c4  " ` , ` "  iso-c5  " ` , ` "
iso-c6  " ` , ` "  iso-c7  " ` , ` "  iso-c8  " ` , ` "  din-d3  " ` , ` "
din-d4  " ` , ` "  din-d5  " ` , ` "  din-d6  " ` , ` "  din-d7  " ` , ` "
din-d8  " ` , ` "  sis-g5  " ` , ` "  sis-e5  " ` , ` "  ansi-a  " ` , ` "
ansi-b  " ` , ` "  ansi-c  " ` , ` "  ansi-d  " ` , ` "  ansi-e  " ` , ` "
arch-a  " ` , ` "  arch-b  " ` , ` "  arch-c  " ` , ` "  arch-d  " ` , ` "
arch-e1  " ` , ` "  arch-e  " ` , ` "  jis-b0  " ` , ` "  jis-b1  " ` , ` "
jis-b2  " ` , ` "  jis-b3  " ` , ` "  jis-b4  " ` , ` "  jis-b5  " ` , ` "
jis-b6  " ` , ` "  jis-b7  " ` , ` "  jis-b8  " ` , ` "  jis-b9  " ` , ` "
jis-b10  " ` , ` "  jis-b11  " ` , ` "  sac-d0  " ` , ` "  sac-d1  " ` , ` "
sac-d2  " ` , ` "  sac-d3  " ` , ` "  sac-d4  " ` , ` "  sac-d5  " ` , ` "
sac-d6  " ` , ` "  iso-id-1  " ` , ` "  iso-id-2  " ` , ` "  iso-id-3  " ` , `
"  asia-f4  " ` , ` "  jp-shiroku-ban-4  " ` , ` "  jp-shiroku-ban-5  " ` , `
"  jp-shiroku-ban-6  " ` , ` "  jp-kiku-4  " ` , ` "  jp-kiku-5  " ` , ` "
jp-business-card  " ` , ` "  cn-business-card  " ` , ` "  eu-business-card  "
` , ` "  fr-telliÃ¨re  " ` , ` "  fr-couronne-Ã©criture  " ` , ` "  fr-
couronne-Ã©dition  " ` , ` "  fr-raisin  " ` , ` "  fr-carrÃ©  " ` , ` "  fr-
jÃ©sus  " ` , ` "  uk-brief  " ` , ` "  uk-draft  " ` , ` "  uk-foolscap  " `
, ` "  uk-quarto  " ` , ` "  uk-crown  " ` , ` "  uk-book-a  " ` , ` "  uk-
book-b  " ` , ` "  us-letter  " ` , ` "  us-legal  " ` , ` "  us-tabloid  " `
, ` "  us-executive  " ` , ` "  us-foolscap-folio  " ` , ` "  us-statement  "
` , ` "  us-ledger  " ` , ` "  us-oficio  " ` , ` "  us-gov-letter  " ` , ` "
us-gov-legal  " ` , ` "  us-business-card  " ` , ` "  us-digest  " ` , ` "
us-trade  " ` , ` "  newspaper-compact  " ` , ` "  newspaper-berliner  " ` , `
"  newspaper-broadsheet  " ` , ` "  presentation-16-9  " ` , ` "
presentation-4-3  " `

###  ` width `

[ auto ](/docs/reference/foundations/auto/) or  [ length
](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The width of the page.

Default: ` 595.28pt  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(
      width: 3cm,
      margin: (x: 0cm),
    )
    
    #for i in range(3) {
      box(square(width: 1cm))
    }
    

![Preview](/assets/docs/xcDLR5uuky5aEnJroP3JfQAAAAAAAAAA.png)

###  ` height `

[ auto ](/docs/reference/foundations/auto/) or  [ length
](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The height of the page.

If this is set to ` auto  ` , page breaks can only be triggered manually by
inserting a [ page break ](/docs/reference/layout/pagebreak/) . Most examples
throughout this documentation use ` auto  ` for the height of the page to
dynamically grow and shrink to fit their content.

Default: ` 841.89pt  `

###  ` flipped `

[ bool ](/docs/reference/foundations/bool/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Whether the page is flipped into landscape orientation.

Default: ` false  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(
      "us-business-card",
      flipped: true,
      fill: rgb("f2e5dd"),
    )
    
    #set align(bottom + end)
    #text(14pt)[*Sam H. Richards*] \
    _Procurement Manager_
    
    #set text(10pt)
    17 Main Street \
    New York, NY 10001 \
    +1 555 555 5555
    

![Preview](/assets/docs/NEPMLGLUMuCwXHZB6iu3CAAAAAAAAAAA.png)

###  ` margin `

[ auto ](/docs/reference/foundations/auto/) or  [ relative
](/docs/reference/layout/relative/) or  [ dictionary
](/docs/reference/foundations/dictionary/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The page's margins.

  * ` auto  ` : The margins are set automatically to 2.5/21 times the smaller dimension of the page. This results in 2.5cm margins for an A4 page. 
  * A single length: The same margin on all sides. 
  * A dictionary: With a dictionary, the margins can be set individually. The dictionary can contain the following keys in order of precedence: 
    * ` top ` : The top margin. 
    * ` right ` : The right margin. 
    * ` bottom ` : The bottom margin. 
    * ` left ` : The left margin. 
    * ` inside ` : The margin at the inner side of the page (where the [ binding ](/docs/reference/layout/page/#parameters-binding) is). 
    * ` outside ` : The margin at the outer side of the page (opposite to the [ binding ](/docs/reference/layout/page/#parameters-binding) ). 
    * ` x ` : The horizontal margins. 
    * ` y ` : The vertical margins. 
    * ` rest ` : The margins on all sides except those for which the dictionary explicitly sets a size. 

The values for ` left ` and ` right ` are mutually exclusive with the values
for ` inside ` and ` outside ` .

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(
     width: 3cm,
     height: 4cm,
     margin: (x: 8pt, y: 4pt),
    )
    
    #rect(
      width: 100%,
      height: 100%,
      fill: aqua,
    )
    

![Preview](/assets/docs/OMqyTIx7yDwyNT0DUFniFAAAAAAAAAAA.png)

###  ` binding `

[ auto ](/docs/reference/foundations/auto/) or  [ alignment
](/docs/reference/layout/alignment/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

On which side the pages will be bound.

  * ` auto  ` : Equivalent to ` left ` if the [ text direction ](/docs/reference/text/text/#parameters-dir) is left-to-right and ` right ` if it is right-to-left. 
  * ` left ` : Bound on the left side. 
  * ` right ` : Bound on the right side. 

This affects the meaning of the ` inside ` and ` outside ` options for
margins.

Default: ` auto  `

###  ` columns `

[ int ](/docs/reference/foundations/int/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How many columns the page has.

If you need to insert columns into a page or other container, you can also use
the [ ` columns ` function ](/docs/reference/layout/columns/) .

Default: ` 1  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(columns: 2, height: 4.8cm)
    Climate change is one of the most
    pressing issues of our time, with
    the potential to devastate
    communities, ecosystems, and
    economies around the world. It's
    clear that we need to take urgent
    action to reduce our carbon
    emissions and mitigate the impacts
    of a rapidly changing climate.
    

![Preview](/assets/docs/Qem_NgF0Oyp_LY8JRVFBWQAAAAAAAAAA.png)

###  ` fill `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ pattern
](/docs/reference/visualize/pattern/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The page's background fill.

Setting this to something non-transparent instructs the printer to color the
complete page. If you are considering larger production runs, it may be more
environmentally friendly and cost-effective to source pre-dyed pages and not
set this property.

When set to ` none  ` , the background becomes transparent. Note that PDF
pages will still appear with a (usually white) background in viewers, but they
are actually transparent. (If you print them, no color is used for the
background.)

The default of ` auto  ` results in ` none  ` for PDF output, and ` white `
for PNG and SVG.

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(fill: rgb("444352"))
    #set text(fill: rgb("fdfdfd"))
    *Dark mode enabled.*
    

![Preview](/assets/docs/PLEs9jVtSM3FxsoATa6SAAAAAAAAAAAA.png)

###  ` numbering `

[ none ](/docs/reference/foundations/none/) or  [ str
](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to [ number ](/docs/reference/model/numbering/) the pages.

If an explicit ` footer ` (or ` header ` for top-aligned numbering) is given,
the numbering is ignored.

Default: ` none  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(
      height: 100pt,
      margin: (top: 16pt, bottom: 24pt),
      numbering: "1 / 1",
    )
    
    #lorem(48)
    

![Preview](/assets/docs/RY8f9OM2hb3s_Q3tS3fVgwAAAAAAAAAA.png)
![Preview](/assets/docs/RY8f9OM2hb3s_Q3tS3fVgwAAAAAAAAAB.png)

###  ` number-align `

[ alignment ](/docs/reference/layout/alignment/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The alignment of the page numbering.

If the vertical component is ` top ` , the numbering is placed into the header
and if it is ` bottom ` , it is placed in the footer. Horizon alignment is
forbidden. If an explicit matching ` header ` or ` footer ` is given, the
numbering is ignored.

Default: ` center  +  bottom `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(
      margin: (top: 16pt, bottom: 24pt),
      numbering: "1",
      number-align: right,
    )
    
    #lorem(30)
    

![Preview](/assets/docs/ErvjjUjlAuxqdtzputqWQAAAAAAAAAAA.png)

###  ` header `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The page's header. Fills the top margin of each page.

  * Content: Shows the content as the header. 
  * ` auto  ` : Shows the page number if a ` numbering ` is set and ` number-align ` is ` top ` . 
  * ` none  ` : Suppresses the header. 

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set par(justify: true)
    #set page(
      margin: (top: 32pt, bottom: 20pt),
      header: [
        #set text(8pt)
        #smallcaps[Typst Academcy]
        #h(1fr) _Exercise Sheet 3_
      ],
    )
    
    #lorem(19)
    

![Preview](/assets/docs/nNqGFtf4s-uyEOhXjup1zgAAAAAAAAAA.png)

###  ` header-ascent `

[ relative ](/docs/reference/layout/relative/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The amount the header is raised into the top margin.

Default: ` 30%  +  0pt  `

###  ` footer `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The page's footer. Fills the bottom margin of each page.

  * Content: Shows the content as the footer. 
  * ` auto  ` : Shows the page number if a ` numbering ` is set and ` number-align ` is ` bottom ` . 
  * ` none  ` : Suppresses the footer. 

For just a page number, the ` numbering ` property typically suffices. If you
want to create a custom footer but still display the page number, you can
directly access the [ page counter ](/docs/reference/introspection/counter/) .

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set par(justify: true)
    #set page(
      height: 100pt,
      margin: 20pt,
      footer: context [
        #set align(right)
        #set text(8pt)
        #counter(page).display(
          "1 of I",
          both: true,
        )
      ]
    )
    
    #lorem(48)
    

![Preview](/assets/docs/GK4h2efX4DepjGGiUjzejQAAAAAAAAAA.png)
![Preview](/assets/docs/GK4h2efX4DepjGGiUjzejQAAAAAAAAAB.png)

###  ` footer-descent `

[ relative ](/docs/reference/layout/relative/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The amount the footer is lowered into the bottom margin.

Default: ` 30%  +  0pt  `

###  ` background `

[ none ](/docs/reference/foundations/none/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Content in the page's background.

This content will be placed behind the page's body. It can be used to place a
background image or a watermark.

Default: ` none  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(background: rotate(24deg,
      text(18pt, fill: rgb("FFCBC4"))[
        *CONFIDENTIAL*
      ]
    ))
    
    = Typst's secret plans
    In the year 2023, we plan to take
    over the world (of typesetting).
    

![Preview](/assets/docs/edMhg75ws-GIgq5IJNJbrQAAAAAAAAAA.png)

###  ` foreground `

[ none ](/docs/reference/foundations/none/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Content in the page's foreground.

This content will overlay the page's body.

Default: ` none  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(foreground: text(24pt)[ð¥¸])
    
    Reviewer 2 has marked our paper
    "Weak Reject" because they did
    not understand our approach...
    

![Preview](/assets/docs/UxB2Tju0zg4nh85hMFZNOwAAAAAAAAAA.png)

###  ` body `

[ content ](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The contents of the page(s).

Multiple pages will be created if the content does not fit on a single page. A
new page with the page properties prior to the function invocation will be
created after the body has been typeset.

[ ![â](/assets/icons/16-arrow-right.svg) Padding  Previous page
](/docs/reference/layout/pad/) [ ![â](/assets/icons/16-arrow-right.svg) Page
Break  Next page  ](/docs/reference/layout/pagebreak/)

