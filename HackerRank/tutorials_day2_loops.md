# JS Loops notes

## Task

1. Each alphabet is printed on a new line.
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
    
    for (let alphabet of textArray) {
        alphabet.match(vowels) && console.log(alphabet);
    }
    
    for (let alphabet of textArray) {
        !alphabet.match(vowels) && console.log(alphabet);
    }
}
```

Using for loop once
```js
function vowelsAndConsonants(s) {
    const vowels = 'aeiou';
    let consonants = ''; // Not declaring this a string result in undefined answer
    
    // Assign spacing to consonants via \n
    // Since console.log for vowels is a part of for loop, but not consonants
    for (let alphabet of s) {
        vowels.includes(alphabet) ? console.log(alphabet) : consonants += alphabet + '\n';
    }
    
    // Trim out final empty space instroduced by `\n`
    console.log(consonants.trim());
}
```

TODO: Tried using ES6 filter, but as it's built more for intrinsic `return`, not sure how to get it working properly in `console.log`.