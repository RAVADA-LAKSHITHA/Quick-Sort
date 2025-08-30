# Quick-Sort
My Quick Sort code in Java
<br>
import java.util.*;

public class qs {
    public static void main(String args[]) {
        int [] arr = {2, 3, 6, 5, 1, 4};
        Quick_sort a = new Quick_sort();
        a.qs(arr, 0, arr.length - 1);

        System.out.println("Sorted array: " + Arrays.toString(arr));
    }
}

class Quick_sort {
    public void qs(int arr[], int p, int r) {
        if (p < r) {
            int q = partition(arr, p, r);
            qs(arr, p, q - 1);
            qs(arr, q + 1, r);
        }
    }

    public int partition(int arr[], int p, int r) {
        int pivot = arr[r];
        int i = p - 1;

        for (int j = p; j < r; j++) {
            if (arr[j] <= pivot) {
                i++;
                swap(arr, i, j);
            }
        }

        swap(arr, i + 1, r);
        return i + 1;
    }

    public void swap(int arr[], int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
