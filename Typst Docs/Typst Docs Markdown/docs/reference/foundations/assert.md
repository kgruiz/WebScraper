  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Foundations ](/docs/reference/foundations/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Assert ](/docs/reference/foundations/assert/)

#  ` assert `

Ensures that a condition is fulfilled.

Fails with an error if the condition is not fulfilled. Does not produce any
output in the document.

If you wish to test equality between two values, see [ ` assert.eq `
](/docs/reference/foundations/assert/#definitions-eq) and [ ` assert.ne `
](/docs/reference/foundations/assert/#definitions-ne) .

##  Example

    
    
    #assert(1 < 2, message: "math broke")
    

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

assert  (

[ bool ](/docs/reference/foundations/bool/) ,  message  :  [ str
](/docs/reference/foundations/str/) ,

)

###  ` condition `

[ bool ](/docs/reference/foundations/bool/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The condition that must be true for the assertion to pass.

###  ` message `

[ str ](/docs/reference/foundations/str/)

The error message when the assertion fails.

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` eq `

Ensures that two values are equal.

Fails with an error if the first value is not equal to the second. Does not
produce any output in the document.

assert  .  eq  (

any  ,  any  ,  message  :  [ str ](/docs/reference/foundations/str/) ,

)

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #assert.eq(10, 10)
    

####  ` left `

any

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The first value to compare.

####  ` right `

any

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The second value to compare.

####  ` message `

[ str ](/docs/reference/foundations/str/)

An optional message to display on error instead of the representations of the
compared values.

###  ` ne `

Ensures that two values are not equal.

Fails with an error if the first value is equal to the second. Does not
produce any output in the document.

assert  .  ne  (

any  ,  any  ,  message  :  [ str ](/docs/reference/foundations/str/) ,

)

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #assert.ne(3, 4)
    

####  ` left `

any

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The first value to compare.

####  ` right `

any

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The second value to compare.

####  ` message `

[ str ](/docs/reference/foundations/str/)

An optional message to display on error instead of the representations of the
compared values.

[ ![â](/assets/icons/16-arrow-right.svg) Array  Previous page
](/docs/reference/foundations/array/) [ ![â](/assets/icons/16-arrow-
right.svg) Auto  Next page  ](/docs/reference/foundations/auto/)

