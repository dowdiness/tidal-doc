---
title: Muting functions
permalink: wiki/Muting_functions/
layout: wiki
tags:
 - Metapattern
---

Your code editor may have a keystroke to comment a single line. If you
are structuring your code as a multiline block, you can quickly remove /
add back in one or more functions that share a single line. Essentially
'muting' it from your pattern.

In Atom, the keystroke is Ctrl + /

In this example, all the delay parameters are grouped on a single line,
and the delay can be muted quickly by commenting and re-evaluating the
code block.

    d1 $ sound "808oh*4" 
    #delayfeedback 0.75 # delaytime (segment 2 $ choose[3,5,7]/32) # delay 0.5

Additionally, some functions have a value/default value that will negate
their effect on the pattern. A few examples:

-   speed 1
-   fast 1
-   slow 1

You could use **const** to replace the pattern with a blank one (note:
this affects the whole pattern).

    d1 $ (const $ sound "" ) $ sound "808(5,8)" 

See also: [silence](silence "wikilink")

If a function requires another function as an input, you may be able to
mute with the

    id

aka the Haskell identity function. This can also be helpful as a
placeholder

Compare these two examples, the first has transposition as part of the

    stut'

, the second replaces that function with

    id

, effectively muting the transposition

    d1 $ stut' 2 (1/16) (+ note "1") $ sound "808(3,8)"

    d1 $ stut' 2 (1/16) (id) $ sound "808(3,8)"
