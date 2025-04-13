Flowchart Link: https://drive.google.com/file/d/1uATRC7KkD2RC2CESHif-HpV7aQDU9hh8/view?usp=sharing

The main challenges I had in completing this lab were figuring out how to properly used the newly learned interfaces as well as finding out how to properly test for a palendrome.

Video Link: https://drive.google.com/file/d/1RWz003s6DT8sEtFOLVXj7T3AjX49yVYJ/view?usp=sharing

```java
import java.util.LinkedList;
import java.util.Deque;
import java.util.Scanner;

public class Palindrome {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        scanner.close();

        Deque<Character> deque = new LinkedList<>();
        for (char c : input.toCharArray()) {
            deque.addLast(c);
        }

        boolean isPalindrome = true;
        while (deque.size() > 1) {
            if (!deque.removeFirst().equals(deque.removeLast())) {
                isPalindrome = false;
                break;
            }
        }

        if (isPalindrome) {
            System.out.println("Yes, " + input + " is a palindrome.");
        } else {
            System.out.println("No, \"" + input + "\" is not a palindrome.");
        }
    }
}
```
