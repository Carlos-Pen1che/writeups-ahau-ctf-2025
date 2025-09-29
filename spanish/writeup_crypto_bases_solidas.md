# Carlos Peniche (EngivineSQD)

# Write-Up: Mi Resolución del Reto de Sherlock Holmes

Cuando me enfrenté a este reto, lo primero que hice fue analizar la famosa pista de Sherlock: *"no tienes las bases sólidas"*. Inmediatamente pensé en **sistemas de numeración y codificación** de algo me sirvio esas 2 horas de videos sobre cryptografia.

El mensaje era: `F T m m F x I 8 8 e l R u q I u J E K T K j C a 3 Y w f E w 9 A z k m D x J 9 I 0 d h`

Observé que contenía letras mayúsculas (A-Z), minúsculas (a-z) y números (0-9), pero no tenía símbolos como +, /, =.

**La pista clave "bases sólidas"** me hizo pensar en Base64 (pero necesita + y /), Base32 (solo usa A-Z y 2-7), y finalmente **Base62** (¡bingo! usa exactamente 0-9, A-Z, a-z). ¡Ahí estaba la clave! Base62 es la **base sólida** porque es más fundamental y no necesita símbolos especiales.

**Para la decodificación:** Quité los espacios: `FTmmFxI88elRuqIuJEKTKjCa3YwfEw9AzkmDxJ9I0dh` y usé un decodificador Base62 online ([dcode.fr/base62-decoding](https://www.dcode.fr/base62-decoding)). **¡El resultado fue inmediato!**

**Flag obtenida:** `AHAU{el3mEnTarY_mY_d3ar_W4ts0n!}`

Reconocí al instante la famosa frase de Sherlock Holmes: *"Elementary, my dear Watson!"*