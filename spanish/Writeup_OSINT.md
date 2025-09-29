# Carlos Peniche(EngivineSQD)

# Writeup – OSINT

## Contexto

Una antigua **hacienda henequenera** a las afueras de Mérida está próxima a ser demolida.  
Sin embargo, su historia esconde un secreto financiero. Durante una ponencia en el **Museo de la Isla de Cozumel**, el investigador conocido como **“Huachohacker25”** reveló la existencia de una **página de registro de producción** del antiguo dueño.  
Según él, los números en dicho registro contenían un **código cifrado**, una pista que llevaba al **contacto de una empresa fantasma** utilizada para **lavado de dinero**.

Mi objetivo era claro: **encontrar el contacto directo de la empresa fantasma**.

---

## Primeras Pistas

Lo primero que hice fue buscar a **Huachohacker25** en distintas redes sociales.  
Finalmente, encontré una cuenta en **Instagram**, donde publicó una **imagen del registro antiguo** de la hacienda.  
[📷 Ver imagen del registro](https://ibb.co/84GLvt4n)

En ese registro observé **números anómalos**: dos series numéricas de longitudes distintas, una de **tres dígitos** y otra de **un solo dígito**.

La primera hipótesis que surgió fue que se trataba de un **número telefónico**.

---

## Múltiples Combinaciones

Comencé a **probar combinaciones** de los números, intentando formar números con **ladas** de Mérida o Yucatán.  
Tras aproximadamente **20 intentos**, me di cuenta de que ese enfoque no conducía a nada.

Volví a analizar el patrón:  
- **Dos series de números**.  
- La primera serie no correspondía a Yucatán.  

Esto contradecía el reto, por lo que solo quedaba una opción:  
**los 10 números que tenían en común el dígito único**.

---

## Combinación Final

Al **unir los 10 números** obtuve un **número telefónico de Cozumel**, lo cual hizo perfecto sentido, dado que el reto mencionaba el **Museo de la Isla de Cozumel**.

El número final fue:

```
987 140 6063
```

Al agregarlo como contacto, apareció el nombre de la empresa fantasma:

```
papadzules mara sansores
```

---

## Flag

Finalmente, formulé el hallazgo como flag, resultando **correcto**:

```
AHAU{papadzules_mara_sansores}
```
