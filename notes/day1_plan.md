This is a perfect way to drill the logic into your brain. By avoiding `Counter` or `defaultdict`, you are forced to handle the "Key Check" manually every single time.

Here are 10 essential problems (expanded to 15 logic-based tasks) with their manual Python solutions.

---

### Level 1: Frequency Basics

**1. Character Frequency**
Count every character in a string.

```python
def solve(s):
    d = {}
    for char in s:
        if char in d: d[char] += 1
        else: d[char] = 1
    return d

```

**2. Word Frequency**
Count occurrences of words in a sentence.

```python
def solve(sentence):
    words = sentence.split()
    d = {}
    for w in words:
        if w in d: d[w] += 1
        else: d[w] = 1
    return d

```

**3. Vowel-Only Counter**
Count only 'aeiou', ignore everything else.

```python
def solve(s):
    d = {}
    for char in s.lower():
        if char in "aeiou":
            if char in d: d[char] += 1
            else: d[char] = 1
    return d

```

**4. Case-Insensitive Merge**
Count 'A' and 'a' together.

```python
def solve(s):
    d = {}
    for char in s.lower():
        if char in d: d[char] += 1
        else: d[char] = 1
    return d

```

**5. Numeric Frequency**
Count numbers in a list.

```python
def solve(nums):
    d = {}
    for n in nums:
        if n in d: d[n] += 1
        else: d[n] = 1
    return d

```

---

### Level 2: Grouping & Lists

**6. Group by Length**
Key = length, Value = List of words.

```python
def solve(words):
    d = {}
    for w in words:
        L = len(w)
        if L in d: d[L].append(w)
        else: d[L] = [w] # Create list with first element
    return d

```

**7. Even/Odd Grouping**
Group numbers by parity.

```python
def solve(nums):
    d = {"even": [], "odd": []}
    for n in nums:
        if n % 2 == 0: d["even"].append(n)
        else: d["odd"].append(n)
    return d

```

**8. First Letter Indexing**
Group words by their starting character.

```python
def solve(words):
    d = {}
    for w in words:
        first = w[0]
        if first in d: d[first].append(w)
        else: d[first] = [w]
    return d

```

**9. Character Existence Map**
Check if 'a'-'z' exists in string (True/False).

```python
def solve(s):
    d = {}
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    for char in alphabet:
        d[char] = False
    for char in s.lower():
        if char in d: d[char] = True
    return d

```

---

### Level 3: Logic & Search

**10. Find the Duplicate**
Return the first character that appears twice.

```python
def solve(s):
    d = {}
    for char in s:
        if char in d: return char # Found it!
        else: d[char] = 1
    return None

```

**11. Anagram Check**
Are two strings anagrams?

```python
def solve(s1, s2):
    def count(s):
        d = {}
        for c in s:
            if c in d: d[c] += 1
            else: d[c] = 1
        return d
    return count(s1) == count(s2)

```

**12. Find the Mode (Most Frequent)**

```python
def solve(nums):
    counts = {}
    for n in nums:
        if n in counts: counts[n] += 1
        else: counts[n] = 1
    
    max_val = 0
    winner = None
    for key in counts:
        if counts[key] > max_val:
            max_val = counts[key]
            winner = key
    return winner

```

**13. Unique Characters Only**
Return a list of characters that appear exactly once.

```python
def solve(s):
    counts = {}
    for c in s:
        if c in counts: counts[c] += 1
        else: counts[c] = 1
    
    result = []
    for c in s: # Keep original order
        if counts[c] == 1:
            result.append(c)
    return result

```

**14. Replace with Frequency**
Replace each char with its count so far (e.g., "apple" -> "a1p1p2l1e1").

```python
def solve(s):
    counts = {}
    result = ""
    for c in s:
        if c in counts: counts[c] += 1
        else: counts[c] = 1
        result += c + str(counts[c])
    return result

```

**15. Count Consonants**
Ignore vowels and spaces, count the rest.

```python
def solve(s):
    d = {}
    vowels = "aeiou "
    for char in s.lower():
        if char not in vowels and char.isalpha():
            if char in d: d[char] += 1
            else: d[char] = 1
    return d

```

---

### Key takeaway for Muscle Memory

In every single answer, notice the pattern:

1. **Initialize** empty dictionary.
2. **Loop** through data.
3. **Check** `if key in d`.
4. **Else** (The Deal Breaker) handle the first encounter.

**Would you like me to create a "Challenge Mode" version of these where you have to solve them with specific constraints (like using only one line of code)?**