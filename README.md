[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# JavaScript Array HW

<ol>
  <li>Create a function that will get the sum of the numbers between 1 and n and return the answer
  <br>
    <code>summation(5) // should return 15 because 1+2+3+4+5=15</code>
  </li>
  <li>Create a program to get the sum of all the even numbers in a group
  <br>
    <code > summationEven(5) // should return 6 because 2+4=6</code>
  </li>

  <li>Create a function to get the average of a group of numbers
  <br>
    <code> avg([8, 2, 2, 4]) // should return 4</code>
  </li>
  <li>Create a function to reverse the letters in a word
  <br>
    <code > reverse("caterpillar") // should return "rallipretac"</code>
  </li>
  <li>Create a function that takes an array of words and combines them with a dash
  <br>
    <code > addDashes(['test1', 'test2', 'test3']) // should return "test1-test2-test3"</code>
  </li>
  <li>Function that will count up to a number and back down and return a string of the climb
  <br>
    <code> countUpAndDown(3) // should return "1 2 3 2 1"</code>
  </li>
  <li>Write a function that will tell you all of the words in an array that contain the letter `a`
  <br>
    <code > wordsWithA(['cat', 'rabbit', 'dog', 'frog']) // should return ['cat', 'rabbit']</code>
  </li>
  <li>Write a function that will tell you all of the words in an array that contain a specified letter
  <br>
    <code > wordsWithLetter("g", ['cat', 'rabbit', 'dog', 'frog']) // should return ['dog', 'frog']</code>
  </li>
  <li>Function that returns the longest word in sentence
  <br>
    <code>longestWord("The cat in the house") // should return "house"</code>
  </li>
  <li>Function that returns the largest even number
  <br>
    <code>largestEvenNumber([1,2,3,10,4,7,0]) // should return "10"</code>
  </li>
</ol>

## Extra Practice

Create word guessing game where the user gets infinite tries to guess the word (like Hangman without the hangman, or like Wheel of Fortune without the wheel and fortune).

- Create two global arrays: one to hold the letters of the word (e.g. `['F', 'O', 'X']`), and one to hold the current guessed letters (e.g. it would start with `['_', '_', '_]'` and end with `['F', 'O', 'X']`)`.
- Write a function called guessLetter that will:
  - Take one argument, the guessed letter.
  - Iterate through the word letters and see if the guessed letter is in there.
  - If the guessed letter matches a word letter, changed the guessed letters array to reflect that.
  - When it's done iterating, it should log the current guessed letters ('F__') and congratulate the user if they found a new letter.
  - It should also figure out if there are any more letters that need to be guessed, and if not, it should congratulate the user for winning the game.
  - Pretend you don't know the word, and call guessLetter multiple times with various letters to check that your program works.

```js
// start of the game
const wordLetters     = ['G', 'O', 'A', 'T'];
const guessedLetters  = ['_', '_', '_', '_'];

// playing the game
guessLetter('G'); // "Correct, G _ _ _"
guessLetter('I'); // "Incorrect, G _ _ _"
guessLetter('O'); // "Correct, G O _ _"
guessLetter('A'); // "Correct, G O A _"
guessLetter('L'); // "Incorrect, G O A _"
guessLetter('T'); // "You Win, G O A T"
```
**How To: Make it like Hangman:**
- Keep track of all the guessed letters (right and wrong) and only let the user guess a letter once. If they guess a letter twice, do nothing.
- Keep track of the state of the hangman as a number (starting at 0), and subtract or add to that number every time they make a wrong guess.
- Once the number reaches 6 (a reasonable number of body parts for a hangman), inform the user that they lost and show a hangman on the log.

---

Answers will be  here :

// 1

function summation(n) {
  var sum = 0;
  for (var i = 1; i <= n; i++) {
    sum += i;

  }

  console.log("1");
  return console.log(sum);
}
summation(5);
summation(10);


//2
function summationEven(num){
    let sum=0;
    for(let i=1;i<=num;i++){
        if(!(i%2)){
        sum+=i;}
    }
    return sum;
}

console.log(summationEven(5));
//3
function avg(arr){
    let result=0;
    for(let i=0;i<arr.length;i++){
        result+=arr[i];
    }
    return result=result/arr.length;
}

console.log(avg([8, 2, 2, 4]));

//4
function reverse(word){
let reversedWord="";
for(i=word.length-1;i>=0;i--){
    reversedWord+= word[i]
}
return reversedWord
}

console.log(reverse("caterpillar"));

//5
function addDashes(arr){
    return arr.join('-');
 }

 console.log(addDashes(['test1', 'test2', 'test3']));

//6
function countUpAndDown(num){
    let count=""
    for(let i=1;i<=num;i++){
        count+=i+" "
    }
    for(let i=num-1;i>0;i--){
        count+=i+" "
    }
    return count
 }

 console.log(countUpAndDown(3));
// 7

function wordsWithA(arr){
     newArr=[];
     for(let i=0;i<arr.length;i++){
         arr[i]=arr[i].toLowerCase();
        for(let j=0;j<arr[i].length;j++){
            if(arr[i][j]=="a"){
                newArr.push(arr[i]);
            }
        }
    }
    return newArr;
 }

 console.log(wordsWithA(['cat', 'rabbit', 'dog', 'frog']));
//8
 function wordsWithLetter(letter,arr){
    newArr=[];
    for(let i=0;i<arr.length;i++){
        arr[i]=arr[i].toLowerCase();
       for(let j=0;j<arr[i].length;j++){
           if(arr[i][j]==letter){
               newArr.push(arr[i]);
           }
       }
   }
   return newArr;
}

console.log(wordsWithLetter("g", ['cat', 'rabbit', 'dog', 'frog']));
//9
function longestWord(sentence){
    sentence=sentence.split(" ");
    let longest=sentence[0];
    for(let i=0;i<sentence.length;i++){
        if(sentence[i].length>longest.length){
            longest=sentence[i];
        }
    }
    return longest;
}
console.log(longestWord("The cat in the house"));
// 10 
function largestEvenNumber(arr){
    let largest=Number.NEGATIVE_INFINITY;
    for(let i=0;i<arr.length;i++){
        if(!(arr[i]%2)&&arr[i]>largest){
            largest=arr[i];
        }
    }
    return largest;
}

console.log(largestEvenNumber([1,2,3,10,4,7,0]));
// Extra
const wordLetters = ["G", "O", "A", "T"];
var guessedLetters = ["_", "_", "_", "_"];
function guessLetter(letter) {

  if (wordLetters.includes(letter)) {
    guessedLetters.splice(wordLetters.indexOf(letter),1,letter);

    console.log(guessedLetters);
  } else {


    console.log("Wrong");
  }


}

guessLetter('G'); // "Correct, G _ _ _"
guessLetter('I'); // "Incorrect, G _ _ _"
guessLetter('O'); // "Correct, G O _ _"
guessLetter('A'); // "Correct, G O A _"
guessLetter('L'); // "Incorrect, G O A _"
guessLetter('T'); // "You Win, G O A T"

## Reminder
Your opinion for this homework is very important! Please fill up the following questions when you pull request:
 * on a scale from 1 to 5, how comfortable were you with this assignment?
 * How long did it take?
 * What was a challenge you had with this assignment?
 * Is there anything that you'd like some further information on?
 * Do you have any suggestions to improve this assignment?

## Homework Submission
https://github.com/SEI2-jeddah/General/tree/master/homework_submission
