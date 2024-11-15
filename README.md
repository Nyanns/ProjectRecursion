# README

## Table of Contents
- [Overview](#overview)
- [Functions](#functions)
  - [1. Merge Sort](#1-merge-sort)
  - [2. Fibonacci Sequence](#2-fibonacci-sequence)
- [Getting Started](#getting-started)
- [Usage](#usage)

## Overview
This project includes implementations of two popular algorithms:
1. **Merge Sort**: An efficient, comparison-based sorting algorithm using the divide and conquer technique.
2. **Fibonacci Sequence Generator**: A function to generate a Fibonacci sequence up to a specified length or value.

These algorithms are implemented in JavaScript, making them ideal for understanding sorting algorithms and number sequences in programming.

---

## Media

### Demo GIFs

![Recording 1](https://github.com/Nyanns/ProjectRecursion/blob/main/media/ScreenRecording2024-11-10050918-ezgif.com-video-to-gif-converter.gif)

![Recording 2](https://github.com/Nyanns/ProjectRecursion/blob/main/media/ScreenRecording2024-11-10181337-ezgif.com-video-to-gif-converter.gif)

---

## Functions

### 1. Merge Sort
**Merge Sort** is a sorting algorithm that employs the divide-and-conquer strategy. It splits an array into halves, sorts them, and then merges the sorted halves back together.

#### Implementation
```javascript
function mergeSort(array) {
    if (array.length <= 1) {
        return array;
    }

    const middle = Math.floor(array.length / 2);
    const left = array.slice(0, middle);
    const right = array.slice(middle);

    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
    let result = [];
    let leftIndex = 0;
    let rightIndex = 0;

    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }

    return [...result, ...left.slice(leftIndex), ...right.slice(rightIndex)];
}
```

#### Example Usage
```javascript
const array = [3, 2, 1, 13, 8, 5, 0, 1];
console.log(mergeSort(array)); // Output: [0, 1, 1, 2, 3, 5, 8, 13]
```

#### Explanation
1. **Splitting the Array**: The array is recursively split until each subarray has one or zero elements.
2. **Merging**: Sorted subarrays are merged back together one element at a time to form a fully sorted array.

---

### 2. Fibonacci Sequence
The **Fibonacci Sequence** is a number series where each number is the sum of the two preceding ones. This implementation provides two methods for calculating the sequence: iterative and recursive.

#### Implementation
```javascript
// Iterative
function fibonacciIterative(n) {
    let fibSeq = [0, 1];
    for (let i = 2; i < n; i++) {
        fibSeq = [...fibSeq, fibSeq[i - 2] + fibSeq[i - 1]];
    }
    return fibSeq.slice(0, n);
}

// Recursive
function fibonacciRecursive(n, sequence = [0, 1]) {
    if (sequence.length >= n) {
        return sequence.slice(0, n);
    } else {
        return fibonacciRecursive(n, [...sequence, sequence[sequence.length - 2] + sequence[sequence.length - 1]]);
    }
}
```

#### Example Usage
```javascript
console.log(fibonacciIterative(5)); // Output: [0, 1, 1, 2, 3]
console.log(fibonacciRecursive(7)); // Output: [0, 1, 1, 2, 3, 5, 8]
```

#### Explanation
- **Iterative**: Uses a `for` loop to build the Fibonacci sequence up to length `n`.
- **Recursive**: Calls itself to add elements to the `sequence` array until it reaches length `n`.

---

## Getting Started

To use these functions, simply copy the JavaScript code into your project. There are no special dependencies, so they can be used directly in any JavaScript environment.

## Usage

- Ensure to provide the correct input for the desired length of the sequence or array.
- You can use the functions as shown in the examples or modify them according to your needs.

---

Happy coding, and enjoy exploring Merge Sort and Fibonacci algorithms!