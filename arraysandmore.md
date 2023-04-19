# Arrays and 2D Arrays

### Cloning this Repo
Fork this repo to follow along, you will need to submit the hacks on your completed repo: [https://github.com/nicm2/monkeylessonfrontend][repo]

### Arrays
Arrays are 10-15% of the exam, so it is very important to understand the basics of arrays. Collegeboard will typically test you on:
- Representing multiple items as array objects
- Traversing an array by accessing the elements using iteration statements
- Standard algorithms that utilize array traversals to perform functions

### Array Basics
An array can contain primitives (int, char, etc) and object references of a class. Primitive data types have their actual values stored in contiguous memory  location.

Important things to note are that:
- Arrays are fixed in size
- Arrays can be used as a static field, local variable, or method parameter

![array](https://media.geeksforgeeks.org/wp-content/uploads/Arrays1.png)


```java
//BASIC ARRAY CONCEPTS

//Declare an array and then allocate memory
int myArray[];
myArray = new int[4];

//Declare while directly assign values
int[] myArray1 = new int[]{ 1, 6, 7, 9};

//Initialize element
myArray[0] = 2;

//Create an array of objects
Object[] arr = new Object[5];
```

### Traversing an Array
Common ways to traverse an array include for loops and enhanced for loops:
- A for loop allows you to access the index, and manipulations can be done by changing the incrementer (ie. i+=2 instead of i++)
- An enhanced for loop is simpler but you CANNOT access the index, only the value


```java
//Basic for loop to print elements of array
int[] arr1 = {0, 6, 8, 2};

// Looping through array by incrementing value of i
//'i' is an index of array 'arr1'
for (int i = 0; i < arr1.length; i++) {

    // Print array element present at index i
    System.out.println(i + " " + arr1[i]);

}

// NOTE: You may also use an enhanced for loop

for(int value: arr1){
    System.out.println(value);
}

```

    0 0
    1 6
    2 8
    3 2
    0
    6
    8
    2


# Hack: Create method that sets all elements in array to n


```java
void setArray(int[] arr, int n) {
    // your code here
}

int[] array = new int[10];
setArray(array, 10);

for (int i = 0; i<array.length; i++) {
    System.out.println(array[i]);
}

// Should print all 10s when working properly

```

    0
    0
    0
    0
    0
    0
    0
    0
    0
    0


### Developing Algorithms Using Arrays
Arrays are an essential part in developing algorithms. It is important to understand how to traverse an array and the structure of an array to accomplish this.

There are lots of algorithms you can create,and CollegeBoard goes over a lot of good examples of this. They go over this in the 6.4 unit videos. 


```java
//Example finding the max in an array. 

//Finds the maximum in an array
public static int maximum(int[] array) {
    //variable that holds value of max value
    int maxValue = array[0];
    //for each number in the array..
    for (int number: array) {
      //checks if current index is greater than maxValue
      if (number > maxValue) {
        //if new max value found, replace current maxValue
        maxValue = number;
      }
    }
    return maxValue;
  }

//tester array
int[] test = {3, 5, 7, 2, 10};

//returns 10
maximum(test);
```




    10



Generally, when you are coding algorithms using arrays you will probably use some traversal element. The key thing to think about is what you want to do for each element, because once you have a repeatable action you can just put it in a for loop. You also want to consider which elements you actually want to look at beacuse in some causes you may want to skip some elements.

## Think?: What should be changed in the code above to find the minimum?

## Hack: Write an array to find the average of an array


```java
//Example finding the max in an array. 

//Finds the maximum in an array
public static int average(int[] array) {
    // put your code here
    return 0;
}

//tester array
int[] test = {3, 5, 7, 2, 10};

//returns 10
System.out.println(average(test));
```

    0


### 2-D Arrays
2-D arrays are 7.5-10% of the exam, so they are also very important to know for the AP exam. Many concepts of 2-D arrays rely on a solid understanding of arrays. 

A 2-D array is an array of arrays, and store data similar to a row and column fashion.

Length is determined by the number of rows in the array, which is also the number of arrays in the 2-D array.

Columns is based on the size of each row of an array and can be determined based on the number of elements in the first row. 

### 2-D Array Basics


```java
//create a new 2-d array (default to all 0s)
int[][] twoDArray = new int[3][3];

//access the value at row 2 column 1
twoDArray[1][0];

//get value at the end of a 2-d array
// (twoDArray.length - 1) gets how many arrays (rows)
// (twoDArray[0].length - 1) gets how many elements in first array (columns)
twoDArray[twoDArray.length - 1][twoDArray[0].length - 1];
```




    0



The 2D array is useful to represent a matrix as well, which then can be accessed by the rows and columns. This is a good way to visualize a 2d array. Here, I will show an example of how a "grid" looks like + initialization


```java
// GRID of our array
// 4 5 6
// 7 8 9
// 1 2 3

// Initializing our array
int[][] twoDArray = {
    {4,5,6},
    {7,8,9},
    {1,2,3}
}
```

### Traversing 2-D Arrays
2-D arrays are traversed similarly to arrays in that you will primarily use for and while loops. However, since there are both rows and columns now, you will need to use nested for loops or nested enhanced for loops. 


```java
//Prints the 2-d array
public static void print2D(int mat[][])
    {
        // For each row of the array (goes one array at a time)
        for (int row = 0; row < twoDArray1.length; row++) {
 
            //Goes through each element of the array
            for (int column = 0; column < twoDArray1[row].length; column++)
                System.out.print(mat[row][column] + " ");

            // runs for every row (not every element)
            System.out.println();
        }
    }

    int twoDArray1[][] = { { 1, 2, 3 },
                           { 4, 6, 7 },
                           { 8, 9, 10} };
 
print2D(twoDArray1);
```

    1 2 3 
    4 6 7 
    8 9 10 


When traversing 2-D arrays it is important to note wether the code is in row-major or column-major order. This basically indicates what the outer for loop of the method is traversing.

If the outer loop is going by column, its in column major order. If the outer loop is going by row, its in row-major order.

The code example above is in row-major order

When you are traversing, again make sure to consider the pros/cons of for vs enhanced for loop (for loop allows you to mess with index). This can be useful to again think about which elements you actually want to take actions on. Furthermore, you may also consider actions that you only want to do for every row, or every column. This could be opposed to every element, in which case you would put it in the outer for loop (see the ``System.out.println()`` in above code)

# Think: What would this code print and why (without running it yourself)?


```java

public static void main(String[] args){
    int[][] arrayOne = new int[5][7];
    for (int row = 0; row < arrayOne.length; row++){
        for (int col = 0; col < arrayOne[row].length; col++){
            arrayOne[row][col] = row+col - 1;
        }
    }

    System.out.println(arrayOne[4][6]);
}

```

# Hack: Find the average number of a diagonal in a 2d array
For example, here find the average of the bolded #s<br>
**1** 2 3 4<br>
5 **6** 7 8<br>
9 1 **2** 3<br>




```js
public static int averageDiagonal (int[][] array2D) {
    // your code here
    return 0;
}

int[][] arr = {
    {1,2,3,4,5,6},
    {7,8,9,10,11,12},
    {0,1,2,3,4,5},
    {10,11,12,13,14,15},
    {15,16,17,18,19,20}
};

System.out.println(averageDiagonal(arr));
```

    0

