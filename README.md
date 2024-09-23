Search an element in a matrix in C++
Here, in this page we will discuss the program to search an element in a matrix in C++ programming language. We are given with an n x n matrix, and the value of the element that need to be searched in the given matrix.We have to find the position of searched element in the matrix if it is present in it. Otherwise, we need to print “Not Found”. In the given matrix, every row and column is sorted in increasing order.

Search an element in a matrix in C++
Method 1 :
Take the size of the 2d array from the user and store them in the variables say n.
Create an 2d array of size nXn and then take elements of the matrix from the user.
Now, create a variable search that store the value of the element that need to be searched and also declare a bool type variable say flag initialized with false, that becomes true if element is present in the given matrix.
Now, run a nested for loop that will iterate over the matrix and check if current value is equal to the searched value.
If it is then print its position and makes the value of flag true, then break the loop.
Now, if flag becomes true then also break the outer loop.
After coming out from the nested loop, if flag==0 then print “Not Found”
Time and Space Complexities :
Time-Complexity :O(n^2)
Space-Complexity : O(1)
While loop in C
Search an element in a matrix
Code to Search an element in a matrix in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int n;
   cin>>n;

   int a[n][n];
   for(int i=0; i< n; i++){
     for(int j=0; j< n; j++)
       cin>>a[i][j];
   }

  int search;
  cin>>search;

  bool flag=0;

  for(int i=0; i< n; i++){

    for(int j=0; j< n; j++){
        if(a[i][j]==search)
        {
          cout<<"Element is found at ("<< i<<", "<< j<<") position";
          flag=1;
          break;
        }
    }

    if(flag==1)
    break;
  }

  if(flag==0)
  cout<<"Not found";
}
Input :
3
1 2 3
4 5 6
7 8 9
3

Output :
Element found at (0, 2) position
While loop in C
Method 2 :
Take the size of the 2d array from the user and store them in the variables say n.
Create an 2d array of size nXn and then take elements of the matrix from the user.
Now, create a variable search that store the value of the element that need to be searched and also declare a bool type variable say flag initialized with false, that becomes true if element is present in the given matrix.
And, take two variables say i and j, set i at 0 and j at n-1.
Run a loop  that will terminate when i>n
Now, If the current element is greater than x then decrease the count of j. Exclude the current column.
And If the current element is less than x then increase the count of i. Exclude the current row.
If the element is equal, then print the position, set flag = 1 and break the loop.
After coming out from the loop, if flag==0 then print “Not Found”
Time and Space Complexities :
Time-Complexity :O(n)
Space-Complexity : O(1)
Code to Search an element in a matrix in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int n;
   cin>>n;

   int a[n][n];
   for(int i=0; i>a[i][j];
   }

  int search;
  cin>>search;

  bool flag=0;
  int i=0, j=n-1;
  
  while (i < n && j >= 0)
    {
       if (a[i][j] == search)
        {
           cout<<"Element is found at ("< search)
            j--;
        else
            i++;
    }

  if(flag==0)
  cout<<"Not found";
}
Input :
3
1 2 3
4 5 6
7 8 9
3

Output :
Element found at (0, 2) position
