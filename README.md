# zmk-sofle — Diego (Orometh)

Configuración **ZMK** de mi teclado split **Eyelash Sofle** (CYTINFO "Sofle LCD Wireless"):
nice!nano v2 · pantalla **nice!view** · **joystick** direccional · **encoder** (knob) · **RGB** · 58 teclas 1U.

> Fork de [a741725193/zmk-sofle](https://github.com/a741725193/zmk-sofle) (el shield `eyelash_sofle` y todo el hardware es obra del creador original). Acá solo cambia **mi keymap**.

---

## 🧩 Mi layout

### Capa Base
```
 Esc  1 2 3 4 5   [joystick]   6 7 8 9 0  =
  -   Q W E R T   [joystick]   Y U I O P  [
  \|  A S D F G   [joystick]   H J K L ;  '
 SHFT Z X C V B   [joystick]   N M , . /  Del
```
- Pulgares **IZQ**: `▶`Play · `Ctrl` · `FN`(LOWER) · `Alt` · `Win`(Super)
- Pulgares **DER**: `◄`Enter · `▼`Space · `FN`(RAISE) · `Alt`(AltGr) · `Menu`
- **Esc** está arriba-izquierda; el home-pinky izq es `\|`. (El press del encoder es el **click derecho**, no Esc.)
- AJUSTE = mantener **LOWER + RAISE** juntas.

### 🖱️ Mouse
| Acción | Cómo |
|---|---|
| Mover cursor | Joystick |
| Click izquierdo | Apretar el joystick |
| Click derecho | Apretar el encoder (capa Base) |
| Click medio | LOWER + apretar el encoder |

### 🎛️ Encoder (por capa)
| Capa | Girar | Apretar |
|---|---|---|
| Base | Scroll vertical | Click derecho |
| LOWER | Scroll horizontal | Click medio |
| RAISE | Volumen | Mute |
| AJUSTE | Brillo RGB | — |

El keymap completo está en [`config/eyelash_sofle.keymap`](config/eyelash_sofle.keymap).

---

## 🛠️ Cómo generar el firmware
1. Cada `push` (o *Actions → Build ZMK firmware → Run workflow*) compila solo.
2. Cuando la corrida está en verde: abrir la corrida → **Artifacts → firmware** → descargar el `.zip`.
3. Adentro hay 3 `.uf2`:
   - `eyelash_sofle_left ...` → **mitad izquierda** (es la central, lleva ZMK Studio).
   - `eyelash_sofle_right ...` → **mitad derecha**.
   - `settings_reset ...` → solo para limpiar el pareo si hace falta.

## ⚡ Cómo flashear
1. Conectar una mitad por USB → **doble-tap** al botón de reset → aparece como pendrive `NICENANO`.
2. Arrastrar **su** `.uf2` adentro (izquierda a la izquierda, derecha a la derecha).
3. Repetir con la otra mitad. Las mitades se reconectan solas.

**Si las mitades no se hablan tras cambiar de firmware:** flashear `settings_reset` a **ambas**, y después volver a flashear izquierda + derecha.

## 🎨 Edición visual (ZMK Studio)
El firmware se compila con soporte **ZMK Studio**. Con la mitad izquierda conectada por USB,
se editan las capas en vivo desde [zmk.studio](https://zmk.studio) sin recompilar.

---

## Créditos
Hardware y shield `eyelash_sofle`: [a741725193](https://github.com/a741725193/zmk-sofle). Vendido por CYTINFO.
