## Odd or Even?

### Task:
```Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

Examples:
Input: [0]
Output: "even"

Input: [0, 1, 4]
Output: "odd"

Input: [0, -1, -5]
Output: "even"
Have fun!
```

#### The Solution


```php
// SOLUTION 1
// function odd_or_even(array $a): string {
//   $summed = 0;
//   foreach($a as $b) {
//     $summed += $b;
//   }
//   return $summed % 2 == 0 ? "even" : "odd";
// }

// SOLUTION 2
// function odd_or_even(array $a): string {
//   $summed = array_reduce($a, function($accumulator, $current){
//     return $accumulator += $current;
//   });
//   return $summed % 2 == 0 ? "even" : "odd";
// }

// SOLUTION 3
function odd_or_even(array $a): string {
  $summed = array_sum($a);
  return $summed % 2 == 0 ? "even" : "odd";
}
```