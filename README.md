# English Dictionary for building your Hangman game
Choose the dictionary based on your requirements:  
~ [1000 most used English words](/1k-top-english-words.txt) (for quick tests)  
~ [5000 most used English words](/5k-top-english-words.txt)  
~ [8000 most used English words](/8k-top-english-words.txt)  
~ [10000 most used English words](/10k-top-english-words.txt)  
~ [13000 most used English words](/13k-top-english-words.txt)  

## Disclaimer
Those are the most used English words. I downloaded the 13k dictionary back in 2010 and can't find the source. I remember the author saying that they merged a number of books, web articles and posts on forums into one big text file and sorted all the words.  
I did my best to clean the dictionaries, but make sure to check the words first.  
You may find some of these words offensive (I removed only the words I know).  
You may find some remaining duplicates ('color' and 'colour')  
You may find some of these words useless ('aye', 'an') or missing spaces or hyphens ('guineapig' instead of 'guinea pig').

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
const minLength = 6;
let longerWord = '';
let counter = 0;

// run the cycle until we find a word that meets the requirements:
while (longerWord.length < minLength) { 
  longerWord = getRandomWord();
  counter++;
  if (counter > 1000) {  
    console.log('Failed to find a long enough word!');
    break;               // prevents getting into the infinite loop
  }                      // if conditions you've set are too strict 
}
console.log(longerWord); // COOKIE
```

You can use this code sample to also set a maximum length, or generate a word with fixed length:

```Javascript
const maxLength = 8;
while (longerWord.length < minLength || longerWord.length > maxLength) {...};

const fixedLength = 6;
while (longerWord.length !== fixedLength) {...};
```

## Examples of using the dictionary
[Console Hangman (Python)](https://github.com/NSokolov114/Hangman_Python)
