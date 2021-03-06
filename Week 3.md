<p align=center>WEEK 3

## Monday

**1. You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.**

**Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples:**

```
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```

**Solution:**

```javascript
function likes(names) {
  let length = names.length;
  let likesPost;
  if (length == 0) likesPost = "no one likes this";
  if (length == 1) likesPost = `${names[0]} likes this`;
  if (length > 1) {
    if (length == 2) {
      likesPost = `${names[0]} and ${names[1]} like this`;
    } else if (length == 3) {
      likesPost = `${names[0]}, ${names[1]} and ${names[2]} like this`;
    } else {
      let rest = length - 2;
      likesPost = `${names[0]}, ${names[1]} and ${rest} others like this`;
    }
  }

  return likesPost;
}
```

<hr>
<br>

**2. Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.**

**Example: The binary representation of 1234 is 10011010010, so the function should return 5 in this case**

<br>

**Solution :**

```javascript
var countBits = function(n) {
  let counter = 0ñ

  Array.from(n.toString(2)).forEach(function(bit){
    if(bit == 1) counter++;
  })

    return counter
};

```

<hr>
<br>

**3. In this kata you have to write a simple Morse code decoder. While the Morse code is now mostly superseded by voice and digital data communication channels, it still has its use in some applications around the world.**

**The Morse code encodes every character as a sequence of "dots" and "dashes". For example, the letter A is coded as ·−, letter Q is coded as −−·−, and digit 1 is coded as ·−−−−. The Morse code is case-insensitive, traditionally capital letters are used. When the message is written in Morse code, a single space is used to separate the character codes and 3 spaces are used to separate words. For example, the message HEY JUDE in Morse code is** `···· · −·−− ·−−− ··− −·· ·.`

<br>

**Solution :**

```javascript
decodeMorse = function (morseCode) {
  let string = "";
  let counterWords = 1;
  let arrayWords = morseCode.trim().split("   ");

  arrayWords.forEach((word) => {
    let letters = word.split(" ");

    letters.forEach((letter) => {
      string += MORSE_CODE[letter];
    });

    if (counterWords != arrayWords.length) {
      string += " ";
    }

    counterWords++;
  });

  return string;
};
```

<br>
<hr>
<br>

## Tuesday

**1. Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.**

**Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).**

**If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.**

**Examples:**

```
"is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"
""  -->  ""
```

**Solution:**

```javascript
function order(words) {
  let expresion = /\d/;
  let inOrderWords = [];

  words.split(" ").forEach((word) => {
    let numOrder = parseInt(word.match(expresion));
    inOrderWords[numOrder - 1] = word;
  });

  return inOrderWords.join(" ");
}
```

<hr>
<br>

**2. Count the number of Duplicates, write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string**

**The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.**

**Examples:**

```
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabBcde" -> 2 # 'a' occurs twice and 'b' twice (`b` and `B`)
"indivisibility" -> 1 # 'i' occurs six times
"Indivisibilities" -> 2 # 'i' occurs seven times and 's' occurs twice
"aA11" -> 2 # 'a' and '1'
"ABBA" -> 2 # 'A' and 'B' each occur twice
```

**Solution:**

```javascript
function duplicateCount(text) {
  let arrayfromText = text.toLowerCase().split("").sort();
  let arrayResult = {};
  let counter = 0;

  arrayfromText.forEach((letter) => {
    if (arrayResult[letter] == undefined) {
      arrayResult[letter] = 1;
    } else {
      arrayResult[letter] = arrayResult[letter] += 1;
    }
  });

  for (const key in arrayResult) {
    if (arrayResult[key] != 1) counter++;
  }

  return counter;
}
```

<hr>
<br>

**3. Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.**

**Exampels:**

```
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !
```

**Solution:**

```javascript
function pigIt(str) {
  let regex = /[.!?\\-]/;

  let pigIt = str.split(" ").map((word) => {
    let newWord = "";
    if (word.match(regex) == null) {
      newWord = `${word.substring(1, word.length)}${word[0]}ay`;
      return newWord;
    }
    return word;
  });

  return pigIt.join(" ");
}
```

<br>
<hr>
<br>

## Wednesday

**1. Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return true if the string is valid, and false if it's invalid.**

**Examples:**

```
"()"              =>  true
")(()))"          =>  false
"("               =>  false
"(())((()())())"  =>  true
```

**Solution:**

```javascript
function validParentheses(parens) {
  let validator = 0;
  let valid = true;
  let arrayParents = parens.split("");
  let length = arrayParents.length - 1;

  arrayParents.forEach((paren) => {
    if (validator < 0) {
      valid = false;
    }
    paren == "(" ? validator++ : validator--;
  });

  if (validator != 0 || arrayParents[0] == ")" || arrayParents[length] == "(")
    valid = false;

  return valid;
}
```

<hr>
<br>

**2. Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).**

**Examples:**

```
"the-stealth-warrior" gets converted to "theStealthWarrior"
"The_Stealth_Warrior" gets converted to "TheStealthWarrior"
```

**Solution:**

```javascript
function toCamelCase(str) {
  let arrayWords = str.split(/[-_]/);
  let WordsCompelte = arrayWords[0];

  for (let i = 1; i < arrayWords.length; i++) {
    let word = arrayWords[i];
    WordsCompelte += `${word[0].toUpperCase()}${word.substring(
      1,
      word.length
    )}`;
  }
  return WordsCompelte;
}
```

<hr>
<br>

**3. Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.**

**Examples:**

```
uniqueInOrder('AAAABBBCCDAABBB') == ['A', 'B', 'C', 'D', 'A', 'B']
uniqueInOrder('ABBCcAD')         == ['A', 'B', 'C', 'c', 'A', 'D']
uniqueInOrder([1,2,2,3,3])       == [1,2,3]
```

**Solution:**

```javascript
var uniqueInOrder = function (iterable) {
  let arrayIterable = Array.from(iterable);
  let result = [];

  for (let i = 0, length = arrayIterable.length; i < length; i++) {
    if (arrayIterable[i] != arrayIterable[i + 1]) {
      result.push(arrayIterable[i]);
    }
  }

  return result;
};
```

<br>
<hr>
<br>

## Thursday

**1. In this kata you have to write a method that folds a given array of integers by the middle x-times.**

**Example:**

```
Fold 1-times:
[1,2,3,4,5] -> [6,6,3]

A little visualization (NOT for the algorithm but for the idea of folding):

 Step 1         Step 2        Step 3       Step 4       Step5
                     5/           5|         5\
                    4/            4|          4\
1 2 3 4 5      1 2 3/         1 2 3|       1 2 3\       6 6 3
----*----      ----*          ----*        ----*        ----*

Fold 2-times:
[1,2,3,4,5] -> [9,6]
```

<br>

**Solution:**

```javascript
function foldArray(array, runs) {
  let counterRuns = 0;
  let arrayPrimary = [...array];
  let result = [];
  while (counterRuns != runs) {
    result = arrayPrimary.map((value, index, arr) => {
      if (index != arr.length - 1) {
        value += arr[arr.length - 1];
      }
      arr.pop();
      return value;
    });
    arrayPrimary = result.filter((num) => num != undefined);
    counterRuns++;
  }
  return result.filter((num) => num != undefined);
}
```

<hr>
<br>

**2. Encrypt this!**

**You want to create secret messages which can be deciphered by the Decipher this! kata. Here are the conditions:**

**2.1 Your message is a string containing space separated words.**

**2.2 You need to encrypt each word in the message using the following rules:**

**2.3 The first letter must be converted to its ASCII code.**

**2.4 The second letter must be switched with the last letter**

**2.5 Keepin' it simple: There are no special characters in the input.**

**Example:**

```
encryptThis("Hello") === "72olle"
encryptThis("good") === "103doo"
encryptThis("hello world") === "104olle 119drlo"
```

<br>

**Solution:**

```javascript
var encryptThis = function (text) {
  return text
    .split(" ")
    .reduce((pre, curr) => {
      let letra = curr[1];
      let letra2 = curr[curr.length - 1];
      console.log(letra);
      let regex = new RegExp(`(${letra})\\D*(${letra2})`);
      console.log(regex);
      return `${pre} ${curr[0].charCodeAt(0)}${curr
        .slice(1)
        .replace(regex, `$2${curr.slice(2, curr.length - 1)}$1`)}`;
    }, "")
    .trim();
};
```

<hr>

**3. Return: a string formatted as a list of names separated by commas except for the last two names, which should be separated by an ampersand.**

**Examples :**

```
list([ {name: 'Bart'}, {name: 'Lisa'}, {name: 'Maggie'} ])
// returns 'Bart, Lisa & Maggie'

list([ {name: 'Bart'}, {name: 'Lisa'} ])
// returns 'Bart & Lisa'

list([ {name: 'Bart'} ])
// returns 'Bart'

list([])
// returns ''
```

**Solution :**

```javascript
function list(names) {
  return names
    .reduce((prev, curr, index, array) => {
      return `${prev}${index != array.length - 1 ? ", " : " & "}${curr.name}`;
    }, "")
    .trim()
    .slice(2);
}
```

<br>
<hr>
<br>
