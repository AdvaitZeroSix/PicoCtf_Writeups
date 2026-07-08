# 2.Tunn3l V1s10n

> We found this file. Recover the flag.  
> Hint: Weird that it won't display right...

---

## Solution:

- **Files given:** `tunn3l_v1s10n` (no extension).

- **Initial recon:**
  - I checked the file metadata with `exiftool` and confirmed it's a BMP image (1134×306, 24-bit).  
  - I inspected the file with `binwalk` which found some odd signatures but no obvious embedded files to extract.  
  - I opened the file in a hex editor (hexed.it) and verified the BMP header and raw bytes — there were no obvious appended files or magic headers for embedded archives.
<img width="1139" height="303" alt="image" src="https://github.com/user-attachments/assets/b00f32f4-68e8-4d46-8fc6-a419378547a5" />

- **Approaches tried (in order):**
  1. **Data appending / file structure exploits** — checked for appended archives or extra magic but nothing useful was found.  
  2. **Masking and filtering** — considered imagefilter based stego but deferred deeper learning until other options were exhausted.  
  3. **Steganography tools** — tried common tools (`steghide`, `zsteg` where applicable) but they did not reveal a payload.  
  4. **Dimension / pixel-interpretation manipulation (the winning method)** — based on the hint “won't display right”, I suspected the image's width/height or row stride might be wrong. I returned to the hex editor to experiment with header fields rather than extracting hidden files.

- **Dimension manipulation details:**  
  - Changing the **width** field repeatedly corrupted the file, so I switched to experimenting with the **height** field.  
  - I iteratively modified the BMP height value and opened the image each time to see how it rendered. I tried values like `400, 450, 500, ...` and found corruption starting around `850` pixels. I then tested heights starting from `810` upward.  
  - At a height of **830 pixels**, the image rendered correctly and revealed the hidden flag printed inside the image.
<img width="915" height="666" alt="image" src="https://github.com/user-attachments/assets/22428b10-ab87-4832-a293-8d45bf495998" />

- **Flag:**  
```
  picoCTF{qu1t3_a_v13w_2020}
```
---

## Concepts learnt:

- File type metadata (via `exiftool`) can be correct even when an image's internal dimension fields are intentionally wrong.  
- Not all stego is about embedded files; sometimes the data is present but misinterpreted due to incorrect header fields (dimension/stride). Changing image dimensions can re-interpret the pixel stream correctly.  
- Iterative, small changes (start coarse then refine) are useful when brute-forcing header fields — here, stepping height upwards and testing revealed the correct value (830).

---

## Notes / practical tips:

- When an image “won’t display right”, try reinterpreting dimensions (swap width/height) or tweak the header height/width values by small amounts.  
- Always keep a backup of the original file before editing headers. Use a hex editor that preserves file structure and lets you revert easily.  
- If width changes immediately corrupt the file, try adjusting height or padding instead — BMP row padding can be subtle.  

---

## Resources:

- `exiftool`, `binwalk`, hex editors (e.g., hexed.it) and Image viewers (default OS viewer) are handy for these tasks.  
- Steganography writeups discussing dimension/stride manipulation and BMP internals.

---

## Incorrect Tangents:

- Relying solely on appended-file checks (binwalk) — this was a useful first step but would not have found the pixel-interpretation trick.
