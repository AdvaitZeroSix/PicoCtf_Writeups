# Warmed Up

## Category

General Skills

## Difficulty

Easy

## Challenge

The challenge asks us to convert the hexadecimal number `0x3D` (base 16) into its decimal (base 10) equivalent.

## Approach

The prefix `0x` indicates that the number is written in hexadecimal. To convert it to decimal, we can either calculate it manually or use a programming language.

Hexadecimal digits use base 16, where:

* `3` = 3
* `D` = 13

Calculating the decimal value:

```text
3 × 16¹ + 13 × 16⁰
= 3 × 16 + 13
= 48 + 13
= 61
```

Another quick way is to use Python:

```python
print(0x3D)
```

Output:

```text
61
```

The challenge requires submitting the answer in the `picoCTF{}` format.

## Flag

```text
picoCTF{61}
```

## What I Learned

* The `0x` prefix denotes a hexadecimal number.
* Hexadecimal is a base-16 numbering system.
* Python automatically interprets hexadecimal literals and converts them to decimal when printed.
