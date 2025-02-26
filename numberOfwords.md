# Edabit - Get word count

> Calculates the number of words in a string

## Java

```java
Scanner scanner = new Scanner(System.in);
System.out.print("Enter a string: ");
String str = scanner.nextLine();
scanner.close();

int count = 1;

for (int i = 0; i < str.length(); i++) {
    if (Character.isWhitespace(str.charAt(i)))
    {
        count++;
    }
}

System.out.println(count);
```

This program gets a string from the user and counts the number of words. I started with a counter (count = 1), iterated through our string, and incremented the counter by one everytime we hit a whitespace. I am using `Character.isWhitespace(str.charAt(i))` because it not only checks for a single whitespace, but also for multiple whitespaces between two words and it treats it as one. This gives us right output even if we have some whitespace error in our string.
