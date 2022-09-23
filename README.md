# Bitwise operations
Topics one must know
=====================
- [Bitwise Operators](#bitwise-operators)
    - [AND Operator](#and-operator)
    - [OR Operator](#or-operator)
    - [XOR Operator](#xor-operator)
    - [Complement Operator](#complement-operator)
    - [Left Shift Operator](#left-shift-operator)
    - [Right Shift Operator](#right-shift-operator)
- [Basic Problems](#basic-problems)
    - [Check if Kth bit is set or not](#check-if-kth-bit-is-set-or-not)
        - [Check if a number is odd or even](#check-if-a-number-is-odd-or-even)
    - [Set Kth bit](#set-kth-bit)
    - [clear Kth bit](#clear-kth-bit)
- [Toggle Kth bit](#toggle-kth-bit)
- [Toggle right most set bit](#toggle-right-most-set-bit)
- [Capture position of right most set bit](#capture-position-of-right-most-set-bit)
- [Capture position of right most unset bit](#capture-position-of-right-most-unset-bit)
- [Check if number is power of 2](#check-if-number-is-power-of-2)
- [Multiplying number by power of 2](#multiplying-number-by-power-of-2)
- [Dividing number by power of 2](#dividing-number-by-power-of-2)
- [Finding modulo of a given number](#finding-modulo-of-given-number)
- [Reversing a binary number](#reversing-a-binary-number)
- [Extract odd and even bit numbers]
- [Swap all odd and even bits]
- [Counting number of set bits in a number](#counting-number-of-set-bits-in-a-number)
- [Peforming average without division](#performing-average-without-divison)

### Bitwise Operators
#### AND Operator
```
X   0  0  1  1
Y   0  1  0  1
---------------
R   0  0  0  1
---------------
```

#### OR Operator
```
X   0  0  1  1
Y   0  1  0  1
---------------
R   0  1  1  1
---------------
```

#### XOR Operator
Same bit results 0.
Different bits results to 1.
To remember - XOR operator is used to find the element in an array having pairs except one number which is only once. Since, each pair will result 0 using XOR.
```
X   0  0  1  1
Y   0  1  0  1
---------------
R   0  1  1  0
---------------
```
#### Complement Operator
```
X   0  1
---------
R   1  0
---------
```
#### Left Shift Operator
```
m = 19
m = 10011
m << 1 = 10011 = 38
n = 21
n = 10101
n << 2 = 1010100 = 84
```
#### Right Shift Operator
```

m = 19
m = 10011
m >> 1 = 1001 = 9
n = 21
n = 10101
n >> 2 = 101 = 5
```
### Basic Problems
#### Check if Kth bit is set or not
```
n = 75 = 0100 1011
k = 4   // It means we need to check if 4th bit is set or not
int res = (n & (1 << (k-1)))
if(res == 0)
    Sop("Kth bit is 1")
else
    Sop("Kth bit is 0")
```
##### Check if a number is odd or even
**FACT:** A number can be odd only if its first bit is one.
So to check if a number is odd or even we need to check if the 0th bit is set or not
```
n1 = 1 = 0001
n2 = 3 = 0011
n3 = 5 = 0101
n4 = 7 = 0111
if((n1 & 1) == 0)
    Sop("n1 is even")
else
    Sop("n1 is odd")
``` 
#### Set Kth bit
```
n = 75 = 0100 1011
k = 3   // It means we need to set the 3rd bit
int res = (n | (1 << k-1))
// res = 79 = 0100 1111
```
