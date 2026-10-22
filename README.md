# itsuki-npp

Resaltado de sintaxis de [itsuki-lang](https://github.com/Apolo1061/itsuki-lang) para [Notepad++](https://notepad-plus-plus.org/). Un solo archivo, cero instalación de plugins.

![Versión](https://img.shields.io/badge/versi%C3%B3n-1.0.0-blue)
![Estado](https://img.shields.io/badge/estado-experimental-orange)
![Notepad++](https://img.shields.io/badge/Notepad%2B%2B-8.9.8.1%2B-brightgreen)
![UDL](https://img.shields.io/badge/formato-UDL%202.1-9cf)
![Licencia](https://img.shields.io/badge/licencia-MIT-green)
[![Discord](https://img.shields.io/badge/Discord-Unirse-7289DA?logo=discord&logoColor=white)](https://discord.gg/K6SEpB7Pf5)

---

## Descripción

**itsuki-npp** es una definición de lenguaje de usuario (UDL 2.1) para Notepad++ que da resaltado completo a los archivos de Itsuki: fuentes (`.suki`) y cabeceras (`.huki`).

Cubre el lenguaje completo y las 8 bibliotecas estándar, con la sintaxis verificada contra la documentación oficial del lenguaje y el código fuente del compilador:

- **Control de flujo:** `if`, `else`, `while`, `for`, `do`, `switch`, `case`, `default`, `break`, `continue`, `return`.
- **Declaraciones y POO:** `fn`, `var`, `const`, `struct`, `union`, `enum`, `typedef`, `namespace`, `using`, `class`, `public`/`private`/`protected`, `this`, `template`, `typename`, `inline`, `static`, `extern`, `asm`.
- **Tipos:** `int` (y variantes `int8`/`int16`/`int32`/`int64`, `uint8`…`uint64`), `float`, `double`, `char`, `bool`, `void`, `string`.
- **Literales:** `true`, `false`, `null`/`NULL`/`nullptr`, hex `0x`, flotantes con sufijo `f`.
- **Directivas de preprocesador:** `#include`, `#import`, `#define`, `#pragma`, `#line`.
- **Bibliotecas estándar:** funciones de `fundamental` (`println`, `malloc`, `printf`, `read_str`, `file_*`, `vector_*`…), `math` (`gcd`, `is_prime`, `fibonacci`, constantes `PI_APPROX`…) y `string` (`string_new`, `string_append`, `string_c_str`…).
- **Interpolación de cadenas:** `f"..."` y `$"..."` con su propio color, distinto de las cadenas comunes.
- **Caracteres y cadenas** con secuencias de escape.
- **Plegado de código** por llaves `{}` y comentarios `//` y `/* */`.
- **Tests:** toda función que empiece con `test_` se resalta (test runner integrado de Itsuki).

---

## Instalación

### Opción A — Copiar a la carpeta de UDLs (recomendada)

1. Descargá `userDefineLang_itsuki.xml`.
2. Copialo a la carpeta de lenguajes de usuario de Notepad++:
   - **Instalación normal:** `%AppData%\Notepad++\userDefineLangs\`
   - **Instalación portable:** `<carpeta de Notepad++>\userDefineLangs\`
3. Reiniciá Notepad++. Los `.suki` y `.huki` se resaltan solos.

### Opción B — Importar desde el diálogo

1. Menú **Lenguaje → Definido por el usuario → Definir lenguaje...**
2. Botón **Importar...** y elegí `userDefineLang_itsuki.xml`.
3. Aceptá. Asociá extensiones si el import no lo hizo (ya trae `suki huki`).

---

## Uso

Una vez instalado, abrí cualquier `.suki` o `.huki`:

~~~itsuki
#include <fundamental.huki>

struct Punto {
    var x: int;
    var y: int;
};

fn main() -> void {
    var p: struct Punto;
    var nombre: char[64];

    print("¿Cómo te llamás? ");
    read_str(nombre);

    for (var i: int = 0; i < 3; i++) {
        println(f"Hola {nombre}, i = {i}");
    }
}
~~~

Si Notepad++ no detecta la extensión, seleccioná manualmente: **Lenguaje → Definido por el usuario → Itsuki**.

---

## Paleta de colores

| Elemento | Color | Estilo |
|---|---|---|
| Control de flujo | Azul | Negrita |
| Declaraciones / POO | Celeste | Negrita |
| Tipos | Turquesa | Negrita |
| Literales (`true`, `null`) | Magenta | — |
| Preprocesador | Marrón | — |
| Bibliotecas estándar | Violeta / Marrón | — |
| Comentarios | Verde | Itálica |
| Números | Naranja | — |
| Cadenas `"` | Marrón | — |
| Caracteres `'` | Oliva | — |
| Interpolación `f"` / `$"` | Violeta | — |
| Operadores y llaves | Rojo | Negrita |

> La paleta está pensada para el tema claro por defecto de Notepad++. Si usás tema oscuro, personalizá los colores desde **Definir lenguaje... → Estilos**.

---

## Mantenedor

Hecho y mantenido por [Mateo Collar](https://github.com/mateocollar).

---

## Contribuir

- 🐛 [Reportar bugs](https://github.com/mateocollar/itsuki-npp/issues)
- 🛠️ [Enviar Pull Requests](https://github.com/mateocollar/itsuki-npp/pulls)
- 💬 [Discord de Itsuki](https://discord.gg/K6SEpB7Pf5)

---

## Licencia

MIT. Ver [LICENSE](LICENSE).