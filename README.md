# Bitwise operations
Topics one must know
=====================
- [Bitwise Operators](#bitwise-operators)
    - [AND Operator](#and-operator)
    - [OR Operator](#or-operator)
    - [XOR Operator](#xor-operator)
        - [Find the element which appear only once in an array containing all other elements twice](#find-the-element-which-appear-only-once-in-an-array-containing-all-other-elements-twice)
    - [Complement Operator](#complement-operator)
    - [Left Shift Operator](#left-shift-operator)
    - [Right Shift Operator](#right-shift-operator)
- [Basic Problems](#basic-problems)
    - [Check if Kth bit is set or not](#check-if-kth-bit-is-set-or-not)
        - [Check if a number is odd or even](#check-if-a-number-is-odd-or-even)
    - [Set Kth bit](#set-kth-bit)
    - [clear Kth bit](#clear-kth-bit)
    - [Toggle Kth bit](#toggle-kth-bit)
    - [Capture position of right most set bit](#capture-position-of-right-most-set-bit)
    - [Capture position of right most unset bit](#capture-position-of-right-most-unset-bit)
    - [Count number of set bits in a number](#count-number-of-set-bits-in-a-number)
        - [Check if number is power of 2](#check-if-number-is-power-of-2)
    - [Multiplying number by power of 2](#multiplying-number-by-power-of-2)
    - [Dividing number by power of 2](#dividing-number-by-power-of-2)
 - [Complex Problems](#complex-problems)
    - [Hamming Distance](#hamming-distance)
    - 

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
##### Find the element which appear only once in an array containing all other elements twice
XOR of duplicate elements result in 0
```
class Solution {
    public int singleNumber(int[] nums) {
        int res = 0;
        for(int i=0; i<nums.length;i++)
            res ^= nums[i];
        return res;
    }
}
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
#### clear Kth bit
```
n = 75 = 0100 1011
k = 4   // It means we need to clear the 4th bit
int res = n & (~(1 << k-1))
// res = 67 = 0100 0011
```
#### Toggle Kth bit
```
n = 75 = 0100 1011
k = 4   // It means we need to toggle the 4th bit
int res = n ^ (1 << k-1)
// res = 67 = 0100 0011
```
#### Capture position of right most set bit
```
n = 72 = 0100 1000
int res = n & -n;
// res = 8 = 1000 
// the 1 tells the ocation where we first encounter 1
```
#### Capture position of right most unset bit
```
n = 239 = 1110 1111
int res = ~n & (n+1);
// res = 16 = 10000
// the 1 tells the location where we first encounter 0
```
#### Count number of set bits in a number
**Memorize It**
```
int n = 239 = 1110 1111
int count = 0;
while(n != 0){
    n &= (n-1);
    count++;
}
// count = 7
```
##### Check if number is power of 2
A number will be power of 2 only if it has only one bit as set.
For example - 
2^0 = 1 = 0001
2^1 = 2 = 0010
2^2 = 4 = 0100
2^3 = 8 = 1000
2^10 = 1024  = 0100 0000 0000
2^15 = 32768 = 1000 0000 0000 0000
There are 2 ways to solve it - 
* Counting the number of set bits in the number and verify its only one
* (n & (n-1)) should result to 0.

### Complex Problems
#### Hamming Distance
The Hamming distance between two integers is the number of positions at which the corresponding bits are different.
```
class Solution {
    public int hammingDistance(int x, int y) {
        int xor = x ^ y;
        int res = 0;
        while(xor != 0){
            res += xor & 1;
            xor = xor >> 1;
        }
        return res;
    }
}
```
