Flowchart Link: 

The major challenges I had in this lab were 

Video Link: 

```java
import java.util.*;

public class MergeSort {
    private static int comparisons = 0;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int size = scanner.nextInt();
        int[] array = new int[size];
        Set<Integer> seen = new HashSet<>();

        for (int i = 0; i < size; i++) {
            int value = scanner.nextInt();
            if (seen.contains(value)) {
                System.out.println("No Duplicate Values");
                return;
            }
            seen.add(value);
            array[i] = value;
        }

        System.out.print("Unsorted: ");
        printArray(array);

        mergeSort(array, 0, array.length - 1);

        System.out.print("Sorted: ");
        printArray(array);
        System.out.println("Comparisons: " + comparisons);
    }

    private static void mergeSort(int[] array, int left, int right) {
        if (left < right) {
            int middle = (left + right) / 2;
            mergeSort(array, left, middle);
            mergeSort(array, middle + 1, right);
            merge(array, left, middle, right);
        }
    }

    private static void merge(int[] array, int left, int middle, int right) {
        int n1 = middle - left + 1;
        int n2 = right - middle;

        int[] L = new int[n1];
        int[] R = new int[n2];

        System.arraycopy(array, left, L, 0, n1);
        System.arraycopy(array, middle + 1, R, 0, n2);

        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            comparisons++;
            if (L[i] <= R[j]) {
                array[k++] = L[i++];
            } else {
                array[k++] = R[j++];
            }
        }

        while (i < n1) {
            array[k++] = L[i++];
        }

        while (j < n2) {
            array[k++] = R[j++];
        }
    }

    private static void printArray(int[] array) {
        for (int value : array) {
            System.out.print(value + " ");
        }
        System.out.println();
    }
}

```
