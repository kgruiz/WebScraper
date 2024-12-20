#  boxr

0.1.0

A modular, and easy to use, package for creating cardboard cutouts in Typst.

Boxr is a modular, and easy to use, package for creating cardboard cutouts in
Typst.

##  Usage

Create a boxr structure in your project with the following code:

    
    
    #import "@preview/boxr:0.1.0": *
    
    #render-structure(
      "box",
      width: 100pt,
      height: 100pt,
      depth: 100pt,
      tab-size: 20pt,
      [
        Hello from boxr!
      ]
    )
    

The ` render-structure ` function is the main function for boxr. It either
takes a path to one of the default structures provided by boxr (e.g.: ` "box"
` ) or an unpacked json file with your own custom structure (e.g.: ` json(my-
structure.json) ` ). These describe the structure of the cutout.  
The other named arguments depend on the structure you are rendering. All
unnamed arguments are passed to the structure as content and will be rendered
on each box face (not triangles or tabs).

##  Creating your own structures

Structures are defined in ` .json ` files. An example structure that just
shows a box with a tab on one face is shown below:

    
    
    {
      "variables": ["height", "width", "tab-size"],
      "width": "width",
      "height": "height + tab-size",
      "offset-x": "",
      "offset-y": "tab-size",
      "root": {
        "type": "box",
        "id": 0,
        "width": "width",
        "height": "height",
        "children": {
          "top": "tab(tab-size, tab-size)"
        }
      }
    }
    

The ` variables ` key is a list of variable names that can be passed to the
structure. These will be required to be passed to the ` render-structure `
function.  
The ` width ` and ` height ` keys are evaluated to calculate the width and
height of the structure.  
The ` offset-x ` and ` offset-y ` keys are evaluated to place the structure in
the middle of its bounds. It is relative to the root node. In this case for
example, the top tab adds a ` tab-size ` on top of the box as opposed to the
bottom, where there is no tab. So this ` tab-size ` is added to the ` offset-y
` .  
` root ` denotes the first node in the structure.  
A node can be of the following types:

  * ` box ` : 
    * The root node has a ` width ` and a ` height ` . All following nodes have a ` size ` . Child nodes use ` size ` and the parent nodeâs ` width ` and ` height ` to calculate their own width and height. 
    * Can have ` children ` nodes. 
    * Can have an ` id ` key that is used to place content on the face of the box. The id-th unnamed argument is placed on the face. Multiple faces can have the same id. 
    * Can have a ` no-fold ` key. If this exists, no fold stroke will be drawn between this box and its parent. 
  * ` triangle-<left|right> ` : 
    * Has a ` width ` and ` height ` . 
    * ` left ` and ` right ` denote the direction the other right angled line is facing relative to the base. 
    * Can have ` children ` nodes. 
    * Can have a ` no-fold ` key. If this exists, no fold stroke will be drawn between this triangle and its parent. 
  * ` tab ` : 
    * Is not a json object, but a string that denotes a tab. The tab is placed on the parent node. 
    * Has a tab-size and a cutin-size inside the ` () ` separted by a ` , ` . 
  * ` none ` : 
    * Is not a json object, but a string that denotes no node. This is useful for deleting a cut-stroke between two nodes. 

Every string value in the json file ( ` width: "__", height: "__", ... offset-x/y: "__" ` and the values between the ` | ` for tabs) is evaluated as regular typst code. This means that you can use all named variables passed to the structure. All inputs are converted to points and the result of the evaluation will be converted back to a length. 

###  How to add

Copy this into your project and use the import as  ` boxr `

    
    
    #import "@preview/boxr:0.1.0"

![Copy](/assets/icons/16-copy.svg)

Check the docs for  [ more information on how to import packages
](https://typst.app/docs/reference/scripting/#packages) .

###  About

Author  :

     [ Lypsilonx ](https://github.com/Lypsilonx)
License:

     MIT 
Current version:

     0.1.0 
Last updated:

     May 23, 2024 
First released:

     May 23, 2024 
Archive size:

     6.23 kB [ ![Size icon](/assets/icons/16-download.svg) ](https://packages.typst.org/preview/boxr-0.1.0.tar.gz)
Repository:

     [ GitHub ](https://github.com/Lypsilonx/boxr)
Discipline  :

    

  * [ Design ](https://typst.app/universe/search/?discipline=design)

Categor  ies  :

    

  * ![Visualization icon](/assets/icons/16-chart.svg) [ Visualization ](https://typst.app/universe/search/?category=visualization)
  * ![Layout icon](/assets/icons/16-layout.svg) [ Layout ](https://typst.app/universe/search/?category=layout)

###  Where to report issues?

This  package  is a project of  Lypsilonx  .  Report issues on  [ their
repository ](https://github.com/Lypsilonx/boxr) .  You can also try to ask for
help with this  package  on the  [ Forum ](https://forum.typst.app) .

Please report this  package  to the Typst team using the  [ contact form
](https://typst.app/contact) if you believe it is a safety hazard or infringes
upon your rights.

###  Version history

Version  |  Release Date   
---|---  
0.1.0  |  May 23, 2024   
  
Typst GmbH did not create this  package  and cannot guarantee correct
functionality of this  package  or compatibility with any version of the Typst
compiler or app.

