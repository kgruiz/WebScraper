  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Math ](/docs/reference/math/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Cancel ](/docs/reference/math/cancel/)

#  ` cancel ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

Displays a diagonal line over a part of an equation.

This is commonly used to show the elimination of a term.

##  Example

    
    
    Here, we can simplify:
    $ (a dot b dot cancel(x)) /
        cancel(x) $
    

![Preview](/assets/docs/fVEZvXjKTk2s3WO88t3K8AAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

math  .  cancel  (

[ content ](/docs/reference/foundations/content/) ,  length  :  [ relative
](/docs/reference/layout/relative/) ,  inverted  :  [ bool
](/docs/reference/foundations/bool/) ,  cross  :  [ bool
](/docs/reference/foundations/bool/) ,  angle  :  [ auto
](/docs/reference/foundations/auto/) [ angle ](/docs/reference/layout/angle/)
[ function ](/docs/reference/foundations/function/) ,  stroke  :  [ length
](/docs/reference/layout/length/) [ color ](/docs/reference/visualize/color/)
[ gradient ](/docs/reference/visualize/gradient/) [ stroke
](/docs/reference/visualize/stroke/) [ pattern
](/docs/reference/visualize/pattern/) [ dictionary
](/docs/reference/foundations/dictionary/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` body `

[ content ](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The content over which the line should be placed.

###  ` length `

[ relative ](/docs/reference/layout/relative/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The length of the line, relative to the length of the diagonal spanning the
whole element being "cancelled". A value of ` 100%  ` would then have the line
span precisely the element's diagonal.

Default: ` 100%  +  3pt  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    $ a + cancel(x, length: #200%)
        - cancel(x, length: #200%) $
    

![Preview](/assets/docs/_RSKVrNDnF5_pAJyRMmcrAAAAAAAAAAA.png)

###  ` inverted `

[ bool ](/docs/reference/foundations/bool/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Whether the cancel line should be inverted (flipped along the y-axis). For the
default angle setting, inverted means the cancel line points to the top left
instead of top right.

Default: ` false  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    $ (a cancel((b + c), inverted: #true)) /
        cancel(b + c, inverted: #true) $
    

![Preview](/assets/docs/GWluRapeZy8kHQiZ5c3XbQAAAAAAAAAA.png)

###  ` cross `

[ bool ](/docs/reference/foundations/bool/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Whether two opposing cancel lines should be drawn, forming a cross over the
element. Overrides ` inverted ` .

Default: ` false  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    $ cancel(Pi, cross: #true) $
    

![Preview](/assets/docs/biIi09LikcDnwaA0WaNwJQAAAAAAAAAA.png)

###  ` angle `

[ auto ](/docs/reference/foundations/auto/) or  [ angle
](/docs/reference/layout/angle/) or  [ function
](/docs/reference/foundations/function/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How much to rotate the cancel line.

  * If given an angle, the line is rotated by that angle clockwise with respect to the y-axis. 
  * If ` auto  ` , the line assumes the default angle; that is, along the rising diagonal of the content box. 
  * If given a function ` angle => angle ` , the line is rotated, with respect to the y-axis, by the angle returned by that function. The function receives the default angle as its input. 

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    $ cancel(Pi)
      cancel(Pi, angle: #0deg)
      cancel(Pi, angle: #45deg)
      cancel(Pi, angle: #90deg)
      cancel(1/(1+x), angle: #(a => a + 45deg))
      cancel(1/(1+x), angle: #(a => a + 90deg)) $
    

![Preview](/assets/docs/OCEmML9KQSY4Sru0zk3XGwAAAAAAAAAA.png)

###  ` stroke `

[ length ](/docs/reference/layout/length/) or  [ color
](/docs/reference/visualize/color/) or  [ gradient
](/docs/reference/visualize/gradient/) or  [ stroke
](/docs/reference/visualize/stroke/) or  [ pattern
](/docs/reference/visualize/pattern/) or  [ dictionary
](/docs/reference/foundations/dictionary/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

How to [ stroke ](/docs/reference/visualize/stroke/) the cancel line.

Default: ` 0.5pt  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    $ cancel(
      sum x,
      stroke: #(
        paint: red,
        thickness: 1.5pt,
        dash: "dashed",
      ),
    ) $
    

![Preview](/assets/docs/KCV7eimRh0Q3LxZudj8IDAAAAAAAAAAA.png)

[ ![â](/assets/icons/16-arrow-right.svg) Binomial  Previous page
](/docs/reference/math/binom/) [ ![â](/assets/icons/16-arrow-right.svg)
Cases  Next page  ](/docs/reference/math/cases/)

