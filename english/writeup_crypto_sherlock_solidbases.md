# Carlos Peniche (EngivineSQD)
# Write-Up: My Solution to the Sherlock Holmes Challenge

When I faced this challenge, the first thing I did was analyze Sherlock’s famous hint: *"you don't have solid bases"*. Immediately, I thought about **numbering systems and encoding**, and those 2 hours of cryptography videos finally came in handy.

The message was: `F T m m F x I 8 8 e l R u q I u J E K T K j C a 3 Y w f E w 9 A z k m D x J 9 I 0 d h`

I noticed it contained uppercase letters (A-Z), lowercase letters (a-z), and numbers (0-9), but no symbols like +, /, =.

**The key hint "solid bases"** made me think of Base64 (but it needs + and /), Base32 (only uses A-Z and 2-7), and finally **Base62** (bingo! it uses exactly 0-9, A-Z, a-z). That was the key! Base62 is the **solid base** because it’s more fundamental and doesn’t require special symbols.

**For decoding:** I removed the spaces: `FTmmFxI88elRuqIuJEKTKjCa3YwfEw9AzkmDxJ9I0dh` and used an online Base62 decoder ([dcode.fr/base62-decoding](https://www.dcode.fr/base62-decoding)). **The result was immediate!**

**Flag obtained:** `AHAU{el3mEnTarY_mY_d3ar_W4ts0n!}`

I instantly recognized the famous Sherlock Holmes phrase: *"Elementary, my dear Watson!"*