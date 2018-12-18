// QuickSort in C

int partition (int *arr, int left, int right) {
  int i;
  int j;
  int temp;
  int pivot;
  
  //pivot is the element to be placed in the correct position
  pivot = arr[right];
  
  //initialize to smaller element
  i = left - 1;
  
  for (j = left; j < right; j++) {
    if(arr[j] <= pivot) {
      i++;    //increment index of smaller element
      temp = arr[j];
      arr[j] = arr[i];
      arr[i] = temp;
  }
  
  i++;
  arr[right] = arr[i];
  arr[i] = pivot;
  return i;  
}

void quickSort (int *arr, int left, int right) {
  int pi;
  if (left < right) {
    pi = partition (arr, left, right);
    quicksort (arr, left, pi - 1);
    quicksort (arr, pi + 1, right);
  }
}  
  
    
