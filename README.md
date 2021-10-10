# english-dictionary
1000, 8000 top English words in a txt file - for building your word games


## How to use the Dictionary (JavaScript)

### Generate the array from the dictionary string:
  
```JavaScript
const tmp = 'copy-paste all the words from the txt file';  
const dictionary = tmp.split(', ');  // ['ABLE', 'ABOUT', 'ABOVE', ...]  
```

### Get a random word from your dictionary
```JavaScript
function getRandomWord() {  
  return dictionary[Math.floor(Math.random() * dictionary.length)]  
}  
let word = getRandomWord();  
console.log(word);  // HELLO
```
