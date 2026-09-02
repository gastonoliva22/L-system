# Crear poesía por generaciones

Esta herramienta permite escribir un poema que se revela poco a poco. Partís de unas palabras-guía, llamadas etiquetas, y decidís qué texto aparece cuando cada una se despliega. Al avanzar de generación, el poema incorpora nuevas capas.

## Empezar

Abrí [index.html](index.html) en el navegador. A la izquierda están los campos para crear el poema; a la derecha se ve el resultado.

1. Escribí un punto de partida en **Axioma**.
2. Definí en **Reglas** qué debe aportar cada etiqueta.
3. Elegí cuántas capas querés explorar en **Generaciones máximas**.
4. Presioná **Actualizar** cada vez que cambies el axioma, las reglas o el límite.
5. Avanzá con el botón de siguiente generación o reproducí la secuencia.

## La idea básica

Una etiqueta se escribe entre corchetes, por ejemplo `[NOCHE]`. No aparece en el poema: funciona como una invitación a desarrollar una idea.

Cada regla une una etiqueta con el texto que debe surgir de ella:

```text
NOCHE = "la noche respira sobre [CIUDAD]"
CIUDAD = "las ventanas encendidas"
```

Si el axioma es `[NOCHE]`, el poema se revela así:

| Generación | Texto generado |
| --- | --- |
| 0 | Todavía no hay texto visible. |
| 1 | la noche respira sobre |
| 2 | la noche respira sobre las ventanas encendidas |

Las etiquetas dentro de una regla, como `[CIUDAD]`, quedan preparadas para la siguiente generación. De ese modo podés construir una frase por capas.

## Escribir un poema

Probá este punto de partida:

**Axioma**

```text
[YO] [CAMINO]
```

**Reglas**

```text
YO = "yo recuerdo [MEMORIA]"

MEMORIA = "el perfume [INFANCIA] de los jazmines"

INFANCIA = "de los veranos en el patio"

CAMINO = "camino hacia [DESTINO]"

DESTINO = "el horizonte"
```

Presioná **Actualizar** y avanzá una generación a la vez. Vas a ver cómo primero aparecen las frases principales y luego sus imágenes más específicas.

## Cómo usar los controles

- **Primera generación** (`⏮`): vuelve al inicio.
- **Generación anterior** (`◀`): retrocede una capa.
- **Reproducir** (`▶` verde): avanza automáticamente hasta el límite elegido.
- **Detener** (`⏹` rojo): pausa la reproducción.
- **Siguiente generación** (`▶`): avanza una capa.
- **Última generación** (`⏭`): muestra directamente la última capa permitida.

El área **Texto generado** muestra el poema en ese momento. El **Árbol sintáctico** permite ver qué ideas ya se desplegaron y cuáles todavía pueden desarrollarse.

## Dar forma al resultado

- Para que una idea termine, escribí una regla sin etiquetas: `DESTINO = "el horizonte"`.
- Para abrir nuevas imágenes, incluí una o más etiquetas: `MAR = "el mar llama a [NOMBRE]"`.
- Podés comenzar con varias etiquetas en el axioma para entrelazar dos o más líneas del poema.
- Dejá líneas en blanco entre reglas si eso hace que el texto sea más fácil de leer.
- Las comillas son opcionales, pero ayudan a distinguir el texto de cada regla.

## Repetición y profundidad

Una etiqueta puede volver a aparecer dentro de su propia regla. Esto produce repeticiones y variaciones, útiles para crear ritmo:

```text
ECO = "vuelve [ECO]"
```

Como el texto crece en cada generación, empezá con un límite bajo —entre 3 y 5— y aumentalo solo si querés seguir desarrollando el poema. Si el resultado se vuelve demasiado largo, reducí ese número, modificá la regla repetida y presioná **Actualizar**.

## Si no aparece el resultado esperado

- Avanzá una generación más: quizá el texto está guardado dentro de una etiqueta que todavía no se desplegó.
- Revisá que el nombre de una etiqueta coincida exactamente con el nombre de su regla. Por ejemplo, `[MAR]` necesita una regla que comience con `MAR =`.
- Después de cualquier cambio, presioná **Actualizar** para generar el poema desde el comienzo.

## Detalles de escritura

Esta sección reúne algunas particularidades que pueden ser útiles al experimentar:

- El axioma también puede incluir texto directo, por ejemplo `Esta noche [MAR]`. Ese texto aparece desde la generación 0.
- Una regla puede continuar en varias líneas. Las líneas que siguen se suman a la misma regla hasta que escribís otra con el signo `=`.
- Los nombres de las etiquetas deben coincidir exactamente con el nombre de su regla. Pueden contener espacios o minúsculas: `[mar interior]` busca `mar interior =`.
- Las comillas son opcionales. Si las usás, deben encerrar todo el texto de la regla para que no aparezcan en el resultado.
- El resultado reúne los espacios y saltos de línea en un solo espacio; la herramienta no conserva versos ni sangrías.
- El signo `=` inicia una regla nueva, por lo que no conviene usarlo dentro del texto del poema. Tampoco hay alternativas con `|`, elecciones aleatorias ni caracteres de escape para corchetes.
