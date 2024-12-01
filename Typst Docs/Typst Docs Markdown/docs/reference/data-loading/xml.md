  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Data Loading ](/docs/reference/data-loading/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ XML ](/docs/reference/data-loading/xml/)

#  ` xml `

Reads structured data from an XML file.

The XML file is parsed into an array of dictionaries and strings. XML nodes
can be elements or strings. Elements are represented as dictionaries with the
following keys:

  * ` tag ` : The name of the element as a string. 
  * ` attrs ` : A dictionary of the element's attributes as strings. 
  * ` children ` : An array of the element's child nodes. 

The XML file in the example contains a root ` news ` tag with multiple `
article ` tags. Each article has a ` title ` , ` author ` , and ` content `
tag. The ` content ` tag contains one or more paragraphs, which are
represented as ` p ` tags.

##  Example

    
    
    #let find-child(elem, tag) = {
      elem.children
        .find(e => "tag" in e and e.tag == tag)
    }
    
    #let article(elem) = {
      let title = find-child(elem, "title")
      let author = find-child(elem, "author")
      let pars = find-child(elem, "content")
    
      heading(title.children.first())
      text(10pt, weight: "medium")[
        Published by
        #author.children.first()
      ]
    
      for p in pars.children {
        if (type(p) == "dictionary") {
          parbreak()
          p.children.first()
        }
      }
    }
    
    #let data = xml("example.xml")
    #for elem in data.first().children {
      if (type(elem) == "dictionary") {
        article(elem)
      }
    }
    

![Preview](/assets/docs/ImsUm8fcO-Uh3s95k6HvEQAAAAAAAAAA.png)

##  Parameters

Question mark

Parameters are the inputs to a function. They are specified in parentheses
after the function name.

xml  (

[ str ](/docs/reference/foundations/str/)

)  -> any

###  ` path `

[ str ](/docs/reference/foundations/str/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

Path to an XML file.

For more details, see the [ Paths section ](/docs/reference/syntax/#paths) .

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` decode `

Reads structured data from an XML string/bytes.

xml  .  decode  (

[ str ](/docs/reference/foundations/str/) [ bytes
](/docs/reference/foundations/bytes/)

)  -> any

####  ` data `

[ str ](/docs/reference/foundations/str/) or  [ bytes
](/docs/reference/foundations/bytes/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

XML data.

[ ![â](/assets/icons/16-arrow-right.svg) TOML  Previous page
](/docs/reference/data-loading/toml/) [ ![â](/assets/icons/16-arrow-
right.svg) YAML  Next page  ](/docs/reference/data-loading/yaml/)

