# javascript-warm-ups  
Just a collection of some JavaScript exercises.  :) Enjoy and let's add more!  


# Array Problems!  

### Average of Numbers in an Array  
```  
function averageArray (arr) {  
    var sum = 0  
    for (var i = 0; i < arr.length; i++) {  
        sum = sum + arr[i]  
    }  
    return (sum/arr.length)  
}  

//  Using the reduce method  
const average2 = function(arr) {  
    //  reduce creates a new function that take the accumulator and   
    //  loops through starting at the position 0.  
  var sum = arr.reduce(function(acc, n) {  
    return acc + n;  
  }, 0);  
  return sum / arr.length;  
}  


console.log(averageArray([4, 10, 35, 8, 15, 40]))
```  

### Array contains an item  
```
const arrayHasItem = (arr, x) => {  
    if (arr.includes(x)) {  
        return true  
    } else {return false}  
}  

const arrayHasItem2 = (array, y) => {  
    for (let i = 0; i < array.length; i++) {  
        if (array[i] === y) {  
            return true  
        }  
    }   
    return false  
}  

console.log(arrayHasItem([1,2,3],  1))  
console.log(arrayHasItem([1,2,3],  4))  
console.log(arrayHasItem(['code', 'dev', 'nerd'], 'nerd'))  
console.log(arrayHasItem(['code', 'dev', 'nerd'], 'genius'))  
console.log("---------")  
console.log(arrayHasItem2([1,2,3],  1))  
console.log(arrayHasItem2([1,2,3],  4))  
console.log(arrayHasItem2(['code', 'dev', 'nerd'], 'nerd'))  
console.log(arrayHasItem2(['code', 'dev', 'nerd'], 'genius'))  
```

### Remove duplicates from an array  
```
function arr(x) {  
    var newArr = [];  
    for (let i = 0; i < x.length; i++) {  
        x.forEach( integer => {  
           if (!newArr.includes(integer)) {  
               newArr.push(integer);  
           }  
        })  
    }  
    return newArr;  
}  

console.log(arr([1,2,2,3]));  
console.log(arr([4,5,4,4,7,5]));  
console.log(arr([1,2,3,5]));  
```

###  Doubling each elemtn in the array  
```
const doubleArr = (arr) => arr.map(ele => ele*2);  

console.log(doubleArr([1,2,3]))  
console.log(doubleArr([-1,-2,-3]))  
```

### Example of ES6 filter  
```
const userName = ["mark","marcusaurelius","Dimitri", "DimitriNakos"]  
const validUserNames = () => {  
return userName.filter(x => x.length < 10)  
}  

console.log(validUserNames(userName))  
```

### Repeating Integer  
```  
function repeatInt(x) {
    for (var i = 0; i < x.length; i++) {
        if (x[i] === x[x.length - i]) {
            console.log(x[i])
            break;
        }
    }
}
```  

### ES6 Includes  
```  
const ifIncludes = (arr, fn) => {  
    let newArr = []  
for (let i = 0; i< arr.length; i++){  
    if(fn(arr[i])) {  
        newArr.push(arr[i])  
    }  
}  
if (newArr !== []) {  
    return newArr  
}  
return false  
}  


console.log(ifIncludes([1,2,3], function(num){return num === 2}))  
console.log(ifIncludes([1,2,3,4,5,6], function(num){return num % 2 === 0}))  
console.log(ifIncludes([1,2,3,4,5,6], function(num){return num > 3}))  
```  

### Callback example  
```  
function callBackUse(arr, fn) {
    return arr.map( ele => fn(ele))
}

console.log(callBackUse([1,2,3], function(num){return num * 2}))
console.log(callBackUse([1,2,3], function(num){return num + 1}))
console.log(callBackUse([1,2,3], function(num) {return num /2}))
console.log(callBackUse([1,2,3], function(num) {return num - 2}))
```  

### Check an integer  
```  
function isInteger(int) {  
    if (typeof int === "number" && int % 1 === 0) {  
        return true  
    } else {return false}  
}  
```  

### Diagonal array  
```  
function diagonalDifference(arr) {  
    let result = 0;  
    let upperLeft = 0   
    let bottomRight = 0  
    for (let i = 0; i < arr.length; i++) {  
        upperLeft += arr[i][i]  
    }  
    for (let k = arr.length - 1, l = 0; k >= 0; k--, l++) {  
        bottomRight += arr[k][l]  
    }  
    return Math.abs(upperLeft - bottomRight)  
}  
```  
### Min/Max in an Array  
```  
function minMaxSum(arr) {  
    
// find the greatest number in the array  
    var max = Math.max(...arr);  
// filter everything out of the array that isn't the largest number  
    var arrMin = arr.filter(e => e != max);  
// find the lowest number in the array  
    var min = Math.min(...arr);  
// filter everything out of the array that isn't the largest number      
    var arrMax = arr.filter(e => e != min);  

console.log(arrMin.reduce((a,b) => a+b, 0)+" "+arrMax.reduce((a,b) => a+b, 0))  
}
```  

# Strings  

### Count how many vowels are in a string   
```
function howMany(x) {  
    var numberOfVowels = 0  
    var vowels = ["a","e","i","o","u",]  
    var x = x.toLowerCase();  
    var splitUp = x.split("")  

    for (var i = 0; i < vowels.length; i++) {  
        for (var j = 0; j < splitUp.length; j++) {  
            if (vowels[i] == splitUp[j]) {  
                numberOfVowels++  
           }  
         }  
       }  
   return numberOfVowels;  
}  

var countVowels = function(str) {  
    var count = 0;  
    var input = str.toLowerCase();  
    for (var i = 0; i < input.length; i++) {  
        if (  
            input[i] === "a" ||  
            input[i] === "e" ||  
            input[i] === "i" ||  
            input[i] === "o" ||  
            input[i] === "u"  
        ) {  
            count++;  
        }  
    }  
    return count  
}  

var vowelCounter = function(str) {  
    var count = 0;  
    var input = str.toLowerCase();  
    var vowelArr = ["a","e","i","o","u"];  
    for (var i = 0; i < input.length; i++) {  
        if (vowelArr.includes(input[i])) {  
            count++  
        }  
    }  
    return count  
}  
```

### Pangram Checker  
```  
function isPangram(str) {  
    var pangram = ["a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z"]  
    str = str.toLowerCase()  
    for (var i = 0; i < pangram.length; i++) {  
        if (!str.includes(pangram[i])){  
            return false;  
        }   
    }  
     return true  
}  

var isPangram = function (str) {  
  var alphabet = "abcdefghijklmnopqrstuvwxyz";  
  var sentence = str.toLowerCase();  
  for (var character of alphabet) {  
    if (!sentence.includes(character)) {  
      return false;  
    }  
  }  
  return true;  
}  




console.log(isPangram("Watch Jeopardy, Alex Trebek's fun TV quiz game"))  
console.log(isPangram("Five hexing wizard bots jump quickly"))  
console.log(isPangram("JavaScript is the best"))  
```    

### Random # Generator  
```  
// 0-x  
function randoGen(x) {  
    return Math.floor(Math.random() * x)  
}  

//1-x  
function randoGen(x) {  
    return Math.floor(Math.random() * x + 1)  
}  
```  

### Reverse Numbers  
```  
function reverseNumbers(x) {  
    let arr = []  
    let string = x.toString().split("");  
    string.forEach(ele => arr.push(ele));  
    let newArr = arr.reverse().join("");  
    return parseInt(newArr)  
}  

console.log(reverseNumbers(1234))  
console.log(reverseNumbers(1201))  
console.log(reverseNumbers(4))  
```  

### Capitalize every word  
```  
const capitalize = function (str) {  
    var wordsArr = str.split(" ");  
    var newStr = ""  
    for (let i = 0; i < wordsArr.length; i++) {  
        wordsArr[i] = wordsArr[i][0].toUpperCase() + wordsArr[i].substr(1);  
        wordsArr.toString();  

        newStr += wordsArr[i] + " ";  
    }  
    return newStr.slice(0, -1)  
};  
```  

### Check password while statement  
```  
const validPassword = (string) => {  
    
    while (string.length >= 8 && /[a-z]/.test(string) && /[A-Z]/.test(string)) {  
            return true  
    }  
    return false  
}  

console.log(validPassword("RexTheDog"))  
console.log(validPassword("rexthedog"))  
console.log(validPassword("REXTHEDOG"))  
console.log(validPassword("Dog"))  
```  

### Reverse a String  
```  
function reverseStr(str) {  
    var strBack = str.split("").reverse().join("");  
    console.log(strBack);  
}  
```  

### First Char to not repeat
```  
// Write a function that takes in a string and outputs the *first* occurrence of a character that does not repeat itself in that string.  
// Input: "the quick brown fox jumps over the calm kitten quietly"  
// Output: "b"  
// Input: "this hat is the greatest!"  
// Output: "g"  
// Input: "what a wonderful day it has been!"  
// Output: "o"  
function charNoRepeat(str) {  
    var charCount = {};  

    for (var i = 0; 0 < str.length; i++) {  

        if (charCount[str[i]]) {  

            charCount[str[i]]++;  

        } else {  

            charCount[char] = 1;  
        }  
    }  

    for (var j in charCount) {  
        if (charCount[j] === 1) {  
            return charCount[j]  
        }  
    }  
}  
/////////////////////////////////////////////////////////////  

function firstNonRepeat(str) {  
    for (var i = 0; i < str.length; i++) {  
        var c = str.charAt(i);  
        if (str.indexOf(c) === i && str.indexOf(c, i + 1) === -1) {  
            return c  
        }  
    }  
}  
```  

### Palindrome true or false  
```  
const isPalindrome = function (str) {  
    var strBack = str.split("").reverse().join("");  
    if (strBack === str) {  
        return true  
    } else { return false }  
};  
```  

### Sum of Odd Numbers Triangle
## Given the triangle of consecutive odd numbers:
             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29

Calculate the row sums of this triangle from the row index (starting at index 1) e.g.:

```
rowSumOddNumbers(1); // 1
rowSumOddNumbers(2); // 3 + 5 = 8

```

```
function rowSumOddNumbers(n) {
	let rEnd = 1;
  let rStart = 1;
  let accEnd = 4;
  let accStart = 2;
  let sum = 0;
  
  if (n == 1) {
    return 1
  }
  
  for (let i = 1; i < n; i++) {
    rEnd+=accEnd;
    accEnd+=2;
    rStart+=accStart;
    accStart+=2
  }
  
  for (let i = rStart; i <= rEnd; i+=2) {
    sum+=i
  }
    return sum
}
```









