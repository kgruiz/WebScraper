  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Model ](/docs/reference/model/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Figure ](/docs/reference/model/figure/)

#  ` figure ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

A figure with an optional caption.

Automatically detects its kind to select the correct counting track. For
example, figures containing images will be numbered separately from figures
containing tables.

##  Examples

The example below shows a basic figure with an image:

    
    
    @glacier shows a glacier. Glaciers
    are complex systems.
    
    #figure(
      image("glacier.jpg", width: 80%),
      caption: [A curious figure.],
    ) <glacier>
    

![Preview](/assets/docs/udw8J1zW8CDfoYB1XTzdLgAAAAAAAAAA.png)

You can also insert [ tables ](/docs/reference/model/table/) into figures to
give them a caption. The figure will detect this and automatically use a
separate counter.

    
    
    #figure(
      table(
        columns: 4,
        [t], [1], [2], [3],
        [y], [0.3s], [0.4s], [0.8s],
      ),
      caption: [Timing results],
    )
    

![Preview](/assets/docs/_RaOJik9O5UoQO8Eq6OM9gAAAAAAAAAA.png)

This behaviour can be overridden by explicitly specifying the figure's ` kind
` . All figures of the same kind share a common counter.

##  Figure behaviour

By default, figures are placed within the flow of content. To make them float
to the top or bottom of the page, you can use the [ ` placement `
](/docs/reference/model/figure/#parameters-placement) argument.

If your figure is too large and its contents are breakable across pages (e.g.
if it contains a large table), then you can make the figure itself breakable
across pages as well with this show rule:

    
    
    #show figure: set block(breakable: true)
    

See the [ block ](/docs/reference/layout/block/#parameters-breakable)
documentation for more information about breakable and non-breakable blocks.

##  Caption customization

You can modify the appearance of the figure's caption with its associated [ `
caption ` ](/docs/reference/model/figure/#definitions-caption) function. In
the example below, we emphasize all captions:

    
    
    #show figure.caption: emph
    
    #figure(
      rect[Hello],
      caption: [I am emphasized!],
    )
    

![Preview](/assets/docs/_XYhSBTt1dmjYR9A4n_aCgAAAAAAAAAA.png)

By using a [ ` where ` ](/docs/reference/foundations/function/#definitions-
where) selector, we can scope such rules to specific kinds of figures. For
example, to position the caption above tables, but keep it below for all other
kinds of figures, we could write the following show-set rule:

    
    
    #show figure.where(
      kind: table
    ): set figure.caption(position: top)
    
    #figure(
      table(columns: 2)[A][B][C][D],
      caption: [I'm up here],
    )
    

![Preview](/assets/docs/5FXY-vQKID4Q1FYsR4Ix9AAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

figure  (

[ content ](/docs/reference/foundations/content/) ,  placement  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ alignment
](/docs/reference/layout/alignment/) ,  scope  :  [ str
](/docs/reference/foundations/str/) ,  caption  :  [ none
](/docs/reference/foundations/none/) [ content
](/docs/reference/foundations/content/) ,  kind  :  [ auto
](/docs/reference/foundations/auto/) [ str ](/docs/reference/foundations/str/)
[ function ](/docs/reference/foundations/function/) ,  supplement  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ content
](/docs/reference/foundations/content/) [ function
](/docs/reference/foundations/function/) ,  numbering  :  [ none
](/docs/reference/foundations/none/) [ str ](/docs/reference/foundations/str/)
[ function ](/docs/reference/foundations/function/) ,  gap  :  [ length
](/docs/reference/layout/length/) ,  outlined  :  [ bool
](/docs/reference/foundations/bool/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` body `

[ content ](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The content of the figure. Often, an [ image
](/docs/reference/visualize/image/ "image") .

###  ` placement `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ alignment
](/docs/reference/layout/alignment/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The figure's placement on the page.

  * ` none  ` : The figure stays in-flow exactly where it was specified like other content. 
  * ` auto  ` : The figure picks ` top ` or ` bottom ` depending on which is closer. 
  * ` top ` : The figure floats to the top of the page. 
  * ` bottom ` : The figure floats to the bottom of the page. 

The gap between the main flow content and the floating figure is controlled by
the [ ` clearance ` ](/docs/reference/layout/place/#parameters-clearance)
argument on the ` place ` function.

Default: ` none  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(height: 200pt)
    
    = Introduction
    #figure(
      placement: bottom,
      caption: [A glacier],
      image("glacier.jpg", width: 60%),
    )
    #lorem(60)
    

![Preview](/assets/docs/AvTTV4CvkxyZB8XrzNUT3wAAAAAAAAAA.png)
![Preview](/assets/docs/AvTTV4CvkxyZB8XrzNUT3wAAAAAAAAAB.png)

###  ` scope `

[ str ](/docs/reference/foundations/str/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Relative to which containing scope the figure is placed.

Set this to ` "parent"  ` to create a full-width figure in a two-column
document.

Has no effect if ` placement ` is ` none  ` .

Variant  |  Details   
---|---  
` "  column  " ` |  Place into the current column.   
` "  parent  " ` |  Place relative to the parent, letting the content span over all columns.   
  
Default: ` "column"  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set page(height: 250pt, columns: 2)
    
    = Introduction
    #figure(
      placement: bottom,
      scope: "parent",
      caption: [A glacier],
      image("glacier.jpg", width: 60%),
    )
    #lorem(60)
    

![Preview](/assets/docs/_zX5K9NHfd2mYYCeJmag7wAAAAAAAAAA.png)
![Preview](/assets/docs/_zX5K9NHfd2mYYCeJmag7wAAAAAAAAAB.png)

###  ` caption `

[ none ](/docs/reference/foundations/none/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The figure's caption.

Default: ` none  `

###  ` kind `

[ auto ](/docs/reference/foundations/auto/) or  [ str
](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The kind of figure this is.

All figures of the same kind share a common counter.

If set to ` auto  ` , the figure will try to automatically determine its kind
based on the type of its body. Automatically detected kinds are [ tables
](/docs/reference/model/table/) and [ code ](/docs/reference/text/raw/) . In
other cases, the inferred kind is that of an [ image
](/docs/reference/visualize/image/ "image") .

Setting this to something other than ` auto  ` will override the automatic
detection. This can be useful if

  * you wish to create a custom figure type that is not an [ image ](/docs/reference/visualize/image/ "image") , a [ table ](/docs/reference/model/table/ "table") or [ code ](/docs/reference/text/raw/) , 
  * you want to force the figure to use a specific counter regardless of its content. 

You can set the kind to be an element function or a string. If you set it to
an element function other than [ ` table ` ](/docs/reference/model/table/) , [
` raw ` ](/docs/reference/text/raw/) or [ ` image `
](/docs/reference/visualize/image/) , you will need to manually specify the
figure's supplement.

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #figure(
      circle(radius: 10pt),
      caption: [A curious atom.],
      kind: "atom",
      supplement: [Atom],
    )
    

![Preview](/assets/docs/gnEhUtPlQLC9DmHftY4vzQAAAAAAAAAA.png)

###  ` supplement `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ content
](/docs/reference/foundations/content/) or  [ function
](/docs/reference/foundations/function/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The figure's supplement.

If set to ` auto  ` , the figure will try to automatically determine the
correct supplement based on the ` kind ` and the active [ text language
](/docs/reference/text/text/#parameters-lang) . If you are using a custom
figure type, you will need to manually specify the supplement.

If a function is specified, it is passed the first descendant of the specified
` kind ` (typically, the figure's body) and should return content.

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #figure(
      [The contents of my figure!],
      caption: [My custom figure],
      supplement: [Bar],
      kind: "foo",
    )
    

![Preview](/assets/docs/_ow3s-d4xSBN6VX-nVHVzQAAAAAAAAAA.png)

###  ` numbering `

[ none ](/docs/reference/foundations/none/) or  [ str
](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to number the figure. Accepts a [ numbering pattern or function
](/docs/reference/model/numbering/) .

Default: ` "1"  `

###  ` gap `

[ length ](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The vertical gap between the body and caption.

Default: ` 0.65em  `

###  ` outlined `

[ bool ](/docs/reference/foundations/bool/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Whether the figure should appear in an [ ` outline `
](/docs/reference/model/outline/ "`outline`") of figures.

Default: ` true  `

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` caption ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

The caption of a figure. This element can be used in set and show rules to
customize the appearance of captions for all figures or figures of a specific
kind.

In addition to its ` pos ` and ` body ` , the ` caption ` also provides the
figure's ` kind ` , ` supplement ` , ` counter ` , and ` numbering ` as
fields. These parts can be used in [ ` where `
](/docs/reference/foundations/function/#definitions-where) selectors and show
rules to build a completely custom caption.

figure  .  caption  (

position  :  [ alignment ](/docs/reference/layout/alignment/) ,  separator  :
[ auto ](/docs/reference/foundations/auto/) [ content
](/docs/reference/foundations/content/) ,  [ content
](/docs/reference/foundations/content/) ,

)  -> [ content ](/docs/reference/foundations/content/)

    
    
    #show figure.caption: emph
    
    #figure(
      rect[Hello],
      caption: [A rectangle],
    )
    

![Preview](/assets/docs/_9Rae3k-14dcb00bWW4ciAAAAAAAAAAA.png)

####  ` position `

[ alignment ](/docs/reference/layout/alignment/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The caption's position in the figure. Either ` top ` or ` bottom ` .

Default: ` bottom `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #show figure.where(
      kind: table
    ): set figure.caption(position: top)
    
    #figure(
      table(columns: 2)[A][B],
      caption: [I'm up here],
    )
    
    #figure(
      rect[Hi],
      caption: [I'm down here],
    )
    
    #figure(
      table(columns: 2)[A][B],
      caption: figure.caption(
        position: bottom,
        [I'm down here too!]
      )
    )
    

![Preview](/assets/docs/IdFKmiavSqMTEqn8wUXuUgAAAAAAAAAA.png)

####  ` separator `

[ auto ](/docs/reference/foundations/auto/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The separator which will appear between the number and body.

If set to ` auto  ` , the separator will be adapted to the current [ language
](/docs/reference/text/text/#parameters-lang) and [ region
](/docs/reference/text/text/#parameters-region) .

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set figure.caption(separator: [ --- ])
    
    #figure(
      rect[Hello],
      caption: [A rectangle],
    )
    

![Preview](/assets/docs/F47AgUphmXiVn12oCb_ECAAAAAAAAAAA.png)

####  ` body `

[ content ](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The caption's body.

Can be used alongside ` kind ` , ` supplement ` , ` counter ` , ` numbering `
, and ` location ` to completely customize the caption.

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #show figure.caption: it => [
      #underline(it.body) |
      #it.supplement
      #context it.counter.display(it.numbering)
    ]
    
    #figure(
      rect[Hello],
      caption: [A rectangle],
    )
    

![Preview](/assets/docs/JxID--FAnIhAECKLMVFiVwAAAAAAAAAA.png)

[ ![â](/assets/icons/16-arrow-right.svg) Emphasis  Previous page
](/docs/reference/model/emph/) [ ![â](/assets/icons/16-arrow-right.svg)
Footnote  Next page  ](/docs/reference/model/footnote/)

