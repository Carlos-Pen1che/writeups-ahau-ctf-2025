# Carlos Peniche (EngivineSQD)

# Write-Up: Problema de Distribución del Teclado

## Escenario
Dejé mi computadora desbloqueada por un momento. Cuando regresé, escribí mi contraseña correctamente (o eso creía), pero en lugar de la entrada esperada, obtuve esta masacre:

`ADAG?9g1>b{g54{Ek0pAtZ!+`

Estaba seguro de que había escrito bien la contraseña... ¿qué salió mal?

## El Problema
Resulta que, mientras estaba ausente, alguien cambió la distribución de mi teclado a **DVORAK**.  
Escribí mi contraseña usando la distribución **QWERTY** a la que estoy acostumbrado, pero el sistema interpretó las pulsaciones como si el teclado estuviera en DVORAK.

## La Solución
Para recuperar la contraseña real, necesité convertir la cadena distorsionada de **DVORAK** a **QWERTY**.  
Usé un conversor de distribución de teclado en línea:  
[https://awsm-tools.com/keyboard-layout](https://awsm-tools.com/keyboard-layout)

- **Desde:** Dvorak  
- **Hacia:** Qwerty  
- **Texto de entrada:** `ADAG?9g1>b{g54{Ek0pAtZ!+`

## El Resultado
Después de la conversión, la salida fue:

`AHAU{9u1En_u54_Dv0rAk?!}`

Esta es la contraseña real, y también resulta ser la flag.

## La Flag
`AHAU{9u1En_u54_Dv0rAk?!}`

## Conclusión
Siempre verifica la distribución de tu teclado si tu entrada aparece distorsionada, especialmente después de que alguien más haya usado tu computadora. La flag en sí es una referencia juguetona al problema: "9u1En_u54_Dv0rAk", insinuando el problema de distribución.

---
