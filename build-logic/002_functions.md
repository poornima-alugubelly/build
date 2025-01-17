# Functions

## Easy

1. Given a and b, your function should return the value of a<sup>b</sup>  
**Example:**  
**Input:** `power(2,3)` ––> **Output:** `8`
// solution

```
const power = (a,b) => {

    let result=1
    for(let i=0;i<b;i++){
        result*=a
    }
    return result
}
```

// or

`const power = (a,b) => a**b`
1. Given length of a regular hexagon, your function should return area of the hexagon.  
**Example:**  
**Input:** `areaOfHexagon(10)` ––> **Output:** `259.80`

// solution

`const areaHexagon = side => (3*Math.sqrt(3)/2)*(side**2)`
1. Given a sentence, your functions should return the number of words in the sentence.  
**Example:**  
**Input:** `noOfWords(We are neoGrammers)` ––> **Output:**`3
`
//solution

`const numOfWords = sentnce => sentnce.split().length`
1. Given n numbers, your function should return the minimum of them all. The number of parameters won't be accepted from user.  
**Example:**  
**Input:** `findMin(3,5)` ––> **Output:** `3`  
**Input:** `findMin(3,5,9,1)` ––> **Output:** `1`  
*(Hint: Lookup rest parameters in JavaScript)*

//solution

```
const minNum = (...rest) => {
    let minVal = Number.MAX_SAFE_INTEGER

    for(let num of rest){
        minVal = num<minVal? num: minVal
    }
    return minVal
}
```
//or

`const minNum = (...rest) => Math.min.apply(null,rest)`
//apply passes the array-like DS we give as parameters, null is used here because Math.min doesn't need any context here (which `this` provides

1. Given n numbers, your function should return the maximum of them all. The number of parameters won't be accepted from user.  
**Example:**  
**Input:** `findMax(3,5)` ––> **Output:** `5`  
**Input:** `findMax(3,5,9,1)` ––> **Output:** `9`  
*(Hint: Lookup rest parameters in JavaScript)*

//Solution

```
const maxNum = (...rest) => {
    let maxVal = Number.MIN_SAFE_INTEGER

    for(let num of rest){
        maxVal = num>maxVal? num: maxVal
    }
    return maxVal
}
```
//or

`const maxNum = (...rest) => Math.max.apply(null,rest)`
 
1. Given three angles of a triange, your function should return if it is a scalene, isosceles, equilateral triangle or not a triangle at all.
**Example:**  
**Input:** `typeOfTriangle(30, 60, 90)` ––> **Output:** `Scalene Triangle`

//solution

```
const typeOfTriangle = (a,b,c) => {

    if(a+b+c === 180){
        if(a===b || b===c){
            if(a===b && b===c){
                console.log("It is an equilateral triangle")
            }
            else{
                console.log("It is an isosceles triangle")
            }

        }
        else{
            console.log("It is a scalene triangle")
        }

    }
    else{
        console.log("Not a traingle")
    }
}
```

## Medium

1. Given an array, your function should return the length of the array.  
**Example:**  
**Input:** `arrayLength([1,5,3,7,8])` ––> **Output:** `5`
// Solution
```
const arrLength = arr =>{
    let count=0
    for( const item in arr){
        count++
    }
    return count
}
```
//or
`const arrLength = arr => arr.length`
1. Given an array and an item, your function should return the index at which the item is present.  
**Example:**  
**Input:** `indexOf([1,6,3,5,8,9], 3)` ––> **Output:** `2
//Solution
```
const findIndex = (arr,givenElem) => {
   let index=0
   while(arr[index]!=givenElem){
       index++
   }
   return index
}
```
//or
`const findIndex = (arr,givenElem) => arr.indexOf(givenElem)
`
1. Given an array and two numbers, your function should replace all entries of first number in an array with the second number.  
**Example:**  
**Input:** `replace([1,5,3,5,6,8], 5, 10)` ––> **Output:** `[1,10,3,10,6,8]`
//Solution
```
const replace = (arr,toReplace,replaceWith) => {
    arr = arr.map( element => element===toReplace? replaceWith: element)
    return arr
}
```
//or
```
const replace = (arr,toReplace,replaceWith) => {
    let result=[]
    arr.forEach( element => {
        result.push(element===toReplace? replaceWith: element)
    })
    return result
}
```


1. Given two arrays, your function should return single merged array.  
**Example:**  
**Input:** `mergeArray([1,3,5], [2,4,6])` ––> **Output:** `[1,3,5,2,4,6]`
// Solution
`const merge = (arr1,arr2) => [...arr1,...arr2]`
//or
`const mergeArray = (...args) => {
   return [].concat(...args)
  }
  `
1. Given a string and an index, your function should return the character present at that index in the string.  
**Example:**  
**Input:** `charAt("neoGcamp", 4)` ––> **Output:** `c`
// Solution
`const charAtIndex = (str,index) => str.charAt(index)`
//or
`const charAtIndex = (str,index) => str[index]`
1. Given two dates, your function should return which one comes before the other.  
**Example:**  
**Input:** `minDate('02/05/2021', '24/01/2021')` ––> **Output:** `24/01/2021`

## Advanced

1. Write a function which generates a secret code from a given string, by shifting characters of alphabet by N places.
**Example:**  
**Input:** `encodeString("neogcamp", 2)` ––> **Output:** `pgqiecor`  
Explanation: 2 represents shifting alphabets by 2 places. a –> c, b –> d, c –> e and so on.
1. Given a sentence, return a sentence with first letter of all words as capital.  
**Example:**  
**Input:** `toSentenceCase('we are neoGrammers')` ––> **Output:** `We Are NeoGrammers`
1. Given an array of numbers, your function should return an array in the ascending order.  
**Example:**  
**Input:** `sortArray([100,83,32,9,45,61])` ––> **Output:** `[9,32,45,61,83,100]`
1. Given a sentence, your function should reverse the order of characters in each word, keeping same sequence of words.  
**Example:**  
**Input:** `reverseCharactersOfWord('we are neoGrammers')` –––> **Output:** `ew era sremmarGoen`
