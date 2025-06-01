
---

### 🔢 **Problem Recap**

You're given:

* A **hidden word** `S` (like the real word in Wordle),
* A **guess word** `T` (the player's guess),
* Both are 5 letters long.

You have to compare them **character by character**, and generate a new string `M` of length 5:

* `G` (for "Good") if the letter in the guess is **correct** and in the **correct position**.
* `B` (for "Bad") if the letter in the guess is **incorrect** or in the **wrong position**.

---

### ✅ **Code Breakdown**

```cpp
#include <iostream>   // For input and output
using namespace std;
```

* Includes necessary header for input/output and uses the standard namespace.

---

```cpp
int main() {
    int T;
    cin >> T;
```

* Reads the number of test cases `T`.

---

```cpp
    while (T--) {
```

* A loop that runs `T` times (one for each test case).

---

```cpp
        string S, T;
        cin >> S >> T;
        string M = "";
```

* Reads two 5-letter strings:

  * `S` = the hidden word,
  * `T` = the guess word.
* Initializes an empty string `M` which will hold the result (like "GGBBG").

---

```cpp
        for (int i = 0; i < 5; i++) {
            if (S[i] == T[i]) {
                M += 'G';
            } else {
                M += 'B';
            }
        }
```

* Loops over each of the 5 characters.
* Compares the characters at the same index (`i`) in both strings:

  * If they match, appends `'G'` to `M`.
  * If not, appends `'B'`.

---

```cpp
        cout << M << endl;
    }
```

* After finishing the comparison, prints the resulting `M` string for that test case.

---

```cpp
    return 0;
}
```

* Standard return statement for the `main` function.

---

### 🧪 **Example**

Input:

```
1
HELLO
HEART
```

Steps:

* Compare `H` with `H` → G
* Compare `E` with `E` → G
* Compare `L` with `A` → B
* Compare `L` with `R` → B
* Compare `O` with `T` → B

Output:

```
GGBBB
```

This C++ program solves a modified Wordle game by comparing a hidden word S and a guess word T, both 5 letters long. For each test case, it checks each character at the same position in both strings. If the characters match, it appends 'G' to the result string M; otherwise, it appends 'B'. This process builds a string of length 5 indicating which letters are correct and in the correct position.

The program runs for multiple test cases as specified by the input. After comparing the characters for each test case, it prints the resulting string M. This gives immediate feedback for each guess, showing correct letters (G) and incorrect ones (B) at each position, much like the original Wordle game but without tracking misplaced letters.
