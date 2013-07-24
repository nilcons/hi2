# hi2

haskell-indentation, 2nd try.

## Installation

Put `hi2.el` into your load-path and add this to .emacs:

    (require 'hi2)
    (add-hook haskell-mode-hook 'turn-on-hi2)

## Notable changes to haskell-indentation-mode

* DEL and C-d is not mapped: if you want to indent backwards, you can
  use S-TAB.

* TAB steps to the right as before, but when the end is reached, it
  starts going to the left instead of wrapping around.

* TAB stays inside the code, instead of going to the beginning of the
  line.

* Region indentation common case is supported: TAB and S-TAB is simply
  moving the whole region to the left/right.

* The code for all this is somewhat commented and cleaned.
