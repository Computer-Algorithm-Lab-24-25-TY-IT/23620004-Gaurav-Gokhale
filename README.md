# 23620004-Gaurav-Gokhale
# Quick Sort
#include <iostream>
using namespace std;

int partition(int arr[], int start, int end)
{

    int pivot = arr[start];

    int count = 0;
    for (int i = start + 1; i <= end; i++) {
        if (arr[i] <= pivot)
            count++;
    }

    int pivotIndex = start + count;
    swap(arr[pivotIndex], arr[start]);

    int i = start, j = end;

    while (i < pivotIndex && j > pivotIndex) {

        while (arr[i] <= pivot) {
            i++;
        }

        while (arr[j] > pivot) {
            j--;
        }

        if (i < pivotIndex && j > pivotIndex) {
            swap(arr[i++], arr[j--]);
        }
    }

    return pivotIndex;
}

void quickSort(int arr[], int start, int end)
{

    if (start >= end)
        return;

    int p = partition(arr, start, end);

    quickSort(arr, start, p - 1);

    quickSort(arr, p + 1, end);
}

int main()
{

    int arr[] = { 7, 5, 4, 3, 2, 9 };
    int n = 6;

    quickSort(arr, 0, n - 1);

    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
# Output
![gprof](https://github.com/user-attachments/assets/0cb802e7-485a-4915-a3f8-84fbfc0c686d)
