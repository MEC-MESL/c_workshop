---
transition: fade
layout: cover
---

# Array & Pointer

(abir CSE-6th)

---
transition: fade
zoom: 1.4
---

## Brief 

An array is a linear data structure that stores a fixed-size sequence of elements of the same data type in contiguous memory locations.

````md magic-move
```c
#include<stdio.h>
int main() {}
```
```c
#include<stdio.h>
int main() {
  // data type | 
  // a preferred name | 
  // size of array
  // values
}
```
```c
#include<stdio.h>
int main() {
  int arr[] = {2,4,8,12,16,18}
}
```
````
---
transition: fade
layout: image
zoom: 1.4
---

## Indexing

<img src="./assets/Arrays-in-C.webp">

---
transition: slide-down
zoom: 1.4
---

## Accessing elements

````md magic-move
```c
#include<stdio.h>
int main() {
  int arr[] = {3, 4, 5, 6}
}
```
```c
#include<stdio.h>
int main() {
  int arr[] = {3, 4, 5, 6}
  printf("%d ",arr[0])
}
```
````

---
transition: fade-out
zoom: 1.4
---

## Print it!!

````md magic-move
```c
#include<stdio.h>
int main() {
  int arr[4] = {3, 4, 5, 6};
}
```
```c
#include<stdio.h>
int main() {
  int arr[4] = {3, 4, 5, 6};
  for (int i=0; i<4; i++) {
    printf("%d ",arr[i]);
  }
}
```
````

---
transition: fade
zoom: 1.4
---

# Size of array?

````md magic-move

```c
#include<stdio.h>
int main() {
    int arr[] = {10, 20, 30, 40, 50};
    // answer!!!
}
```
```c
#include<stdio.h>
int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int size = sizeof(arr) / sizeof(arr[0]);
    printf("size of array: %d\n", size);
}
```
````

--- 
transition: fade
---

## Task: Reverse an array

````md magic-move
```c
#include<stdio.h>
int main () {}
```
```c
#include<stdio.h>
int main () {
  int val[5] = {1,2,3,4,5};
}
```
```c
#include<stdio.h>
int main () {
  int val[5] = {1,2,3,4,5};
  
  // assume a magic function, which reverse array
  reverse_it(val,5);
}
```
```c
#include<stdio.h>
void reverse_it(int arr[], int n) {

}
int main () {
  int val[5] = {1,2,3,4,5};
  
  reverse_it(val,5);
}
```
```c
#include<stdio.h>
void reverse_it(int arr[], int n) {
  // 2 pointers
  int l=0, r=n-1;

}
int main () {
  int val[5] = {1,2,3,4,5}
  
  reverse_it(val,5);
}
```
```c
#include<stdio.h>
void reverse_it(int arr[], int n) {
  int l=0, r=n-1;

  while(l<r) {
    
  }
}
int main () {
  int val[5] = {1,2,3,4,5}
  
  reverse_it(val,5);
}
```
```c
#include<stdio.h>
void reverse_it(int arr[], int n) {
  int l=0, r=n-1;

  while(l<r) {
    int tmp = arr[l];
    arr[l] = arr[r];
    arr[r] = tmp;

  }
}
int main () {
  int val[5] = {1,2,3,4,5}
  
  reverse_it(val,5);
}
```
```c
#include<stdio.h>
void reverse_it(int arr[], int n) {
  int l=0, r=n-1;

  while(l<r) {
    int tmp = arr[l];
    arr[l] = arr[r];
    arr[r] = tmp;

    l++;
    r--;
  }
}
int main () {
  int val[5] = {1,2,3,4,5}
  
  reverse_it(val,5);

}
```
```c
#include<stdio.h>
void reverse_it(int arr[], int n) {
  int l=0, r=n-1;

  while(l<r) {
    int tmp = arr[l];
    arr[l] = arr[r];
    arr[r] = tmp;

    l++;
    r--;
  }
}
int main () {
  int val[5] = {1,2,3,4,5};
  
  reverse_it(val,5);

  for (int i = 0; i < 5; i++){
    printf("%d ", val[i]);
  }
}
```
````

---
transition: fade
---

## Task: Reversing array

```c {all|16|all|19}
#include<stdio.h>
void reverse_it(int arr[], int n) {
  int l=0, r=n-1;

  while(l<r) {
    int tmp = arr[l];
    arr[l] = arr[r];
    arr[r] = tmp;

    l++;
    r--;
  }
}
int main () {
  int val[] = {1,2,3,4,5};
  int n = sizeof(val)/sizeof(val[0]);
  reverse_it(val,n);

  for (int i = 0; i < n; i++){
    printf("%d ", val[i]);
  }
}
```

---
transition: slide-down
layout: center
zoom: 1.4
---

# Pointers

a variable that stores address of another variable

---
transition: fade
---

## Why pointers?
- C can talk directly to hardware
- Operating systems exist
- Compilers exist
- Embedded systems exist
- Games engines exist


--- 
transition: fade 
zoom: 1.4
---

# Samples:
<br>
````md magic-move
```c 
 int h = 63;
 int *ptr = &h; //address of operator
 printf("%d" , *ptr); // dereferencing
```
```c 
 int h = 63;
 int *ptr = &h; 
 *ptr = 20;
 printf("%d" , h) 
```
````
<div v-click>
<br> Congrats!! You have successfully manipulated variable with memory address.
</div>

---
transition: slide-down
---

## Play with function

````md magic-move
```c
void change(int a) {
    a = 100;
}

int main() {
    int x = 10;
    change(x);
    printf("%d", x);
}
```
```c
void change(int *a) {
    *a = 100;
}

int main() {
    int x = 10;
    change(&x);
    printf("%d", x);
}
```
````

---
transition: slide-up
---

## Array & Pointers

````md magic-move
```c
int arr[] = {4,7,2}
printf("%d\n", arr[0]); 
```
```c
int arr[] = {4,7,2}
printf("%d\n", *arr); 
```
```c
int arr[] = {4,7,2}
printf("%d\n", *arr); 
printf("%d\n", *(arr+1)); 
```

```c
int arr[] = {4,7,2}
printf("%d\n", *arr); 
printf("%d\n", *(arr+1)); 
printf("%d\n", *(arr+2)); 
```
````

<br>
arr[0] == *(arr+0)


---
transition: fade
---

# Pointer Arithmetic

```c {all|5|6-7|all}
#include <stdio.h> 
int main() { 
  int arr[5] = { 1, 2, 3, 4, 5 }; 
  int n = sizeof(arr) / sizeof(arr[0]); 
  int* ptr = &arr[0]; 
  for (int i = 0; i < n; i++)
   printf("%d ",ptr[i]); 
   return 0; 
  }
```
<br>

ptr[i]  ==  *(ptr + i)

---
transition: slide-up
---

# Self-study
- types of pointers
- we know array follows a contiguous block of memory
but there is another data structure close to array which follows non-contiguous block of memory. 