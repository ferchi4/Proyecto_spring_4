# Análisis de Pedidos de Instacart: Comportamiento de Compra de Comestibles

Este proyecto realiza un análisis exhaustivo de los datos de pedidos de Instacart, una plataforma de entregas de comestibles. El objetivo es comprender los patrones de compra de los clientes, identificar productos populares y analizar el comportamiento de reordenamiento para obtener insights que puedan mejorar la experiencia del usuario y optimizar la gestión del negocio.

## Objetivo
Analizar los datos de pedidos de Instacart para identificar patrones de compra, productos más populares, tasas de reorden y comportamiento de los clientes, con el fin de proporcionar información valiosa para la toma de decisiones comerciales.

## 🛠️ Tecnologías Utilizadas
- **Python:** Análisis de datos y visualización.
- **Pandas:** Manipulación y limpieza de datos.
- **NumPy:** Operaciones numéricas.
- **Matplotlib y Seaborn:** Visualización de datos.
- **Jupyter Notebook:** Entorno interactivo para el análisis.

## Estructura de Datos
El conjunto de datos consta de cinco tablas principales:
- **instacart_orders.csv:** Información de pedidos (order_id, user_id, order_dow, order_hour_of_day, days_since_prior_order)
- **products.csv:** Catálogo de productos (product_id, product_name, aisle_id, department_id)
- **order_products.csv:** Productos por pedido (order_id, product_id, add_to_cart_order, reordered)
- **aisles.csv:** Categorías de pasillos (aisle_id, aisle)
- **departments.csv:** Departamentos (department_id, department)

## Pasos Clave

### 1. **Descripción de los Datos**
   - Exploración inicial de los cinco DataFrames
   - Identificación de valores ausentes en:
     - `days_since_prior_order` (orders): 28,819 valores nulos
     - `product_name` (products): 1,258 valores nulos
     - `add_to_cart_order` (order_products): 836 valores nulos
   - Verificación de tipos de datos y estructura general

### 2. **Preprocesamiento de Datos**
   - **Verificación y corrección de tipos de datos:** Asegurar que las columnas de ID sean enteros
   - **Manejo de valores ausentes:**
     - Reemplazo de valores nulos en `product_name` con 'Unknown'
     - Identificación de patrones en valores nulos de `add_to_cart_order` (70 pedidos únicos)
     - Imputación de valores nulos en `add_to_cart_order` con 999 para casos atípicos
   - **Eliminación de duplicados:**
     - Identificación de 15 pedidos duplicados (miércoles a las 2 AM)
     - Verificación de duplicados en productos y otras tablas
   - **Validación de datos:** Confirmación de rangos razonables y consistencia

### 3. **Análisis de Datos**

#### [A] Análisis Básico
   1. **Verificación de rangos:** `order_hour_of_day` (0-23) y `order_dow` (0-6) - 0 registros fuera de rango
   2. **Pedidos por hora:** Identificación de horas pico (mañanas y tardes)
   3. **Pedidos por día:** Domingo y lunes como días de mayor actividad
   4. **Tiempo entre pedidos:** Identificación de perfiles de compra (mensual, semanal, frecuente)

#### [B] Análisis Intermedio
   1. **Comparación miércoles vs sábados:** Patrones distintos en horas pico
   2. **Distribución de pedidos por cliente:** 55,357 clientes con 1 pedido, 36,508 con 2 pedidos
   3. **Top 20 productos más populares:** Bananas, aguacates orgánicos, fresas, leche

#### [C] Análisis Avanzado
   1. **Tamaño de pedidos:** Promedio de 10.1 artículos por pedido (rango: 1-127)
   2. **Productos más reordenados:** Bananas (55,763 veces), aguacates orgánicos
   3. **Tasa de reorden por producto:** Productos con tasa del 100% (productos especializados)
   4. **Tasa de reorden por cliente:** Distribución de frecuencia de reorden por usuario
   5. **Productos prioritarios en carritos:** Análisis de productos añadidos primero

## Resultados Clave

- **Patrones temporales:** Los pedidos se concentran en horas de la mañana y fines de semana, con picos significativos los domingos y lunes.
- **Comportamiento de compra:** La mayoría de los clientes (55,357) han realizado solo un pedido, mientras que un grupo más pequeño (clientes recurrentes) muestra alta fidelidad.
- **Productos estrella:** Los productos más populares son alimentos básicos y perecederos, con bananas y aguacates orgánicos liderando las listas.
- **Reordenamiento:** Productos esenciales muestran altas tasas de reorden, indicando su importancia en la cesta básica de los clientes.
- **Prioridades de compra:** Los productos añadidos primero al carrito son consistentemente alimentos básicos, revelando patrones de compra predecibles.

## Aplicaciones de Negocio

Los hallazgos permiten:
- Optimizar la gestión de inventario basada en productos de alta demanda
- Diseñar estrategias de marketing personalizadas por segmentos de clientes
- Mejorar la experiencia del usuario mediante recomendaciones inteligentes
- Implementar programas de fidelización para clientes recurrentes
- Planificar promociones en horas y días de menor actividad

## Cómo Ejecutar
Clona este repositorio:
(https://github.com/Jeduardocastel/proyecto4)
