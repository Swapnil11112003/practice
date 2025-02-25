# Rosetta Code

> There are 100 doors in a row that are all initially closed. 
>
> You make 100 passes by the doors. 
>
>The first time through, visit every door and toggle the door (if the door is closed, open it; if it is open, close it). 
>
>The second time, only visit every 2nd door (door #2, #4, #6, ...), and toggle it. 
>
>The third time, visit every 3rd door (door #3, #6, #9, ...), etc, until you only visit the 100th door.
>
>What state are the doors in after the last pass? Which are open, which are closed?

## Java

```java
boolean [] doors = new boolean[100];

        for (int i = 0; i < 100; i++)
            doors[i] = false;

        for (int pass = 1; pass <= 100; pass++) 
            for (int index = 0; index < 100; index++) 
                if((index + 1) % pass == 0)
                    doors[index] = !doors[index];

        for (int i = 0; i < 100; i++)
            System.out.println((i + 1)  + " : " + doors[i]); // All the perfect square doors will be open(true)
```

This algorithm uses an array to store the status of 100 doors. We start by 100 closed(false) doors, and then we use a nested for loop to iterate over the 100 doors, 100 times, and changing its status every time we visit a door (true if false and vice versa). On every pass, we visit our doors (indexing 0 to 99), and checking if (index+1) is a multiple of the pass number. We are checking (index+1) because our door at 0 index is our first door. 
