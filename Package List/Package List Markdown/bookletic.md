#  bookletic

0.3.0

Create beautiful booklets with ease.

Create beautiful booklets with ease.

The current version of this library (0.3.0) contains a single function to take
in an array of content blocks and order them into a ready to print booklet,
bulletin, etc. No need to fight with printer settings or document converters.

###  Example Output

Here is an example of the output generated by the ` sig ` function (short for
a bookâs signature) with default parameters and some sample content:

![Example1](https://github.com/typst/packages/raw/main/packages/preview/bookletic/0.3.0/example/basic.png)

Here is an example with some customization applied:

![Example2](https://github.com/typst/packages/raw/main/packages/preview/bookletic/0.3.0/example/fancy.png)

##  ` sig ` Function

The ` sig ` function is used to create a signature (booklet) layout from
provided content. It takes various parameters to automatically configure the
layout.

###  Parameters

  * ` page_margin_binding ` : The binding margin for each page in the booklet (space between pages). 
  * ` page_border ` : Takes a color space value to draw a border around each page. If set to none no border will be drawn. 
  * ` draft ` : A boolean value indicating whether to output an unordered draft or final layout. 
  * ` p-num-layout ` : A configuration for page numbering styles, allowing multiple layouts that apply to specified page ranges. Each layout can be provided as a dictonary specifying the following options: 
    * ` p-num-start ` : Starting page number for this layout 
    * ` p-num-alt-start ` : Alternative starting page number (e.g., for chapters) 
    * ` p-num-pattern ` : Pattern for page numbering (e.g., ` "1" ` , ` "i" ` , ` "a" ` , ` "A" ` ) 
    * ` p-num-placment ` : Placement of page numbers ( ` top ` or ` bottom ` ) 
    * ` p-num-align-horizontal ` : Horizontal alignment of page numbers ( ` left ` , ` center ` , or ` right ` ) 
    * ` p-num-align-vertical ` : Vertical alignment of page numbers ( ` top ` , ` horizon ` , or ` bottom ` ) 
    * ` p-num-pad-left ` : Extra padding added to the left of the page number 
    * ` p-num-pad-horizontal ` : Horizontal padding for page numbers 
    * ` p-num-size ` : Size of page numbers 
    * ` p-num-border ` : The border color for the page numbers. If set to none no border will be drawn. 
    * ` p-num-halign-alternate ` : A boolean for whether to alternate horizontal alignment between left and right pages. 
  * ` pad_content ` : The padding around the page content. 
  * ` contents ` : The content to be laid out in the booklet. This should be an array of blocks. 

###  Usage

To use the ` sig ` function, first set your desired page settings using the
native page function. Then simply call the sig function with the desired
parameters and provide the content to be laid out in the booklet:

    
    
    #set page(flipped: true, paper: "us-letter")
    #bookletic.sig(
      contents: [
        ["Page 1 content"],
        ["Page 2 content"],
        ["Page 3 content"],
        ["Page 4 content"],
      ],
    )
    

This will create a signature layout with the provided content, using the
default values for the other parameters.

You can customize the layout by passing different values for the various
parameters. For example:

    
    
    #set page(flipped: true, paper: "us-legal", margin: (top: 1in, bottom: 1in, left: 1in, right: 1in))
    #bookletic.sig(
      page_margin_binding: 0.5in,
      page_border: none,
      draft: true,
      p-num-layout: (
        bookletic.num-layout(
          p-num-start: 1,
          p-num-alt-start: none,
          p-num-pattern: "~ 1 ~", 
          p-num-placment: bottom,
          p-num-align-horizontal: right,
          p-num-align-vertical: horizon,
          p-num-pad-left: -5pt,
          p-num-pad-horizontal: 0pt,
          p-num-size: 16pt,
          p-num-border: rgb("#ff4136"),
          p-num-halign-alternate: false,
        ),
      ),
      pad_content: 10pt,
      contents: (
        ["Page 1 content"],
        ["Page 2 content"],
        ["Page 3 content"],
        ["Page 4 content"],
      ),
    )
    

This will create an unordered draft signature layout with US Legal paper size,
larger margins, no page borders, page numbers at the bottom right corner with
a red border, and more padding around the content.

###  Notes

  * The ` sig ` function is currently hardcoded to only handle two-page single-fold signatures. Other more complicated signatures may be supported in the future. 
  * The ` num-layout ` function is a helper to create page number layouts with default values. 
  * The ` booklet ` function is a placeholder for automatically breaking a single content block into pages dynamically. It is not implemented yet but will be added in coming versions. 

##  Collaboration

I would love to see this package eventually turn into a community effort. So
any interest in collaboration is very welcome! You can find the github
repository for this library here: [ Bookletic Repo
](https://github.com/harrellbm/Bookletic) . Feel free to file an issue, pull
request, or start a discussion.

##  Changlog

####  0.3.0

  * Remove internal dependency on native page function. This allows the user to set the page function separately with full control over paper type, outer margins and everything else defined by the native page function. 
  * Add p-num-halign-alternate to page number layout allowing setting page numbers to alternate on facing pages making it possible to place page numbers along the outside or inside edges of facing pages. 
  * Internal improvements for ordering algorithm. 
  * Add ` num-layout ` function helper. 

####  0.2.0

  * Handle odd number of pages by inserting a blank back cover 
  * Implements page number layouts to allow defining different page numbers for different page ranges. 
  * Add various other page number options 

####  0.1.0

Initial Commit

###  How to add

Copy this into your project and use the import as  ` bookletic `

    
    
    #import "@preview/bookletic:0.3.0"

![Copy](/assets/icons/16-copy.svg)

Check the docs for  [ more information on how to import packages
](https://typst.app/docs/reference/scripting/#packages) .

###  About

Author  s  :

     [ Brenden Harrell ](https://github.com/harrellbm) & [ Paul DE TEMMERMAN ](https://github.com/paul2t)
License:

     Apache-2.0 
Current version:

     0.3.0 
Last updated:

     October 10, 2024 
First released:

     May 8, 2024 
Minimum Typst version:

     0.11.0 
Archive size:

     7.91 kB [ ![Size icon](/assets/icons/16-download.svg) ](https://packages.typst.org/preview/bookletic-0.3.0.tar.gz)
Repository:

     [ GitHub ](https://github.com/harrellbm/Bookletic.git)
Categor  ies  :

    

  * ![Book icon](/assets/icons/16-docs.svg) [ Book ](https://typst.app/universe/search/?category=book)
  * ![Layout icon](/assets/icons/16-layout.svg) [ Layout ](https://typst.app/universe/search/?category=layout)
  * ![Flyer icon](/assets/icons/16-map.svg) [ Flyer ](https://typst.app/universe/search/?category=flyer)

###  Where to report issues?

This  package  is a project of  Brenden Harrell and Paul DE TEMMERMAN  .
Report issues on  [ their repository
](https://github.com/harrellbm/Bookletic.git) .  You can also try to ask for
help with this  package  on the  [ Forum ](https://forum.typst.app) .

Please report this  package  to the Typst team using the  [ contact form
](https://typst.app/contact) if you believe it is a safety hazard or infringes
upon your rights.

###  Version history

Version  |  Release Date   
---|---  
0.3.0  |  October 10, 2024   
[ 0.2.0 ](https://typst.app/universe/package/bookletic/0.2.0/) |  May 23, 2024   
[ 0.1.0 ](https://typst.app/universe/package/bookletic/0.1.0/) |  May 8, 2024   
  
Typst GmbH did not create this  package  and cannot guarantee correct
functionality of this  package  or compatibility with any version of the Typst
compiler or app.
