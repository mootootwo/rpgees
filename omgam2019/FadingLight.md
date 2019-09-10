# Fading Light

- Fly between stars
- Peer into the history of worlds
- Collect artifacts
- Influence cultural evolution
- Mine singularities
- Run out of gas
- Get caught within an event horizon

a tabletop game for one or more

created by Luke Miller (https://twitter.com/mootootwo)

Original pamphlet at https://mootootwo.itch.io/fading-light

Written for the 2019 #PamphletJam

at https://itch.io/jam/pamphletjam

And #mapemounde2019 at https://itch.io/jam/mapemounde2019 
  
Part of the OMGAM project  at https://exposit.github.io/omgam/

More at https://ktsink.blogspot.com/

cc by-sa 4.0

Noto Sans by Google, licensed under Apache 2.0

## Terms

- **dF** — Fudge die.  Six sided dice with equal sides labeled `[+]` ,  `[_]` , and  `[-]`
- **Endurance** —  Each `<<>>` represents 5 gigaseconds of lifetime or travel capability for your starship.
- **Cultural Artifacts** —  Each `[[]]` represents an object or information set produced by a culture.  It may be fungible or used to influence the direction of other cultures.
- **Gigasecond** —  A unit of time close to 30 years, or a unit of distance (light-gigaseconds) close to 10 parsecs.

## Map Setup

There is an inhabited world present at the midpoint and at each edge of the map.

For each of the other six spots on the map, roll 1dF.  

On `[+]` there is an inhabited world present

## World Culture

For each world, sum 2dF to find the cultural era.

    [+][+]           transcendent  ( level 4 )
    [+][_]           networked     ( level 3 )
    [_][_] or [+][-] global        ( level 2 )
    [-][_]           regional      ( level 1 )
    [-][-]           local         ( level 0 )

Roll 1dF for velocity

    [+]	>	advancing
    [_]	0	stable
    [-]	<	declining

## Starting conditions

Your starship begins in the midpoint system with 50 gigaseconds of endurance (10 `<<>>` ) with which to travel the stars.

Add a number of cultural artifacts to your ship’s hold, equal to the level of cultural era in the starting system.

## Light Lag

For every 5 gigaseconds distance from your ship, there is equal lag to a world.  Track the light lag for each world in the `[gigaseconds]` field.

## Turn Flow

### Move to new destination

Choose another world on the map, and move your ship there.  Deduct one endurance <<>> for every 5 gigaseconds traveled.

### Advance time track

Update the light lag of each world based on distance from the ship.  In the next steps, the update time in gigaseconds for each world will equal  (current lag - previous lag + travel time)

###Update cultural level of the local world       —>

Roll dF to modify the cultural era, `[+]` increases and `[-]` decreases the level.  Sum:

- 1dF for each level of cultural era.  Count only `[+]` if the cultural velocity is Advancing.  Count only `[-]` if the cultural velocity is Declining.
- 1dF in sequence, for every 5 gigaseconds of time update.

If at any time, the cultural era increases above Transcendent, a singularity occurs and the era is set at zero.  Continue rolling for every 5 gigaseconds to determine the current cultural level of the world.

If the final roll takes the cultural era above level 4, a singularity occurs while the ship is present.  The game ends.

If a singularity occurs at some time in the history of the world, you may collect 20 artifacts minus one for every gigasecond elapsed between the singularity and your ship’s arrival.

### Collect news from other worlds    —>

Use the same process to advance the history of other worlds,  up to the current light lag.

### Collect cultural artifacts

Add one cultural artifact `[[]]` to your ship’s hold for every cultural level of the local world

### Spend artifacts to effect cultural level and velocity

You may spend one artifact `[[]]` to increase or decrease the current cultural era by 1 level.

You may spend one artifact `[[]]` to set the velocity, otherwise  the latest progress roll sets the current velocity ( `[+]` for Advancing, `[_]` for Stable, `[-]` for Declining )

### Trade artifacts for additional ship endurance

If the local world has a Networked culture, you may spend 2 artifacts `[[]]` to buy 5 gigaseconds of endurance (one `<<>>` )

If the local world has a Transcendent culture, you may spend 1 artifact `[[]]` to buy 10 gigaseconds of endurance (two `<<>>`‘s )

## Ending Conditions

### Stability

If you do not have enough endurance to reach another world, you settle in place and spend the cultural artifacts in your hold to sustain a stable cultural level.

Each artifact sustains 5 gigaseconds.  Count every 10 gigaseconds of stability as one point.

### Exploration

If you have at least 25 gigaseconds of endurance while at one of the edge worlds, you may choose to explore beyond this region of space.

Count all cultural artifacts, plus excess endurance (above 25 gigaseconds) as points.

### Transcendence

You have at least 25 cultural artifacts in your hold while you are present in a system undergoing singularity.

Count all cultural artifacts as points.
