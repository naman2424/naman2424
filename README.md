

public class Searches{

 /**
 * Searches items array for goal
 * pre: items is sorted from low to high
 * post: Position of goal has been returned,
 * or -1 has been returned if goal not found.
 */
 public static int binarySearch(int[] items, int start,
 int end, int goal) {
int mid
do {
mid = (start + end) / 2
   if (goal==items[mid]) {
   return(mid);
 } else if (goal < items[mid]) {
end = mid -1;
 } else {
   start = mid +1;
}
} while (start <= end);
return(-1);
}
}
 import java.util.Scanner;
 import java.util.Random;
 public class TestSorts {

 public static void displayArray(int[] array) {
 for (int i = 0; i < array.length; i++) {
 System.out.print(array[i] + " ");
 }
 System.out.println("\n");
 }

 public static void sortIntArray() {
 Scanner input = new Scanner(System.in);
 int numItems, searchNum, location;
 int[] test;
 Random rand = new Random();

 System.out.print("Enter number of elements: ");
 numItems = input.nextInt();

 /* populate and sort array */
 test = new int[numItems];
 for (int i = 0; i < test.length; i++) {
 test[i] = rand.nextInt(100);
 }
 Sorts.mergesort(test, 0, test.length - 1);
 System.out.println("Sorte
/* search for number in sorted array */
 System.out.print("Enter a number to search for: ");
 searchNum = input.nextInt();
 while (searchNum != -1){
 location = Searches.binarySearch(test, 0,
 test.length-1, searchNum);
 System.out.println("Number at position: " + location);
 System.out.print("Enter a number to search for: ");
 searchNum = input.nextInt();
 }
 }
 public static void main(String[] args) {
 sortIntArray();
 }
}
