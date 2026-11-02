# Respuestas — Interactive Profile Card

## 1. ¿Por qué escribimos `onPress={handlePress}` y no `onPress={handlePress()}`?

Con handlePress le damos la función a React Native para que la use cuando se toque el botón. Con handlePress() la función se ejecuta luego luego, antes de tocar nada.

## 2. ¿Cuál es la diferencia entre `Button` y `Pressable`? ¿Cuándo usarías cada uno?

Button es un botón ya hecho y fácil de usar, pero casi no se le puede cambiar el diseño. Pressable se puede diseñar como uno quiera, así que se usa cuando necesito un botón con mi propio estilo.

## 3. ¿Qué recibe la función `style` de `Pressable` y qué regresa? Da un ejemplo.

Recibe pressed, que dice si el botón está presionado, y regresa los estilos que se van a usar. Ejemplo: style={({ pressed }) => [styles.button, pressed && styles.pressed]}.

## 4. ¿Por qué no puedes cambiar una variable de estado directamente (`isFollowing = true`) y qué haces en su lugar?

Porque si la cambias directo, la pantalla no se actualiza. Hay que usar su función: setIsFollowing(true).

## 5. ¿Por qué `followers` no es un segundo `useState`? ¿Qué es un *valor derivado*?

Porque se puede calcular con isFollowing, así que no hace falta guardarlo aparte. Un valor derivado es un valor que se calcula a partir del estado.

## 6. ¿Qué significa *controlled input* en `TextInput`? ¿Qué dos props lo hacen controlado?

Significa que el texto del input siempre viene del estado. Lo hacen controlado value y onChangeText.

## 7. ¿Por qué `selectedSkills.push(skill)` está mal cuando `selectedSkills` es estado? Escribe el código correcto.

Porque push cambia el mismo arreglo y React no se da cuenta del cambio. Lo correcto es crear un arreglo nuevo:

```js
setSelectedSkills([...selectedSkills, skill]);
```
