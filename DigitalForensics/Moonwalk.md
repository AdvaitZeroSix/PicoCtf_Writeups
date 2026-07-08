# 3.m00nwalk

> Decode this message from the moon.

---

## Solution:

- **Files given:** A link that downloads an **audio file**.


  - The challenge name *m00nwalk* and the description *“Decode this message from the moon”* hint toward the **moon landing**.
  - The provided hint — *“How did pictures from the moon landing get sent back to Earth?”* — directly pointed toward researching the transmission method.
  - Researching the technology used during the Apollo missions revealed that video transmissions from the moon used **SSTV (Slow-Scan Television)** — a method of encoding images as audio tones.
  - I searched online for **SSTV decoding tools** and learned about how SSTV transmits image data through audio frequencies.
  - I uploaded the provided audio file to an online SSTV decoder.
  <img width="740" height="592" alt="image" src="https://github.com/user-attachments/assets/3a9c2912-ad27-40c8-86c6-e3c9259e3a80" />

  - The decoded output revealed an **image file** containing the flag.
  
- **Flag:**  
  ```
  picoCTF{beep_boop_im_in_space}
  ```

---

## Concepts learnt:

- **SSTV (Slow-Scan Television):** A method used to transmit static images over radio using sound frequencies.  
- How **audio files** can contain **visual data** encoded as tone variations.  
- Basic understanding of how to identify SSTV-encoded signals and decode them using online tools.

---

## Notes:

- When an audio challenge references space or transmission, **think about SSTV or other radio-based encoding** methods.  
- Always start by researching key terms from the challenge (like *moon transmission* in this case).  
- Free online SSTV decoders can save time if you don’t want to set up tools locally.

---

## Resources:

- [SSTV Decoder Online](https://sstv-decoder.mathieurenaud.fr/)  
- Google searches about Apollo 11 video transmission and SSTV

---

## Incorrect Tangents:
