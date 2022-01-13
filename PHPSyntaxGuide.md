PHP Syntax Guide

PHP Comments:
Comments are text that is ignored by the php engine to provide explanation or notes on the code. PHP supports both single and multi line comments.
A single line comment is written starting with either // or #
Multi line comments are written starting with /* and ending with */.

Variables:
Variables are used to store data in php.  Variables can change over the course of your code. A variable does not need to be declared before adding a value to it, php converts the variable to its correct data type based on the variables value.  Be sure to include ; at the end.
Variables are declared like this: 
$var_name = value;
$greeting = "Welcome";  - assigned with string value
$pay = 10;  - assigned with a number value

Echo statements can be used to display the value of a variable to the browser.

Rules for nameing Variables:
- must start with $
- start with letter or underscore char
- cant start with a number
- only contain alpha numeric chars and underscores
- no spaces
- are case sensitive

Echo/Print:
Echo statements can be used to output strings and generally anything that can be displayed to the browser.  
Echo is not a function so parenthesis are not needed.  Print is also used to display to browser and works very similarly, also not a function. Print only outputs one string and returns one so echo is considered marginally faster.


Display string of text:

<?php

echo "Hello there";

?>

HTML code:

<?php

echo "<h1>This is a heading.</h1>";
echo "<h1 style='color: blue;'>Add some color.</h1>";

?>

Declare/Display Variables With Echo:

<?php

$txt = "Welcome!";
$nums = 123;
$food = array("pizza", "burger", "salad");

echo $txt;
echo $nums;
echo $food[0];

?>

 

Data Types:
Values assigned to php variables may be anything from strings, numeric, arrays, or objects.
PHP supports 8 primitive data types:
Integer
Float/Floating Point Number
Strings
Boolean
Object
Resource
Null


Strings:
Strings are a sequence of characters.  Strings can consist of letters, numbers, as well as special characters. Use single or double quotes to enclose ex "this is a string".

Php has built in features such as strlen to calculate the number of characters within a string.
str_word_count($my_var); counts the number of words in a string
str_replace can be used to replace all occurences of the search string within a target string
strrev reverses a string


Numbers:
Php automatically provides data type conversion.  If you assign an integer to a variable then the type of variable will automatically be an integer, same with a string.
Integer rules:
- must have one digit
- must not have decimal point
- either positive or negative
- three formats, decimal(10), hexadecimal(16), or octal(8)

Constants for Integers:
PHP_INT_MAX - largest integer supported
PHP_INT_MIN - smallest integer supported
PHP_INT_SIZE - size of an integer in bytes

Floats:
A float is a number with a decimal point or in exponential form. Can normally have a max precision of 14 digits.
PHP_FLOAT_MAX - largest representable floating point number, value larger is considered infinite
PHP_FLOAT_MIN - smallest ""
- PHP_FLOAT_MAX - smallest representable negative floating point number
PHP_FLOAT_DIG - number of decimal digits that can be rounded into a float and back withot precision loss
PHP_FLOAT_EPSILON - smallest representable postitive number x, so that x + 1.0 != 1.0

PHP NaN - not a number, is used for impossible mathematical operations

Constants:
A name or identifier for a fixed value.  Like variables expect once they are defined they cant be changed or undefined.  Useful for storing info that doesnt change while script is running ex username, password, company name.

Constants are defined using PHPs define() function. Accepts two arguements, the constants name and value.  

Once defined the constant can be accessed by refering to its name.

<?php

define("SITE_URL", "https://www.google.com");   - defining constants info

echo 'Thank you for visiting' . SITE_URL;   - using echo to display

?>


Operators:
Symbols that tell the php processor to perform certain things.
Arithmetic:
+ addition $x + $y
- subtraction
* multiplication
/ division
% modulus - remainder

Assignment operators:
= assign
+= add and assign
-= subtract and assign
* multiply and assign
/= divide and assign quotient
%= divide and assign modulus

Comparison:
== equal
=== identical
!= not equal
<> not equal
!== not identical
< less than
> greater than
<= less than or equal to
>= greater than or equal to

Increment and Decrement:
++$x pre-increment - increment x by one, then return x
$x++ post-inc - return x, then increment by 1
--$x pre-decrement - decrement x by on, then return x
$x-- post-decrement - return x, then decrement x by one

Logical:
and - $x and $y - true if both $x and $y are true
or - true if either x or y is true
xor - true if either x or y is true, but not both
&& -and- true if both x and y are true
|| -or- true if either x or y is true
! -not- true if x is not true

String Operator:
. - concatenation
.= - concatenation assignment

Array Operator:
+ - union   union of x and y
== equality     true if x and y have the same key/value pairs
=== identity    true if x and y have the same key/value pairs in the same order and of the same type
!= inequality   true if x is not equal to y
<> inequality   true if x is not equal to y
!== non-identity true if x is not identical to y

Spaceship:
<=> - used to compare two expressions
ex ($x <=> $y)
Operator returns 0 if both are equal, 1 if left is greater, and -1 if right is greater.


If & Else & Elseif:

Provides conditional execution of multiple statements.
ex if(expression)
    statement;

The if keyword is a logical expression that evaluates to true or false, if true the next line of code is executed, if false then it may move on to the next expression.
ex. if (expression){
        item1;
        item2;
} else {
        item3;
        item4;
}

The elseif statement is a combo of both else and if statements. It can be used to move through statements to find an appropriate result and execution through a cascade of elseif conditions.

ex. if (expression){
    statement;
}
elseif (expression){
    statement;
}
elseif (expression){
    statement;
}
else{
    statement;
}
}


Functions:
Block of code that performs a task.  Php has a large collection of built-in functions that can be used for specific tasks.
Users are also able to define their own functions as a way to create reusable code to perform tasks.
Makes code easier to read and maintain, easier to eliminate errors, can be used in other applications.
Creating function with parameters:

function myFunc($parameteron, $parametertwo){
    echo "hello";
}

myFunc();

Variable scope - by default variables defined within a function are local and cannot be viewed or manipulated from outside of that function.  Variables can be defined outside of the function but if defined inside they will not be globally defined.

Recursive - function that calls itself again and again until a condition is met.  Often these are used to solve complex mathematical calculations.

function printValues($arr) {

    global $count;
    global $items;

    if(!is_array($arr)){
        die("error");
    }
}

Arrays:
Complex variables that allow for multiple values or group of values under a single variable name.
Types of Arrays:
Indexed - array with a numeric key, automatically assigns indexes and starts at 0, values can be any data type.
    $food - array("pizza", "burger", "salad");

Associative- the keys assigned to values can be arbitary and user defined strings.
$food = array("Pizza"=>1, "Burger"=>2, "Salad:=>3);

Mulitdimensional - each element can also be an array and each element can contain another array.
$food = array(

array(
    "name" => "Pizza"
    "day" => "monday",
),
array{
    "name" => "Burger"
    "day" => "tuesday",
}
)

Array structure and values can be viewed by using either var_dump() or print_r()
ex. var_dump($food);

Sorting Arrays:
sort() and rsort() - sorting indexed arrays in ascending and descending order
asort() - sorts elements of an associative array in ascending order by value, works like sort but shows association between keys and values.
ksort() - sort associative arrays in ascending order by key.
krsort() - sort associative arrays in descending order by key.


Loops:
Used to execute the same code over again until a condition has been met or as long as a condition is being met.  Loops are used to automate what would be a repetitive task.
Types:
While - loops through code as long as condition evaluates to true
    ex. $i = 1;
        while($i <= 3){
            $i++;
        }

Do...while - code executed once and then condition is evaluated, if true the loop is repeated.
    ex. $i = 1;
    do{
        $i++;
    }
    while($i <= 3);

For - loops code until counter reaches specified amount/number
    ex. for($i=1; $i<=3;, $i++){
        echo $i;
    }

For each - loops through code for each element in array
    ex. $food = array("pizza", "burger", "salad");
        foreach($food as $value){
            echo $value . "<br>";
        }