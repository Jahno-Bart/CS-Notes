## Floating Point Binary
<br><br>

**FLOATING POINT IS ALWAYS SIGNED**

<br><br>
**Mantissa:** The binary number

**Exponent:** Where the binary point sits within the Mantissa

*Floating point is always put in between the first and second bit*
<br><br>
Example:

| Mantissa | Exponent |
| -------------- | --------------- |
| 01101010 | 0011 |
| 0.1101010 | 3 |
| 0.110.1010 | |
| 6.625 | |

<br><br>

Convert 3.25 into floating point binary

3.25 = 011.01000  (Needs to be the required amount of bits (8))

| Mantissa | Exponent |
| -------------- | --------------- |
| 011.01000 | 0010 |

Point only moves 2 spaces so the exponent is 0010

### Negative Floating Point Binary

| Mantissa | Exponent |
| -------------- | --------------- |
| 10100100 | 0100 |
| 1.0100100 | 4 |
| 1.0100.100 |  |
| -11.5 | |

| Mantissa | Exponent |
| -------------- | --------------- |
| 01010000 | 1110 |
| 0.1010000 | -2 |
| 0.00.101000 |  |
| 0.15626 |  |


**Always going to be less than 1**

| Mantissa | Exponent |
| -------------- | --------------- |
| 10110000 | 1110 |
| 1.110110000 | -2 |
| -01.5625 | |

<br><br>

If denary = -6.75
| Mantissa | Exponent |
| -------------- | --------------- |
| 1001.0100 | 0011 |

<br><br>
<br><br>

### Normalising

Normalising floating points saves memory

How to tell:

- Significant bit after binary point
- Bit after point different to bit before point
- Negative number starts with 10... positive number starts with 01...

Do NOT ever say it is because there are no leading 0s this is wrong in some cases and will be rejected

### Generalised form

How would you easily know the which number is the following:

- Largest poitive number
    - 0 followed by all ones, large positive exponent
- Smallest positive number
    - 0 followed by as many 0s as possible, small positive exponent
- Largest negative number
    - Starts with one, large positive exponent
- Smallest negative number
    - Start with one, small negative exponent
