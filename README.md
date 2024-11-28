# find-characters
How to find files with "forbidden" characters in their names on a Linux system. Forbidden characters could be non-printable or non-ASCII characters.

## Part 1
Copy and paste these commands in the Linux Terminal.

```
LC_ALL=C find . -name '*[! -~]*'

The "forbidden" characters are returned as questions marks, e.g., "??".
```

```
LC_COLLATE=C find . -name '*[! -~]*'

The "forbidden" characters are returned as they are.
```

```
LC_ALL=C find . -name '*[![:print:]]*'

This might not work as well as the two other ones.
```

Sources:
- https://www.baeldung.com/linux/find-special-character-filenames
