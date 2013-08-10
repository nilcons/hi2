# hi2

haskell-indentation, 2nd try.

## Installation

Put `hi2.el` into your load-path and add this to .emacs:

    (require 'hi2)
    (add-hook 'haskell-mode-hook 'turn-on-hi2)

The package can also be found on MELPA, if you install from there, you
can leave out the require line above.

## Notable changes to haskell-indentation-mode

* DEL and C-d is not mapped: if you want to indent backwards, you can
  use S-TAB.  This means no random jumping on backspace anymore.

* TAB steps to the right as before, but when the end is reached, it
  starts going to the left instead of wrapping around.

* TAB stays inside the code, instead of going to the beginning of the
  line.  As in pyhton-mode and perl-mode.

* Region indentation common case is supported: TAB and S-TAB is simply
  moving the whole region to the left/right by 1-column.  Can be
  pressed repeatedly.

* The current indentations are shown as underscores in the current
  line.  So you have some visual indication on what's gonna happen.
  Also useful while hacking on the parser and want to see the results.
  Can be turned off by setting hi2-show-indentations to nil in your
  init file or calling hi2-disable-show-indentations from the buffer.
  If there are collisions with other overlay hacking modes
  (e.g. fill-column-indicator), try to turn off
  hi2-show-indentations-after-eol.

* The buffer is not changed when indentation is not changed (so there
  are no undo points created and no dirty flag in the buffer if
  pressing TAB had no effect).

* The code for all this is somewhat commented and cleaned.
