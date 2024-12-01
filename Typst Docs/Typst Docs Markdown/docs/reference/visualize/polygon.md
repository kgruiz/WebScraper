  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Visualize ](/docs/reference/visualize/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Polygon ](/docs/reference/visualize/polygon/)

#  ` polygon ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

A closed polygon.

The polygon is defined by its corner points and is closed automatically.

##  Example

    
    
    #polygon(
      fill: blue.lighten(80%),
      stroke: blue,
      (20%, 0pt),
      (60%, 0pt),
      (80%, 2cm),
      (0%,  2cm),
    )
    

![Preview](/assets/docs/TuzATomarVg-0NmUVu3QFAAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

polygon  (

fill  :  [ none ](/docs/reference/foundations/none/) [ color
](/docs/reference/visualize/color/) [ gradient
](/docs/reference/visualize/gradient/) [ pattern
](/docs/reference/visualize/pattern/) ,  fill-rule  :  [ str
](/docs/reference/foundations/str/) ,  stroke  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ length
](/docs/reference/layout/length/) [ color ](/docs/reference/visualize/color/)
[ gradient ](/docs/reference/visualize/gradient/) [ stroke
](/docs/reference/visualize/stroke/) [ pattern
](/docs/reference/visualize/pattern/) [ dictionary
](/docs/reference/foundations/dictionary/) ,  ..  [ array
](/docs/reference/foundations/array/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` fill `

[ none ](/docs/reference/foundations/none/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ pattern
](/docs/reference/visualize/pattern/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to fill the polygon.

When setting a fill, the default stroke disappears. To create a rectangle with
both fill and stroke, you have to configure both.

Default: ` none  `

###  ` fill-rule `

[ str ](/docs/reference/foundations/str/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The drawing rule used to fill the polygon.

See the [ path documentation ](/docs/reference/visualize/path/#parameters-
fill-rule) for an example.

Variant  |  Details   
---|---  
` "  non-zero  " ` |  Specifies that "inside" is computed by a non-zero sum of signed edge crossings.   
` "  even-odd  " ` |  Specifies that "inside" is computed by an odd number of edge crossings.   
  
Default: ` "non-zero"  `

###  ` stroke `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ length
](/docs/reference/layout/length/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ stroke
](/docs/reference/visualize/stroke/) or  [ pattern
](/docs/reference/visualize/pattern/) or  [ dictionary
](/docs/reference/foundations/dictionary/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to [ stroke ](/docs/reference/visualize/stroke/ "stroke") the polygon.
This can be:

Can be set to ` none  ` to disable the stroke or to ` auto  ` for a stroke of
` 1pt  ` black if and if only if no fill is given.

Default: ` auto  `

###  ` vertices `

[ array ](/docs/reference/foundations/array/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

Variadic

Question mark

Variadic parameters can be specified multiple times.

The vertices of the polygon. Each point is specified as an array of two [
relative lengths ](/docs/reference/layout/relative/) .

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` regular `

A regular polygon, defined by its size and number of vertices.

polygon  .  regular  (

fill  :  [ none ](/docs/reference/foundations/none/) [ color
](/docs/reference/visualize/color/) [ gradient
](/docs/reference/visualize/gradient/) [ pattern
](/docs/reference/visualize/pattern/) ,  stroke  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ length
](/docs/reference/layout/length/) [ color ](/docs/reference/visualize/color/)
[ gradient ](/docs/reference/visualize/gradient/) [ stroke
](/docs/reference/visualize/stroke/) [ pattern
](/docs/reference/visualize/pattern/) [ dictionary
](/docs/reference/foundations/dictionary/) ,  size  :  [ length
](/docs/reference/layout/length/) ,  vertices  :  [ int
](/docs/reference/foundations/int/) ,

)  -> [ content ](/docs/reference/foundations/content/)

    
    
    #polygon.regular(
      fill: blue.lighten(80%),
      stroke: blue,
      size: 30pt,
      vertices: 3,
    )
    

![Preview](/assets/docs/nSKAw-cASGAIxDorv3UyHgAAAAAAAAAA.png)

####  ` fill `

[ none ](/docs/reference/foundations/none/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ pattern
](/docs/reference/visualize/pattern/)

How to fill the polygon. See the general [ polygon's documentation
](/docs/reference/visualize/polygon/#parameters-fill) for more details.

####  ` stroke `

[ none ](/docs/reference/foundations/none/) or  [ auto
](/docs/reference/foundations/auto/) or  [ length
](/docs/reference/layout/length/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ stroke
](/docs/reference/visualize/stroke/) or  [ pattern
](/docs/reference/visualize/pattern/) or  [ dictionary
](/docs/reference/foundations/dictionary/)

How to stroke the polygon. See the general [ polygon's documentation
](/docs/reference/visualize/polygon/#parameters-stroke) for more details.

####  ` size `

[ length ](/docs/reference/layout/length/)

The diameter of the [ circumcircle
](https://en.wikipedia.org/wiki/Circumcircle) of the regular polygon.

Default: ` 1em  `

####  ` vertices `

[ int ](/docs/reference/foundations/int/)

The number of vertices in the polygon.

Default: ` 3  `

[ ![â](/assets/icons/16-arrow-right.svg) Pattern  Previous page
](/docs/reference/visualize/pattern/) [ ![â](/assets/icons/16-arrow-
right.svg) Rectangle  Next page  ](/docs/reference/visualize/rect/)

