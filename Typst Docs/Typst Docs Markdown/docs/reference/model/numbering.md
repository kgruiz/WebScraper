  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Model ](/docs/reference/model/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Numbering ](/docs/reference/model/numbering/)

#  ` numbering `

Applies a numbering to a sequence of numbers.

A numbering defines how a sequence of numbers should be displayed as content.
It is defined either through a pattern string or an arbitrary function.

A numbering pattern consists of counting symbols, for which the actual number
is substituted, their prefixes, and one suffix. The prefixes and the suffix
are repeated as-is.

##  Example

    
    
    #numbering("1.1)", 1, 2, 3) \
    #numbering("1.a.i", 1, 2) \
    #numbering("I â 1", 12, 2) \
    #numbering(
      (..nums) => nums
        .pos()
        .map(str)
        .join(".") + ")",
      1, 2, 3,
    )
    

![Preview](/assets/docs/ViM4jxlRNjTCcZLHAqTQsQAAAAAAAAAA.png)

##  Numbering patterns and numbering functions

There are multiple instances where you can provide a numbering pattern or
function in Typst. For example, when defining how to number [ headings
](/docs/reference/model/heading/) or [ figures
](/docs/reference/model/figure/) . Every time, the expected format is the same
as the one described below for the [ ` numbering `
](/docs/reference/model/numbering/#parameters-numbering) parameter.

The following example illustrates that a numbering function is just a regular
[ function ](/docs/reference/foundations/function/ "function") that accepts
numbers and returns [ ` content ` ](/docs/reference/foundations/content/
"`content`") .

    
    
    #let unary(.., last) = "|" * last
    #set heading(numbering: unary)
    = First heading
    = Second heading
    = Third heading
    

![Preview](/assets/docs/y3Y2xT6PKYJ3nJF6y9bcPwAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

numbering  (

[ str ](/docs/reference/foundations/str/) [ function
](/docs/reference/foundations/function/) ,  ..  [ int
](/docs/reference/foundations/int/) ,

)  -> any

###  ` numbering `

[ str ](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

Defines how the numbering works.

**Counting symbols** are ` 1 ` , ` a ` , ` A ` , ` i ` , ` I ` , ` ä¸ ` , `
å£¹ ` , ` ã ` , ` ã ` , ` ã¢ ` , ` ã¤ ` , ` × ` , ` ê° ` , ` ã± ` , `
* ` , ` â ` , and ` âµ ` . They are replaced by the number in the sequence,
preserving the original case.

The ` * ` character means that symbols should be used to count, in the order
of ` * ` , ` â ` , ` â¡ ` , ` Â§ ` , ` Â¶ ` , ` â ` . If there are more
than six items, the number is represented using repeated symbols.

**Suffixes** are all characters after the last counting symbol. They are
repeated as-is at the end of any rendered number.

**Prefixes** are all characters that are neither counting symbols nor
suffixes. They are repeated as-is at in front of their rendered equivalent of
their counting symbol.

This parameter can also be an arbitrary function that gets each number as an
individual argument. When given a function, the ` numbering ` function just
forwards the arguments to that function. While this is not particularly useful
in itself, it means that you can just give arbitrary numberings to the `
numbering ` function without caring whether they are defined as a pattern or
function.

###  ` numbers `

[ int ](/docs/reference/foundations/int/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

Variadic

Question mark

Variadic parameters can be specified multiple times.

The numbers to apply the numbering to. Must be positive.

If ` numbering ` is a pattern and more numbers than counting symbols are
given, the last counting symbol with its prefix is repeated.

[ ![â](/assets/icons/16-arrow-right.svg) Numbered List  Previous page
](/docs/reference/model/enum/) [ ![â](/assets/icons/16-arrow-right.svg)
Outline  Next page  ](/docs/reference/model/outline/)

