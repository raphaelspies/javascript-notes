# Javacript Basics

1. Use curly braces and semicolons to delineate paragraphs and lines
2. Declare variables using "var"  

<h><b>Data types:</b></h>  

1. <b>Number:</b> float, int, +Infinity, -Infinity (all same data type)
2. <b>Bool:</b> True, False
3. <b>String:</b> "words" (can be called as an array to return the character at that index)

<h><b>Parameters vs. arguments:</b></h>  

1. Parameter: When defining a function `function addTwo(parameters)`  
2. Argument: When calling a function `var callFunction = addTwo(arguments)`

```javascript
function addTwo(parameters) { //define function with parameters
return 0;
}
var callFunction = addTwo(arguments); //call function using arguments
```

# Scope: Global vs. Local
<b>Global variables: </b>usable throughout the program <br>
<b>Local variables: </b> usable only within that particular scope (object, function, etc.)

# Operators & Methods:

## Logical Operators: 

1. Not (!)  
Returns the opposite of the operand
```javascript
var sense = true;
// to describe nonsense
var nonsense = !sense;
console.log('nonsense:', nonsense);

var notNonsense = !nonsense;
console.log('not nonsense:', notNonsense);
```

2.  Or (||)  
If either value is true, then returns true
```javascript
console.log(true || true); // will log true
console.log(true || false); // will log true
console.log(false || true); // will log true
console.log(false || false); // will log false
```
3. And (&&)  
Will only return true if BOTH are true
```javascript
console.log(true && true); // will log true
console.log(true && false); // will log false
console.log(false && true); // will log false
console.log(false && false); // will log false
```
4. Equals (===)  
Checks to see if any two scalar values are the same.  
Returns true only IF both values are THE SAME
In the case of undefined:

var declared;
var undefinedMatch = declared === undefined;
console.log('undefinedMatch:',undefinedMatch);

In the case of Booleans:
```javascript
var isRaining = true;
var weatherPredictedRain = true;

var weathermanWasRight = isRaining === weatherPredictedRain;
console.log('weathermanWasRight:', weathermanWasRight);
```
In the case of Numbers:
```javascript
var expectedCount = 10;
var actualCount = 9;

var expectationsMet = expectedCount === actualCount;
console.log('expectationsMet:', expectationsMet);
```
In the case of Strings:
```javascript
var currentString = 'happiness';
var nextString = 'happiness';

var stringsMatch = currentString === nextString;
console.log('stringsMatch:', stringsMatch);
```
5. Not Equal (!==)  
Returns true if the two operands are different 

## Mathematical Operators:

1. Plus `+`
2. Minus `-`
3. Multiplication `*`
4. Division `/`
5. Exponents `**`
6. Modulo `%` - returns the whole remainder of a division problem
7. Plus-Equals `+=` - adds two numbers and assigns the new value to the sum of the first two. (Increments)
8. Minus-Equals `-=` - subtracts a number from the base and assigns the new value to the base. (Decrements)
9. Multiple-Equals `*=`
10. Divide-Equals `/=`
11. `Math.abs()` - returns the absolute value
12. Round up `Math.ceil()`
13. Round down `Math.floor()`
14. Parse a number from a string: `Number.parseInt()`
15. Parse a float from a string: `Number.parseFloat()`
```javascript
var userIdString = "49";
var parsedUserId = Number.parseInt(userIdString);
console.log("parsedUserId:", parsedUserId);

var userRatingString = "29.45";
var parsedUserRating = Number.parseFloat(userRatingString)
console.log('parsedUserRating:', parsedUserRating);
```
16. Random number: `Math.random()` - generates a random float between 0 and 1

Random Number between a min and max:
```javascript
function generateRandomNumber(min, max) {
var result;  // create a result variable
result = Math.random() * (max - min) + min;  // assign it to formula for random number between min and max
return result;  // return result
}
```
17. Greater than `>` and Greater than or Equal to `>=`
18. Less than `<` and Less than or Equal to `<=`
19. Math.PI - gives you the value of pi (not a function; takes no parameters.)
```javascript
var areaOfCircle = Math.PI * r ** 2 //gives you pi r^2
```

# Objects:

1. An object is a collection of properties
2. A property is an association between a name <b>(key)</b> and a <b>value</b> (some data type)
3. A property's value can be any of the types we have gone over, as well as being another object, or even a function
4. In the case where the value of a property is a function, we refer to the property as a <b>method</b>  
5. Arrays are a type of object

An object is a data type composed of methods and key:value pairs. Object contents are always wrapped in curly braces.<br>
Syntax:

```javascript
var newObject = {
firstkey:1, secondkey:2
};
```

## Adding a value to an object
For an object that looks like this:
```javascript
var obj = {
    key1: value1,
    key2: value2
};
```
1. If you know the name of the value to be added, use **dot notation**:
```javascript
obj.key3 = "value3";
```

2. If you want the name of a property "dynamically determined" (for instance, when you're returning a value you don't know the name of), use **bracket notation**:
```javascript
obj["key3"] = "value3";
```
Example of a "dynamically determined" use:
```javascript
var getProperty = function (propertyName) {
    return obj[propertyName];
};

getProperty("key1");
getProperty("key2");
getProperty("key3");
```
(borrowed from stackOverflow)


<h><b>Accessing the Value of a Property</b></h>
    
1. We need to know the name of the <b>object</b>, and the name of the <b>key</b> (both do the same thing):
3. Can use <b>"dot notation":</b> `var valueOfName = stringsObj.name;`
4. Can use <b>"bracket notation":</b>`var valueOfName = stringsObj['name'];`

<h><b>Object Methods & Operators</b></h>
1. `typeof`: operator that returns what data type of the called variable is. Proper syntax: `if (typeof obj[value] === "number") { ...`
2. Since arrays are a type of object, in order to return whether a variable is an array or not, use method `Array.isArray()` (returns a true/false value). Proper syntax: `if (Array.isArray(objectName[keyOfArrayInObjectName])) { ...`
3. to remove an key:value pair, use `delete arrayName[key];`
4. `Object.keys()` returns an array whose elements are strings corresponding to the enumerable properties found directly upon object. The ordering of the properties is the same as that given by looping over the properties of the object manually.
5. `Object.values()` returns an array whose elements are the enumerable property values found on the object. The ordering of the properties is the same as that given by looping over the property values of the object manually.

# Strings:

1. To get the length of a string, call the `.length` property (NOT a method, since it's a property, not a function)
2. To get a slice of a string with a defined start and/or end, use the `.substring()` method. Takes two arguments: (1) starting index, and (2) ending index.
3. To FIND a particular substring, use the `.indexOf()` method. Takes two arguments: (1) the requested search value, and (if requested) (2) the requested starting point for the search.  
If the query is not found, the method will return -1.
4. To convert a different data type TO a string, us the `.toString()` method. Takes NO arguments, so proper syntax is `var stringVersion = parameter.toString()` (unless you want a binary[2], octal[8], or hex[16] value; in this case, it will convert the number to the appropriate base, THEN change the type to string).


# Arrays:

1. Can use `.length`
2. To add an element to the back of the array, use the `.push()` method
3. To remove an element from the back of the array, use the `.pop()` method (returns the popped value)
4. to add an element to ther FRONT of an array, use the `.unshift()` method (takes value to be added as an argument)
5. To remove an element from the FRONT of an array, use the `.shift()` method (takes no arguments)
6. To insert an element into the middle of an array, use the `.splice()` method. <br>Takes the following arguments: 
 <br> `.splice(starting index, number of elements to replace, new element)`. Can be used to replace OR remove elements at the given index.
 7. To determine whether an item is an array, use the `Array.isArray()` method. <br>Takes the element to be tested as an argument: <br> `var returnBool = Array.isArray(subject)`
 8. To extract a slice of an array without affecting the subject, use the `.slice()` method. <br> Takes the following arguments: <br> `var returnSlice = subject.slice(starting element, up to but not including this element)`. If no parameters are given, then it will return the entire array.
 9. To concatenate two arrays, use the `.concat()` method. <br>Call the method ON the first array, and use the second array as an argument as such: <br>`var resultOfConcat1 = array1.concat(addArray2, addArray3);`. Can take infinite arrays to concatenate as arguments.
 10. To transform an array into a string, use the `.join()` method. <br> Call the method ON the first array, then use the "separator" as an argument (which will be inserted between each element): <br> 
 ```javascript
 var result = ["words", "in", "string"].join("-");
 output: words-in-string
 ```
 11. To split a string into separate elements in an array, use the `.split()` method. 
 <br> Call the method ON the string, then use the "separator" as an argument (anywhere the method finds that element, it will split the string): <br> 
 ```javascript
 var result = "words-in-string".split("-")
 output: ['words', 'in', 'string']
 ```
 12. To search for a particular element, use the `.indexOf()` method. <br> 
Takes the following arguments: <br>
`searchSubject.indexOf(search Criterion,starting Point)`
```javascript
var indexOfElement = ['c', 'a', 'b', 'c', 'd'].indexOf('c',2);
output: 3
```

<h2><b>Formatting:</b></h2>
Template literals: if you use backticks in lieu of quotes, you can put the name of the variable INSIDE the string as such: 

> `inside this string, you can use ${variableName}`

# Loops:

## 1. While loop: <br>
While some condition is true, repeat some task. Iterate inside the loop.
```javascript
function loopAnArray(array) {
    var index = 0;
    while (index < array.length) {
        current = array[index];
        console.log(current);
        index++;
    }
}
```

## 2. For loop: <br>

    The for statement creates a loop that consists of three optional expressions <br>
        

- <b>initialization</b> <br>
 An expression or variable declaration that evaluated once before the loop begins
    

- <b>condition</b> <br>
 An expression to be evaluated before each loop iteration. If it evaluates to true, statement is executed

- <b>final-expression</b> <br>
 An expression to be evaluated at the end of each loop iteration
    <br>These expressions are enclosed in parentheses and separated by semicolons
    They are followed by a statement to be executed in the loop
    Will often be referred to as a "for loop"

```javascript
for (/*initialization*/ ; /*condition*/ ; /*final-expression*/ ) {
  /* statement */
}
```

## 3. For...in loop:<br>

    A quick way to <b> iterate over an object</b> is to use a for...in loop: `for (i in object) {...}`
    <br> This calls the loop once `for` each {element} `in` an {object}.  
    No iteration (i++) is required.  
    Not recommended for strings or numbers; mainly used for objects.

# Iteration & Accumulation:

### Using an Object to Count Elements
Technique for counting the number of unique elements in an array/object.
<br> using a loop to iterate through all the items in the array (or object).
<br> if the element is new (undefined in the counting object), it will instantiate with a value of 1.
<br> if the element is a duplicate, the loop will add to the count of that element.

```javascript
function countWords(str) {
    //edge case: if the input is empty, return an empty object
	if (str === "") {
		return {};
	}
  // split string at every space into an array
	var splitString = str.split(" ");
	//create a new object to iterate into
	var countObject = {};
	//create a loop to iterate through the array
	for (i in splitString) {
		currentElement = splitString[i];
		//for every element in the array, if that element is NOT a key in the object (undefined), create a new element in that array with value 1
		if (countObject[currentElement] === undefined) {
			countObject[currentElement] = 1;
		}
		//if that element IS in the object, iterate the value
		else {
			countObject[currentElement]++;
		}
	}
	return countObject;
}
```

## Copying unique elements into another array
Given two objects, "extend" adds properties from the 2nd object to the 1st object. <br>
Add any keys that are not in the 1st object. <br>
If the 1st object already has a given key, ignore it (do not overwrite the property value). <br>
Do not modify the 2nd object at all.

```javascript
function extend(obj1, obj2) {
	//read each element in obj2 to see if it's in obj1
  for (var keyFromObj2 in obj2) {
		//if obj2[keyFromObj2] is not in obj1 (is undefined), then
		if (obj1[keyFromObj2] === undefined) {
		//initialize it in obj1, by reading the value at the key in obj2
			obj1[keyFromObj2] = obj2[keyFromObj2];
		}
	}
	//else, do nothing
	//return obj2.	
	return obj1;
}

var obj1 = {
  a: 1,
  b: 2
};
var obj2 = {
  b: 4,
  c: 3
};

extend(obj1, obj2);

console.log(obj1); // --> {a: 1, b: 2, c: 3}
console.log(obj2); // --> {b: 4, c: 3}
```

Iterating through elements to see which is the shortest

```javascript
function findShortestOfThreeWords(word1, word2, word3) {
    //create array with all words
	var words = [word1, word2, word3];
	//assign shortest to first word 
	var shortest = word1;
	//if subsequent element is shorter than the first, then update shortest
	for (i = 0; i<words.length; i++) {
		if (words[i].length < shortest.length) {
			shortest = words[i];
		}
	}
	return shortest;
}
```
