# Trivial Flag Transfer Protocol

## Category

Forensics

## Difficulty

Easy

## Challenge

The challenge provides a packet capture (`.pcapng`) file containing network traffic. The goal is to analyze the capture and recover the hidden flag.

---

## Approach

Since the challenge title references the **Trivial File Transfer Protocol (TFTP)**, I opened the packet capture in Wireshark.

To quickly locate the relevant packets, I applied the following display filter:

```text
tftp
```

The filtered packets showed a TFTP file transfer. Following the transfer, I noticed that a file was being transmitted between the client and the server.

To reconstruct the transferred file, I used Wireshark's export feature:

```
File → Export Objects → TFTP
```

Wireshark listed the transferred file. I selected it and saved it locally.

After opening the exported file, it contained the flag.

---

## Flag

```text
picoCTF{tftp_1snt_t0ugh_t0_b34t}
```

---

## What I Learned

* TFTP is a simple file transfer protocol that does not provide encryption.
* Wireshark can reconstruct files transferred over supported protocols.
* The **Export Objects** feature is extremely useful for extracting files from network captures.
* When analyzing packet captures, filtering by the protocol mentioned in the challenge title is often the quickest way to find the solution.
