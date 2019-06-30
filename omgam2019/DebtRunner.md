# DebtRunner

Choose an amount of principal funds `(P)` to borrow, and amortize at a percentage rate `(i)` such that `i=[-10*tanh(0.5*log10(P)-2)+12]`

    Principal    Interest Percentage	
    10           21.0514825364
    100          19.6159415596
    1000         16.6211715726       Payday loan
    10000        12                  Credit card debt
    100000       7.3788284274        Small rural real estate
    1000000      4.38405844044       Urban real estate
    10000000     2.94851746355       Small business investment
    100000000    2.35972419924       Major capital venture

Calculate payment amount per turn `(A)` such that `A=[P*(i+(i/(((1+i)^30)-1)))]` -- remembering that `(i)` is a percentage and thus equal to `[0.01 * the above amortization rate]`

    Principal    Interest Percentage    Payment Amount
    10           21.0514825364          2.111996665
    100          19.6159415596          19.70734366
    1000         16.6211715726          167.8777004
    10000        12                     1241.436576
    100000       7.3788284274           8367.458277
    1000000      4.38405844044          60556.77921
    10000000     2.94851746355          506803.2369
    100000000    2.35972419924          4688851.939

Each turn:

- Collect returns on any investments due this turn
- Make any number of investments totaling a funds value up to your current liquid principal
- Pay the scheduled amount for your loan

Investments pay off at `[Size * ( Duration in turns * 1.1 ) * ( risk  * 0.1)]` where risk is `[( n * 0.5) + (n)dF]` and `n` is any whole number value greater than 0 and less than or equal to the total number of dF that you can find to roll.

    Size     Duration    Risk    Return
    1000     1           0       1100
    1000     5           0       5500
    100000   10          0       1100000
    100000   15          0       1650000
    10000000 5           0       55000000
    10000000 20          0       220000000

`(n)dF` represents a number of Fudge Dice, summing the sides such that `[+]` is `+1`, `[-]` is `-1`, and a blank side is `0`.

    Risk    Sum
    0       [0]
    1       [0.5 + 1dF]
    2       [1 + 2dF]
    3       [1.5 + 3dF]
    4       [2 + 4dF]

An investment made on turn 1 with duration 1 will be paid at the start of turn 2, and so-on

If on any turn a payment is not made in full, add `[1.5 * the missed amount]` to the next turn's payment

Score is total liquid funds after 30 turns, minus any outstanding payments (which might exist due to missed payments)
