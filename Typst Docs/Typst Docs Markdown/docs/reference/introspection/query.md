  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Introspection ](/docs/reference/introspection/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Query ](/docs/reference/introspection/query/)

#  ` query ` Contextual

Question mark

Contextual functions can only be used when the context is known

Finds elements in the document.

The ` query ` functions lets you search your document for elements of a
particular type or with a particular label. To use it, you first need to
ensure that [ context ](/docs/reference/context/ "context") is available.

##  Finding elements

In the example below, we manually create a table of contents instead of using
the [ ` outline ` ](/docs/reference/model/outline/ "`outline`") function.

To do this, we first query for all headings in the document at level 1 and
where ` outlined ` is true. Querying only for headings at level 1 ensures
that, for the purpose of this example, sub-headings are not included in the
table of contents. The ` outlined ` field is used to exclude the "Table of
Contents" heading itself.

Note that we open a ` context ` to be able to use the ` query ` function.

    
    
    #set page(numbering: "1")
    
    #heading(outlined: false)[
      Table of Contents
    ]
    #context {
      let chapters = query(
        heading.where(
          level: 1,
          outlined: true,
        )
      )
      for chapter in chapters {
        let loc = chapter.location()
        let nr = numbering(
          loc.page-numbering(),
          ..counter(page).at(loc),
        )
        [#chapter.body #h(1fr) #nr \ ]
      }
    }
    
    = Introduction
    #lorem(10)
    #pagebreak()
    
    == Sub-Heading
    #lorem(8)
    
    = Discussion
    #lorem(18)
    

![Preview](/assets/docs/jo-em7a3jFROfNLdVe33CwAAAAAAAAAA.png)
![Preview](/assets/docs/jo-em7a3jFROfNLdVe33CwAAAAAAAAAB.png)

To get the page numbers, we first get the location of the elements returned by
` query ` with [ ` location `
](/docs/reference/foundations/content/#definitions-location) . We then also
retrieve the [ page numbering
](/docs/reference/introspection/location/#definitions-page-numbering) and [
page counter ](/docs/reference/introspection/counter/#page-counter) at that
location and apply the numbering to the counter.

##  A word of caution

To resolve all your queries, Typst evaluates and layouts parts of the document
multiple times. However, there is no guarantee that your queries can actually
be completely resolved. If you aren't careful a query can affect
itselfâleading to a result that never stabilizes.

In the example below, we query for all headings in the document. We then
generate as many headings. In the beginning, there's just one heading, titled
` Real ` . Thus, ` count ` is ` 1 ` and one ` Fake ` heading is generated.
Typst sees that the query's result has changed and processes it again. This
time, ` count ` is ` 2 ` and two ` Fake ` headings are generated. This goes on
and on. As we can see, the output has a finite amount of headings. This is
because Typst simply gives up after a few attempts.

In general, you should try not to write queries that affect themselves. The
same words of caution also apply to other introspection features like [
counters ](/docs/reference/introspection/counter/) and [ state
](/docs/reference/introspection/state/ "state") .

    
    
    = Real
    #context {
      let elems = query(heading)
      let count = elems.len()
      count * [= Fake]
    }
    

![Preview](/assets/docs/C2bjyzuukR06BSWIMgC89wAAAAAAAAAA.png)

##  Command line queries

You can also perform queries from the command line with the ` typst query `
command. This command executes an arbitrary query on the document and returns
the resulting elements in serialized form. Consider the following `
example.typ ` file which contains some invisible [ metadata
](/docs/reference/introspection/metadata/ "metadata") :

    
    
    #metadata("This is a note") <note>
    

You can execute a query on it as follows using Typst's CLI:

    
    
    $ typst query example.typ "<note>"
    [
      {
        "func": "metadata",
        "value": "This is a note",
        "label": "<note>"
      }
    ]
    

Frequently, you're interested in only one specific field of the resulting
elements. In the case of the ` metadata ` element, the ` value ` field is the
interesting one. You can extract just this field with the ` --field `
argument.

    
    
    $ typst query example.typ "<note>" --field value
    ["This is a note"]
    

If you are interested in just a single element, you can use the ` --one ` flag
to extract just it.

    
    
    $ typst query example.typ "<note>" --field value --one
    "This is a note"
    

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

query  (

[ label ](/docs/reference/foundations/label/) [ selector
](/docs/reference/foundations/selector/) [ location
](/docs/reference/introspection/location/) [ function
](/docs/reference/foundations/function/) ,  [ none
](/docs/reference/foundations/none/) [ location
](/docs/reference/introspection/location/) ,

)  -> [ array ](/docs/reference/foundations/array/)

###  ` target `

[ label ](/docs/reference/foundations/label/) or  [ selector
](/docs/reference/foundations/selector/) or  [ location
](/docs/reference/introspection/location/) or  [ function
](/docs/reference/foundations/function/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

Can be

  * an element function like a ` heading ` or ` figure ` , 
  * a ` <label> ` , 
  * a more complex selector like ` heading  .  where  (  level  :  1  )  ` , 
  * or ` selector  (  heading  )  .  before  (  here  (  )  )  ` . 

Only [ locatable ](/docs/reference/introspection/location/#locatable) element
functions are supported.

###  ` location `

[ none ](/docs/reference/foundations/none/) or  [ location
](/docs/reference/introspection/location/)

Positional

Question mark

Positional parameters are specified in order, without names.

_Compatibility:_ This argument is deprecated. It only exists for compatibility
with Typst 0.10 and lower and shouldn't be used anymore.

Default: ` none  `

[ ![â](/assets/icons/16-arrow-right.svg) Metadata  Previous page
](/docs/reference/introspection/metadata/) [ ![â](/assets/icons/16-arrow-
right.svg) State  Next page  ](/docs/reference/introspection/state/)

