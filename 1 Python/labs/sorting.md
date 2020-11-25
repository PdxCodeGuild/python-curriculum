# Sorting

Implement an array sorting algorithm such that the elements are returned in ascending order.

Each student will be assigned one or more algorithm. At the end of class, students will present on their algorithm.

Include the following in your presentation:

* explain how the sort works
* walk through your implementation code
* time and space complexity (big-O notation)
* in-place or new array?
* visualization if possible
  * ok to link to outside sources
* stable or not?
* what are the best and worst case scenarios
* what situations is this sort preferred?
* what situations is this sort best avoided?

## List of Algorithms

Wikipedia has a pretty good [page on sorting algorithms](https://en.wikipedia.org/wiki/Sorting_algorithm). For visualization, visualgo.net is pretty good. Although it doesn't have all sorting algorithms, it has the most common ones. Also check out [15 Sorting Algorithms in 6 Minutes](https://www.youtube.com/watch?v=kPRA0W1kECg) which is an awesome visualization video (with epic sound effects). Also check out [visualgo](https://visualgo.net/en/sorting) for visualizations and pseudocode.

**Note**: since sorting is such a common and classic computer science problem, it is incredibly easy to find the solution online. Please try your best to avoid copying code while looking up how the sort works.

Here are acceptable sorts for this assignment:

* selection sort
* bubble sort
* insertion sort
* merge sort
* quicksort
* radix sort

The following notes are taken from [geeksforgeeks.org](https://www.geeksforgeeks.org/). However, please don't go to the site because you will be exposed to the solution code! I present the following so you can view the description without seeing the solution.

### Selection Sort

>The selection sort algorithm sorts an array by repeatedly finding the minimum element (considering ascending order) from unsorted part and putting it at the beginning. The algorithm maintains two subarrays in a given array.
>
>1) The subarray which is already sorted.
>2) Remaining subarray which is unsorted.
>
>In every iteration of selection sort, the minimum element (considering ascending order) from the unsorted subarray is picked and moved to the sorted subarray.

Example:

```
arr[] = 64 25 12 22 11

// Find the minimum element in arr[0...4]
// and place it at beginning
11 25 12 22 64

// Find the minimum element in arr[1...4]
// and place it at beginning of arr[1...4]
11 12 25 22 64

// Find the minimum element in arr[2...4]
// and place it at beginning of arr[2...4]
11 12 22 25 64

// Find the minimum element in arr[3...4]
// and place it at beginning of arr[3...4]
11 12 22 25 64
```

### Bubble Sort

```
Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.
Example:
First Pass:
( 5 1 4 2 8 ) –> ( 1 5 4 2 8 ), Here, algorithm compares the first two elements, and swaps since 5 > 1.
( 1 5 4 2 8 ) –>  ( 1 4 5 2 8 ), Swap since 5 > 4
( 1 4 5 2 8 ) –>  ( 1 4 2 5 8 ), Swap since 5 > 2
( 1 4 2 5 8 ) –> ( 1 4 2 5 8 ), Now, since these elements are already in order (8 > 5), algorithm does not swap them.

Second Pass:
( 1 4 2 5 8 ) –> ( 1 4 2 5 8 )
( 1 4 2 5 8 ) –> ( 1 2 4 5 8 ), Swap since 4 > 2
( 1 2 4 5 8 ) –> ( 1 2 4 5 8 )
( 1 2 4 5 8 ) –>  ( 1 2 4 5 8 )
Now, the array is already sorted, but our algorithm does not know if it is completed. The algorithm needs one whole pass without any swap to know it is sorted.

Third Pass:
( 1 2 4 5 8 ) –> ( 1 2 4 5 8 )
( 1 2 4 5 8 ) –> ( 1 2 4 5 8 )
( 1 2 4 5 8 ) –> ( 1 2 4 5 8 )
( 1 2 4 5 8 ) –> ( 1 2 4 5 8 )
```

### Insertion Sort

>Insertion sort is a simple sorting algorithm that works similar to the way you sort playing cards in your hands. The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part.
>
>To sort an array of size n in ascending order:
>
>1. Iterate from arr[1] to arr[n] over the array.
>2. Compare the current element (key) to its predecessor.
>3. If the key element is smaller than its predecessor, compare it to the elements before. Move the greater elements one position up to make space for the swapped element.

### Merge Sort

>Merge Sort is a Divide and Conquer algorithm. It divides the input array into two halves, calls itself for the two halves, and then merges the two sorted halves. The merge() function is used for merging two halves. The merge(arr, l, m, r) is a key process that assumes that arr[l..m] and arr[m+1..r] are sorted and merges the two sorted sub-arrays into one. See the following C implementation for details.

Check out [this diagram on wikipedia](https://en.wikipedia.org/wiki/File:Merge_sort_algorithm_diagram.svg).

```
MergeSort(arr[], l,  r)
If r > l
     1. Find the middle point to divide the array into two halves:  
             middle m = (l+r)/2
     2. Call mergeSort for first half:   
             Call mergeSort(arr, l, m)
     3. Call mergeSort for second half:
             Call mergeSort(arr, m+1, r)
     4. Merge the two halves sorted in step 2 and 3:
             Call merge(arr, l, m, r)
```

### Quicksort

>Like Merge Sort, QuickSort is a Divide and Conquer algorithm. It picks an element as pivot and partitions the given array around the picked pivot. There are many different versions of quickSort that pick pivot in different ways.

>1. Always pick first element as pivot.
>2. Always pick last element as pivot (implemented below)
>3. Pick a random element as pivot.
>4. Pick median as pivot.

>The key process in quickSort is partition(). Target of partitions is, given an array and an element x of array as pivot, put x at its correct position in sorted array and put all smaller elements (smaller than x) before x, and put all greater elements (greater than x) after x. All this should be done in linear time.

```
/* low  --> Starting index,  high  --> Ending index */
quickSort(arr[], low, high)
{
    if (low < high)
    {
        /* pi is partitioning index, arr[pi] is now
           at right place */
        pi = partition(arr, low, high);

        quickSort(arr, low, pi - 1);  // Before pi
        quickSort(arr, pi + 1, high); // After pi
    }
}
```

#### Partition Algorithm

>There can be many ways to do partition... The logic is simple, we start from the leftmost element and keep track of index of smaller (or equal to) elements as i. While traversing, if we find a smaller element, we swap current element with arr[i]. Otherwise we ignore current element.


```
/* This function takes last element as pivot, places
   the pivot element at its correct position in sorted
    array, and places all smaller (smaller than pivot)
   to left of pivot and all greater elements to right
   of pivot */
partition (arr[], low, high)
{
    // pivot (Element to be placed at right position)
    pivot = arr[high];  
 
    i = (low - 1)  // Index of smaller element

    for (j = low; j <= high- 1; j++)
    {
        // If current element is smaller than the pivot
        if (arr[j] < pivot)
        {
            i++;    // increment index of smaller element
            swap arr[i] and arr[j]
        }
    }
    swap arr[i + 1] and arr[high])
    return (i + 1)
}
```

### Radix Sort

>The idea of Radix Sort is to do digit by digit sort starting from least significant digit to most significant digit. Radix sort uses counting sort as a subroutine to sort.

```
Original, unsorted list:
170, 45, 75, 90, 802, 24, 2, 66

Sorting by least significant digit (1s place) gives: 
[*Notice that we keep 802 before 2, because 802 occurred 
before 2 in the original list, and similarly for pairs 
170 & 90 and 45 & 75.]

170, 90, 802, 2, 24, 45, 75, 66

Sorting by next digit (10s place) gives: 
[*Notice that 802 again comes before 2 as 802 comes before 
2 in the previous list.]

802, 2, 24, 45, 66, 170, 75, 90

Sorting by the most significant digit (100s place) gives:
2, 24, 45, 66, 75, 90, 170, 802
```
