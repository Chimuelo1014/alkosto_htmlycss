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
