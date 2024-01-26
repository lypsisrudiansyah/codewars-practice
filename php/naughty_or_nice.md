### DESCRIPTION:

In this kata, you will write a function that receives an array of string and returns a string that is either `'naughty'` or `'nice'`. Strings that start with the letters `b`, `f`, or `k` are `naughty`. Strings that start with the letters `g`, `s`, or `n` are `nice`. Other strings are neither naughty nor nice.

If there is an equal amount of bad and good actions, return `'naughty'`

Examples:

```php
$bad_actions = ["broke someone's window", "fought over a toaster", "killed a bug"];
what_list_am_i_on($bad_actions); // => "naughty"
$good_actions = ["got someone a new car", "saved a man from drowning", "never got into a fight"];
what_list_am_i_on($good_actions); // => "nice"
$actions = ["broke a vending machine", "never got into a fight", "tied someone's shoes"];
what_list_am_i_on($actions); // => "naughty"
```



My Solution :

```php
function what_list_am_i_on(array $actions): string {
  $naughtyCount = 0;
  $niceCount = 0;
  $checkerNaughty = ['b', 'f', 'k'];
  $checkerNice = ['g','s','n'];

  foreach($actions as $action) {
    if (in_array($action[0], $checkerNaughty)) {
      $naughtyCount++;
    } else if(in_array($action[0], $checkerNice)) {
      $niceCount++;
    }
  }

  return $naughtyCount >= $niceCount ? "naughty" : "nice";
}
```

Other Idea Solution :

```php
function what_list_am_i_on(array $actions): string {
  $res = array_reduce($actions, function(array $carry, $cur){
    if (strpos('bfk', $cur[0]) !== false) {
      $carry[0] += 1;
    }
    if (strpos('gsn', $cur[0]) !== false) {
      $carry[1] += 1;
    }
    return $carry;
  }, [0, 0]);

  return $res[0] >= $res[1] ? 'naughty' : 'nice';
}

```

Source : https://www.codewars.com/kata/585eaef9851516fcae00004d
