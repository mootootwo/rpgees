# 2dF Drop Cellular Automata Lemmingslike
Drop 2df on a one-dimensional board to determine starting state, and shepherd r@bbits into a h0le.

## Key:

- `[+]` positive charge
- `[-]` negative charge
- `[#]` blocking space
- `[@]` r@bbit
- `[0]` h0le

- `[z]` any charge ( `[+]` or `[-]` ) (multiple `[z]` in an example will be like-charges)
- `[s]` opposite charge of `[z]` (conditional, always the inverse of what `[z]` is in any given example)
- `[?]` any space (empty or non-empty)

## Setup gamespace:

Chart out a game board with 8 empty spaces `[ ]`:

	      [ ][ ][ ][ ][ ][ ][ ][ ]

Drop 2dF and mark `[+]`, `[-]`, or `[#]` in the spaces where they land

Prepend `[0][@]` to the board:

	[0][@][ ][ ][ ][ ][ ][ ][ ][ ]

Postpend `[0]` to the board:

	[0][@][ ][ ][ ][ ][ ][ ][ ][ ][0]

## Each Turn (for 30 turns):

Evaluate each set of three `[?]` and record a new object `[*]` for the center space, on a new line, according to the formulas below, presented in this format:

	 Input [?][?][?]
	Result    [*]

(see Wolfram's one-dimensional cellular automaton for more examples of this evaluation process)

All rule sets are symmetric such that `[ ][ ][z]` is evaluated in the same way as `[z][ ][ ]`, or `[?][z][0]` is evaluated in the same way as `[0][z][?]`.

Once per turn, you may do one of:
	
	Change [ ] to [#]
	Change [#] to [ ]
	Change [+] to [-]
	Change [-] to [+]

Score +1:

	When [@] vanishes into rightmost [0]

### Optional Rule:

Roll 4dF and spend up to one per turn:

	Spend [+] to change [+] to [ ], or [-] to [+]
	Spend [-] to change [-] to [ ], or [+] to [-]
	Spend [ ] to change [#] to [ ], or [ ] to [#]

### Evaluation Sets:

`[z]` grows one square in either direction

	 Input [z][ ][ ] input
	Result    [z]

`[z]` collides with `[s]` forming `[#]`

	 Input [z][s][?] input
	    or [z][ ][s]
	Result    [#]

`[z]` collides with `[#]` vanishing

	 Input [z][z][#]
	    or [ ][z][#]
	Result    [ ]

`[z]` collides with `[0]` vanishing

	 Input [?][z][0]
	Result    [ ]

`[z]` collides with `[z]` vanishing

	 Input [z][z][z]
	    or [z][z][ ]
	    or [z][ ][z]
	Result    [ ]

`[z]` does not persist

	Input [ ][z][ ]
	Result   [ ]

`[#]` persists

	Input [?][#][?]
	Result   [#]

`[@]` behaves as a charge

	Input [@][ ][ ]
	   or [@][ ][#]
	Result   [@]
	
	Input [@][ ][z]
	   or [@][z][ ]
	   or [@][z][#]
	   or [?][@][0]
	Result   [ ]

## Example of Play
(with no interaction):

	01.[0][@][ ][ ][-][ ][ ][+][ ][ ][0]
	02.[0][ ][@][-][ ][-][+][ ][+][ ][0]
	03.[0][@][ ][ ][ ][#][#][ ][ ][+][0]
	04.[0][ ][@][ ][ ][#][#][ ][+][ ][0]
	05.[0][@][ ][@][ ][#][#][+][ ][+][0]
	06.[0][ ][ ][ ][@][#][#][ ][ ][ ][0]
	07.[0][ ][ ][@][ ][#][#][ ][ ][ ][0]
	08.[0][ ][@][ ][@][#][#][ ][ ][ ][0]
	09.[0][@][ ][ ][ ][#][#][ ][ ][ ][0]
	10.[0][ ][@][ ][ ][#][#][ ][ ][ ][0]

[2dFCAL](https://mootootwo.github.io/rpgees/omgam2019/2dFDCAL) by [Luke Miller](https://twitter.com/mootootwo) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).
