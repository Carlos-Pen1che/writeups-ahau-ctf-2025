# Carlos Peniche (EngivineSQD)
## Write-UP — Forensics Challenge “Azul”  
**Flag:** `AHAU{s0l0_4zul_br0}`

At the beginning, I was given a JPG file named **azul** along with a hash. The first thing I did was check its metadata to see if the flag was in the copyright, but it wasn’t that simple. Instead, I got a hint: > **“Just look at the blue :)”** After some tests with chunks and metadata, I realized the flag was actually encoded directly in the blue channel values. With a Python script, I read the blue channel, filtered the printable bytes, and obtained the flag.

### Steps
1. Verify hash and file type:
```bash
file azul.jpg
sha256sum azul.jpg
# The hash matched the provided one
```
2. Dump metadata:
```bash
exiftool -a -u -g1 azul.jpg
```
Relevant output:
```
Artist    : Soqui
Copyright : Just look at the blue :)
```
3. Confirm it was actually PNG:
```bash
mv azul.jpg azul.png
pngcheck -v azul.png
```
4. Run the script to extract the flag. I saved this script as `azul.py`:
```python
from PIL import Image
filename = "azul.png"
img = Image.open(filename).convert("RGB")
r, g, b = img.split()
b.save("blue_channel.png")
pixels = list(b.getdata())
flag_chars = []
for px in pixels:
    if 32 <= px <= 126:  # range of printable ASCII characters
        flag_chars.append(chr(px))
flag_guess = ''.join(flag_chars)
print("Possible flag/ASCII found:")
print(flag_guess)
```
Run it with:
```bash
python3 azul.py
```
And the flag obtained:
```
AHAU{s0l0_4zul_br0}
```

