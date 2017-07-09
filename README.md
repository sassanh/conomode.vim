
This is a fork of https://github.com/vim-scripts/conomode.vim

This fork requires Neovim to work, it needs `guicursor`.

New features (July 9 2017):
-------------
- It no longer shows a colon over cursor.
- It changes cursor shape to block shape when user activates Conomode in command line.

Old Readme
-------------

Implements a kind of Normal mode ( "Cmdline-Normal mode" ) on top of the Command line.  Purpose is similar to the cmdline-window (q:), but navigation and editing can be done in-place.  Of course the cmdline-window is much more powerful.

- enter with c_<C-O>   (press CTRL-O while in Command-line mode)
- mode indicator is a colon ":", moved along with the cursor, hiding the char under it
- quit to Cmdline-mode with I, i, a, A, : or any unmapped key (which then executes or inserts itself), or wait 60 seconds.
- quit to Normal mode with Esc

    Features So Far:
- Motions: h l w b e W B E 0 ^ $ f{char} F{char} t{char} T{char} ; , %    also in Operator pending mode
- Operators: d y c    these write to the unnamed register; c prompts for input()
- Shortcuts: yy D x X s C    yy -> 0y$, D -> d$, x -> dl, X -> dh, s -> dli, C -> c$
- Simple Changes: ~ r{char}
- Putting: P p    puts the unnamed register
- Repeating: .    repeatable commands: d r c ~ o    also: I i a A
- Macros: q @    q starts[/stops] recording, @ executes, no register involved
- Mode Switching:    I i a A - back to Cmdline (with positioned cursor),  <Esc> - back to Normal mode, <CR> - execute Cmdline, : - back to Cmdline (remove all text)
- Insert: o    input() version of i (accepts a count and is recordable)
- Undo: u U    redo with "U" (to keep c_CTRL-R working); undo information survives mode switching (!); undo is yet unlimited
- Count: can be given for most commands
- Misc: <C-L> - redraw the Cmdline

    Notes:
- the mode indicator makes UTF-8 characters look garbled - it's only a display problem; press Ctrl-L to redraw the Cmdline; I'd rather not use conomode with UTF-8, sorry ...

    Feedback is welcome (bugs, usage improvements, does it feel like vi?, etc.)

    Have fun!
