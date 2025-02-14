# Day 4 task
## **Do the below programs in anonymous function & IIFE**
**1.Print odd numbers in an array**

// Anonymous function
let printOddNumbers = function(arr) {
    arr.forEach(num => {
        if (num % 2 !== 0) {
            console.log(num);
        }
    });
};

printOddNumbers([1, 2, 3, 4, 5]); // Output: 1, 3, 5

// IIFE
(function(arr) {
    arr.forEach(num => {
        if (num % 2 !== 0) {
            console.log(num);
        }
    });
})([1, 2, 3, 4, 5]); // Output: 1, 3, 5

**2.Convert all the strings to title caps in a string array**
// Anonymous function

let convertToTitleCaps = function(arr) {
    return arr.map(str => str.charAt(0).toUpperCase() + str.slice(1).toLowerCase());
};

let strings = ["hi", "my", "name", "bharath"];
let titleCapsArray = convertToTitleCaps(strings);
console.log(titleCapsArray); // Output: [ 'Hi', 'My', 'Name', 'Bharath' ]

// IIFE
let titleCaps = (function(arr) {
    return arr.map(str => str.charAt(0).toUpperCase() + str.slice(1).toLowerCase());
})(["hi", "my", "name", "bharath"]);
console.log(titleCaps);  // Output: [ 'Hi', 'My', 'Name', 'Bharath' ]

**3.Sum of all numbers in an array**

// Anonymous function
const add = function(num1, num2) {
    return num1+num2;
}
console.log(add(700, 300)); // Output: 1000

// IIFE

let sum =((num1, num2) => num1 + num2)(70, 30)

console.log(sum) // Output: 100

**4.Return all the prime numbers in an array**
// Anonymous function

let getPrimes = function(arr) {
    return arr.filter(num => {
        if (num <= 1) return false; 
        for (let i = 2; i <= Math.sqrt(num); i++) {
            if (num % i === 0) return false; 
        }
        return true; 
    });
};

let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let primes = getPrimes(numbers);
console.log(primes); // Output: [2, 3, 5, 7]

// IIFE

let primes = (function(arr) {
    return arr.filter(num => {
        if (num <= 1) return false;
        for (let i = 2; i <= Math.sqrt(num); i++) {
            if (num % i === 0) return false;
        }
        return true;
    });
})([2, 3, 4, 5, 6, 7, 8, 9, 10]);
console.log(primes); // Output: [2, 3, 5, 7]

**5.Return all the palindromes in an array**

// Anonymous function

let getPalindromes = function(arr) {
    return arr.filter(function(str) {
        let lowerCaseStr = str.toLowerCase();
        return lowerCaseStr === lowerCaseStr.split('').reverse().join('');
    });
};

let words = ["level", "hello", "radar", "world"];
let palindromes = getPalindromes(words);
console.log(palindromes); // Output: ["level", "radar"]

//IIFE

let palindromes = (function(arr) {
    return arr.filter(str => str === str.split('').reverse().join(''));
})(["level", "hello", "radar", "world"]);
console.log(palindromes);  // Output: ["level", "radar"]

**6.Return median of two sorted arrays of the same size**

// Anonymous function

let findMedianSortedArrays = function(nums1, nums2) {
    let merged = nums1.concat(nums2).sort((a, b) => a - b);
    let length = merged.length;
    if (length % 2 === 0) {
        return (merged[length / 2 - 1] + merged[length / 2]) / 2;
    } else {
        return merged[Math.floor(length / 2)];
    }
};

let arr1 = [1, 3, 5];
let arr2 = [2, 4, 6];
let median = findMedianSortedArrays(arr1, arr2);
console.log(median); // Output: 3.5

// IIFE
let median = (function(nums1, nums2) {
    let merged = nums1.concat(nums2).sort((a, b) => a - b);
    let length = merged.length;
    if (length % 2 === 0) {
        return (merged[length / 2 - 1] + merged[length / 2]) / 2;
    } else {
        return merged[Math.floor(length / 2)];
    }
})([1, 3, 5], [2, 4, 6]);
console.log(median);  // Output: 3.5

**7.Remove duplicates from an array**

// Anonymous function

let removeDuplicates = function(arr) {
    return arr.filter(function(value, index, self) {
        // Return only the elements that are first occurrence in the array
        return self.indexOf(value) === index;
    });
};

let numbers = [1, 2, 2, 3, 4, 4, 5, 5];
let uniqueArray = removeDuplicates(numbers);
console.log(uniqueArray); // Output: [1, 2, 3, 4, 5]

// IIFE
let uniqueArray = (function(arr) {
    return arr.filter((value, index, self) => self.indexOf(value) === index);
})([1, 2, 2, 3, 4, 4, 5, 5]);
console.log(uniqueArray);  // Output: [1, 2, 3, 4, 5]


**8.Rotate an array by k times**
// Anonymous function

let rotateArray = function(arr, k) {
    let len = arr.length;
    k = k % len; 
    let rotated = arr.slice(len - k).concat(arr.slice(0, len - k));
    return rotated;
};


let originalArray = [1, 2, 3, 4, 5];
let rotated = rotateArray(originalArray, 2);
console.log(rotated); // Output: [4, 5, 1, 2, 3]


// IIFE
let rotatedArray = (function(arr, k) {
    let len = arr.length;
    k = k % len;
    let rotated = arr.slice(len - k).concat(arr.slice(0, len - k));
    return rotated;
})([1, 2, 3, 4, 5], 2);
console.log(rotatedArray);  Output: [4, 5, 1, 2, 3]


## **Do the below programs in arrow functions**

**1.Print odd numbers in an array**

let printOddNumbers = arr => {
    arr.forEach(num => {
        if (num % 2 !== 0) {
            console.log(num);
        }
    });
};

// Example usage:
printOddNumbers([1, 2, 3, 4, 5]); // Output: 1, 3, 5

**2.Convert all the strings to title caps in a string array**

let convertToTitleCaps = arr => {
    return arr.map(str => str.charAt(0).toUpperCase() + str.slice(1).toLowerCase());
};

// Example usage:
let strings = ["hi", "my", "name", "is", "bharath"];
let titleCapsArray = convertToTitleCaps(strings);
console.log(titleCapsArray); // Output: [ 'Hi', 'My', 'Name', 'Is', 'Bharath' ]

**3.Sum of all numbers in an array**

let sumArray = arr => {
    return arr.reduce((acc, num) => acc + num, 0);
};

let numbers = [1, 2, 3, 4, 5];
let sum = sumArray(numbers);
console.log(sum); // Output: 15

**4.Return all the prime numbers in an array**

let getPrimes = arr => {
    return arr.filter(num => {
        if (num <= 1) return false; 
        for (let i = 2; i <= Math.sqrt(num); i++) {
            if (num % i === 0) return false; 
        }
        return true; 
    });
};

let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let primes = getPrimes(numbers);
console.log(primes); // Output: [2, 3, 5, 7]

**5.Return all the palindromes in an array**

let getPalindromes = arr => {
    return arr.filter(str => {
        let lowerCaseStr = str.toLowerCase();
        return lowerCaseStr === lowerCaseStr.split('').reverse().join('');
    });
};

let words = ["level", "hello", "radar", "world"];
let palindromes = getPalindromes(words);
console.log(palindromes); // Output: ["level", "radar"]




#   d a y 4  
 