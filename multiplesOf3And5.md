# Project Euler - 1: Multiples of 3 and 5 

> Calculates and prints the sum of all multiples of 3 and 5 below 1000

## Java 

```java
int sum = 0;

for (int i = 1; i < 1000; i++ ) 
{
    if (i % 3 == 0)
    {
        sum = sum + i;
    }

    if (i % 5 == 0)
    {
        sum = sum + i;
    }

    if (i % 3 == 0 && i % 5 == 0)
    {
        sum = sum - i;
    }
}

System.out.println(sum); // prints 233168
```

This algorithm uses the set formula { n(A union B) = n(A) + n(B) - n(A intersection B) } to find to find all the multiples of 3 and 5. This means we find all the multiples of 3 and 5 and add them together, and then we substract the multiples which are common to both.