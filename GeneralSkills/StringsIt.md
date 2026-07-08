# strings it

## Category

General Skills

## Difficulty

Easy

## Challenge

The challenge provides a file and asks us to find the hidden flag. The challenge title hints that the `strings` command may be useful.

## Approach

First, I listed the files in the directory to identify the provided file.

```bash
ls
```

Since the challenge is named **strings it**, I used the `strings` command to extract all human-readable text from the binary.

```bash
strings strings
```

The output contained several readable strings. Scrolling through the output, I found the flag.

```text
...
picoCTF{5tRIng5_1T_827aee91}
...
```

The `strings` command is commonly used to inspect binaries for embedded text such as error messages, URLs, filenames, or even flags left in plaintext.

## Flag

```text
picoCTF{5tRIng5_1T_827aee91}
```

## What I Learned

* The `strings` command extracts printable text from binary files.
* Many beginner CTF challenges hide flags directly inside executables or binary files.
* Always try `strings` on unknown binaries before moving on to more advanced reverse engineering techniques.
