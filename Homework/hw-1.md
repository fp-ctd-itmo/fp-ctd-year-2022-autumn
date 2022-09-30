
Homework #1
===========

[Classroom](https://classroom.github.com/a/_R0WPtzC)

Task 1
------

1. Create a module named `HW1.T1` and define the following data type in it:

   ```
   data Day = Monday | Tuesday | ... | Sunday
   ```

   (Obviously, fill in the `...` with the rest of the week days).

   Do not derive `Enum` for `Day`, as the derived `toEnum` is partial:

   ```
   ghci> toEnum 42 :: Day
   *** Exception: toEnum{Day}: tag (42) is outside of enumeration's range (0,6)
   ```

2. Implement the following functions:

   ```
   -- | Returns the day that follows the day of the week given as input.
   nextDay :: Day -> Day

   -- | Returns the day of the week after a given number of days has passed.
   afterDays :: Natural -> Day -> Day

   -- | Checks if the day is on the weekend.
   isWeekend :: Day -> Bool

   -- | Computes the number of days until Friday.
   daysToParty :: Day -> Natural
   ```

   In `daysToParty`, if it is already `Friday`, the party can start
   immediately, we don't have to wait for the next week (i.e. return `0` rather than `7`).

   <small>Good job if you spotted that this task is a perfect fit for modular
   arithmetic, but that is not the point of the exercise. The functions must
   be implemented by operating on `Day` values directly, without conversion to
   a numeric representation. </small>

