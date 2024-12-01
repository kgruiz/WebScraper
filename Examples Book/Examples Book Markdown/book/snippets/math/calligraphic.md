#  Calligraphic letters

    
    
    #let scr(it) = math.class("normal",
      text(font: "", stylistic-set: 1, $cal(it)$) + h(0em)
    )
    
    $ scr(A) scr(B) + scr(C), -scr(D) $

![Rendered image](typst-
img/6ee9ca10515c1b6158d8d7bddd4418a713313052c0114fe851be455fc09b2c92-1.svg)

Unfortunately, currently just ` stylistic-set  ` for math creates bad spacing.
Math engine detects if the letter should be correctly spaced by whether it is
the default font. However, just making it "normal" isn't enough, because than
it can be reduced. That's way the snippet is as hacky as it is (probably
should be located in Typstonomicon, but it's not large enough).

