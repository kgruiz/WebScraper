  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Foundations ](/docs/reference/foundations/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Dictionary ](/docs/reference/foundations/dictionary/)

#  dictionary

A map from string keys to values.

You can construct a dictionary by enclosing comma-separated ` key: value `
pairs in parentheses. The values do not have to be of the same type. Since
empty parentheses already yield an empty array, you have to use the special `
(:) ` syntax to create an empty dictionary.

A dictionary is conceptually similar to an array, but it is indexed by strings
instead of integers. You can access and create dictionary entries with the `
.at() ` method. If you know the key statically, you can alternatively use [
field access notation ](/docs/reference/scripting/#fields) ( ` .key ` ) to
access the value. Dictionaries can be added with the ` + ` operator and [
joined together ](/docs/reference/scripting/#blocks) . To check whether a key
is present in the dictionary, use the ` in ` keyword.

You can iterate over the pairs in a dictionary using a [ for loop
](/docs/reference/scripting/#loops) . This will iterate in the order the pairs
were inserted / declared.

##  Example

    
    
    #let dict = (
      name: "Typst",
      born: 2019,
    )
    
    #dict.name \
    #(dict.launch = 20)
    #dict.len() \
    #dict.keys() \
    #dict.values() \
    #dict.at("born") \
    #dict.insert("city", "Berlin ")
    #("name" in dict)
    

![Preview](/assets/docs/1ByIQqDPZ4VVxPmFNoQXgwAAAAAAAAAA.png)

##  Constructor

Question mark

If a type has a constructor, you can call it like a function to create a new
value of the type.

Converts a value into a dictionary.

Note that this function is only intended for conversion of a dictionary-like
value to a dictionary, not for creation of a dictionary from individual pairs.
Use the dictionary syntax ` (key: value) ` instead.

dictionary  (

[ module ](/docs/reference/foundations/module/)

)  -> [ dictionary ](/docs/reference/foundations/dictionary/)

    
    
    #dictionary(sys).at("version")
    

![Preview](/assets/docs/vrwNZ5Jfl6kz7gYnEOsM0AAAAAAAAAAA.png)

####  ` value `

[ module ](/docs/reference/foundations/module/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The value that should be converted to a dictionary.

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` len `

The number of pairs in the dictionary.

self  .  len  (

)  -> [ int ](/docs/reference/foundations/int/)

###  ` at `

Returns the value associated with the specified key in the dictionary. May be
used on the left-hand side of an assignment if the key is already present in
the dictionary. Returns the default value if the key is not part of the
dictionary or fails with an error if no default value was specified.

self  .  at  (

[ str ](/docs/reference/foundations/str/) ,  default  :  any  ,

)  -> any

####  ` key `

[ str ](/docs/reference/foundations/str/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The key at which to retrieve the item.

####  ` default `

any

A default value to return if the key is not part of the dictionary.

###  ` insert `

Inserts a new pair into the dictionary. If the dictionary already contains
this key, the value is updated.

self  .  insert  (

[ str ](/docs/reference/foundations/str/) ,  any  ,

)

####  ` key `

[ str ](/docs/reference/foundations/str/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The key of the pair that should be inserted.

####  ` value `

any

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The value of the pair that should be inserted.

###  ` remove `

Removes a pair from the dictionary by key and return the value.

self  .  remove  (

[ str ](/docs/reference/foundations/str/) ,  default  :  any  ,

)  -> any

####  ` key `

[ str ](/docs/reference/foundations/str/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The key of the pair to remove.

####  ` default `

any

A default value to return if the key does not exist.

###  ` keys `

Returns the keys of the dictionary as an array in insertion order.

self  .  keys  (

)  -> [ array ](/docs/reference/foundations/array/)

###  ` values `

Returns the values of the dictionary as an array in insertion order.

self  .  values  (

)  -> [ array ](/docs/reference/foundations/array/)

###  ` pairs `

Returns the keys and values of the dictionary as an array of pairs. Each pair
is represented as an array of length two.

self  .  pairs  (

)  -> [ array ](/docs/reference/foundations/array/)

[ ![â](/assets/icons/16-arrow-right.svg) Decimal  Previous page
](/docs/reference/foundations/decimal/) [ ![â](/assets/icons/16-arrow-
right.svg) Duration  Next page  ](/docs/reference/foundations/duration/)

