# Tab, Tab, Attack

## Category

General Skills

## Difficulty

Easy

## Challenge

The challenge provides an executable file with a long and unusual filename. The goal is to execute the file and retrieve the flag.

## Approach

After downloading the challenge files, I listed the contents of the directory.

```bash
ls
```

The filename was long and inconvenient to type manually. Instead of typing the entire name, I used the shell's auto-completion feature by pressing the `Tab` key.

```bash
./<first_few_characters><Tab>
```

The terminal automatically completed the filename. I then executed the file.

```bash
./<completed_filename>
```

The program printed the flag to the terminal.

## Flag

```text
picoCTF{l3arn_about_3x3cut4bl3s_4nd_5h3ll_5k1115}
```

## What I Learned

* The `Tab` key can auto-complete filenames and commands in the terminal.
* Tab completion is especially useful when working with long or complex filenames.
* Executable files can be run from the current directory using `./filename`.
* Learning shell shortcuts improves both speed and accuracy when working in Linux terminals.
