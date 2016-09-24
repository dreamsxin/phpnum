# phpnum

[![Build Status](https://travis-ci.org/phpnum/phpnum.svg?branch=master)](https://travis-ci.org/phpnum/phpnum)

A PHP extension for scientific computing. Inspired by [NumPy](https://github.com/numpy/numpy) & [NumPHP](https://github.com/NumPHP/NumPHP).



# Table of contents
-----
1. [Installing/Configuring](#installingconfiguring)
   * [Requirement](#requirement)
   * [Installation](#installation)
2. [Classes and methods](#classes-and-methods)
   * [Usage](#usage)
   * [Characteristics](#characteristics)
   * [Arithmetic Operations](#arithmetic-operations)
   * [Statistics](#statistics)

-----

# Installing/Configuring
-----

Everything you should need to install phpnum on your system.

## requirement
- PHP 7 +

## Installation

~~~
phpize
./configure
make && make install
~~~

`make install` copies `num.so` to an appropriate location, but you still need to enable the module in the PHP config file. To do so, either edit your php.ini or add a num.ini file in `/path/to/php.d` with the following contents: `extension=num.so`.

# Classes and methods

-----

## Usage

1. [Class Num](#class-num) - Creates a Num object
2. [Class NumNdarray](#class-numndarray) - Creates a N-dimensional array (ndarray) object
3. [Printing](#printing) - Prints a ndarray object

### Class Num
-----
_**Description**_: Creates a Num object

##### *Example*

~~~
$num = new Num();
~~~

### Class NumNdarray
-----
_**Description**_: Creates a N-dimensional array (ndarray) object

##### *Parameters*
array: *Array*

##### *Return value*

ndarray: *Object*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[1.0, 2, 3], [2, 3, 4]]);
~~~
### Printing
-----
_**Description**_: Prints a ndarray object

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[1.0, 2, 3], [2, 3, 4]]);
echo $ndarray;
/* output: 
array([
  [1,2,3],
  [2,3,4]
])
*/
~~~



## Characteristics

1. [getData](#getdata) - Data of the ndarray
2. [getShape](#getshape) - Shape of ndarray dimensions
3. [getNdim](#getndim) - Number of ndarray dimensions
4. [getSize](#getsize) - Number of elements in the ndarray

### getData
-----
_**Description**_: Data of the ndarray

##### *Parameters*
None

##### *Return value*
data: *Array*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$ndarray->getData(); // returns array(array(1.0, 2, 3), array(2, 3, 4))
~~~

### getShape
-----
_**Description**_: Shape of ndarray dimensions

##### *Parameters*
None

##### *Return value*
shape: *Array*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$ndarray->getShape(); // returns array(2, 3)
~~~

### getNdim
-----
_**Description**_: Number of ndarray dimensions

##### *Parameters*
None

##### *Return value*
ndim: *LONG*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$ndarray->getNdim(); // returns 2
~~~

### getSize
-----
_**Description**_: Number of elements in the ndarray

##### *Parameters*
None

##### *Return value*
size: *LONG*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$ndarray->getSize(); // returns 6
~~~



## Arithmetic Operations

1. [add](#add) - Add a ndarray to an other ndarray
2. [sub](#sub) - Subtract a ndarray from an other ndarray
3. [mult](#mult) - Multiply a ndarray by an other ndarray
4. [div](#div) - A ndarray divided by an other ndarray

### add
-----
_**Description**_: Add a ndarray to an other ndarray

##### *Parameters*
ndarray: *Object*

##### *Return value*
ndarray: *Object*

##### *Example*

~~~
$num = new Num();
$a = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$b = $num->array([[3.2, 1.5, 1], [2.5, 4, 2]]);
echo $a->add($b);
/* output:
array([
  [4.2,3.5,4],
  [4.5,7,6]
])
*/
~~~

### sub
-----
_**Description**_: Subtract a ndarray from an other ndarray

##### *Parameters*
ndarray: *Object*

##### *Return value*
ndarray: *Object*

##### *Example*

~~~
$num = new Num();
$a = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$b = $num->array([[3.2, 1.5, 1], [2.5, 4, 2]]);
echo $a->sub($b);
/* output:
array([
  [-2.2,0.5,2],
  [-0.5,-1,2]
])
*/
~~~

### mult
-----
_**Description**_: Multiply a ndarray by an other ndarray

##### *Parameters*
ndarray: *Object*

##### *Return value*
ndarray: *Object*

##### *Example*

~~~
$num = new Num();
$a = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$b = $num->array([[3.2, 1.5, 1], [2.5, 4, 2]]);
echo $a->mult($b);
/* output:
array([
  [3.2,3,3],
  [5,12,8]
])
*/
~~~

### div
-----
_**Description**_: A ndarray divided by an other ndarray

##### *Parameters*
ndarray: *Object*

##### *Return value*
ndarray: *Object*

##### *Example*

~~~
$num = new Num();
$a = $num->array([[1.0, 2, 3], [2, 3, 4]]);
$b = $num->array([[3.2, 1.5, 1], [2.5, 4, 2]]);
echo $a->div($b);
/* output:
array([
  [0.3125,1.3333333333333,3],
  [0.8,0.75,2]
])
*/
~~~



## Statistics

1. [amin](#amin) - Return the minimum of a ndarray
2. [amax](#amin) - Return the maximum of a ndarray

### amin
-----
_**Description**_: Return the minimum of a ndarray

##### *Parameters*
ndarray: *Object*

##### *Return value*
amin: *Double*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[3.2, 1.5, 1], [2.5, 4, 2]]);
$num->min($ndarray); // returns 1
~~~

### amax
-----
_**Description**_: Return the maximum of a ndarray

##### *Parameters*
ndarray: *Object*

##### *Return value*
amax: *Double*

##### *Example*

~~~
$num = new Num();
$ndarray = $num->array([[3.2, 1.5, 1], [2.5, 4, 2]]);
$num->amax($ndarray); // returns 4
~~~