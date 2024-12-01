  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Introspection ](/docs/reference/introspection/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Counter ](/docs/reference/introspection/counter/)

#  counter

Counts through pages, elements, and more.

With the counter function, you can access and modify counters for pages,
headings, figures, and more. Moreover, you can define custom counters for
other things you want to count.

Since counters change throughout the course of the document, their current
value is _contextual._ It is recommended to read the chapter on [ context
](/docs/reference/context/ "context") before continuing here.

##  Accessing a counter

To access the raw value of a counter, we can use the [ ` get `
](/docs/reference/introspection/counter/#definitions-get) function. This
function returns an [ array ](/docs/reference/foundations/array/ "array") :
Counters can have multiple levels (in the case of headings for sections,
subsections, and so on), and each item in the array corresponds to one level.

    
    
    #set heading(numbering: "1.")
    
    = Introduction
    Raw value of heading counter is
    #context counter(heading).get()
    

![Preview](/assets/docs/jqVSznl_yGBcNN9ecF8OVAAAAAAAAAAA.png)

##  Displaying a counter

Often, we want to display the value of a counter in a more human-readable way.
To do that, we can call the [ ` display `
](/docs/reference/introspection/counter/#definitions-display) function on the
counter. This function retrieves the current counter value and formats it
either with a provided or with an automatically inferred [ numbering
](/docs/reference/model/numbering/ "numbering") .

    
    
    #set heading(numbering: "1.")
    
    = Introduction
    Some text here.
    
    = Background
    The current value is: #context {
      counter(heading).display()
    }
    
    Or in roman numerals: #context {
      counter(heading).display("I")
    }
    

![Preview](/assets/docs/7EUi61p1PXmzQyka_2NqiAAAAAAAAAAA.png)

##  Modifying a counter

To modify a counter, you can use the ` step ` and ` update ` methods:

  * The ` step ` method increases the value of the counter by one. Because counters can have multiple levels , it optionally takes a ` level ` argument. If given, the counter steps at the given depth. 

  * The ` update ` method allows you to arbitrarily modify the counter. In its basic form, you give it an integer (or an array for multiple levels). For more flexibility, you can instead also give it a function that receives the current value and returns a new value. 

The heading counter is stepped before the heading is displayed, so ` Analysis
` gets the number seven even though the counter is at six after the second
update.

    
    
    #set heading(numbering: "1.")
    
    = Introduction
    #counter(heading).step()
    
    = Background
    #counter(heading).update(3)
    #counter(heading).update(n => n * 2)
    
    = Analysis
    Let's skip 7.1.
    #counter(heading).step(level: 2)
    
    == Analysis
    Still at #context {
      counter(heading).display()
    }
    

![Preview](/assets/docs/EOYqv5YWVpmiQyBJoYpqQAAAAAAAAAAA.png)

##  Page counter

The page counter is special. It is automatically stepped at each pagebreak.
But like other counters, you can also step it manually. For example, you could
have Roman page numbers for your preface, then switch to Arabic page numbers
for your main content and reset the page counter to one.

    
    
    #set page(numbering: "(i)")
    
    = Preface
    The preface is numbered with
    roman numerals.
    
    #set page(numbering: "1 / 1")
    #counter(page).update(1)
    
    = Main text
    Here, the counter is reset to one.
    We also display both the current
    page and total number of pages in
    Arabic numbers.
    

![Preview](/assets/docs/PDCorO6nPZEoa3HjHUVgRwAAAAAAAAAA.png)
![Preview](/assets/docs/PDCorO6nPZEoa3HjHUVgRwAAAAAAAAAB.png)

##  Custom counters

To define your own counter, call the ` counter ` function with a string as a
key. This key identifies the counter globally.

    
    
    #let mine = counter("mycounter")
    #context mine.display() \
    #mine.step()
    #context mine.display() \
    #mine.update(c => c * 3)
    #context mine.display()
    

![Preview](/assets/docs/CxXLMyCvJp2FnmacPN3WUgAAAAAAAAAA.png)

##  How to step

When you define and use a custom counter, in general, you should first step
the counter and then display it. This way, the stepping behaviour of a counter
can depend on the element it is stepped for. If you were writing a counter
for, let's say, theorems, your theorem's definition would thus first include
the counter step and only then display the counter and the theorem's contents.

    
    
    #let c = counter("theorem")
    #let theorem(it) = block[
      #c.step()
      *Theorem #context c.display():*
      #it
    ]
    
    #theorem[$1 = 1$]
    #theorem[$2 < 3$]
    

![Preview](/assets/docs/af6Y7nOR_IldvYHIWDmkIQAAAAAAAAAA.png)

The rationale behind this is best explained on the example of the heading
counter: An update to the heading counter depends on the heading's level. By
stepping directly before the heading, we can correctly step from ` 1 ` to `
1.1 ` when encountering a level 2 heading. If we were to step after the
heading, we wouldn't know what to step to.

Because counters should always be stepped before the elements they count, they
always start at zero. This way, they are at one for the first display (which
happens after the first step).

##  Time travel

Counters can travel through time! You can find out the final value of the
counter before it is reached and even determine what the value was at any
particular location in the document.

    
    
    #let mine = counter("mycounter")
    
    = Values
    #context [
      Value here: #mine.get() \
      At intro: #mine.at(<intro>) \
      Final value: #mine.final()
    ]
    
    #mine.update(n => n + 3)
    
    = Introduction <intro>
    #lorem(10)
    
    #mine.step()
    #mine.step()
    

![Preview](/assets/docs/wodRGpSsJgDZtfsMk_GNgwAAAAAAAAAA.png)

##  Other kinds of state

The ` counter ` type is closely related to [ state
](/docs/reference/introspection/state/ "state") type. Read its documentation
for more details on state management in Typst and why it doesn't just use
normal variables for counters.

##  Constructor

Question mark

If a type has a constructor, you can call it like a function to create a new
value of the type.

Create a new counter identified by a key.

counter  (

[ str ](/docs/reference/foundations/str/) [ label
](/docs/reference/foundations/label/) [ selector
](/docs/reference/foundations/selector/) [ location
](/docs/reference/introspection/location/) [ function
](/docs/reference/foundations/function/)

)  -> [ counter ](/docs/reference/introspection/counter/)

####  ` key `

[ str ](/docs/reference/foundations/str/) or  [ label
](/docs/reference/foundations/label/) or  [ selector
](/docs/reference/foundations/selector/) or  [ location
](/docs/reference/introspection/location/) or  [ function
](/docs/reference/foundations/function/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The key that identifies this counter.

  * If it is a string, creates a custom counter that is only affected by manual updates, 
  * If it is the [ ` page ` ](/docs/reference/layout/page/ "`page`") function, counts through pages, 
  * If it is a [ selector ](/docs/reference/foundations/selector/ "selector") , counts through elements that matches with the selector. For example, 
    * provide an element function: counts elements of that type, 
    * provide a [ ` <label> ` ](/docs/reference/foundations/label/) : counts elements with that label. 

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` get ` Contextual

Question mark

Contextual functions can only be used when the context is known

Retrieves the value of the counter at the current location. Always returns an
array of integers, even if the counter has just one number.

This is equivalent to ` counter  .  at  (  here  (  )  )  ` .

self  .  get  (

)  -> [ int ](/docs/reference/foundations/int/) [ array
](/docs/reference/foundations/array/)

###  ` display ` Contextual

Question mark

Contextual functions can only be used when the context is known

Displays the current value of the counter with a numbering and returns the
formatted output.

_Compatibility:_ For compatibility with Typst 0.10 and lower, this function
also works without an established context. Then, it will create opaque
contextual content rather than directly returning the output of the numbering.
This behaviour will be removed in a future release.

self  .  display  (

[ auto ](/docs/reference/foundations/auto/) [ str
](/docs/reference/foundations/str/) [ function
](/docs/reference/foundations/function/) ,  both  :  [ bool
](/docs/reference/foundations/bool/) ,

)  -> any

####  ` numbering `

[ auto ](/docs/reference/foundations/auto/) or  [ str
](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Positional

Question mark

Positional parameters are specified in order, without names.

A [ numbering pattern or a function ](/docs/reference/model/numbering/) ,
which specifies how to display the counter. If given a function, that function
receives each number of the counter as a separate argument. If the amount of
numbers varies, e.g. for the heading argument, you can use an [ argument sink
](/docs/reference/foundations/arguments/) .

If this is omitted or set to ` auto  ` , displays the counter with the
numbering style for the counted element or with the pattern ` "1.1"  ` if no
such style exists.

Default: ` auto  `

####  ` both `

[ bool ](/docs/reference/foundations/bool/)

If enabled, displays the current and final top-level count together. Both can
be styled through a single numbering pattern. This is used by the page
numbering property to display the current and total number of pages when a
pattern like ` "1 / 1"  ` is given.

Default: ` false  `

###  ` at ` Contextual

Question mark

Contextual functions can only be used when the context is known

Retrieves the value of the counter at the given location. Always returns an
array of integers, even if the counter has just one number.

The ` selector ` must match exactly one element in the document. The most
useful kinds of selectors for this are [ labels
](/docs/reference/foundations/label/) and [ locations
](/docs/reference/introspection/location/) .

_Compatibility:_ For compatibility with Typst 0.10 and lower, this function
also works without a known context if the ` selector ` is a location. This
behaviour will be removed in a future release.

self  .  at  (

[ label ](/docs/reference/foundations/label/) [ selector
](/docs/reference/foundations/selector/) [ location
](/docs/reference/introspection/location/) [ function
](/docs/reference/foundations/function/)

)  -> [ int ](/docs/reference/foundations/int/) [ array
](/docs/reference/foundations/array/)

####  ` selector `

[ label ](/docs/reference/foundations/label/) or  [ selector
](/docs/reference/foundations/selector/) or  [ location
](/docs/reference/introspection/location/) or  [ function
](/docs/reference/foundations/function/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The place at which the counter's value should be retrieved.

###  ` final ` Contextual

Question mark

Contextual functions can only be used when the context is known

Retrieves the value of the counter at the end of the document. Always returns
an array of integers, even if the counter has just one number.

self  .  final  (

[ none ](/docs/reference/foundations/none/) [ location
](/docs/reference/introspection/location/)

)  -> [ int ](/docs/reference/foundations/int/) [ array
](/docs/reference/foundations/array/)

####  ` location `

[ none ](/docs/reference/foundations/none/) or  [ location
](/docs/reference/introspection/location/)

Positional

Question mark

Positional parameters are specified in order, without names.

_Compatibility:_ This argument is deprecated. It only exists for compatibility
with Typst 0.10 and lower and shouldn't be used anymore.

Default: ` none  `

###  ` step `

Increases the value of the counter by one.

The update will be in effect at the position where the returned content is
inserted into the document. If you don't put the output into the document,
nothing happens! This would be the case, for example, if you write ` let  _  =
counter  (  page  )  .  step  (  )  ` . Counter updates are always applied in
layout order and in that case, Typst wouldn't know when to step the counter.

self  .  step  (

level  :  [ int ](/docs/reference/foundations/int/)

)  -> [ content ](/docs/reference/foundations/content/)

####  ` level `

[ int ](/docs/reference/foundations/int/)

The depth at which to step the counter. Defaults to ` 1  ` .

Default: ` 1  `

###  ` update `

Updates the value of the counter.

Just like with ` step ` , the update only occurs if you put the resulting
content into the document.

self  .  update  (

[ int ](/docs/reference/foundations/int/) [ array
](/docs/reference/foundations/array/) [ function
](/docs/reference/foundations/function/)

)  -> [ content ](/docs/reference/foundations/content/)

####  ` update `

[ int ](/docs/reference/foundations/int/) or  [ array
](/docs/reference/foundations/array/) or  [ function
](/docs/reference/foundations/function/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

If given an integer or array of integers, sets the counter to that value. If
given a function, that function receives the previous counter value (with each
number as a separate argument) and has to return the new value (integer or
array).

[ ![â](/assets/icons/16-arrow-right.svg) Introspection  Previous page
](/docs/reference/introspection/) [ ![â](/assets/icons/16-arrow-right.svg)
Here  Next page  ](/docs/reference/introspection/here/)

