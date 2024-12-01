#  Scripting

##  Unflatten arrays

    
    
    // author: PgSuper
    #let unflatten(arr, n) = {
      let columns = range(0, n).map(_ => ())
      for (i, x) in arr.enumerate() {
        columns.at(calc.rem(i, n)).push(x)
      }
      array.zip(..columns)
    }
    
    #unflatten((1, 2, 3, 4, 5, 6), 2)
    #unflatten((1, 2, 3, 4, 5, 6), 3)

![Rendered image](typst-
img/98271a255f0fb10f31ba1d8199ba5a91ebb6f647cdd570220f95e1b88d193ca0-1.svg)

##  Create an abbreviation

    
    
    #let full-name = "Federal University of Ceará"
    
    #let letts = {
      full-name
        .split()
        .map(word => word.at(0)) // filter only capital letters
        .filter(l => upper(l) == l)
        .join()
    }
    #letts

![Rendered image](typst-
img/e95b77243a1305a47517cb128577d1c7633d858561de0ef797ff551f35be40de-1.svg)

##  Split the string retrieving separators

    
    
    #",this, is a a a a; a. test? string!".matches(regex("(\b[\P{Punct}\s]+\b|\p{Punct})")).map(x => x.captures).join()

![Rendered image](typst-
img/c5d183e45097449e4f52b07f82185847092ad28bcad3b9474093d341c4b07c4a-1.svg)

##  Create selector matching any values in an array

This snippet creates a selector (that is then used in a show rule) that
matches any of the values inside the array. Here, it is used to highlight a
few raw lines, but it can be easily adapted to any kind of selector.

    
    
    // author: Blokyk
    #let lines = (2, 3, 5)
    #let lines-selectors = lines.map(lineno => raw.line.where(number: lineno))
    #let lines-combined-selector = lines-selectors.fold(
      // start with the first selector by default
      // you can also use a selector that wouldn't ever match anything, if possible
      lines-selectors.at(0),
      selector.or // create an OR of all selectors (alternatively: (acc, sel) => acc.or(sel))
    )
    
    #show lines-combined-selector: highlight
    
    ```py
    def foo(x, y):
      if x == y:
        return False
      z = x + y
      return z * x - z * y >= z
    ```

![Rendered image](typst-
img/085d1ae3a0672ba278edcde3ebb229a34a40ab5166d0b6d5b469d838b9262a51-1.svg)

##  Synthesize show (or show-set) rules from dictionnary

This snippet applies a show-set rule to any element inside a dictionary, by
using the key as the selector and the value as the parameter to set. In this
example, it's used to give custom supplements to custom figure kinds, based on
a dictionnary of correspondances.

    
    
    // author: laurmaedje
    #let kind_supp_dict = (
      algo: "Pseudo-code",
      ex: "Example",
      prob: "Problem",
    )
    
    // apply this rule to the whole (rest of the) document
    #show: it => {
      kind_supp_dict
        .pairs() // get an array of key-value pairs
        .fold( // we're going to stack show-set rules before the document
          it, // start with the default document
          (acc, (kind, supp)) => {
            // add the curent kind-supp combination on top of the rest
            show figure.where(kind: kind): set figure(supplement: supp)
            acc
          }
        )
    }
    #figure(
        kind: "algo",
        caption: [My code],
        ```Algorithm there```
    )

![Rendered image](typst-
img/9de9b5f4bb801735b13ffafe54d35ebcfc78f1df78a34a8ab90f8a6c350b986e-1.svg)

Additonnaly, as this is applied at the position where you write it, these
show-set rules will appear as if they were added in the same place where you
wrote this rule. This means that you can override them later, just like any
other show-set rules.
