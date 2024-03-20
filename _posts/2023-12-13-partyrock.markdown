---
layout: post
title:  "PartyRock, and why AI is not ready yet to replace coders"
date:   2023-12-13 11:33:00 -0500
categories:
  - Coding
  - AI
tags: coding skills PHP PartyRock AI
image:
  thumbnail: /assets/images/partyrock.jpg
  name: "artistic AI-generated representation of AWS' PartyRock"
images:
  - path: /assets/images/partyrock.jpg
    name: "artistic AI-generated representation of AWS' PartyRock"
    caption: "artistic AI-generated representation of AWS' PartyRock"
---
Using #PartyRock, the new app generator from Amazon.com, I tried to "create an app that would show the best algorithm in PHP to solve a specific problem, and the syntax of the PHP functions used".

PartyRock in no time generated me a simple app, and then I submitted to the app the following problem to the app: "given a string of alphabetic characters and symbols, I want to reverse the alphabetic characters but keep the symbols at the same place". I found that problem in a javascript coding test recently, and was wondering the best way to do something similar in PHP.

This is what PartyRock offered for the algorithm part:

<hr/>

"Here is one way to reverse the alphabetic characters while keeping the symbols in place in PHP:
```php
function reverseAlpha($str) {
 preg_match_all('/\w+|\W+/', $str, $matches);

 $result = '';
 foreach ($matches[0] as $part) {
  if (ctype_alpha($part)) {
   $result .= strrev($part); 
  } else {
   $result .= $part;
  }
 }

 return $result;
}

$str = 'abc123$%^xyz';
echo reverseAlpha($str); // 'zyx123$%^cba'
```

The key steps are:

1. Use preg_match_all() to split the string into an array of alphabetic and non-alphabetic parts.

2. Loop through the parts array.

3. For alphabetic parts, reverse using strrev().

4. For non-alphabetic parts, append as-is.

5. Join the reversed alphabetic and unchanged non-alphabetic parts back into a string.

This allows us to reverse only the alphabetic characters while preserving the symbols in their original positions."

<hr/>

Sounded great, but running it, it just doesn't give the expected output "zyx123$%^cba", but rather "abc123$%^zyx"

The main reason is, instead of grouping by letters, the code grouped by words and non-words: w+ and W+ in the regular expression syntax, rather than by letters, so then it reversed the the letters inside the groups. Second issue is, the "w" character class considers numbers can be part of a word, but the ctype_alpha function checks every character is alphabetic, not alphanumeric, so the first group (abc123) is not even reversed, which would still fail to solve the problem...

In the PHP Syntax part, where I was expecting to see the syntax of functions like preg_match, strrev, etc... that were used in the result code, PartyRock instead gave me ANOTHER way to do it (not sure why... maybe some misunderstanding here), calling it "PHP Syntax".

<hr/>

"Here is a sample PHP code to reverse the alphabetic characters while keeping the symbols in place:

```php
function reverseAlpha($str) {

 // Split string into an array of characters
 $chars = str_split($str);

 // Reverse the alphabetic characters
 $alphaChars = preg_replace('/\W/', '', $str); 
 $revAlphaChars = strrev($alphaChars);

 // Map original string to reversed alpha chars
 $map = str_split($revAlphaChars);
 $result = '';
 foreach ($chars as $char) {
  if (ctype_alpha($char)) {
   $result .= array_shift($map); 
  } else {
   $result .= $char;
  }
 }

 return $result;

}

$str = 'abc123$%^xyz';
echo reverseAlpha($str); // 'zyx123$%^cba'
```

The key steps are:

1. Split the string into an array of characters.

2. Reverse only the alphabetic characters.

3. Map the original string to the reversed alphabetic characters.

4. Build the result string by taking either the reversed alphabetic char or the original symbol.

This reverses the alphabetic characters while keeping the symbols in their original order."
<hr/>

Again, sounded promising, but this time the result shown was "zyx123$%^321", instead of the expected "zyx123$%^cba".

Looking at the code, it seems it started the way I had myself started the javascript version, by reversing just the alphabetical
characters first. Yet, AI does it wrong because, once more, it considers numeric characters as alphabetical, keeping
the numbers in its supposed alphabetical only chain (it removes any non alphanumeric character using \W in a regular
expression). Then it reverses any purely aphabetical character in it and, thanks to ctype_alpha, rescans the initial
chain and replaces with its assumedly reversed chain... which starts fine, but ends badly due to the mistake made earlier.

So, AI failed in both examples, not by the lack of knowledge (both algorithms were smart, but badly executed).

## These would be my fixes in both cases:

case 1: actually, reversing characters in each set doesn't make much sense, since the number of characters per set may differ,
e.g. if you submit ab123cde (result: ed123cba), then you'd get ab-123-cde, which when reversed would give ba-123-edc, but
reversing the order of the alphabetic sets would give edc-123-ba, which would be wrong. I think this method is not
really going anywhere.

case 2:
1. split into characters
2. select alphabetic characters only and reverse them
3. replace each alphabetic character from initial string by next one in the reversed string, keep others unchanged.

```
function reverseAlpha($str) {

    // Split string into an array of characters
    $chars = str_split($str);

    // Reverse the alphabetic characters
    $alphaChars = preg_replace('/[[:^alpha:]]/', '', $str);
    $revAlphaChars = strrev($alphaChars);

    // Map original string to reversed alpha chars
    $map = str_split($revAlphaChars);
    $result = '';
    foreach ($chars as $char) {
        if (ctype_alpha($char)) {
            $result .= array_shift($map);
        } else {
            $result .= $char;
        }
    }

    return $result;

}

$str = 'ab123$%^xyz';
echo reverseAlpha($str); // 'zy123$%^xba'
```
Note that I changed the example to have a group of 2 alphabetic characters and a group of 3 to be sure things work
as expected. And voilà! It worked.

## Summary of it all

AI can get good ideas for an algorithm, but that's not necessary the case, yet the execution
seems to be failing for some reason. I have a feeling that the failure of the overall process is related to the
existence of steps in the generation, rather than an overall flow. E.g.:
1. figure an algorithm
2. convert the algorithm to text
3. convert the algorithm to code

Each of the steps above can go slightly wrong, but if they do, then the result can go fairly wrong (exponentially 
growing the level of error).

So, having AI code for me? Well, not without control, tests and fixes...
Have a nice day!

