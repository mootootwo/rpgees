# dF Cyclical Scenario Generator

Describe a scenario as a series of interconnected nodes along cyclical paths

Generate the cyclical paths between the Start and End node

## Layout a grid from which to generate the scenario paths

Working from a 7x5 grid of cells: 

Place the Start node `[S]` in the left-most (1st) column, middle (3rd) row

Place the End node `[E]` in the right-most (7th) column, middle (3rd) row

    |---|---|---|---|---|---|---|
    
    5
    
    +   +   +   +   +   +   +   +
    
    4
    
    +   +   +   +   +   +   +   +
    
    3[S]                     [E]
    
    +   +   +   +   +   +   +   +
    
    2
    
    +   +   +   +   +   +   +   +
    
    1
    
    |-1-|-2-|-3-|-4-|-5-|-6-|-7-|


## Generate the first path

Working from the Start node, generate a new path
move one place right, and roll 2dF and evaluate rules in order

## Generate path features

for any `[+]`, advance the path one place right

    +   +
    
     --- 
    
    +   +

for `[+][+]`, advance the path an additional place right

    +   +   +
    
     --- --- 
    
    +   +   +

for any `[_]`, place a node `0` in the current cell cell

    +   +
    
      0  
    
    +   +

for `[_][_]`, place a major `!` node in the current cell

    +   +
    
      !  
    
    +   +

for any `[-]` or `[-][-]`, from the middle (3rd) row, branch the path to the rows above and below

    +   +
      |
     -
      |
    +   +

for any `[-]` or `[-][-]` in the top (5th) or bottom-most (1st) row, bend the path inwards (towards the middle row) instead of branching it

    |---|        +   +
                   |
     -\           -/
      | 
    +   +        |---|

for any `[-]` in rows 2 or 4, bend the path inwards to the middle row

    +   +        +   +
                   |
     -\           -/
      | 
    +   +        +   +


for any `[-][-]` in rows 2 or 4, branch the path to the rows above and below

    +   +
      |
     -
      |
    +   +
 
After evaluating the dice, advance the path one column to the right and roll 2dF.  
Repeat the evaluation process.
When a path reaches the 7th column, connect it to the End node `[E]` which complete this path

## Complete additional paths

Beginning again from each point where a path has branched, repeat the `Generate path features` process

Whenever the path converges on a cell containing another path, join the two and this completes the path being processed

When all paths are complete, the scenario is complete

## Example

    |---|---|---|---|---|---|---|
    
                  /- --- -0- -\
                  |           | 
    +   +   +   +   +   +   +   +
                  |           |
          /- --- -0           |
          |       |           |
    +   +   +   +   +   +   +   +
          |       |           |
     [S] -        \- - - -0- [E]
          |           | 
    +   +   +   +   +   +   +   +
          |           | 
          \- --- --- -0
    
    +   +   +   +   +   +   +   +
    
    
    
    |---|---|---|---|---|---|---|

## Enhancements

Derive characteristics from paths
- Distance
- Loop hierarchy
- Junctions

Add features to paths
- Risks
- Gambits
- Rewards
- Tools

[dFCycles](https://mootootwo.github.io/rpgees/omgam2019/dFCycles) by [Luke Miller](https://twitter.com/mootootwo) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).
