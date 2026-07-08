# Secret of the Polyglot

## Category

Forensics

## Difficulty

Easy

## Challenge

The challenge provides a file that appears to be a PNG image. However, the title "Secret of the Polyglot" suggests that the file may contain more than one type of data. The goal is to uncover the hidden flag.

## Approach

First, I checked the file type.

```bash
file flag2of2-final.png
```

Although the file was recognized as a PNG image, the challenge title hinted that it was a polyglot file-a file that is valid as multiple formats.

Next, I opened the image to see if anything unusual was visible.

```bash
xdg-open flag2of2-final.png
```

The image looked normal and did not reveal the flag.

To investigate further, I renamed the file with a `.pdf` extension and opened it as a PDF.

```bash
mv flag2of2-final.png flag2of2-final.pdf
```

Opening the file as a PDF revealed the hidden document containing the flag.

A polyglot file works because it is carefully crafted to satisfy the format requirements of multiple file types simultaneously.

## Flag

```text
picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}
```

## What I Learned

* A polyglot file is valid as more than one file format.
* The `file` command identifies the primary file type but may not reveal embedded or alternate formats.
* Challenge titles often provide important hints about the intended solution.
* Trying different file extensions or viewers can uncover hidden content in forensic challenges.
