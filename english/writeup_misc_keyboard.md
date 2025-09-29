# Carlos Peniche (EngivineSQD)
# Write-Up: Keyboard Layout Problem

## Scenario
I left my computer unlocked for a moment. When I returned, I typed my password correctly (or so I thought), but instead of the expected input, I got this mess:

`ADAG?9g1>b{g54{Ek0pAtZ!+`

I was sure I had typed the password correctly... what went wrong?

## The Problem
It turns out that while I was away, someone changed my keyboard layout to **DVORAK**. I typed my password using the **QWERTY** layout I’m used to, but the system interpreted the keystrokes as if the keyboard were in DVORAK.

## The Solution
To recover the actual password, I needed to convert the distorted string from **DVORAK** to **QWERTY**. I used an online keyboard layout converter:  
[https://awsm-tools.com/keyboard-layout](https://awsm-tools.com/keyboard-layout)

- **From:** Dvorak  
- **To:** Qwerty  
- **Input text:** `ADAG?9g1>b{g54{Ek0pAtZ!+`

## The Result
After conversion, the output was:

`AHAU{9u1En_u54_Dv0rAk?!}`

This is the actual password and also the flag.

## The Flag
`AHAU{9u1En_u54_Dv0rAk?!}`

## Conclusion
Always check your keyboard layout if your input appears distorted, especially after someone else has used your computer. The flag itself is a playful reference to the issue: "9u1En_u54_Dv0rAk", hinting at the layout problem.