# Carlos Peniche (EngivineSQD)
# Write-Up 1 – All In

## The Challenge
After the previous challenge, Sherlock suspected I had received help. So he told me:  
“This time it will be difficult, even if you get help from someone else!”  
I realized the difficulty level had increased.

---

## My First Attempt: Base58, of Course!
Seeing the messages, I noticed those **strategic capital letters** that screamed “hidden code.”  
Since Sherlock had already used the “solid bases” trick, it was suspicious, as the previous challenge was about bases. I took all the capital letters, combined them, and fed them into a Base58 decoder.

The result:
```
ELEMENTARY YOUR DARE WAAAK!
```

WAAAK? Clearly, something was off.  
**WATSON** had become **WAAAK**, and that wasn’t a good sign. I tried Base62 just in case, but nothing… it only confirmed Sherlock was trying to mess with me.

---

## The Emojis!
After questioning whether it was worth continuing studying engineering, I stopped and thought:  
“Wait… what if Sherlock put that on purpose?”  

Those emojis weren’t random. They must have a clear pattern.  

Investigating a bit, I found that emojis can be treated as numeric values, and there exists something called **Base100**, where each emoji represents a number.  
That was the key!

I took the complete emoji sequence:
```
🐸🐿🐸👌👲🐪👤🐧👡👠👪👖👘👉🐪👖👚🐧👦👣🐘👴
```

I ran them through a Base100 decoder and… **BOOM!**  
The screen showed:
```
AHAU{3m0jis_aR3_c0ol!}
```

---

## Conclusion
In the end, Sherlock tried to mislead me with suspicious capitals and random things (frogs? animal clothes?). The real clue was in the emojis, and Base100 was the solution.

**Moral:** in the world of crypto, sometimes the most “innocent” things hide the secret.  
And yes, Sherlock, *emojis are cool* 😎.

---

## Flag Obtained
```
AHAU{3m0jis_aR3_c0ol!}
```

Excellent! Upon testing, the flag was correct. In conclusion, my main mistake was following intentionally misleading hints, as they were meant to throw me off. Sherlock never left nice messages or emojis (maybe because it was a bit abstract back then). This challenge was more about reasoning than anything else.