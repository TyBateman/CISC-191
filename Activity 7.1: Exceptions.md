Flowchart Link: https://drive.google.com/file/d/1dyiwIKLMafnyt0EShfDMtoeX2YGj2EMv/view?usp=sharing

I didn't really have any major problems or challenges with this lab, it was fairly straightforward from beginning to end.

Video Link: https://drive.google.com/file/d/1Gy9hcgvDqlZ_adbRm1yJ7suy1ZzxKwP2/view?usp=sharing

```java
import java.util.Scanner;

public class Pedometer {

    public static double stepsToMiles(int steps) throws Exception {
        if (steps < 0) {
            throw new Exception("Exception: Negative step count entered.");
        }
        return steps / 2000.0;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the number of steps: ");
        int steps = scanner.nextInt();
        
        try {
            double miles = stepsToMiles(steps);
            System.out.printf("%.2f\n", miles);
        } 
        catch (Exception e) {
            System.out.println(e.getMessage());
        }

        scanner.close();
    }
}


```
