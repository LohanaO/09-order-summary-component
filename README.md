## RETO N°9 100 DAYS OF PROYECTS 

### 09-Order-summary-component

<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1714251911171/b4c9d876-d1f4-4156-83ab-80039d704393.jpeg?auto=compress,format&format=webp" alt="Texto alternativo" width="800"/>

### Tecnologias
[![HTML](https://img.shields.io/badge/HTML5-orange?style=flat&logo=html5)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
[![CSS](https://img.shields.io/badge/CSS3-blue?style=flat&logo=css3)](https://developer.mozilla.org/en-US/docs/Web/CSS)

### Ver demo

[Demo](https://lohanao.github.io/09-order-summary-component/)

## Desafio
Nuestra misión será crear un componente orden de pedido, usando HTML y CSS; y lograr que se parezca lo más posible al diseño.
### Los usuarios deberían poder:
1-Ver un diseño óptimo en pantallas grandes(1200px), medianas(768px) y pequeñas(375px).

2-Ver un color diferente(hover) al pasar el mouse sobre el botón principal.

3-Bonus: Visualizar una ventana modal después de presionar el botón principal.
### Importante:

Agrega un icono favicon al proyecto.

Agrega una URL fácil de recordar (ej. 09-order-summary-component).

Agrega un título al proyecto (ej. Order Summary Component - Frontend Club).

Bonus: Agrega un archivo readme.md al proyecto.

## Solución
### Resolución con HTML y CSS
Este proyecto consiste en un componente de resumen de pedido que muestra la información básica de un pedido, como el plan seleccionado y el precio. Además, incluye un botón para proceder al pago y un enlace para cancelar el pedido. También se implementa un modal que se abre al hacer clic en el botón "Proceed to Payment".

### Estructura HTML
El contenido de la tarjeta se estructuró utilizando elementos HTML semánticos para mejorar la accesibilidad y el SEO del sitio web. A continuación se muestra una vista general de la estructura HTML utilizada:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="css/style.css" />
    <link rel="shortcut icon" href="images/favicon-32x32.png" type="image/png">
    <title>Order Summary Component - Frontend Club</title>
  </head>
  <body>
    <main>
      <article class="card">
        <img class="hero" src="images/illustration-hero.svg" alt="Hero image" />

        <h2>Order Summary</h2>

        <p>
          You can now listen to millions of songs, audiobooks, and podcasts on
          any device anywhere you like!
        </p>

        <div class="plan">
          <div>
            <img src="images/icon-music.svg" alt="Music icon" />
          </div>
          <div>
            <h4>Annual Plan</h4>
            <p>$59.99/year</p>
          </div>
          <a href="#">Change</a>
        </div>
        <button id="open-Modal" class="btn">Proceed to Payment</button>
        <a  href="#" class="cancel">Cancel Order</a>
        <div id="myModal" class="modal">
            <div class="modal-content">
                <span class="close">&times;</span>
                <p>Abriendo Modal.....</p>
            </div>
        </div>
      </article>
    </main>
  </body>
  <script src="js/app.js"></script>
</html>

```


Para lograr el diseño deseado de la tarjeta de producto, sigue estos pasos:

### Definir estilos básicos para el contenedor y la tarjeta:
#### El contenedor debe tener un estilo para centrar su contenido verticalmente y horizontalmente. Para lograr esto use display: flex, justify-content: center y align-items: center.
#### La tarjeta en movil tiene un ancho maximo de 350px y 400 en pantallas mas grandes
```
@import url('https://fonts.googleapis.com/css2?family=Red+Hat+Display:ital,wght@0,300..900;1,300..900&display=swap');
:root{
    --pale-blue: hsl(225, 100%, 94%);
    --bright-blue: hsl(245, 75%, 52%);
    --very-pale-blue: hsl(225, 100%, 98%);
    --desaturated-blue: hsl(224, 23%, 55%);
    --dark-blue: hsl(223, 47%, 23%);

}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body{
    background-color: var(--pale-blue);
    font-family: 'Red Hat Display', sans-serif;
    font-size: 16px;
    
}

main{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 10px;
}

.card{
    display: flex;
    flex-direction: column;
    width: 100%;
    align-items: center;
    gap: 1.2rem;
    max-width: 320px;
    background-color: white;
    border-radius: 20px;
    overflow: hidden;
}

.hero{
    width: 100%;
    margin-bottom: 10px;
}

h2{
    text-align: center;
    color: var(--dark-blue);
    font-weight: 900;
}

.card p{
    text-align: center;
    width: 85%;
    color: var(--desaturated-blue);
    font-weight: 500;
    line-height: 1.5rem;
}

.plan{
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 85%;
    padding: 15px;
    background-color: var(--very-pale-blue);
    border-radius: 10px;
}

.plan img{
    width: 40px;
}

.plan h4{
    color: var(--dark-blue);
    font-weight: 900;
}

.plan p{
    color: var(--desaturated-blue);
    font-weight: 500;
    
}

.plan a{
    color: var(--bright-blue);
    font-weight: 700;
    text-decoration: none;
}

.btn{
    width: 85%;
    padding: 15px;
    background-color: var(--bright-blue);
    color: white;
    font-weight: 700;
    font-size: 16px;
    border: none;
    border-radius: 10px;
    box-shadow: 0 5px 20px 5px hsla(239, 76%, 43%, 0.3);
    transition: all 1s ease;
}

.btn:hover{
    cursor: pointer;
    opacity: 0.8;
}

.cancel{
    color: var(--desaturated-blue);
    font-weight: 700;
    text-decoration: none;
    font-size: 16px;
    margin-bottom: 25px;
    transition: all 1s ease;
}

.cancel:hover{
    cursor: pointer;
    color: var(--dark-blue);
}

.modal {
    display: none; 
    position: fixed; 
    z-index: 1; 
    left: 0;
    top: 0;
    width: 100%; 
    height: 100%; 
    overflow: auto; 
    background-color: rgb(0,0,0); 
    background-color: rgba(0,0,0,0.5); 
}

.modal-content {
    background-color: #fefefe;
    margin: 15% auto; 
    padding: 20px;
    border: 1px solid #888;
    width: 80%; 
    border-radius: 10px;
    position: relative;
}

.close {
    position: absolute;
    color: #aaa;
    right: 10px;
    top: 0;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}

@media screen and (min-width: 768px) {
    .card{
        max-width: 400px;
    }

    .modal-content {
        width: 400px;
    }
    
}


 ```

## Funcionalidad JavaScript
Se implementa una funcionalidad JavaScript para controlar la apertura y el cierre del modal. Al hacer clic en el botón "Proceed to Payment", se abre el modal, y al hacer clic en la "x" o fuera del modal, se cierra.
 ```
const modal = document.getElementById("myModal");
const btn = document.getElementById("open-Modal");
const span = document.getElementsByClassName("close")[0];

btn.onclick = function () {
    modal.style.display = "block";
};

span.onclick = function () {
    modal.style.display = "none";
};

window.onclick = function (event) {
    if (event.target == modal) {
        modal.style.display = "none";
    }   
}
 ```
## Conclusiones
En conclusión,  Este proyecto me permitió practicar la estructura básica de HTML, la aplicación de estilos con CSS y la manipulación del DOM con JavaScript. Espero que este README te haya proporcionado una buena comprensión del proyecto y de mi proceso de desarrollo.

¡Gracias por revisar mi proyecto!

Para cualquier pregunta o comentario, no dudes en contactarme a través de mi correo electrónico: lohaorellano13@gmail.com
