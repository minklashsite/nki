 agregar una tercera galería en el futuro:

```markdown
# Galerías de Imágenes - Guía de Implementación

Este proyecto muestra cómo implementar múltiples galerías de imágenes en una página HTML utilizando JavaScript. Actualmente, el proyecto cuenta con dos galerías, y esta guía proporcionará los pasos necesarios para agregar una tercera galería de manera eficiente.

## Estructura del Proyecto

- `index.html`: Contiene la estructura HTML de las galerías.
- `script.js`: Contiene el código JavaScript para manejar las galerías.

## Añadiendo una Tercera Galería

Para añadir una tercera galería, seguiremos un proceso similar al utilizado para las primeras dos galerías. A continuación se describen los pasos detallados:

### 1. Actualizar el HTML

Añadimos una nueva sección en `index.html` para la tercera galería.

```html
<h2 style="text-align: center; color: white;">Tercera Galería</h2>
<div id="image-gallery-3" class="d-flex flex-column align-items-center">
    <div class="d-flex justify-content-center align-items-center mb-3">
        <button class="btn btn-primary" onclick="prevImage3()">&#8592;</button>
        <div class="image-wrapper mx-3">
            <img id="current-image-3" src="images/third_image1.jpg" alt="Galería 3" class="img-fluid">
        </div>
        <button class="btn btn-primary" onclick="nextImage3()">&#8594;</button>
    </div>
    <div id="image-description-3" class="description-wrapper text-center"></div>
</div>
```

### 2. Actualizar el JavaScript

Duplicamos y modificamos el código JavaScript para manejar la tercera galería. 

#### Paso 1: Añadir las imágenes y descripciones

En `script.js`, definimos un nuevo array para las imágenes de la tercera galería.

```javascript
const images3 = [
    { 
        src: 'images/third_image1.jpg', 
        title: 'Tercera Imagen 1', 
        price: '$150.00 mxn', 
        promo: '3x2 en promoción $400.00 mxn', 
        prepTime: '12 minutos', 
        ingredients: 'Descripción de la tercera imagen 1' 
    },
    { 
        src: 'images/third_image2.jpg', 
        title: 'Tercera Imagen 2', 
        price: '$180.00 mxn', 
        promo: 'No Aplica', 
        prepTime: '18 minutos', 
        ingredients: 'Descripción de la tercera imagen 2' 
    },
    // Añade más imágenes y descripciones aquí
];
```

#### Paso 2: Definir el índice y las funciones de actualización

Definimos una nueva variable para el índice de la tercera galería y las funciones para actualizar la imagen y manejar la navegación.

```javascript
let currentIndex3 = 0;

function updateImage3() {
    const imgElement = document.getElementById('current-image-3');
    const descriptionElement = document.getElementById('image-description-3');
    imgElement.src = images3[currentIndex3].src;
    descriptionElement.innerHTML = `
        <h2 style="text-align: center;">${images3[currentIndex3].title}</h2>
        <p><strong style="color: red;">Precio:</strong> ${images3[currentIndex3].price}</p>
        <p><strong style="color: red;">Promoción:</strong> ${images3[currentIndex3].promo}</p>
        <p><strong style="color: red;">Tiempo de preparación:</strong> ${images3[currentIndex3].prepTime}</p>
        <p><strong style="color: red;">Ingredientes:</strong> ${images3[currentIndex3].ingredients}</p>
    `;
}

function prevImage3() {
    if (currentIndex3 > 0) {
        currentIndex3--;
        updateImage3();
    }
}

function nextImage3() {
    if (currentIndex3 < images3.length - 1) {
        currentIndex3++;
        updateImage3();
    }
}
```

#### Paso 3: Inicializar la nueva galería al cargar la página

Asegúrate de que la función `updateImage3` se llame cuando la página se cargue.

```javascript
window.onload = function() {
    updateImage();
    updateImage2();
    updateImage3();
};
```

### Consideraciones Finales

1. **Mantenimiento del Código**: Asegúrate de que cada galería tenga nombres únicos para las variables y funciones para evitar conflictos.
2. **Escalabilidad**: Si planeas agregar más galerías en el futuro, considera refactorizar el código para que sea más dinámico, utilizando clases y objetos para evitar la duplicación de código.
3. **Estilo y Responsividad**: Revisa que el CSS mantenga un diseño coherente y responsivo al agregar nuevas galerías.

## Conclusión

Siguiendo estos pasos, puedes añadir fácilmente una tercera galería a tu proyecto. Asegúrate de probar cada galería después de realizar cambios para garantizar que todo funcione correctamente.

¡Buena suerte y feliz codificación!
```

Este README.md proporciona una guía clara y detallada sobre cómo agregar una tercera galería, asegurando que el usuario entienda cada paso del proceso
