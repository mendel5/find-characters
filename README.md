# find-characters
How to find files with "forbidden" characters in their names on a Linux system. Forbidden characters could be non-printable or non-ASCII characters.

## Part A
Copy and paste these commands in the Linux Terminal.

### Part 1
```
LC_COLLATE=C find . -name '*[! -~]*'

The "forbidden" characters are returned as they are.
```

### Part 2
```
LC_ALL=C find . -name '*[! -~]*'

The "forbidden" characters are returned as questions marks, e.g., "??".
```

```
LC_ALL=C find . -name '*[![:print:]]*'

This might not work as well as the two other ones.
```

Sources:
- https://www.baeldung.com/linux/find-special-character-filenames

## Part B
Another good idea could be to list all filenames with a command like `tree`, then save this output to a file, then analyze this file with another command.
When it is done like this, the file system does not have to be scanned so frequently because scanning the whole filesystem takes a lot of time.
