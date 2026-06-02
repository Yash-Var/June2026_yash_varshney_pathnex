# Linux Commands and File Permissions - Notes

## Introduction

Today, I learned some basic Linux commands and file permission concepts. These commands help in navigating directories, managing files, and controlling access to files and folders.

---

## 1. Current Working Directory (`pwd`)

* `pwd` stands for **Print Working Directory**.
* It displays the full path of the directory where I am currently working.

### Example

```bash
pwd
```

Output:

```bash
/home/yash/Documents
```

---

## 2. Listing Files and Directories (`ls`)

### `ls -la`

* Lists all files and directories.
* Displays hidden files as well.
* Hidden files start with a dot (`.`).

```bash
ls -la
```

### `ls -l`

* Displays files and directories in a detailed format.
* Shows:

  * Permissions
  * Owner
  * Group
  * File size
  * Date and time
  * File name

```bash
ls -l
```

### `ls -lh`

* Similar to `ls -l`.
* Displays file sizes in a human-readable format such as KB, MB, and GB.

```bash
ls -lh
```

---

## 3. Hidden Files

* In Linux, files starting with a dot (`.`) are hidden.

### Example

```bash
mv notes.txt .notes.txt
```

* The file becomes hidden.
* To view hidden files:

```bash
ls -la
```

---

## 4. Renaming Files Using `mv`

* The `mv` command is used to move files.
* It can also be used to rename files.

### Example

```bash
mv old.txt new.txt
```

* This renames `old.txt` to `new.txt`.

---

## 5. Linux Permission System

Every file and directory has permissions for three categories:

### Owner

* The user who owns the file.

### Group

* Users belonging to the same group.

### Others

* All other users on the system.

Permission Structure:

```text
Owner | Group | Others
```

Example:

```text
rwx r-x r--
```

---

## 6. Permission Values

| Permission | Symbol | Value |
| ---------- | ------ | ----- |
| Read       | r      | 4     |
| Write      | w      | 2     |
| Execute    | x      | 1     |

---

## 7. Meaning of Permissions

### Read (4)

* Allows viewing the contents of a file.

### Write (2)

* Allows modifying or editing a file.

### Execute (1)

* Allows running a file as a program or script.

---

## 8. Permission Combinations

### 7 = 4 + 2 + 1

```text
rwx
```

Permissions:

* Read
* Write
* Execute

### 6 = 4 + 2

```text
rw-
```

Permissions:

* Read
* Write

### 5 = 4 + 1

```text
r-x
```

Permissions:

* Read
* Execute

### 4 = Read Only

```text
r--
```

Permissions:

* Read

---

## 9. Changing Permissions (`chmod`)

* `chmod` stands for **Change Mode**.
* Used to modify file permissions.

### Example

```bash
chmod 755 script.sh
```

Meaning:

* Owner = 7 (rwx)
* Group = 5 (r-x)
* Others = 5 (r-x)

---

## 10. Changing File Owner (`chown`)

* `chown` stands for **Change Owner**.
* Used to change the ownership of a file.

### Example

```bash
chown yash file.txt
```

---

## 11. Changing Group (`chgrp`)

* `chgrp` stands for **Change Group**.
* Used to change the group associated with a file.

### Example

```bash
chgrp developers file.txt
```

---

## Summary

### Commands Learned

* `pwd` → Show current directory
* `ls -la` → List all files including hidden files
* `ls -l` → Detailed file information
* `ls -lh` → Detailed information with human-readable sizes
* `mv` → Move or rename files
* `chmod` → Change file permissions
* `chown` → Change file owner
* `chgrp` → Change file group

### Important Concepts

* Hidden files start with `.`
* Linux permissions are divided into:

  * Owner
  * Group
  * Others
* Permission values:

  * Read = 4
  * Write = 2
  * Execute = 1
* Common permission combinations:

  * 7 = rwx
  * 6 = rw-
  * 5 = r-x
  * 4 = r--
