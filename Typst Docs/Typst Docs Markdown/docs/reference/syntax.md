  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Syntax ](/docs/reference/syntax/)

#  Syntax

Typst is a markup language. This means that you can use simple syntax to
accomplish common layout tasks. The lightweight markup syntax is complemented
by set and show rules, which let you style your document easily and
automatically. All this is backed by a tightly integrated scripting language
with built-in and user-defined functions.

##  Modes

Typst has three syntactical modes: Markup, math, and code. Markup mode is the
default in a Typst document, math mode lets you write mathematical formulas,
and code mode lets you use Typst's scripting features.

You can switch to a specific mode at any point by referring to the following
table:

New mode  |  Syntax  |  Example   
---|---|---  
Code  |  Prefix the code with ` # ` |  ` Number:  #  (  1  +  2  )  `  
Math  |  Surround equation with ` $  ..  $  ` |  ` $  -  x  $  is the opposite of  $  x  $  `  
Markup  |  Surround markup with ` [..] ` |  ` let  name  =  [  *Typst!*  ]  `  
  
Once you have entered code mode with ` # ` , you don't need to use further
hashes unless you switched back to markup or math mode in between.

##  Markup

Typst provides built-in markup for the most common document elements. Most of
the syntax elements are just shortcuts for a corresponding function. The table
below lists all markup that is available and links to the best place to learn
more about their syntax and usage.

Name  |  Example  |  See   
---|---|---  
Paragraph break  |  Blank line  |  [ ` parbreak ` ](/docs/reference/model/parbreak/ "`parbreak`")  
Strong emphasis  |  ` *strong*  ` |  [ ` strong ` ](/docs/reference/model/strong/ "`strong`")  
Emphasis  |  ` _emphasis_  ` |  [ ` emph ` ](/docs/reference/model/emph/ "`emph`")  
Raw text  |  ` `print(1)`  ` |  [ ` raw ` ](/docs/reference/text/raw/ "`raw`")  
Link  |  ` https://typst.app/  ` |  [ ` link ` ](/docs/reference/model/link/ "`link`")  
Label  |  ` <intro> ` |  [ ` label ` ](/docs/reference/foundations/label/ "`label`")  
Reference  |  ` @intro  ` |  [ ` ref ` ](/docs/reference/model/ref/ "`ref`")  
Heading  |  ` = Heading  ` |  [ ` heading ` ](/docs/reference/model/heading/ "`heading`")  
Bullet list  |  ` -  item ` |  [ ` list ` ](/docs/reference/model/list/ "`list`")  
Numbered list  |  ` +  item ` |  [ ` enum ` ](/docs/reference/model/enum/ "`enum`")  
Term list  |  ` /  Term  :  description ` |  [ ` terms ` ](/docs/reference/model/terms/ "`terms`")  
Math  |  ` $  x  ^  2  $  ` |  [ Math ](/docs/reference/math/)  
Line break  |  ` \  ` |  [ ` linebreak ` ](/docs/reference/text/linebreak/ "`linebreak`")  
Smart quote  |  ` 'single' or "double" ` |  [ ` smartquote ` ](/docs/reference/text/smartquote/ "`smartquote`")  
Symbol shorthand  |  ` ~  ` , ` ---  ` |  [ Symbols ](/docs/reference/symbols/sym/)  
Code expression  |  ` #  rect  (  width  :  1cm  )  ` |  [ Scripting ](/docs/reference/scripting/#expressions)  
Character escape  |  ` Tweet at us  \#  ad ` |  Below   
Comment  |  ` /* block */  ` , ` // line  ` |  Below   
  
##  Math mode

Math mode is a special markup mode that is used to typeset mathematical
formulas. It is entered by wrapping an equation in ` $ ` characters. This
works both in markup and code. The equation will be typeset into its own block
if it starts and ends with at least one space (e.g. ` $  x  ^  2  $  ` ).
Inline math can be produced by omitting the whitespace (e.g. ` $  x  ^  2  $
` ). An overview over the syntax specific to math mode follows:

Name  |  Example  |  See   
---|---|---  
Inline math  |  ` $  x  ^  2  $  ` |  [ Math ](/docs/reference/math/)  
Block-level math  |  ` $  x  ^  2  $  ` |  [ Math ](/docs/reference/math/)  
Bottom attachment  |  ` $  x  _  1  $  ` |  [ ` attach ` ](/docs/reference/math/attach/)  
Top attachment  |  ` $  x  ^  2  $  ` |  [ ` attach ` ](/docs/reference/math/attach/)  
Fraction  |  ` $  1 +  (  a+b  )  /  5  $  ` |  [ ` frac ` ](/docs/reference/math/frac/)  
Line break  |  ` $  x  \  y  $  ` |  [ ` linebreak ` ](/docs/reference/text/linebreak/ "`linebreak`")  
Alignment point  |  ` $  x  & = 2  \  & = 3  $  ` |  [ Math ](/docs/reference/math/)  
Variable access  |  ` $  #  x  $  ,  $  pi  $  ` |  [ Math ](/docs/reference/math/)  
Field access  |  ` $  arrow  .  r  .  long  $  ` |  [ Scripting ](/docs/reference/scripting/#fields)  
Implied multiplication  |  ` $  x y  $  ` |  [ Math ](/docs/reference/math/)  
Symbol shorthand  |  ` $  -> $  ` , ` $  !=  $  ` |  [ Symbols ](/docs/reference/symbols/sym/)  
Text/string in math  |  ` $  a  "is natural"  $  ` |  [ Math ](/docs/reference/math/)  
Math function call  |  ` $  floor  (  x  )  $  ` |  [ Math ](/docs/reference/math/)  
Code expression  |  ` $  #  rect  (  width  :  1cm  )  $  ` |  [ Scripting ](/docs/reference/scripting/#expressions)  
Character escape  |  ` $  x  \^  2  $  ` |  Below   
Comment  |  ` $  /* comment */  $  ` |  Below   
  
##  Code mode

Within code blocks and expressions, new expressions can start without a
leading ` # ` character. Many syntactic elements are specific to expressions.
Below is a table listing all syntax that is available in code mode:

Name  |  Example  |  See   
---|---|---  
None  |  ` none  ` |  [ ` none ` ](/docs/reference/foundations/none/ "`none`")  
Auto  |  ` auto  ` |  [ ` auto ` ](/docs/reference/foundations/auto/ "`auto`")  
Boolean  |  ` false  ` , ` true  ` |  [ ` bool ` ](/docs/reference/foundations/bool/ "`bool`")  
Integer  |  ` 10  ` , ` 0xff  ` |  [ ` int ` ](/docs/reference/foundations/int/ "`int`")  
Floating-point number  |  ` 3.14  ` , ` 1e5  ` |  [ ` float ` ](/docs/reference/foundations/float/ "`float`")  
Length  |  ` 2pt  ` , ` 3mm  ` , ` 1em  ` , ..  |  [ ` length ` ](/docs/reference/layout/length/ "`length`")  
Angle  |  ` 90deg  ` , ` 1rad  ` |  [ ` angle ` ](/docs/reference/layout/angle/ "`angle`")  
Fraction  |  ` 2fr  ` |  [ ` fraction ` ](/docs/reference/layout/fraction/ "`fraction`")  
Ratio  |  ` 50%  ` |  [ ` ratio ` ](/docs/reference/layout/ratio/ "`ratio`")  
String  |  ` "hello"  ` |  [ ` str ` ](/docs/reference/foundations/str/ "`str`")  
Label  |  ` <intro> ` |  [ ` label ` ](/docs/reference/foundations/label/ "`label`")  
Math  |  ` $  x  ^  2  $  ` |  [ Math ](/docs/reference/math/)  
Raw text  |  ` `print(1)`  ` |  [ ` raw ` ](/docs/reference/text/raw/ "`raw`")  
Variable access  |  ` x ` |  [ Scripting ](/docs/reference/scripting/#blocks)  
Code block  |  ` {  let  x  =  1  ;  x  +  2  }  ` |  [ Scripting ](/docs/reference/scripting/#blocks)  
Content block  |  ` [  *Hello*  ]  ` |  [ Scripting ](/docs/reference/scripting/#blocks)  
Parenthesized expression  |  ` (  1  +  2  )  ` |  [ Scripting ](/docs/reference/scripting/#blocks)  
Array  |  ` (  1  ,  2  ,  3  )  ` |  [ Array ](/docs/reference/foundations/array/)  
Dictionary  |  ` (  a  :  "hi"  ,  b  :  2  )  ` |  [ Dictionary ](/docs/reference/foundations/dictionary/)  
Unary operator  |  ` -  x ` |  [ Scripting ](/docs/reference/scripting/#operators)  
Binary operator  |  ` x  +  y ` |  [ Scripting ](/docs/reference/scripting/#operators)  
Assignment  |  ` x  =  1  ` |  [ Scripting ](/docs/reference/scripting/#operators)  
Field access  |  ` x  .  y ` |  [ Scripting ](/docs/reference/scripting/#fields)  
Method call  |  ` x  .  flatten  (  )  ` |  [ Scripting ](/docs/reference/scripting/#methods)  
Function call  |  ` min  (  x  ,  y  )  ` |  [ Function ](/docs/reference/foundations/function/)  
Argument spreading  |  ` min  (  ..  nums  )  ` |  [ Arguments ](/docs/reference/foundations/arguments/)  
Unnamed function  |  ` (  x  ,  y  )  => x  +  y ` |  [ Function ](/docs/reference/foundations/function/)  
Let binding  |  ` let  x  =  1  ` |  [ Scripting ](/docs/reference/scripting/#bindings)  
Named function  |  ` let  f  (  x  )  =  2  *  x ` |  [ Function ](/docs/reference/foundations/function/)  
Set rule  |  ` set  text  (  14pt  )  ` |  [ Styling ](/docs/reference/styling/#set-rules)  
Set-if rule  |  ` set  text  (  ..  )  if  .. ` |  [ Styling ](/docs/reference/styling/#set-rules)  
Show-set rule  |  ` show  heading  :  set  block  (  ..  )  ` |  [ Styling ](/docs/reference/styling/#show-rules)  
Show rule with function  |  ` show  raw  :  it  => {  ..  }  ` |  [ Styling ](/docs/reference/styling/#show-rules)  
Show-everything rule  |  ` show  :  template  ` |  [ Styling ](/docs/reference/styling/#show-rules)  
Context expression  |  ` context  text  .  lang ` |  [ Context ](/docs/reference/context/)  
Conditional  |  ` if  x  ==  1  {  ..  }  else  {  ..  }  ` |  [ Scripting ](/docs/reference/scripting/#conditionals)  
For loop  |  ` for  x  in  (  1  ,  2  ,  3  )  {  ..  }  ` |  [ Scripting ](/docs/reference/scripting/#loops)  
While loop  |  ` while  x  < 10  {  ..  }  ` |  [ Scripting ](/docs/reference/scripting/#loops)  
Loop control flow  |  ` break  ,  continue  ` |  [ Scripting ](/docs/reference/scripting/#loops)  
Return from function  |  ` return  x ` |  [ Function ](/docs/reference/foundations/function/)  
Include module  |  ` include  "bar.typ"  ` |  [ Scripting ](/docs/reference/scripting/#modules)  
Import module  |  ` import  "bar.typ"  ` |  [ Scripting ](/docs/reference/scripting/#modules)  
Import items from module  |  ` import  "bar.typ"  :  a  ,  b  ,  c ` |  [ Scripting ](/docs/reference/scripting/#modules)  
Comment  |  ` /* block */  ` , ` // line  ` |  Below   
  
##  Comments

Comments are ignored by Typst and will not be included in the output. This is
useful to exclude old versions or to add annotations. To comment out a single
line, start it with ` // ` :

    
    
    // our data barely supports
    // this claim
    
    We show with $p < 0.05$
    that the difference is
    significant.
    

![Preview](/assets/docs/qmPJyf2DgB8m9bpdDccxUQAAAAAAAAAA.png)

Comments can also be wrapped between ` /* ` and ` */ ` . In this case, the
comment can span over multiple lines:

    
    
    Our study design is as follows:
    /* Somebody write this up:
       - 1000 participants.
       - 2x2 data design. */
    

![Preview](/assets/docs/0bd3Pt_MGVIAagJ8npuMMAAAAAAAAAAA.png)

##  Escape sequences

Escape sequences are used to insert special characters that are hard to type
or otherwise have special meaning in Typst. To escape a character, precede it
with a backslash. To insert any Unicode codepoint, you can write a hexadecimal
escape sequence: ` \u{1f600}  ` . The same kind of escape sequences also work
in [ strings ](/docs/reference/foundations/str/) .

    
    
    I got an ice cream for
    \$1.50! \u{1f600}
    

![Preview](/assets/docs/2Hq1wVq0JUPd4EarGtBZUQAAAAAAAAAA.png)

##  Paths

Typst has various features that require a file path to reference external
resources such as images, Typst files, or data files. Paths are represented as
[ strings ](/docs/reference/foundations/str/) . There are two kinds of paths:
Relative and absolute.

  * A **relative path** searches from the location of the Typst file where the feature is invoked. It is the default: 
    
        #image("images/logo.png")
    

  * An **absolute path** searches from the _root_ of the project. It starts with a leading ` / ` : 
    
        #image("/assets/logo.png")
    

###  Project root

By default, the project root is the parent directory of the main Typst file.
For security reasons, you cannot read any files outside of the root directory.

If you want to set a specific folder as the root of your project, you can use
the CLI's ` --root ` flag. Make sure that the main file is contained in the
folder's subtree!

    
    
    typst compile --root .. file.typ
    

In the web app, the project itself is the root directory. You can always read
all files within it, no matter which one is previewed (via the eye toggle next
to each Typst file in the file panel).

###  Paths and packages

A package can only load files from its own directory. Within it, absolute
paths point to the package root, rather than the project root. For this
reason, it cannot directly load files from the project directory. If a package
needs resources from the project (such as a logo image), you must pass the
already loaded image, e.g. as a named parameter ` logo:  image  (
"mylogo.svg"  )  ` . Note that you can then still customize the image's
appearance with a set rule within the package.

In the future, paths might become a [ distinct type from strings
](https://github.com/typst/typst/issues/971) , so that they can retain
knowledge of where they were constructed. This way, resources could be loaded
from a different root.

[ ![â](/assets/icons/16-arrow-right.svg) Reference  Previous page
](/docs/reference/) [ ![â](/assets/icons/16-arrow-right.svg) Styling  Next
page  ](/docs/reference/styling/)

