# Day 06 – Linux Fundamentals: Read and Write Text Files

## Objective

Practice basic file read and write operations using Linux commands.

---

## File Creation

### Command

```bash
touch notes.txt
```

### Purpose

Created an empty file named `notes.txt`.

---

## Writing to a File

### Command

```bash
echo "Linux is the foundation of DevOps." > notes.txt
```

### Purpose

Created the first line in the file using the `>` redirection operator.

---

### Command

```bash
echo "Today I practiced file read and write operations." >> notes.txt
echo "Redirection operators help write data into files." >> notes.txt
```

### Purpose

Appended additional lines using the `>>` operator.

---

## Using tee

### Command

```bash
echo "tee command writes and displays output." | tee -a notes.txt
```

### Purpose

Displayed the text on the screen and appended it to the file at the same time.

---

## Reading the File

### Command

```bash
cat notes.txt
```

### Purpose

Displayed the complete contents of the file.

---

### Command

```bash
head -n 2 notes.txt
```

### Purpose

Displayed the first two lines of the file.

---

### Command

```bash
tail -n 2 notes.txt
```

### Purpose

Displayed the last two lines of the file.

---

## File Content

```text
Linux is the foundation of DevOps.
Today I practiced file read and write operations.
Redirection operators help write data into files.
tee command writes and displays output.
cat displays the complete file.
head shows the first lines.
tail shows the last lines.
File operations are important for logs and configs.
```

## What I Learned

* `touch` creates an empty file.
* `>` writes content and overwrites existing content.
* `>>` appends content to a file.
* `tee` writes and displays output simultaneously.
* `cat` displays the entire file.
* `head` and `tail` display specific sections of a file.

## Conclusion

Today I practiced basic Linux file operations including creating, writing, appending, and reading text files. These commands are essential for working with logs, configuration files, and automation scripts.

