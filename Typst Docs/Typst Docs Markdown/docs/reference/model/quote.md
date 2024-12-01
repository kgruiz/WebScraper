  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Model ](/docs/reference/model/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Quote ](/docs/reference/model/quote/)

#  ` quote ` Element

Question mark

Element functions can be customized with ` set ` and  ` show ` rules.

Displays a quote alongside an optional attribution.

##  Example

    
    
    Plato is often misquoted as the author of #quote[I know that I know
    nothing], however, this is a derivation form his original quote:
    
    #set quote(block: true)
    
    #quote(attribution: [Plato])[
      ... á¼Î¿Î¹ÎºÎ± Î³Î¿á¿¦Î½ ÏÎ¿ÏÏÎ¿Ï Î³Îµ ÏÎ¼Î¹ÎºÏá¿· ÏÎ¹Î½Î¹ Î±á½Ïá¿· ÏÎ¿ÏÏá¿³ ÏÎ¿ÏÏÏÎµÏÎ¿Ï Îµá¼¶Î½Î±Î¹, á½ÏÎ¹
      á¼ Î¼á½´ Î¿á¼¶Î´Î± Î¿á½Î´á½² Î¿á¼´Î¿Î¼Î±Î¹ Îµá¼°Î´Î­Î½Î±Î¹.
    ]
    #quote(attribution: [from the Henry Cary literal translation of 1897])[
      ... I seem, then, in just this little thing to be wiser than this man at
      any rate, that what I do not know I do not think I know either.
    ]
    

![Preview](/assets/docs/SJpe1zkhE_liZRMF5cAy4gAAAAAAAAAA.png)

By default block quotes are padded left and right by ` 1em  ` , alignment and
padding can be controlled with show rules:

    
    
    #set quote(block: true)
    #show quote: set align(center)
    #show quote: set pad(x: 5em)
    
    #quote[
      You cannot pass... I am a servant of the Secret Fire, wielder of the
      flame of Anor. You cannot pass. The dark fire will not avail you,
      flame of UdÃ»n. Go back to the Shadow! You cannot pass.
    ]
    

![Preview](/assets/docs/QLNv4Pfp0zBKSvwxIfby-wAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

quote  (

block  :  [ bool ](/docs/reference/foundations/bool/) ,  quotes  :  [ auto
](/docs/reference/foundations/auto/) [ bool
](/docs/reference/foundations/bool/) ,  attribution  :  [ none
](/docs/reference/foundations/none/) [ label
](/docs/reference/foundations/label/) [ content
](/docs/reference/foundations/content/) ,  [ content
](/docs/reference/foundations/content/) ,

)  -> [ content ](/docs/reference/foundations/content/)

###  ` block `

[ bool ](/docs/reference/foundations/bool/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Whether this is a block quote.

Default: ` false  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    An inline citation would look like
    this: #quote(
      attribution: [RenÃ© Descartes]
    )[
      cogito, ergo sum
    ], and a block equation like this:
    #quote(
      block: true,
      attribution: [JFK]
    )[
      Ich bin ein Berliner.
    ]
    

![Preview](/assets/docs/bYLjzIuUOzRO9HYX7xT11wAAAAAAAAAA.png)

###  ` quotes `

[ auto ](/docs/reference/foundations/auto/) or  [ bool
](/docs/reference/foundations/bool/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

Whether double quotes should be added around this quote.

The double quotes used are inferred from the ` quotes ` property on [
smartquote ](/docs/reference/text/smartquote/ "smartquote") , which is
affected by the ` lang ` property on [ text ](/docs/reference/text/text/
"text") .

  * ` true  ` : Wrap this quote in double quotes. 
  * ` false  ` : Do not wrap this quote in double quotes. 
  * ` auto  ` : Infer whether to wrap this quote in double quotes based on the ` block ` property. If ` block ` is ` false  ` , double quotes are automatically added. 

Default: ` auto  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #set text(lang: "de")
    
    Ein deutsch-sprechender Author
    zitiert unter umstÃ¤nden JFK:
    #quote[Ich bin ein Berliner.]
    
    #set text(lang: "en")
    
    And an english speaking one may
    translate the quote:
    #quote[I am a Berliner.]
    

![Preview](/assets/docs/3Qsm4wm5qgO3MH7h3rFICAAAAAAAAAAA.png)

###  ` attribution `

[ none ](/docs/reference/foundations/none/) or  [ label
](/docs/reference/foundations/label/) or  [ content
](/docs/reference/foundations/content/)

Settable

Question mark

Settable parameters can be customized for all following uses of the function
with a ` set ` rule.

The attribution of this quote, usually the author or source. Can be a label
pointing to a bibliography entry or any content. By default only displayed for
block quotes, but can be changed using a ` show  ` rule.

Default: ` none  `

![](/assets/icons/16-arrow-right.svg) View example

    
    
    #quote(attribution: [RenÃ© Descartes])[
      cogito, ergo sum
    ]
    
    #show quote.where(block: false): it => {
      ["] + h(0pt, weak: true) + it.body + h(0pt, weak: true) + ["]
      if it.attribution != none [ (#it.attribution)]
    }
    
    #quote(
      attribution: link("https://typst.app/home")[typst.com]
    )[
      Compose papers faster
    ]
    
    #set quote(block: true)
    
    #quote(attribution: <tolkien54>)[
      You cannot pass... I am a servant
      of the Secret Fire, wielder of the
      flame of Anor. You cannot pass. The
      dark fire will not avail you, flame
      of UdÃ»n. Go back to the Shadow! You
      cannot pass.
    ]
    
    #bibliography("works.bib", style: "apa")
    

![Preview](/assets/docs/bB0B3x32glSn_oATlkF6mQAAAAAAAAAA.png)

###  ` body `

[ content ](/docs/reference/foundations/content/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The quote.

[ ![â](/assets/icons/16-arrow-right.svg) Paragraph Break  Previous page
](/docs/reference/model/parbreak/) [ ![â](/assets/icons/16-arrow-right.svg)
Reference  Next page  ](/docs/reference/model/ref/)

