# ALBA: Amanecer de un hogar

### Análisis del Mercado Solar Informal en La Habana

Proyecto de la asignatura **Introducción a Ciencias de Datos** · Universidad de La Habana
Autor: Luis Daniel

> ¿Cuántos tendría que trabajar un hogar promedio de La Habana, sin gastar nada más, para comprar un equipo solar en el mercado informal?

---

## Descripción del proyecto

Este proyecto analiza la **accesibilidad del mercado solar informal en La Habana** para un hogar con salario promedio estatal. Combina dos fuentes:

1. **Datos de mercado:** una base de datos de ofertas reales publicadas (precios, potencia, baterías, ubicación).
2. **Un caso de estudio humano:** la entrevista a una persona que representa a un hogar promedio en Cuba.

## Pregunta de investigación

**¿Qué tan accesible es el mercado solar informal en La Habana para un hogar promedio, considerando precios, oferta disponible y capacidad técnica?**

## Contexto

Cuba enfrenta una crisis energética severa con apagones prolongados. El mercado informal de equipos solares ha crecido como respuesta, pero se desconoce si es realmente accesible para un hogar con salario promedio estatal.

## Objetivos

### Objetivo general

Evaluar la accesibilidad económica y técnica del mercado solar informal en La Habana.

### Objetivos específicos

1. **Caracterizar la oferta** de equipos solares (tipos, marcas, potencias, precios) en el mercado informal habanero.
2. **Calcular el costo real** de un sistema que cubra las necesidades básicas de un hogar promedio, a partir de su consumo eléctrico.
3. **Comparar ese costo con el salario promedio estatal** para determinar la viabilidad: cuántos meses o años de salario representa.

## Datos

### Base de datos de mercado

- **Archivo:** `CSV_Solar_Alba_1_1.csv`
- **Registros:** 159 ofertas · **Variables:** 16
- **Tipo de fuente:** publicaciones recopiladas del mercado informal. Fuente(s) concreta(s): `[COMPLETAR]`
- **Fecha de recopilación:** `[COMPLETAR]`

| Variable | Descripción |
|---|---|
| `Tipo` | Kit, panel, batería, inversor, inversor + batería, estación de energía, estructura |
| `Marca`, `Modelo` | Identificación del producto (con muchos vacíos) |
| `Potencia_inversor_kW` | Potencia del inversor, en kW |
| `Potencia_panel_W`, `Cantidad_paneles` | Potencia por panel y número de paneles del kit |
| `Capacidad_bateria_kWh` | Capacidad de almacenamiento, en kWh |
| `Tecnologia` | Litio, híbrido, bifacial, etc. |
| `Precio_USD` | Precio publicado, en dólares |
| `Precio_con_instalacion_USD` | Precio con instalación (casi siempre vacío) |
| `Estado` | Nuevo o no especificado |
| `Municipio` | Ubicación de la oferta |
| `Modalidad_venta` | Kit o unidad |
| `Fuente`, `Observaciones` | Origen y detalles del anuncio |
| `Precio_por_W_USD` | Precio por vatio (solo para kits con datos de panel) |

### Caso de estudio: el hogar promedio

Entrevista a una trabajadora de la residencia estudiantil, que vive de un salario promedio, sin ingresos en divisas y sin una vivienda de gran tamaño. La entrevista recoge:

- Salario mensual y estructura de gastos básicos.
- Electrodomésticos del hogar y horas de uso (base para estimar el consumo).
- Su experiencia con los apagones.

## Metodología

1. **Limpieza de datos:** eliminar duplicados, tratar precios faltantes y unificar categorías.
2. **Caracterización de la oferta:** distribución de precios por tipo de equipo, rangos de potencia, marcas y municipios.
3. **Dimensionamiento del sistema:** estimar el consumo del hogar a partir de la entrevista y determinar la potencia de inversor y la capacidad de batería necesarias.
4. **Selección de kits comparables:** buscar en la base de datos los kits que cubran esas necesidades (opción económica, intermedia y amplia).
5. **Índice de accesibilidad:** `precio del kit ÷ salario mensual = meses de salario necesarios`, calculado con una tasa de cambio USD/CUP explícita y modificable.
6. **Visualización:** dashboard en Tableau con narrativa de datos.

## Limitaciones

- La muestra no es aleatoria ni representa todo el mercado: es lo que se pudo recopilar.
- Muchas variables tienen datos faltantes (marca, modelo, estado, precio con instalación).
- El caso de estudio es una sola persona: ilustra, pero no demuestra, la situación de todos los hogares.
