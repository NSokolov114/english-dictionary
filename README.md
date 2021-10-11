# English Dictionary for building your Hangman game
There are few txt files containing a number of top English words:  
~ [1000 most used English words](/1k-top-english-words.txt) (best for testing)  
~ [5000 most used English words](/5k-top-english-words.txt)  
~ [8000 most used English words](/8k-top-english-words.txt)  
~ [10000 most used English words](/10k-top-english-words.txt) (best for playing)  
~ [13000 most used English words](/13k-top-english-words.txt)  

## Disclaimer
Those are the most used English words. I can't get a credit to the person who did this work of collecting a number of books and articles and sorting them - I downloaded those dictionaries in ~2010 and can't find the source.  
You may find some of these words offensive.  
You may find some remaining duplicates ('color' and 'colour')  
You may find some of these words useless ('aye', 'an') or missing spaces or hyphens ('guineapig' instead of 'guinea pig').
I did my best to clean the dictionaries, but if you're going to use them commercially, make sure to check the words first.  

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
