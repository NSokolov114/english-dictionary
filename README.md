# English Dictionary for building your Hangman game
There are few txt files containing a number of top English words:  
~ 1000 most used English words  
~ 8000 most used English words  


## How to use the Dictionary (JavaScript)

### Generate the array from the dictionary string:
  
```JavaScript
const tmp = 'copy-paste all the words from the txt file';
const dictionary = tmp.split(', ');  // ['ABLE', 'ABOUT', 'ABOVE', ...]
```

### Get a random word from your dictionary:

```JavaScript
function getRandomWord() {
  return dictionary[Math.floor(Math.random() * dictionary.length)];
}
let word = getRandomWord();
console.log(word);  // HELLO
```

### You may set the minimal length of the random word (it's hard to guess a really short word):

```Javascript
const minLength = 4;
let longerWord = '';
let counter = 0;

// run the cycle until we find a word that meets the requirements:
while (longerWord.length < minLength) { 
  longerWord = getRandomWord();
  counter++;
  if (counter > 1000) {  
    console.log('Failed to find a long enough word!')
    break;               // without this line in case you set a really high,
  }                      // you'll get into the infinite loop
}
console.log(longerWord);
```

You can use this code sample to also set a maximum length, or generate a word with fixed length:

```Javascript
const maxLength = 8;
while (longerWord.length < minLength || longerWord.length > maxLength) {...};

const fixedLength = 6;
while (longerWord.length !== fixedLength) {...};
```
