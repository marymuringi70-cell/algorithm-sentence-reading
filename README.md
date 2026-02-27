# Sentence Analyzer Algorithm

A simple, efficient algorithm designed to perform character-by-character analysis of a sentence to determine its length, word count, and vowel count.

## 📝 Problem Description

The objective is to create a program that reads a sentence provided by the user. The sentence is processed one character at a time until a period (`.`) is encountered.

The algorithm tracks three specific metrics:

1. **Sentence Length:** The total number of characters (including spaces and the terminal period).
2. **Word Count:** The total number of words (defined as groups of characters separated by a single space).
3. **Vowel Count:** The total number of vowels (a, e, i, o, u) present in the sentence.

---

## ⚙️ Logic & Constraints

To ensure accuracy and efficiency, the algorithm follows these specific constraints:

* **Character-by-Character:** The input is processed as a stream, meaning we don't look at the whole sentence at once.
* **Termination:** The process stops immediately when the character `.` is detected.
* **Counter Initialization:** * `length_counter` starts at 0.
* `vowel_counter` starts at 0.
* `word_counter` starts at 1 (to account for the final word ending in a period rather than a space).



---

## 🚀 The Algorithm (Pseudocode)

```pascal
ALGORITHM analyze_sentence
VAR
    char_count : INTEGER := 0;
    word_count : INTEGER := 1;
    vowel_count : INTEGER := 0;
    c : CHAR;
BEGIN
    Write("Enter a sentence ending with a period:");
    
    REPEAT
        Read(c);
        char_count := char_count + 1;

        // Count Vowels (Case-Insensitive)
        IF (c = 'a' OR c = 'e' OR c = 'i' OR c = 'o' OR c = 'u' OR
            c = 'A' OR c = 'E' OR c = 'I' OR c = 'O' OR c = 'U') THEN
            vowel_count := vowel_count + 1;
        END_IF

        // Count Words based on spaces
        IF (c = ' ') THEN
            word_count := word_count + 1;
        END_IF

    UNTIL (c = '.')

    Write("Length of sentence: ", char_count);
    Write("Number of words: ", word_count);
    Write("Number of vowels: ", vowel_count);
END

```

---

## 📊 Example Trace

**Input:** `Learning is fun.`

| Character | Length | Words | Vowels |
| --- | --- | --- | --- |
| `L` | 1 | 1 | 0 |
| `e` | 2 | 1 | 1 |
| ... | ... | ... | ... |
| `     ` (space) | 9 | 2 | 3 |
| `f` | 10 | 2 | 3 |
| `.` | 15 | 3 | 5 |

---

## 🛠 Usage

This algorithm is intended for educational purposes to demonstrate:

* Use of **conditional statements** (IF/ELSE).
* Implementation of **loops** (WHILE or REPEAT/UNTIL).
* **Variable tracking** and state management.
