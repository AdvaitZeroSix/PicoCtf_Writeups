# RED

## Category

Forensics

## Difficulty

Easy

## Challenge

The challenge provides a PNG image named `red.png`. Although the image appears to be a plain red square, the hints suggest that there is hidden information embedded within it.

---

## Approach

The image looked completely red, so I started by checking its file type.

```bash
file red.png
```

The output confirmed that it was a valid PNG image.

Since the challenge hinted that the image wasn't as simple as it looked, I checked it for hidden data using `zsteg`, a tool commonly used to detect steganography in PNG images.

```bash
zsteg -a red.png
```

Among the output, `zsteg` revealed a Base64-encoded string hidden in the image's least significant bits (LSB).

```text
cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==
```

I decoded the Base64 string using the `base64` utility.

```bash
echo "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d
```

The decoded output revealed the flag.

---

## Flag

```text
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```

---

## What I Learned

* PNG images can hide data using Least Significant Bit (LSB) steganography.
* `zsteg` is a powerful tool for detecting and extracting hidden data from PNG and BMP images.
* Hidden data is often encoded using Base64, so checking for common encodings is a useful next step.
* Even a seemingly plain image can contain embedded information, making steganography a common technique in forensic CTF challenges.
