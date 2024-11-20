# IntegerList

This project involves creating a custom `IntegerList` class that provides various operations for managing a list of integers. The program includes methods to add integers, check for existence, find positions, swap elements, and reverse the list.

## Objective

Create a Java program that:

- Implements the `IntegerList` class with the following methods:
    - `boolean contains(int x)`: Returns true if `x` is included in the list, false otherwise.
    - `int position(int x)`: Returns the position of `x` in the list (or -1 if `x` is not included in the list).
    - `String swap(int i, int j)`: Swaps the integers stored at positions `i` and `j` (returns an error message or a string confirming the swap).
    - `void reverse()`: Reverses the order of the elements in the list.

### Example Implementation

#### IntegerList.java

```java
import java.util.ArrayList;

public class IntegerList {
    private ArrayList<Integer> list;

    public IntegerList() {
        list = new ArrayList<>();
    }

    // Adds an integer to the list
    public void add(int value) {
        list.add(value);
    }

    // Returns the size of the list
    public int size() {
        return list.size();
    }

    // Checks if the list contains a specific integer
    public boolean contains(int x) {
        return list.contains(x);
    }

    // Returns the position of the integer in the list, or -1 if not found
    public int position(int x) {
        return list.indexOf(x);
    }

    // Swaps the integers at positions i and j
    public String swap(int i, int j) {
        if (i < 0 || i >= list.size() || j < 0 || j >= list.size()) {
            return "Error: Invalid indices.";
        }
        int temp = list.get(i);
        list.set(i, list.get(j));
        list.set(j, temp);
        return "Swapped elements at positions " + i + " and " + j + ".";
    }

    // Reverses the order of the elements in the list
    public void reverse() {
        int left = 0;
        int right = list.size() - 1;
        while (left < right) {
            int temp = list.get(left);
            list.set(left, list.get(right));
            list.set(right, temp);
            left++;
            right--;
        }
    }

    // Returns a string representation of the list
    @Override
    public String toString() {
        return list.toString();
    }
}
```

#### IntegerListTest.java

```java
import java.util.Scanner;

public class IntegerListTest {
    public static void main(String[] args) {
        IntegerList integerList = new IntegerList();
        Scanner scanner = new Scanner(System.in);

        // Adding integers to the list
        System.out.println("Enter integers to add to the list (enter -1 to stop):");
        while (true) {
            int input = scanner.nextInt();
            if (input == -1) {
                break;
            }
            integerList.add(input);
        }

        // Displaying the list
        System.out.println("Current Integer List: " + integerList);

        // Checking if a number is contained in the list
        System.out.print("Enter a number to check if it is in the list: ");
        int checkNum = scanner.nextInt();
        System.out.println("Contains " + checkNum + ": " + integerList.contains(checkNum));

        // Getting the position of a number
        System.out.print("Enter a number to find its position in the list: ");
        int posNum = scanner.nextInt();
        System.out.println("Position of " + posNum + ": " + integerList.position(posNum));

        // Swapping two positions
        System.out.print("Enter two indices to swap: ");
        int index1 = scanner.nextInt();
        int index2 = scanner.nextInt();
        System.out.println(integerList.swap(index1, index2));
        System.out.println("List after swapping: " + integerList);

        // Reversing the list
        integerList.reverse();
        System.out.println("List after reversing: " + integerList);

        scanner.close();
    }
}
```

### Example Usage

When you run the `IntegerListTest` class, it will prompt you to enter integers to add to the list. You can then check for existence, find positions, swap elements, and reverse the list.

### Notes

- Ensure that you have the necessary Java environment set up to compile and run the program.
- You can extend the functionality of the `IntegerList`

Happy coding! 🎉 