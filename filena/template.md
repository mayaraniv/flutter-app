# **Invisible Trail**

Category: Web

Author: Gouri M R

Answer / Flag: `MAZE{fL465H1p_Ie3E}`

## Problem Statement

You've stumbled upon a mysterious website. Your task is to uncover the hidden flag that's been cleverly concealed within the depths of this website.
## Relevant files / links

https://ieee-flagship-ctf-web.netlify.app/

## Hint

The key might not be readily apparent. Explore every corner.


## Solution

1. The message displayed on the website hints that the flag is hidden from virtual wanderers or automated bots.

2. The flag is hidden within the seemingly disallowed path: /theflag.html. Upon inspection of robots.txt file (append /robots.txt to the website's URL) one can find the directive:
User-agent: *
Disallow: /flag.html

This suggests that /theflag.html is hidden from web crawlers.

3. To access the flag, take the direct route by appending "/theflag.html" to the website's URL. This action will lead to the page where the flag is located.
