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


