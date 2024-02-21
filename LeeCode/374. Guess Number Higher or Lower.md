## Description
We are playing the Guess Game. The game is as follows:

I pick a number from `1` to `n`. You have to guess which number I picked.

Every time you guess wrong, I will tell you whether the number I picked is higher or lower than your guess.

You call a pre-defined API `int guess(int num)`, which returns three possible results:

- `-1`: Your guess is higher than the number I picked (i.e. `num > pick`).
- `1`: Your guess is lower than the number I picked (i.e. `num < pick`).
- `0`: your guess is equal to the number I picked (i.e. `num == pick`).

Return _the number that I picked_.

## Intuition  

This problem requires me to find the guess number, I can have the feedback whenever I guess the number. Then, I can adjust my number based on the feedback. 

The condition is 1 to n, which reminds me of the ordered array. If we want to search things in an ordered array. We choose binary search.

In order to convert this idea into solution, I summarised :

1. The search range is (1, n)
2. Determine the direction by the feedback of  API
## Approach



## Complexity

## Code