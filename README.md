Una barra lateral (sidebar) se puede hacer fácilmente con HTML y CSS usando `flexbox` o `grid`. Aquí tienes un ejemplo básico con `flexbox`:

### HTML

```html
<div class="layout">
  <aside class="sidebar">
    <ul>
      <li>Inicio</li>
      <li>Productos</li>
      <li>Contacto</li>
    </ul>
  </aside>
  <main class="contenido">
    <h1>Contenido principal</h1>
  </main>
</div>
```

### CSS

```css
.layout {
  display: flex;
  height: 100vh;
}

.sidebar {
  width: 250px;
  background-color: #333;
  color: white;
  padding: 1rem;
}

.contenido {
  flex: 1;
  padding: 2rem;
}
```

Este diseño crea una barra lateral a la izquierda y el contenido principal a la derecha. ¿La quieres fija, colapsable o responsive?


##barra lateral
Una barra lateral (sidebar) en HTML y CSS puede hacerse fácilmente con Flexbox o Grid, dependiendo del diseño. Aquí te muestro una forma simple con Flexbox:

✅ Ejemplo de una barra lateral fija a la izquierda
🔹HTML:

<div class="layout">
  <aside class="sidebar">
    <h2>Menú</h2>
    <ul>
      <li><a href="#">Inicio</a></li>
      <li><a href="#">Servicios</a></li>
      <li><a href="#">Contacto</a></li>
    </ul>
  </aside>

  <main class="main-content">
    <h1>Contenido principal</h1>
    <p>Aquí va el contenido de la página.</p>
  </main>
</div>
🔹CSS:

.layout {
  display: flex;
  min-height: 100vh; /* que ocupe toda la altura del viewport */
}

.sidebar {
  width: 250px;
  background-color: #2c3e50;
  color: white;
  padding: 20px;
}

.sidebar ul {
  list-style: none;
  padding: 0;
}

.sidebar li a {
  color: white;
  text-decoration: none;
  display: block;
  margin: 10px 0;
}

.main-content {
  flex-grow: 1; /* ocupa el espacio restante */
  padding: 20px;
  background-color: #ecf0f1;
}
🔁 Si quieres que sea colapsable, fija, o que aparezca con un botón (tipo "hamburguesa") en móviles, se puede hacer con más CSS o JavaScript.
¿Quieres que la barra sea:

fija al desplazarse?
responsive (que se oculte en móvil)?
animada al entrar/salir?
Puedo darte una versión más avanzada si me dices cómo la necesitas.


##para sobresalir imagen
.home__categorias > div:hover img {
    transform: scale(1.1);
    transition: transform 0.3s ease;
}

.home__categorias img {
    transition: transform 0.3s ease;
}



El símbolo `>` en CSS es un **combinador de hijo directo**. Sirve para aplicar estilos **solo a los elementos que son hijos directos** del selector anterior.

### En tu caso:

```css
.home__categorias > div:hover img {
    transform: scale(1.1);
    transition: transform 0.3s ease;
}
```

Esto significa:

> Selecciona **la etiqueta `<img>`** que esté **dentro de un `<div>`** que sea **hijo directo de `.home__categorias`**, **cuando ese `<div>` está en estado `:hover`**.

---

### Ejemplo para visualizarlo:

```html
<div class="home__categorias">
  <div class="categorias__item"> <!-- Este sí es un hijo directo -->
    <img src="imagen.jpg">
  </div>
  
  <section>
    <div class="categorias__item"> <!-- Este NO es hijo directo -->
      <img src="imagen2.jpg">
    </div>
  </section>
</div>
```

* Solo el primer `<img>` será afectado por esa regla con `>`.
* El segundo `<img>` **no será afectado**, porque su `<div>` está dentro de un `<section>` y por tanto **no es hijo directo** de `.home__categorias`.

---

### ¿Y si quitas el `>`?

Si usas esto:

```css
.home__categorias div:hover img
```

Afectará **cualquier imagen dentro de cualquier `div` descendiente** de `.home__categorias`, sin importar cuántos niveles haya entre ellos.

¿Quieres que lo limite solo a hijos directos, o debería aplicarse a cualquier profundidad?
