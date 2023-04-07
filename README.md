# Single for loop traversal of three dimensional arrays

It demonstrates the use of a single for-loop for three-dimensional arrays, with an extrapolation to multidimensional arrays. A 3D-array variable (<i>A</i>) is declared with mixed datatypes, namely with string literals and number literals. The 3D-array is represented by five matrices, in which the columns represent one dimension, the rows represent the second dimension, and the number of matrices, represents the third dimension. Thus, this array can be understood as a cube-like structure. A string variable <i>t</i> is initially set to empty. A variable <i>v</i> is set to zero and it represents the main counter of the for-loop. Another three variables (ie. <i>i</i>, <i>j</i> and <i>d</i>) are initialized with a value of zero and are the main coordinates for array element identification. Each dimension of array <i>A</i> is stored in variables <i>s</i>, <i>m</i> and <i>n</i>, namely the number of matrices in <i>s</i>, the number of rows in <i>m</i> and the number of columns in <i>n</i>. The upper limit of the for-loop is calculated as <i>s × m × n</i>. Here, the value of the counter <i>v</i> from the for-loop is used, as before, to calculate the <i>i</i>, <i>j</i> and <i>d</i> values that are used as an index to traverse the array variable <i>A</i>. The value of variable <i>j</i> is computed as the <i>v % m</i>. A condition increments a variable <i>i</i> (rows) each time <i>j</i> (columns) equals zero. Thus, both <i>i</i> and <i>j</i> values are computed. However, the value for variable <i>d</i> (matrix number) is calculated as <i>v % (m×n)</i>, which provides a value of zero each time a matrix was traversed. Thus, a condition increments variable <i>d</i> and resets variable <i>i</i>, each time the value of <i>k</i> equals zero. At each iteration, the value from an element (<i>d</i>, <i>i</i>, <i>j</i>) is added to the content of variable <i>t</i>. Once the end of the for-loop is reached, the string value collected in variable <i>t</i> is printed in the output for inspection. The end result is the enumeration of each value in the output, in a linear manner.

Online demo: https://gagniuc.github.io/Single-for-loop-traversal-of-3D-arrays/

```javascript

let A = [
        [
   ["a", 55, 146],
   ["b", 34, 124],
   ["c", 96, 564],
   [100, 12, "d"],
        ],
        [
   ["e", 88, 146],
   ["f", 34, 124],
   ["g", 96, 564],
   [100, 12, "h"],
        ],
        [
   ["i", 88, 146],
   ["j", 34, 124],
   ["k", 96, 564],
   [100, 12, "k"],
        ],
        [
   ["m", 88, 146],
   ["n", 34, 124],
   ["o", 96, 564],
   [100, 12, "p"],
        ],
        [
   ["q", 88, 146],
   ["r", 34, 124],
   ["s", 96, 564],
   [100, 12, "t"],
        ]
        ];

let t = "";

let s = A.length;       // 5 matrices
let m = A[0].length;    // 4 rows
let n = A[0][0].length; // 3 columns

let i = 0;
let j = 0;
let d = 0;
let k = 0;

let q = n * m * s;

for (let v = 0; v < q; v++){
    
   k = v % (m*n);
   j = v % n;
   
   if(v!=0 && j == 0){i++;}
   if(v!=0 && k == 0){i = 0; d++;}
   
   t += v + " A["+d+"]["+i+"]["+j+"]=";
   t += A[d][i][j] + "\n";
}

print(t);

```


# Note

This JavaScript example is written for the Rhino JavaScript engine. To use this particular Javascript example in browsers, please put the source between the <script></script> tags, and replace any "print" keyword with the "alert" keyword.

# References

- Paul A. Gagniuc. <i>An Introduction to Programming Languages: Simultaneous Learning in Multiple Coding Environments</i>. Synthesis Lectures on Computer Science. Springer International Publishing, 2023, pp. 1-280.

