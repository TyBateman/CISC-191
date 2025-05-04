Flowchart Link: 

The major challenges I had in this lab were 

Video Link: 

```java
import java.util.Scanner;

public class InsertionSort {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int size = scanner.nextInt();
        int[] array = new int[size];
        for (int i = 0; i < size; i++) {
            array[i] = scanner.nextInt();
        }

        printArray(array);

        int comparisons = 0;
        int swaps = 0;

        for (int i = 1; i < size; i++) {
            int key = array[i];
            int j = i - 1;

            while (j >= 0) {
                comparisons++;
                if (array[j] > key) {
                    array[j + 1] = array[j];
                    j--;
                    swaps++;
                } else {
                    break;
                }
            }
            array[j + 1] = key;

            printArray(array);
        }

        System.out.println("\nComparisons: " + comparisons);
        System.out.println("Swaps: " + swaps);
    }

    private static void printArray(int[] array) {
        for (int num : array) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```
