# Matryoshka Dolls

## Category

Forensics

## Difficulty

Easy

## Challenge

The challenge provides an image file named `dolls.jpg`. The title and hints suggest that files are hidden inside one another, similar to Russian Matryoshka dolls. The goal is to keep extracting the embedded files until the final flag is found.

---

## Approach

First, I checked the file type.

```bash
file dolls.jpg
```

The file was recognized as a JPEG image. Since the hints mentioned hidden files, I used `binwalk` to look for embedded data.

```bash
binwalk dolls.jpg
```

The output showed that additional files were embedded inside the image.

To extract all embedded files automatically, I used:

```bash
binwalk -e dolls.jpg
```

This created a directory containing the extracted files. Inside it was another image, which also contained embedded files.

I repeated the process on each extracted image:

```bash
binwalk -e <extracted_image>
```

After several rounds of extraction, I eventually reached a directory containing a text file named `flag.txt`.

Displaying its contents revealed the flag.

```bash
cat flag.txt
```

---

## Flag

```text
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}
```

---

## What I Learned

* Files can be embedded inside other files multiple times.
* `binwalk` is a useful tool for detecting and extracting embedded files.
* The `-e` option automatically extracts embedded data.
* Some forensic challenges require repeating the same extraction process several times until the final hidden file is reached.
