Created: 30/07/2023 at 18:08

### Counting Decimal
Base 10, 0-9, 10 digits.
Keep incrementing rightmost digit until highest digit is reached, then apply same mechanism to increment digit to the left and reset current digit to 0.

### Counting Binary
Base 2, 0-1, 2 digits.
Keep incrementing rightmost digit until highest digit is reached, then apply same mechanism to increment digit to the left and reset current digit to 0.

### Counting Hexadecimal
Base 16, 0-9, A-F, 16 digits.
Keep incrementing rightmost digit until highest digit is reached, then apply same mechanism to increment digit to the left and reset current digit to 0.

### General Case Radix R
Base R, 0-R-1, R digits.
Keep incrementing rightmost digit until highest digit is reached, then apply same mechanism to increment digit to the left and reset current digit to 0.

### Polynomial Representation
Each digit is weighted according to its position.

![[Number Representations-1690712115443.jpeg]]

### Integer Conversion
#### Decimal to Radix
```python
while (number != 0)
    remainder = number % radix
    number = number / radix
    append remainder to list
```

![[Number Representations-1690712380160.jpeg]]
![[Number Representations-1690712429991.jpeg]]

#### Binary to Hex
Four Binary digits can be represented by one Hex digit.

![[Number Representations-1690712487957.jpeg]]

### Fixed Point Real Numbers
General Case Radix $R$,
$$d_n \space d_{n-1} ... d_0 \space . \space d_{-1} \space d_{-2} ... d_{-m}$$

Decimal equivalent
$$\sum_{i=-m}^{n} d_i \times R^i$$
![[Number Representations-1690712772518.jpeg]]

### Fixed Point Conversion
#### Decimal to Radix
```python
while (fraction != 0 && count <= precision)
    fraction = fraction * radix
    digit = trunc(fraction) # integear part
    fraction = fraction - digit
    count += 1
```
![[Number Representations-1690712911659.jpeg]]![[Number Representations-1690712994604.jpeg]]

### Signed Numbers
Signed numbers result naturally from counting backwards.

#### Binary
![[Number Representations-1690713326291.jpeg]]
![[Number Representations-1690713399306.jpeg]]

#### Hexadecimal
![[Number Representations-1690713431236.jpeg]]

### Negating Binary Numbers
![[Number Representations-1690713500835.jpeg]]

### Roll-over vs Overflow
#### Roll-over
Correct transition between negative and positive range,
$$1111 + 0001 = 0000$$
$$-1 + 1 = 0$$

#### Overflow
Incorrect transition between negative and positive range,
$$0111 + 0001 \neq 1000$$
$$7 + 1 \neq -8$$

### Signed Fixed-Point Numbers
![[Number Representations-1690713683991.jpeg]]

### Floating Point Numbers
We use IEEE standard for FP numbers
32 bits, 1 sign bit, 8 exponent bits, 23 bits for the fraction.
![[Number Representations-1690713861071.jpeg]]

#### Special Cases
![[Number Representations-1690714118233.jpeg]]![[Number Representations-1690714182553.jpeg]] 