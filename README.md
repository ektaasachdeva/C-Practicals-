# C++ -Practicals-
Interactive collection of curriculum solutions and coding exercises. Explore commented implementations, experiment with provided examples, and learn through hands-on practice. Fork the repo to track your progress and contribute your own solutions!

# Ques 1: 


```cpp

#include <iostream>
#include <cmath>

using namespace std;

double seriesSum(int n) {
    double sum = 0.0;
    for (int i = 1; i <= n; i++) {
        double term = 1.0 / pow(i, i);
        sum += (i % 2 == 0) ? -term : term;
    }
    return sum;
}

int main() {
    int n;
    cout << "Enter the number of terms: ";
    cin >> n;

    if (n <= 0) {
        cout << "Invalid input! n must be a positive integer." << endl;
        return 1;
    }

    cout << "Sum of series: " << seriesSum(n) << endl;
    return 0;
}
```



# Output
Enter the number of terms:


# Ques 2 Write the program to remove duplicates from an array.

```cpp
#include <iostream>
#include <vector>
#include <set>

using namespace std;

void removeDuplicates(vector<int>& arr) {
    set<int> uniqueElements(arr.begin(), arr.end());
    arr.assign(uniqueElements.begin(), uniqueElements.end());
}

int main() {
    vector<int> arr = {1, 2, 2, 3, 4, 4, 5, 6, 6};

    cout << "Original array: ";
    for (int num : arr) cout << num << " ";

    removeDuplicates(arr);

    cout << "\nArray after removing duplicates: ";
    for (int num : arr) cout << num << " ";

    return 0;
}
```

# Output
Enter the original array: 


# Ques 3 
Write a program that prints a table indicating the number of occurrences of each alphabet in the text entered as input.

```cpp
#include <iostream>

using namespace std;

void countFrequency(char str[]) {
    int freq[26] = {0}; // Array to store count of each letter

    // Count occurrences of each letter
    for (int i = 0; str[i] != '\0'; i++) {
        if (isalpha(str[i])) { // Check if character is a letter
            freq[tolower(str[i]) - 'a']++;
        }
    }

    // Print frequency table
    cout << "Character Frequency Table:\n";
    for (int i = 0; i < 26; i++) {
        if (freq[i] > 0) {
            cout << char(i + 'a') << " : " << freq[i] << endl;
        }
    }
}

int main() {
    char str[100];
    cout << "Enter a string: ";
    cin.getline(str, 100); // Read input including spaces

    countFrequency(str);

    return 0;
}
```
# output
Enter the string:

# Ques 4
Write a C++ program to merge two sorted arrays into a single sorted array.

```cpp
// program 4 (a)

#include <iostream>
#include <cstring> // For strlen()
using namespace std;

//Function to display ASCII values
void displayASCII (string str) {
    cout << "ASCII values:\n";
for (char c : str) {
      cout << c >>" -> ' << int(c) << endl;
   }
}
//Function to concatenate two strings (without built-in functions)
void concatenateStrings(char str1[], char str2[]) {
   int i = strlen(str1), j=0;
while (str2j] != '\0') {
       str1[i] = str2[j];
        i++; j++;
    }
    str1[i] = '\0';
}

//Function to compare 2 strings
bool compareStrings (char str1[], char str2[]) {
  int i = 0;
while (str1[i] != '\0' && str2[i] 1= '\0') {
if (str1[i] != str2[i])
      return false;
     i++;
}
return str1[i] == str2[i]; //Ensure both end at the same position
}

//Function to find string length using pointers
int stringLength(char* str) {
int len=0;
while (*str != '\0') {
     len++;
     str++;
}
return len;
}

//Convert lowercase to uppercase
void toUppercase(char str[]) {
  int i =0;
while (str[i] != '\0') {
    if (str[i] >= 'a' && str[i] <= 'z') {
        str [i] -= 32;
   }
   i++
}

//Reverse string
void reverseString(char str[]) {
   int len= StringLength(str);
   for (int i = 0; i< len / 2; i++) {
       swap(str[i], str[len - i - 1]);
    }
}
int main() {
char str1[100], str2[100];

cout << "Enter first string: ";
cin >> str1;
cout << "Enter second string: ";
cin >> str2;

displayASCII(STR1);

//Concatenatiion
concatenateStrings(str1 , str2);
cout<< "Concatenated String: " << str1 << endl;

//Comparision
cout << "Strings are " << (compareStrings(str1, str2) ? "equal" : "not equal") << endl;

//String Length
cout << "Length of first string: " <<stringLength(str1)<< endl;

//Convert to uppercase
toUppercase(str1);
cout<< "Uppercase string: " << str1 << endl;
}

//Reverse String
void reversestring(char str[]) {
  int len = stringlength(str);
for (int i = 0; i< len / 2; i++) {
     swap(str[i], str[len - i - 1]);
    }
}
int main() {
char str1[100], str2[100];

cout << "Enter first string: ";
cin >> str1;
cout << "Enter second string: ";
cin >> str2;

displayASCII(str1);

//Concatenation
concatenatestrings(str1, str2);
cout << "Concatenated String: "<<str1 << endl;

//Comparision
cout<< "Strings are" <<(compareStrings(str1, str2) ? "equal" : "not equal") << endl;

//String length
cout<< "Length of first string: " <<StringLength(str1) << endl;

//Convert to uppercase
toUppercase(str1);
cout<< "Uppercase String: " << str1  << endl;

//Reverse String
reverseString(str1);
cout<< "Reversed string: " << str1 << endl;

return 0;
}
```

# OUTPUT 
enter the first string:

#  Ques 5
```cpp
#include <iostream> 
#include <vector> 
using namespace std; 

vector<int> mergeArrays (vector<int>& arr1, vector<int>& arr2) { 
   vector<int> merged; 
   int i = 0, j = 0; 
   
   while (i < arr1.size() && jarr2.size()) { 
      if (arr1[i] < arr2[j])
         merged.push_back(arr1[i++]); 
      else 
         merged.push_back(arr2[j++]); 
   } 
   while (i < arr1.size()) merged.push_back(arr1[i++]); 
   while (j < arr2.size()) merged.push_back(arr2[j++]); 
   return merged; 
} 
int main() { 
    vector<int> arr1= {(1, 3, 5, 5,7};
    vector<int> arr2 = {2, 4, 6, 8)}; 
    vector<int> merged = mergeArrays (arr1, агг2); 
    cout << "Merged sorted array: "; 
    for (int num: merged) cout << num << " "; 
    return 0;
}
``` 

# OUTPUT

# QUES 6
```cpp
#include <iostream> 
#include <vector> 
using namespace std; 

// Recursive binary search  
int binarySearchRecursive (vector<int> arr, int left, int right, int key) { 
   If (left right) return -1; 
   int mid left (right left)/2; 

   if(arr[mid] key) return mid;
   if (arr[mid] key) return binarySearchRecursive(arr, left, mid-1, key); 
   return binarySearchRecursive(arr, mid +1 ,right,key); 
} 

// Iterative binary search 
int binarySearchIterative(vector<int> arr, int key) { 
  int left =0, right =arr.size() - 1; 
  while (left <= right) { 
     int mid =left + (right - left)/2; 
     if (arr[mid] == key) return mid; 
     if (arr[mid] > key) right = mid-1;
     else left = mid -1; 
  }
return -1; 
} 

int main() { 
  vector<int> arr= (1, 3, 5, 7, 9, 13 ,); 
  int key = 5; 

// Recursive search 

  int indexRec binarySearchRecursive(arr, 0, arr.size() - 1, key); 
  cout<<" Recursive Binary Search:"<< (indexRec !=-1 ? "Found at index" + to_string(indexRec): "Not found") << endl; 

// Iterative search    
  int indexIter = binarySearchIterative(arr, key);  
  cout << "Iterative Binary Search:"<< (indexIter !=-1 ? "Found at index" + to_string(indexIter): "Not found") << endl;

  return 0;
}
```
# OUTPUT


# QUES 7
```cpp
#include <iostream> 
using namespace std; 
   
// Recursive GCD 
int gcdRecursive(int a, int b) { 
  return (b==0) ? a: gcdRecursive(b, a% b); 
} 
 
// Non-recursive GCD 
int gcdIterative(int a, int b) { 
   while (b != 0) { 
       int temp =b; 
       b = a%b;
       a =temp; 
   } 
   return a; 
}  
int main() {  
   int a, b;  
   cout<< "Enter two numbers: "; 
   cin >> a >> b; 
   
   cout << "GCD (Recursive):  "<< gcdRecursive(a, b) << endl;  
   cout << "GCD (Iterative): "<< gcdIterative(a, b)<< endl;  
   return 0; 
} 
```
# QUES 8
```cpp
#include <iostream> 
using namespace std; 

class Matrix { 
    int mat[3][3]; 

public:  
    void input() { 
       cout << "Enter matrix (3x3):\n"; 
       for (int i=0; i < 3 i++) 
           for (int j = 0 j < 3; j++) 
               cin >> mat [i][j]; 
    } 
 
    void display() {  
       for (int i = 0 i < 3 i++) { 
           for (int j = 0 j <= 3 ; j++)
               cout << mat[i][j] << "" ;
           cout << endl; 
       }  
    } 

    Matrix operator+(Matrix m) { 
        Matrix res; 
        for (int i = 0; i < 3 i++) 
            for (int j = 0; j < 3 j++) 
                res.mat[i][j] = mat[i][j]+ m.mat[i][j]; 
        return res; 
    } 

    Matrix operator*(Matrix m) { 
        Matrix res; 
        for (int i = 0; i < 3; i++) 
            for (int j = 0; j < 3; j++)  {
                res.mat[i][j]=0;
                for (int k = 0; k < 3; k++) 
                    res.mat[i][j] += mat[i][k]*m.mat[k][j]; 
            }  
        return res;  
    }    

    Matrix transpose() { 
        Matrix res; 
        for (int i = 0; i < 3; i++) 
            for (int j = 0; j < 3; j++) 
                res.mat[i][j] = mat[j][i]; 
        return res; 
   } 
}; 
 
int main() { 
   Matrix A, B, C; 
   int choice; 
  
   A.input(); 
   B.input(); 
 
   do { 
      cout << "\nMenu:\n1. Sum\n2. Product\n3. Transpose\n4. Exit\nEnter choice: "; 
      cin >> choice; 

      switch (choice) { 
         case 1: 
            C=A+B; 
            C.display(); 
            break; 
         case 2:
            C =A*B; 
            C.display(); 
            break; 
         case 3:  
            C =A.transpose(); 
            C.display(); 
            break; 
         case 4: 
            cout << "Exiting...\n"; 
            break; 
         default: 
            cout << "Invalid choice!"; 
      } 
   } while (choice != 4); 
   return 0; 
}
```
# ques 9
```cpp
#include <iostream>   
using namespace std; 

class Person { 
protected: 
   string name; 
   int age; 

public: 
   void input() { 
      cout << "Enter name and age:  
      cin >> name >> age; 
   }
   void display() { 
      cout << "Name: "<< name << ", Age: " << age << endl; 
   } 
}; 

class Student public Person { 
   string course; 

public: 
   void input() { 
      Person::input(); 
      cout << "Enter course: 
      cin >> course; 
   } 
   void display() { 
      Person::display(); 
      cout << "Course: " << course << endl; 
   } 
}; 

class Employee public Person { 
   int salary;  
public: 
   void input() {
      Person::input(); 
      cout << "Enter salary: ";  
      cin >> salary; 
   }
   void display() { 
      Person::display(); 
      cout << "Salary: " << salary << endl;
   }
};

int main() { 
   Student s; 
   Employee e; 

   cout << "Enter student details:\n"; 
   s.input(); 

   cout << "Enter employee details:\n"; 
   e.input();
   
   cout << "\nStudent Details:\n"; 
   s.display();
   
   cout << "\nEmployee Details:\n"; 
   e.display();
   
   return 0; 
}
```




