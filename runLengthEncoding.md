# Rosetta Code - Run-length encoding

> Given a string containing uppercase characters (A-Z), compress repeated 'runs' of the same character by storing the length of that run, and provide a function to reverse the compression.
>
> The output can be anything, as long as you can recreate the input with it.

```java
String str = "WWWWWWWWWWWWBWWWWWWWWWWWWBBBWWWWWWWWWWWWWWWWWWWWWWWWBWWWWWWWWWWWWWW";
String result = "";

for (int index = 0; index < str.length() - 1; ) {
    int count = 1;
    
    for (int j = index + 1; j < str.length(); j++) {
        if (Character.toString(str.charAt(j)).equals(Character.toString(str.charAt(index)))) {
            count++;
            index++;
        }
        else {
            result += String.valueOf(count);
            result += String.valueOf(str.charAt(index));
            index = j;
            count = 1;
        }
    }
    result += String.valueOf(count);
    result += String.valueOf(str.charAt(index));
}
System.out.println(result);
```