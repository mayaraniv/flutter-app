# **Puzzled Expedition**

Category: Web

Author: Gouri M R

Answer / Flag: `MAZE{1Erdn@tc3p5nv34Lc!}`

## Problem Statement

A seemingly straightforward interface hides a secret message. Can you crack the code and unlock its mysteries? The path ahead requires a keen eye for detail. Scrutinize all information you find.

## Relevant files / links

https://puzzled-expedition.netlify.app/


## Solution

1. When examining the website's JavaScript file, you'll notice it's obfuscated, with variables and the password encoded in Unicode.
2. On decoding the Unicode one can obtain:
```
  var P = document.getElementById('password').value;
  var p = P.substring(0, 6) + P.substring(6, 17).split('').reverse().join('') + P.substring(17);
  var s = 3;

  var checks = [
    { s: 0, e: s, v: 'MAZ' },{ s: s, e: s * 2, v: 'E{1' },
    { s: s * 6, e: s * 7, v: '34L' },{ s: s * 3, e: s * 4, v: '3ct' },
    { s: s * 5, e: s * 6, v: 'rEv' },{ s: s * 4, e: s * 5, v: '@nd' },
    { s: s * 2, e: s * 3, v: 'n5p' },{ s: s * 7, e: s * 8, v: 'c!}' }
  ];

  for (var i = 0; i < checks.length; i++) {
    var check = checks[i];
    if (p.substring(check.s, check.e) !== check.v) {
      document.getElementById('message').innerHTML = 'Incorrect password';
      return;
    }
  }
```
3. Upon user input, a substring of the user entered password undergoes a reverse operation from index 6 to 16.
4. These modified user input is divided into substrings and are compared against preset strings in Unicode format.
5. From these comparisons, find the password which is compared against the reversed user input.
6. Reversing the required substring of this obtained password will reveal the correct password which is to be entered by the user, which also serves as the flag.
