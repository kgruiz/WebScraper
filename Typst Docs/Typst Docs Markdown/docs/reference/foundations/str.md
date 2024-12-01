  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Foundations ](/docs/reference/foundations/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ String ](/docs/reference/foundations/str/)

#  str

A sequence of Unicode codepoints.

You can iterate over the grapheme clusters of the string using a [ for loop
](/docs/reference/scripting/#loops) . Grapheme clusters are basically
characters but keep together things that belong together, e.g. multiple
codepoints that together form a flag emoji. Strings can be added with the ` +
` operator, [ joined together ](/docs/reference/scripting/#blocks) and
multiplied with integers.

Typst provides utility methods for string manipulation. Many of these methods
(e.g., ` split ` , ` trim ` and ` replace ` ) operate on _patterns:_ A pattern
can be either a string or a [ regular expression
](/docs/reference/foundations/regex/) . This makes the methods quite
versatile.

All lengths and indices are expressed in terms of UTF-8 bytes. Indices are
zero-based and negative indices wrap around to the end of the string.

You can convert a value to a string with this type's constructor.

##  Example

    
    
    #"hello world!" \
    #"\"hello\n  world\"!" \
    #"1 2 3".split() \
    #"1,2;3".split(regex("[,;]")) \
    #(regex("\d+") in "ten euros") \
    #(regex("\d+") in "10 euros")
    

![Preview](/assets/docs/gK89AnI9k7dy82m9R3F1jgAAAAAAAAAA.png)

##  Escape sequences

Just like in markup, you can escape a few symbols in strings:

  * ` \\  ` for a backslash 
  * ` \"  ` for a quote 
  * ` \n  ` for a newline 
  * ` \r  ` for a carriage return 
  * ` \t  ` for a tab 
  * ` \u{1f600}  ` for a hexadecimal Unicode escape sequence 

##  Constructor

Question mark

If a type has a constructor, you can call it like a function to create a new
value of the type.

Converts a value to a string.

  * Integers are formatted in base 10. This can be overridden with the optional ` base ` parameter. 
  * Floats are formatted in base 10 and never in exponential notation. 
  * From labels the name is extracted. 
  * Bytes are decoded as UTF-8. 

If you wish to convert from and to Unicode code points, see the [ ` to-unicode
` ](/docs/reference/foundations/str/#definitions-to-unicode) and [ ` from-
unicode ` ](/docs/reference/foundations/str/#definitions-from-unicode)
functions.

str  (

[ int ](/docs/reference/foundations/int/) [ float
](/docs/reference/foundations/float/) [ str
](/docs/reference/foundations/str/) [ bytes
](/docs/reference/foundations/bytes/) [ label
](/docs/reference/foundations/label/) [ decimal
](/docs/reference/foundations/decimal/) [ version
](/docs/reference/foundations/version/) [ type
](/docs/reference/foundations/type/) ,  base  :  [ int
](/docs/reference/foundations/int/) ,

)  -> [ str ](/docs/reference/foundations/str/)

    
    
    #str(10) \
    #str(4000, base: 16) \
    #str(2.7) \
    #str(1e8) \
    #str(<intro>)
    

![Preview](/assets/docs/06jR9z-fP-M4eu8XB2MFnAAAAAAAAAAA.png)

####  ` value `

[ int ](/docs/reference/foundations/int/) or  [ float
](/docs/reference/foundations/float/) or  [ str
](/docs/reference/foundations/str/) or  [ bytes
](/docs/reference/foundations/bytes/) or  [ label
](/docs/reference/foundations/label/) or  [ decimal
](/docs/reference/foundations/decimal/) or  [ version
](/docs/reference/foundations/version/) or  [ type
](/docs/reference/foundations/type/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The value that should be converted to a string.

####  ` base `

[ int ](/docs/reference/foundations/int/)

The base (radix) to display integers in, between 2 and 36.

Default: ` 10  `

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` len `

The length of the string in UTF-8 encoded bytes.

self  .  len  (

)  -> [ int ](/docs/reference/foundations/int/)

###  ` first `

Extracts the first grapheme cluster of the string. Fails with an error if the
string is empty.

self  .  first  (

)  -> [ str ](/docs/reference/foundations/str/)

###  ` last `

Extracts the last grapheme cluster of the string. Fails with an error if the
string is empty.

self  .  last  (

)  -> [ str ](/docs/reference/foundations/str/)

###  ` at `

Extracts the first grapheme cluster after the specified index. Returns the
default value if the index is out of bounds or fails with an error if no
default value was specified.

self  .  at  (

[ int ](/docs/reference/foundations/int/) ,  default  :  any  ,

)  -> any

####  ` index `

[ int ](/docs/reference/foundations/int/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The byte index. If negative, indexes from the back.

####  ` default `

any

A default value to return if the index is out of bounds.

###  ` slice `

Extracts a substring of the string. Fails with an error if the start or end
index is out of bounds.

self  .  slice  (

[ int ](/docs/reference/foundations/int/) ,  [ none
](/docs/reference/foundations/none/) [ int ](/docs/reference/foundations/int/)
,  count  :  [ int ](/docs/reference/foundations/int/) ,

)  -> [ str ](/docs/reference/foundations/str/)

####  ` start `

[ int ](/docs/reference/foundations/int/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The start byte index (inclusive). If negative, indexes from the back.

####  ` end `

[ none ](/docs/reference/foundations/none/) or  [ int
](/docs/reference/foundations/int/)

Positional

Question mark

Positional parameters are specified in order, without names.

The end byte index (exclusive). If omitted, the whole slice until the end of
the string is extracted. If negative, indexes from the back.

Default: ` none  `

####  ` count `

[ int ](/docs/reference/foundations/int/)

The number of bytes to extract. This is equivalent to passing ` start + count
` as the ` end ` position. Mutually exclusive with ` end ` .

###  ` clusters `

Returns the grapheme clusters of the string as an array of substrings.

self  .  clusters  (

)  -> [ array ](/docs/reference/foundations/array/)

###  ` codepoints `

Returns the Unicode codepoints of the string as an array of substrings.

self  .  codepoints  (

)  -> [ array ](/docs/reference/foundations/array/)

###  ` to-unicode `

Converts a character into its corresponding code point.

str  .  to-unicode  (

[ str ](/docs/reference/foundations/str/)

)  -> [ int ](/docs/reference/foundations/int/)

    
    
    #"a".to-unicode() \
    #("a\u{0300}"
       .codepoints()
       .map(str.to-unicode))
    

![Preview](/assets/docs/q50tz6WAJPnwtBCYWbHrIwAAAAAAAAAA.png)

####  ` character `

[ str ](/docs/reference/foundations/str/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The character that should be converted.

###  ` from-unicode `

Converts a unicode code point into its corresponding string.

str  .  from-unicode  (

[ int ](/docs/reference/foundations/int/)

)  -> [ str ](/docs/reference/foundations/str/)

    
    
    #str.from-unicode(97)
    

![Preview](/assets/docs/vNzcsGO4Zd_u-P4qNnxrDQAAAAAAAAAA.png)

####  ` value `

[ int ](/docs/reference/foundations/int/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The code point that should be converted.

###  ` contains `

Whether the string contains the specified pattern.

This method also has dedicated syntax: You can write ` "bc"  in  "abcd"  `
instead of ` "abcd"  .  contains  (  "bc"  )  ` .

self  .  contains  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ bool ](/docs/reference/foundations/bool/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for.

###  ` starts-with `

Whether the string starts with the specified pattern.

self  .  starts-with  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ bool ](/docs/reference/foundations/bool/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern the string might start with.

###  ` ends-with `

Whether the string ends with the specified pattern.

self  .  ends-with  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ bool ](/docs/reference/foundations/bool/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern the string might end with.

###  ` find `

Searches for the specified pattern in the string and returns the first match
as a string or ` none  ` if there is no match.

self  .  find  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ none ](/docs/reference/foundations/none/) [ str
](/docs/reference/foundations/str/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for.

###  ` position `

Searches for the specified pattern in the string and returns the index of the
first match as an integer or ` none  ` if there is no match.

self  .  position  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ none ](/docs/reference/foundations/none/) [ int
](/docs/reference/foundations/int/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for.

###  ` match `

Searches for the specified pattern in the string and returns a dictionary with
details about the first match or ` none  ` if there is no match.

The returned dictionary has the following keys:

  * ` start ` : The start offset of the match 
  * ` end ` : The end offset of the match 
  * ` text ` : The text that matched. 
  * ` captures ` : An array containing a string for each matched capturing group. The first item of the array contains the first matched capturing, not the whole match! This is empty unless the ` pattern ` was a regex with capturing groups. 

self  .  match  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ none ](/docs/reference/foundations/none/) [ dictionary
](/docs/reference/foundations/dictionary/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for.

###  ` matches `

Searches for the specified pattern in the string and returns an array of
dictionaries with details about all matches. For details about the returned
dictionaries, see above.

self  .  matches  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ array ](/docs/reference/foundations/array/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for.

###  ` replace `

Replace at most ` count ` occurrences of the given pattern with a replacement
string or function (beginning from the start). If no count is given, all
occurrences are replaced.

self  .  replace  (

[ str ](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/) ,  [ str
](/docs/reference/foundations/str/) [ function
](/docs/reference/foundations/function/) ,  count  :  [ int
](/docs/reference/foundations/int/) ,

)  -> [ str ](/docs/reference/foundations/str/)

####  ` pattern `

[ str ](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for.

####  ` replacement `

[ str ](/docs/reference/foundations/str/) or  [ function
](/docs/reference/foundations/function/)

Required  Positional

Question mark

Positional parameters are specified in order, without names.

The string to replace the matches with or a function that gets a dictionary
for each match and can return individual replacement strings.

####  ` count `

[ int ](/docs/reference/foundations/int/)

If given, only the first ` count ` matches of the pattern are placed.

###  ` trim `

Removes matches of a pattern from one or both sides of the string, once or
repeatedly and returns the resulting string.

self  .  trim  (

[ none ](/docs/reference/foundations/none/) [ str
](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/) ,  at  :  [ alignment
](/docs/reference/layout/alignment/) ,  repeat  :  [ bool
](/docs/reference/foundations/bool/) ,

)  -> [ str ](/docs/reference/foundations/str/)

####  ` pattern `

[ none ](/docs/reference/foundations/none/) or  [ str
](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to search for. If ` none  ` , trims white spaces.

Default: ` none  `

####  ` at `

[ alignment ](/docs/reference/layout/alignment/)

Can be ` start ` or ` end ` to only trim the start or end of the string. If
omitted, both sides are trimmed.

####  ` repeat `

[ bool ](/docs/reference/foundations/bool/)

Whether to repeatedly removes matches of the pattern or just once. Defaults to
` true  ` .

Default: ` true  `

###  ` split `

Splits a string at matches of a specified pattern and returns an array of the
resulting parts.

self  .  split  (

[ none ](/docs/reference/foundations/none/) [ str
](/docs/reference/foundations/str/) [ regex
](/docs/reference/foundations/regex/)

)  -> [ array ](/docs/reference/foundations/array/)

####  ` pattern `

[ none ](/docs/reference/foundations/none/) or  [ str
](/docs/reference/foundations/str/) or  [ regex
](/docs/reference/foundations/regex/)

Positional

Question mark

Positional parameters are specified in order, without names.

The pattern to split at. Defaults to whitespace.

Default: ` none  `

###  ` rev `

Reverse the string.

self  .  rev  (

)  -> [ str ](/docs/reference/foundations/str/)

[ ![â](/assets/icons/16-arrow-right.svg) Selector  Previous page
](/docs/reference/foundations/selector/) [ ![â](/assets/icons/16-arrow-
right.svg) Style  Next page  ](/docs/reference/foundations/style/)

