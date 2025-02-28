# LeetCode Problem 20 

> Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
>
> An input string is valid if:
>
> * Open brackets must be closed by the same type of brackets.
> * Open brackets must be closed in the correct order.
> * Every close bracket has a corresponding open bracket of the same type.

```java
Stack<Character> stack = new Stack<>();

for (int i = 0; i < s.length(); i++)
{
    if ((s.charAt(i) == '(') || (s.charAt(i) == '{') || (s.charAt(i) == '['))
    {
        Character pushed = stack.push(s.charAt(i));
    }

    if ((s.charAt(i) == ')') || (s.charAt(i) == '}') || (s.charAt(i) == ']'))
    {
        if (stack.isEmpty())
            return false;
        else
        {
            Character popped = stack.pop();
            if ((s.charAt(i) == ')') && !(popped.equals('(')))
                return false;
            else if ((s.charAt(i) == '}') && !(popped.equals('{'))) 
                return false;
            else if ((s.charAt(i) == ']') && !(popped.equals('['))) 
                return false;      
        }
    }
}
return (stack.isEmpty());
```

This problem uses Stack ADT to solve valid parenthesis problem. We start with an empty stack. We iterate through our string and everytime we come across an opening parentheses, we push it to our stack. If we come across a closing parentheses, we pop our stack if it is not empty. If empty, we just return false, because we do not have any opening paretheses. After popping, we check if the popped opening parenthesis matches with the closing parentheses we are currently at. At the end, we return an empty stack. We use `popped.equals('(')` method instead of `(popped == '(')` because `.equal()` method checks the value and returns true whereas `popped == '('` operator checks the memory address and returns false.