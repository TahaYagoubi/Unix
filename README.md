
# Unix Commands – Organized Notes

## 1. Files & Directories

1. **`mkdir x`** → Create a directory.
2. **`touch x.txt`** → Create a blank file.
3. **`ls`** → List files and directories.
4. **`ls Documents`** → View files inside a directory.
5. **`cd Desktop`** → Navigate to Desktop.
6. **`~`** → Home directory.
7. **`cat x.txt`** → View file content.
8. **`head x.txt`** → Display the first 10 lines of a file.

## 2. File Content & Redirection

9. **`echo "Hello" > x.txt`** → Create a file with text or overwrite its content.
10. **`echo "Hello" >> x.txt`** → Append text without deleting existing content.
11. **`cat x1.txt x2.txt > combined.txt`** → Combine files into one.
12. **`>`** → Overwrite file content.
13. **`>>`** → Append content to a file.

## 3. Counting & Editing

14. **`wc x.txt`** → Count lines, words, and bytes.
15. **`wc -l x.txt`** → Count lines only.
16. **`wc -w x.txt`** → Count words only.
17. **`wc -m x.txt`** → Count characters only.
18. **`nano x.txt`** → Edit a file (Ctrl + O save, Ctrl + X exit).

## 4. Moving, Copying & Renaming

19. **`mv todo.txt Desktop/`** → Move a file into a directory.
20. **`mv todo.txt old.txt`** → Rename a file.
21. **`cp x.txt Desktop/`** → Copy a file into a directory.
22. **`cp -r Documents Desktop/`** → Copy a directory and its content.
23. **`cp ~/Desktop/message.txt ~/Documents/`** → Copy a file using its path.
24. **`mv 2017-* 2017/`** → Move all files starting with `2017-` into the 2017 directory.

## 5. Wildcards

25. **`ls allo*`** → List files starting with `allo`.
26. **`ls *jpg`** → List files ending with `jpg`.
27. **`ls *llo*`** → List files containing `llo`.
28. **`*`** → Match zero or more characters in filenames.

## 6. Searching Files & Text

29. **`grep "x" x.txt`** → Display lines containing `x`.
30. **`egrep "x{2,3}" x.txt`** → Find lines containing 2 or 3 consecutive `x` characters.
31. **`egrep "\w" x.txt`** → Find lines containing word characters.
32. **`egrep "\d" x.txt`** → Find lines containing digits.
33. **`egrep "\s" x.txt`** → Find lines containing whitespace.
34. **`egrep -v "\w" x.txt`** → Display lines without word characters.
35. **`egrep "[aeiou]" x.txt`** → Find lines containing vowels.
36. **`egrep "[^aeiou]" x.txt`** → Find lines containing at least one non-vowel character.
37. **`egrep "^M" states.txt`** → Find lines beginning with `M`.
38. **`find . -name "file.txt"`** → Find a file by name in the current directory and its subdirectories.

## 7. Regular Expressions (Regex)

| Symbol | Meaning |
|---|---|
| `.` | Any character except newline |
| `\w` | Word character |
| `\W` | Non-word character |
| `\d` | Digit |
| `\D` | Non-digit |
| `\s` | Whitespace |
| `\S` | Non-whitespace |
| `[def]` | Any character from the set |
| `[^def]` | Any character not in the set |
| `[e-q]` | Character between e and q |
| `^` | Beginning of line |
| `$` | End of line |
| `\n` | Newline |
| `+` | One or more repetitions |
| `*` | Zero or more repetitions |
| `?` | Zero or one occurrence |
| `\|` | OR |
| `{6}` | Exactly 6 repetitions |
| `{4,6}` | Between 4 and 6 repetitions |
| `{4,}` | At least 4 repetitions |

## 8. Documentation & History

39. **`man ls`** → View command documentation.
40. **`/word`** → Search for a word inside `man` (n next, q quit).
41. **`apropos editor`** → Find commands by keyword.
42. **`history`** → View previously executed commands.

---

### Important Notes

- **`*` in filenames** (e.g., `ls *.txt`) is a shell wildcard; **`*` in regex** means zero or more repetitions of the previous element.
- **`egrep`** is equivalent to **`grep -E`**. The latter is preferred in modern scripts.
- Regex shortcuts such as `\d`, `\w`, and `\s` are not universally supported by `grep -E`. For portable commands, use `[[:digit:]]`, `[[:alnum:]_]`, and `[[:space:]]` respectively.
- **`grep`** displays matching lines, not just matching words or characters.
