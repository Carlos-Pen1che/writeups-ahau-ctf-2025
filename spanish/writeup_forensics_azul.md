# Carlos Peniche (EngivineSQD)

## Write-UP — Reto Forensics “Azul”

**Flag:** `AHAU{s0l0_4zul_br0}`

---

## Resumen

Al iniciar me dieron un archivo JPG llamado **azul** junto con un hash.  
Lo primero que hice fue revisar sus metadatos para ver si la flag estaba en el copyright,  
pero claro, eso no iba a ser tan sencillo. En su lugar obtuve una pista:

> **“Solo ve el azul :)”**

Después de hacer algunas pruebas más con chunks y metadatos, me di cuenta de que en realidad la flag estaba codificada directamente en los valores del canal azul.  
Con un script simple en Python leí el canal azul, filtré los bytes imprimibles y así obtuve la flag.

---

## Pasos

### 1. Verificar hash y tipo de archivo
```bash
file azul.jpg
sha256sum azul.jpg
# El hash coincidió con el que me dieron
```

### 2. Volcar metadatos
```bash
exiftool -a -u -g1 azul.jpg
```
Salida relevante:
```
Artist    : Soqui
Copyright : Solo ve el azul :)
```
Ahí apareció la primera pista.

### 3. Confirmar que era PNG
```bash
mv azul.jpg azul.png
pngcheck -v azul.png
```

### 4. Ejecutar el script para extraer la flag
Guardé este script como `azul.py`:

```python
from PIL import Image

filename = "azul.png"

img = Image.open(filename).convert("RGB")

r, g, b = img.split()

b.save("canal_azul.png")

pixels = list(b.getdata())

flag_chars = []
for px in pixels:
    if 32 <= px <= 126:  # rango de caracteres imprimibles ASCII
        flag_chars.append(chr(px))

flag_guess = ''.join(flag_chars)

# Mostrar el posible contenido oculto
print("Posible flag/ASCII encontrado:")
print(flag_guess)
```

Lo corrí con:
```bash
python3 azul.py
```

Y obtuve la flag:
```
AHAU{s0l0_4zul_br0}
```
