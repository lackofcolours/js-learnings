# JS Loops notes

## Task

1. Each letter is printed on a new line.
2. Then the vowels are printed in the same order as they appeared in .
3. Then the consonants are printed in the same order as they appeared in .

### Input
```
javascriptloops
```

### Required output
```
a
a
i
o
o
j
v
s
c
r
p
t
l
p
s
```

## Answers

Using REGEX
```js
function vowelsAndConsonants(s) {
    // REGEX
    const vowels = s.match(/[aeiou]/gi).join('\n');
    const consonants = s.match(/[^aeiou]/gi).join('\n');
    console.log(vowels.concat('\n', consonants));   
}
```

Using for loop twice
```js
function vowelsAndConsonants(s) {  
    // const textArray = s.split("");
    const textArray = [...s]; // ES6 spread operator
    const vowels = "[aeiou]";
    
    // Loop twice with match
    for (let letter of textArray) {
        letter.match(vowels) && console.log(letter);
    }
    
    for (let letter of textArray) {
        !letter.match(vowels) && console.log(letter);
    }
}
```