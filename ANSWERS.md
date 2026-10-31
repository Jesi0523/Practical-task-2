# QUESTIONS AND ANSWERS

## ENGLISH

1. Why do we write `onPress={handlePress}` and not `onPress={handlePress()}`?

- Because if we write it with the parentheses, the function will execute immediately when the application starts. On the other hand, without the parentheses, the function only executes when the user clicks the `Button` or `Pressable`.

2. What is the difference between `Button` and `Pressable`? When would you choose each one?

- `Button` only allows us to add text using `title` and doesn't have a `style` prop, while `Pressable` can be customized however you like. I would choose `Button` for quick actions like clicking a button to submit a form. I would use `Pressable` when I need a custom design.

3. What does the `style` function of `Pressable` receive and what does it return? Give an example.

- It receives an object with the boolean argument `{pressed}` which tells us if a component is being pressed at that moment, and it returns a style object or an array of styles. For example, to change the opacity when pressed it would be like this: `style={({ pressed }) => ({ opacity: pressed ? 0.5 : 1 })}`

4. Why can you not change a state variable directly (`isFollowing = true`) and what do you do instead?

- Because it doesn't notify React that the value changed, so you don't see the changes on the screen in real time. Instead, you must use the setter function provided by `useState` to properly update the value.

5. Why is `followers` not a second `useState`? What is a *derived value*?

- A *derived value* is a value that is calculated from another value. That is why `followers` doesn't need a second `useState`, because it depends directly on `isFollowing`.

6. What does *controlled input* mean for `TextInput`? Which two props make it controlled?

- A *controlled input* means a React state controls the text shown in the `TextInput` and saves what is typed. The two props that control it are `value={message}`, which shows the current state value, and `onChangeText={(newText) => setMessage(newText)}`, which updates the state every time the user types.

7. Why is `selectedSkills.push(skill)` wrong when `selectedSkills` is state? Write the correct code.

- Because `.push()` modifies the original array directly instead of creating a new one, so it doesn't show the change in real time.
- Correct code: `setSelectedSkills([...selectedSkills, skill])`.

## ESPAÑOL

1. ¿Por qué escribimos `onPress={handlePress}` y no `onPress={handlePress()}`?

- Porque si lo escribimos con los paréntesis la función se va a ejecutar al iniciar la aplicación, en cambio sin los paréntesis la función se ejecuta cuando el usuario hace click al `Button` o `Pressable`.

2. ¿Cuál es la diferencia entre `Button` y `Pressable`? ¿Cuándo elegirías cada uno?

- El `Button` solamente nos permite poner texto con `title` y no tiene la propiedad de `style`, mientras que el `Pressable` lo puedes personalizar a tu gusto. Elegiría `Button` para acciones rápidas como presionar un botón al enviar un formulario. `Pressable` lo usaría cuando necesite hacer un diseño personalizado.

3. ¿Qué recibe la función `style` de `Pressable `y qué devuelve? Da un ejemplo.

- Recibe un objeto con el argumento booleano `{pressed}` el cual nos indica si un componente está siendo presionado en ese momento, y devuelve un objeto o un arreglo de estilos. Por ejemplo, para cambiar la opacidad al presionarlo seria así: `style={({ pressed }) => ({ opacity: pressed ? 0.5 : 1 })}`.

4. ¿Por qué no se puede cambiar una variable de estado directamente (`isFollowing = true`) y qué se debe hacer en su lugar?

- Porque no le avisa a React que el valor cambió y no se ven los cambios en tiempo real en la pantalla. Lo que se debe hacer es usar la función actualizadora que nos da el `useState` para poder actualizar el valor.

5. ¿Por qué `followers` no es un segundo `useState`? ¿Qué es un *derived value*?

- Un *derived value* es un valor que se calcula a partir de otro valor o estado que ya existe, es por ello que `followers` no necesita un segundo `useState` porque depende directamente de `isFollowing`.

6. ¿Qué significa *controlled input* para `TextInput`? ¿Cuáles dos props lo controlan?

- El *controlled input* significa que un estado de React controla el texto que se muestra en el `TextInput` y guarda lo que se escribe. Las dos propiedades que lo controlan son `value={message}`, el cual muestra el valor actual del estado, y `onChangeText={(newText) => setMessage(newText)}`, el cual actualiza el estado cada vez que el usuario escribe.

7. ¿Por qué es incorrecto usar `selectedSkills.push(skill)` cuando `selectedSkills` es un estado? Escribe el código correcto.

- Porque `.push()` modifica directamente el arreglo original en lugar de crear uno nuevo y React no muestra el cambio en tiempo real.
- Código correcto: `setSelectedSkills([...selectedSkills, skill])`.