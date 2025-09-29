# Carlos Peniche (EngivineSQD)

# Write-Up 1 – Todo al 100%

## El Desafío
Después del reto anterior, Sherlock olió que había recibido ayuda. Asi que me soltó:  
“Esta vez será difícil, ¡aunque pidas ayuda de alguien más!”.  
Ahí supe que el nivel de dificultad había subido.

---

## Mi Primer intento: ¡Base58, por Supuesto!
Al ver los mensajes, noté esas **mayúsculas estratégicas** que gritaban “código oculto”.  
Como Sherlock ya había usado lo de “bases sólidas”, pues fue algo sospechoso, ya que el reto anterior fue sobre bases,
agarré todas las mayúsculas, las junté, y las metí en un decoder de Base58.

El resultado:
```
ELEMENTARY YOUR DARE WAAAK!
```

¿WAAAK? Claramente, algo olía mal.  
**WATSON** se había convertido en **WAAAK**, y eso no era señal de nada bueno.  
Probé Base62 por si las moscas, pero nada… solo confirmé que Sherlock estaba tratando de hacer que me de baja.

---

## ¡Los Emojis!
Después de cuestionarme si valia la pena seguir estudiando ingenieria, me detuve y pensé:  
“Espera… ¿y si Sherlock en realidad puso eso aproposito?”.  

Ésos emojis puestos porque si. Debian tener un patron claro.  

Investigando un poco mire que los emojis pueden tratarse como valores numéricos, y que existe algo llamado **Base100**, donde cada emoji representa un número.  
¡Ahí estaba la clave!  

Agarré la secuencia completa de emojis:
```
🐸🐿🐸👌👲🐪👤🐧👡👠👪👖👘👉🐪👖👚🐧👦👣🐘👴
```

Los pasé por un decoder de Base100 y… **¡BUM!**  
La pantalla mostró:

```
AHAU{3m0jis_aR3_c0ol!}
```

---

## Conclusión: 
Al final, Sherlock intentó despistarme con mayúsculas sospechosas y temas random (¿ranas? ¿ropa para animales?).
La verdadera pista estaba en los emojis, y Base100 fue el camino.

**Moraleja:** en el mundo de la cripto, a veces lo más “innocente” es lo que esconde el secreto.  
Y sí, Sherlock, *los emojis sí son cool* 😎.

---

## Flag conseguida
```
AHAU{3m0jis_aR3_c0ol!}
```

¡Excelente! Al probarla, la flag fue correcta.  

En conclusión, mi principal error fue dejarme llevar por pistas puestas a propósito, ya que buscan despistarme.  
Sherlock nunca fue de poner mensajes bonitos o emojis (tal vez porque era algo abstracto en la época).  
Así que este fue un reto más de razonamiento.
