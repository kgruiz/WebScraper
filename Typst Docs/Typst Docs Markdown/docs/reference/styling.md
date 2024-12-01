  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Styling ](/docs/reference/styling/)

#  Styling

Typst includes a flexible styling system that automatically applies styling of
your choice to your document. With _set rules,_ you can configure basic
properties of elements. This way, you create most common styles. However,
there might not be a built-in property for everything you wish to do. For this
reason, Typst further supports _show rules_ that can completely redefine the
appearance of elements.

##  Set rules

With set rules, you can customize the appearance of elements. They are written
as a [ function call ](/docs/reference/foundations/function/) to an [ element
function ](/docs/reference/foundations/function/#element-functions) preceded
by the ` set  ` keyword (or ` #  set  ` in markup). Only optional parameters
of that function can be provided to the set rule. Refer to each function's
documentation to see which parameters are optional. In the example below, we
use two set rules to change the [ font family
](/docs/reference/text/text/#parameters-font) and [ heading numbering
](/docs/reference/model/heading/#parameters-numbering) .

    
    
    #set heading(numbering: "I.")
    #set text(
      font: "New Computer Modern"
    )
    
    = Introduction
    With set rules, you can style
    your document.
    

![Preview](/assets/docs/nW0VZeyhJmtpweEOjJR_fgAAAAAAAAAA.png)

A top level set rule stays in effect until the end of the file. When nested
inside of a block, it is only in effect until the end of that block. With a
block, you can thus restrict the effect of a rule to a particular segment of
your document. Below, we use a content block to scope the list styling to one
particular list.

    
    
    This list is affected: #[
      #set list(marker: [--])
      - Dash
    ]
    
    This one is not:
    - Bullet
    

![Preview](/assets/docs/6ckQbXFff1zDBcdWezXxpgAAAAAAAAAA.png)

Sometimes, you'll want to apply a set rule conditionally. For this, you can
use a _set-if_ rule.

    
    
    #let task(body, critical: false) = {
      set text(red) if critical
      [- #body]
    }
    
    #task(critical: true)[Food today?]
    #task(critical: false)[Work deadline]
    

![Preview](/assets/docs/_UlmqEOdrmM6d-OQ9TsAXwAAAAAAAAAA.png)

##  Show rules

With show rules, you can deeply customize the look of a type of element. The
most basic form of show rule is a _show-set rule._ Such a rule is written as
the ` show  ` keyword followed by a [ selector
](/docs/reference/foundations/selector/ "selector") , a colon and then a set
rule. The most basic form of selector is an [ element function
](/docs/reference/foundations/function/#element-functions) . This lets the set
rule only apply to the selected element. In the example below, headings become
dark blue while all other text stays black.

    
    
    #show heading: set text(navy)
    
    = This is navy-blue
    But this stays black.
    

![Preview](/assets/docs/DS2Pe3XVhhMMVWT9eUfjSQAAAAAAAAAA.png)

With show-set rules you can mix and match properties from different functions
to achieve many different effects. But they still limit you to what is
predefined in Typst. For maximum flexibility, you can instead write a show
rule that defines how to format an element from scratch. To write such a show
rule, replace the set rule after the colon with an arbitrary [ function
](/docs/reference/foundations/function/ "function") . This function receives
the element in question and can return arbitrary content. The available [
fields ](/docs/reference/scripting/#fields) on the element passed to the
function again match the parameters of the respective element function. Below,
we define a show rule that formats headings for a fantasy encyclopedia.

    
    
    #set heading(numbering: "(I)")
    #show heading: it => [
      #set align(center)
      #set text(font: "Inria Serif")
      \~ #emph(it.body)
         #counter(heading).display(
           it.numbering
         ) \~
    ]
    
    = Dragon
    With a base health of 15, the
    dragon is the most powerful
    creature.
    
    = Manticore
    While less powerful than the
    dragon, the manticore gets
    extra style points.
    

![Preview](/assets/docs/YrvkqpSwoILjuqAerzw9CAAAAAAAAAAA.png)

Like set rules, show rules are in effect until the end of the current block or
file.

Instead of a function, the right-hand side of a show rule can also take a
literal string or content block that should be directly substituted for the
element. And apart from a function, the left-hand side of a show rule can also
take a number of other _selectors_ that define what to apply the
transformation to:

  * **Everything:** ` show  :  rest  => .. `   
Transform everything after the show rule. This is useful to apply a more
complex layout to your whole document without wrapping everything in a giant
function call.

  * **Text:** ` show  "Text"  :  .. `   
Style, transform or replace text.

  * **Regex:** ` show  regex  (  "\w+"  )  :  .. `   
Select and transform text with a regular expression for even more flexibility.
See the documentation of the [ ` regex ` type
](/docs/reference/foundations/regex/) for details.

  * **Function with fields:** ` show  heading  .  where  (  level  :  1  )  :  .. `   
Transform only elements that have the specified fields. For example, you might
want to only change the style of level-1 headings.

  * **Label:** ` show  <intro> :  .. `   
Select and transform elements that have the specified label. See the
documentation of the [ ` label ` type ](/docs/reference/foundations/label/)
for more details.

    
    
    #show "Project": smallcaps
    #show "badly": "great"
    
    We started Project in 2019
    and are still working on it.
    Project is progressing badly.
    

![Preview](/assets/docs/NBzIViTspdnPhsbo3WGDLAAAAAAAAAAA.png)

[ ![â](/assets/icons/16-arrow-right.svg) Syntax  Previous page
](/docs/reference/syntax/) [ ![â](/assets/icons/16-arrow-right.svg)
Scripting  Next page  ](/docs/reference/scripting/)
