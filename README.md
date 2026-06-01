# scripting-task-guvi-
# Shell Scripting Task

## Task Description

### Task 1

Create a shell script to:

* Print the HTTP status code of `guvi.in`
* Print a Success/Failure message based on the HTTP response code

### Task 2

Given a file, replace all occurrences of the word **"give"** with **"learning"** from the **5th line onwards**, only in lines that contain the word **"welcome"**.

---

## Technology Used

* Shell Scripting
* Git Bash
* GitHub

---

## Task 1: HTTP Status Code Check

### Script

```bash
#!/bin/bash

status=$(curl -o /dev/null -s -w "%{http_code}" https://www.guvi.in)

echo "HTTP Status Code: $status"

if [ "$status" -eq 200 ]; then
    echo "Success: Website is reachable"
else
    echo "Failure: Website returned error code $status"
fi
```

### Execution

```bash
chmod +x task1.sh
./task1.sh
```

### Sample Output

```text
HTTP Status Code: 200
Success: Website is reachable
```

---

## Task 2: Word Replacement Using sed

### Input File

```text
line1
line2
line3
line4
welcome give
hello give
welcome give give
welcome
```

### Command Used

```bash
sed -i '1,4!{/welcome/s/give/learning/g}' sample.txt
```

### Output File

```text
line1
line2
line3
line4
welcome learning
hello give
welcome learning learning
welcome
```

---

## Explanation

* `1,4!` → Applies the operation from line 5 onwards.
* `/welcome/` → Selects only lines containing the word "welcome".
* `s/give/learning/g` → Replaces all occurrences of "give" with "learning".

---

## Screenshots

### Task 1 Output

* Screenshot showing execution of `task1.sh`

### Task 2 Before Replacement

* Screenshot showing original file content

### Task 2 After Replacement

* Screenshot showing modified file content

---

## Author

**Vijaya Sarathy**

