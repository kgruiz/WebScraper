  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Visualize ](/docs/reference/visualize/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Circle ](/docs/reference/visualize/circle/)

#  ` circle ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

A circle with optional content.

##  Example

    
    
    // Without content.
    #circle(radius: 25pt)
    
    // With content.
    #circle[
      #set align(center + horizon)
      Automatically \
      sized to fit.
    ]
    

![Preview](/assets/docs/H1niwFeoKUTVgzuqcmZ_VgAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

circle  (

radius  :  [ length ](/docs/reference/layout/length/) ,  width  :  [ auto
](/docs/reference/foundations/auto/) [ relative
](/docs/reference/layout/relative/) ,  height  :  [ auto
](/docs/reference/foundations/auto/) [ relative
](/docs/reference/layout/relative/) [ fraction
](/docs/reference/layout/fraction/) ,  fill  :  [ none
](/docs/reference/foundations/none/) [ color
](/docs/reference/visualize/color/) [ gradient
](/docs/reference/visualize/gradient/) [ pattern
](/docs/reference/visualize/pattern/) ,  stroke  :  [ none
](/docs/reference/foundations/none/) [ auto
](/docs/reference/foundations/auto/) [ length
](/docs/reference/layout/length/) [ color ](/docs/reference/visualize/color/)
[ gradient ](/docs/reference/visualize/gradient/) [ stroke
](/docs/reference/visualize/stroke/) [ pattern
](/docs/reference/visualize/pattern/) [ dictionary
](/docs/reference/foundations/dictionary/) ,  inset  :  [ relative
](/docs/reference/layout/relative/) [ dictionary
](/docs/reference/foundations/dictionary/) ,  outset  :  [ relative
](/docs/reference/layout/relative/) [ dictionary
](/docs/reference/foundations/dictionary/) ,  [ none
](/docs/reference/foundations/none/) [ content
](/docs/reference/foundations/content/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` radius `

[ length ](/docs/reference/layout/length/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The circle's radius. This is mutually exclusive with ` width ` and ` height `
.

Default: ` 0pt  `

###  ` width `

[ auto ](/docs/reference/foundations/auto/) or  [ relative
](/docs/reference/layout/relative/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The circle's width. This is mutually exclusive with ` radius ` and ` height `
.

In contrast to ` radius ` , this can be relative to the parent container's
width.

Default: ` auto  `

###  ` height `

[ auto ](/docs/reference/foundations/auto/) or  [ relative
](/docs/reference/layout/relative/) or  [ fraction
](/docs/reference/layout/fraction/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The circle's height. This is mutually exclusive with ` radius ` and ` width `
.

In contrast to ` radius ` , this can be relative to the parent container's
height.

Default: ` auto  `

###  ` fill `

[ none ](/docs/reference/foundations/none/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ pattern
](/docs/reference/visualize/pattern/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to fill the circle. See the [ rectangle's documentation
](/docs/reference/visualize/rect/#parameters-fill) for more details.

Default: ` none  `

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

How to stroke the circle. See the [ rectangle's documentation
](/docs/reference/visualize/rect/#parameters-stroke) for more details.

Default: ` auto  `

###  ` inset `

[ relative ](/docs/reference/layout/relative/) or  [ dictionary
](/docs/reference/foundations/dictionary/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How much to pad the circle's content. See the [ box's documentation
](/docs/reference/layout/box/#parameters-inset) for more details.

Default: ` 0%  +  5pt  `

###  ` outset `

[ relative ](/docs/reference/layout/relative/) or  [ dictionary
](/docs/reference/foundations/dictionary/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How much to expand the circle's size without affecting the layout. See the [
box's documentation ](/docs/reference/layout/box/#parameters-outset) for more
details.

Default: ` (  :  )  `

###  ` body `

[ none ](/docs/reference/foundations/none/) or  [ content
](/docs/reference/foundations/content/)

Positional

Question mark

Positional parameters are specified in order, without names.

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The content to place into the circle. The circle expands to fit this content,
keeping the 1-1 aspect ratio.

Default: ` none  `

[ ![â](/assets/icons/16-arrow-right.svg) Visualize  Previous page
](/docs/reference/visualize/) [ ![â](/assets/icons/16-arrow-right.svg) Color
Next page  ](/docs/reference/visualize/color/)

