#### Explicación de Vue.js en el Código HTML:



###   Características
> methods: {
    agregarAlCarrito(producto) {
        if (producto.cantidad <= producto.stock) {
            this.carrito.push({...producto}); // Clonamos el objeto para evitar referencia directa
        } else {
            alert("No hay suficientes productos en stock");
        }
    }
}

### V-for
Interfaz:
Usa la directiva v-for para repetir tarjetas de productos en la interfaz.
#### 1. **Visualización de Productos:**
   - Utiliza Vue.js para dinámicamente mostrar una tarjeta para cada producto disponible.
   - Cada tarjeta muestra el nombre del producto, precio por unidad y un campo para ingresar la cantidad deseada.

#### 2. **Agregar al Carrito:**
   - Al hacer clic en el botón "Agregar" en cada tarjeta, se llama a la función **agregarAlCarrito**.
   - Verifica si la cantidad seleccionada no supera el stock disponible.
   - Agrega una copia del producto al array **carrito** si es válido; de lo contrario, muestra una alerta.

#### 3. **Visualización del Carrito:**
   - Muestra una tabla que presenta el contenido del carrito de compras.
   - La tabla incluye información como el nombre del producto, cantidad, precio unitario y el total por producto.

####  Codigo usado

- Vue.js: Para la manipulación de datos y la creación de componentes interactivos.
- Bootstrap: Para estilos y diseño responsivo.

### Vue
Creamos la App
> Vue.createApp({
    data() {
        return {
            // Array de objetos que representan los productos disponibles
            productos: [
                { nombre: "Piscina de Madera", precio: 300, cantidad: 0, stock: 10 },
                { nombre: "Pelota de Playa", precio: 20, cantidad: 0, stock: 20 },
                // ... otros productos ...
            ],
            // Array que almacena los productos seleccionados por el usuario (carrito)
            carrito: [],
        };
    },
    methods: {
        // Método para agregar un producto al carrito
        agregarAlCarrito(producto) {
            // Verificamos si hay suficiente stock antes de agregar al carrito
            if (producto.cantidad <= producto.stock) {
                // Clonamos el objeto para evitar referencia directa
                this.carrito.push({ ...producto });
            } else {
                alert("No hay suficiente stock disponible.");
            }
        }
    },
}).mount('#app');

