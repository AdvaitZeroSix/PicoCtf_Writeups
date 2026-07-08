# Inspect HTML

## Category

Web Exploitation

## Difficulty

Easy

## Challenge

The challenge provides a webpage and asks us to find the hidden flag. Since the title is "Inspect HTML", it suggests that the flag may be hidden within the page's source code.

## Approach

After opening the webpage, there was nothing unusual displayed on the screen. The next step was to inspect the page source.

There are multiple ways to do this:

* Right-click on the webpage and select **View Page Source** or **Inspect**.
* Press `Ctrl + U` to view the page source.
* Press `F12` to open the browser's Developer Tools.

While examining the HTML source, I found a comment containing the flag.

```html
<!-- picoCTF{...} -->
```

The flag was hidden inside the HTML comments, making it invisible on the webpage but still present in the source code.

## Flag

```text
picoCTF{1n5p3t0r_0f_h7ml_8113f7e2}
```

## What I Learned

* HTML comments are not visible on the webpage but remain in the page source.
* Browser Developer Tools are essential for web security challenges.
* Always inspect the source code of a webpage, as sensitive information may be unintentionally exposed.
