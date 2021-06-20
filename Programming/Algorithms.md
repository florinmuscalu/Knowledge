## Radix Sort
- Algorithm to sort arrays of integers in Java.
- From [Daniel Lemire](https://lemire.me/blog/2021/04/09/how-fast-can-you-sort-arrays-of-integers-in-java/).
```java
publicstaticvoidradixSort(int[]data){
	int[]copy=newint[data.length];
	int[]level0=newint[257];
	int[]level1=newint[257];
	int[]level2=newint[257];
	int[]level3=newint[257];
	for(intvalue:data){
		value-=Integer.MIN_VALUE;
		level0[(value&0xFF)+1]++;
		level1[((value>>>8)&0xFF)+1]++;
		level2[((value>>>16)&0xFF)+1]++;
		level3[((value>>>24)&0xFF)+1]++;
	}
	for(inti=1;i<level0.length;++i){
		level0[i]+=level0[i-1];
		level1[i]+=level1[i-1];
		level2[i]+=level2[i-1];
		level3[i]+=level3[i-1];
	}
	for(intvalue:data){
		copy[level0[(value-Integer.MIN_VALUE)&0xFF]++]=value;
	}
	for(intvalue:copy){
		data[level1[((value-Integer.MIN_VALUE)>>>8)&0xFF]++]=value;
	}
	for(intvalue:data){
	copy[level2[((value-Integer.MIN_VALUE)>>>16)&0xFF]++]=value;
	}
	for(intvalue:copy){
	data[level3[((value-Integer.MIN_VALUE)>>>24)&0xFF]++]=value;
	}
}
```
## Polar Coordinates
A complex number: 
```math
z=x+yj
```
Here, **j** is the imaginary unit.

![Object](Polar.png)

A polar coordinate (r, φ) is completely determined by the modulus **r** and the phase angle **φ**.

If we convert complex number **z** to it's polar coordinate, we find:
- **r** is the distance from z to origin
```math
(x^2+y^2)^1/2
```
- φ is the counter clockwise angle measured from the positive x-axis to the line segment that joins z to the origin.
Python's cmath module provides access to the mathematical functions for complex numbers. This tool returns the phase of complex number z (also known as the argument of z).
```python
>>> cmath.phase(complex(-1.0, 0.0))
3.1415926535897931
```
