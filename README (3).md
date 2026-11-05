# ALBA: Amanecer de un hogar

### Mercado solar informal en La Habana: ¿quién puede pagarlo, según su sector de trabajo?

> Proyecto de la asignatura *Introducción a Ciencias de Datos*, Universidad de La Habana.

---

## Descripción del proyecto

ALBA analiza qué tan accesible es el mercado solar informal de La Habana para los trabajadores estatales de distintos sectores (educación, salud, construcción, comercio y otros). Para eso combina dos fuentes de datos: los **precios y las características de los equipos solares** que se venden, y el **salario medio de cada sector**. Con ellas calcula cuánto tiempo de salario costaría un equipo para quien depende solo de lo que le paga el Estado, sin ayuda de familiares en el exterior.

## Pregunta central de investigación

**¿Qué tan accesible es el mercado solar informal de La Habana para los trabajadores estatales de distintos sectores (educación, salud, construcción, comercio y otros), considerando precios, oferta disponible y capacidad técnica de los equipos, si solo cuentan con su salario?**

## Contexto

Cuba enfrenta una crisis energética severa con apagones prolongados. El mercado informal de equipos solares ha crecido como respuesta, pero se desconoce si es realmente accesible para quienes viven de un salario estatal, y si esa accesibilidad cambia mucho de un sector a otro.

## Objetivos

### Objetivo general
Evaluar la accesibilidad económica del mercado solar informal en La Habana para los trabajadores estatales de distintos sectores.

### Objetivos específicos
1. Caracterizar la oferta de equipos solares (marcas, potencias, capacidades y precios) en el mercado informal habanero.
2. Reunir el salario medio mensual estatal por sector de actividad, con datos oficiales.
3. Comparar, sector por sector, el precio de kits solares de referencia con el salario, usando una tasa de cambio formal y una informal, para calcular cuántos meses o años de salario representa cada equipo.

## Metodología

1. **Recopilación de datos del mercado.** Se reunieron publicaciones de venta de equipos solares (kits completos, paneles, baterías e inversores) entre marzo y el 7 de octubre de 2026, con precio, potencia, capacidad y ubicación.
2. **Limpieza.** De 187 registros se eliminaron 2 duplicados exactos, para quedar con 185. Los registros sin precio o sin precio de instalación se mantienen vacíos: el dato no estaba en la fuente y no se inventa.
3. **Conversión de precios a pesos cubanos (CUP).** Se usan dos tasas: la del Banco Central de Cuba como mercado formal (775 CUP por USD) y la de elTOQUE como mercado informal (910 CUP por USD).
4. **Salario por sector.** Se toman los salarios medios mensuales por actividad económica de la ONEI y de Cubadebate: serie 2021-2025 y datos de agosto de 2026.
5. **Kits de referencia.** Se usan dos kits con batería del CSV: el más barato (500 USD) y el mediano (2,940 USD, mediana de los 62 kits con batería y precio).
6. **Cálculo de accesibilidad.** Se divide el precio del kit en CUP entre el salario mensual de cada sector, para obtener meses o años de salario. Se calcula con el 100% del salario (mínimo teórico) y con un escenario de ahorro del 20%.

## Resultados principales

Años o meses de **salario completo** necesarios para comprar cada kit (el primer número usa la tasa formal y el segundo la informal):

| Sector | Salario mensual (CUP) | Kit más barato (500 USD) | Kit mediano (2,940 USD) |
|---|---|---|---|
| Construcción | 14,743 | 26 a 31 meses | 12.9 a 15.1 años |
| Promedio general | 7,354 | 53 a 62 meses | 25.8 a 30.3 años |
| Salud (dato de 2025) | 6,635 | 58 a 69 meses | 28.6 a 33.6 años |
| Educación | 5,824 | 67 a 78 meses | 32.6 a 38.3 años |
| Industria azucarera | 4,724 | 82 a 96 meses | 40.2 a 47.2 años |

- El salario medio general equivale a entre 8.1 y 9.5 dólares al mes.
- Con un ahorro del 20% del salario, los tiempos se multiplican por cinco.
- Los salarios de agosto de 2026 son del sistema empresarial y presupuestado; el de Salud es el promedio anual de 2025 porque no se encontró el de agosto de 2026.

## Datos

| Archivo | Contenido |
|---|---|
| `CSV_Solar_Alba_Limpio.csv` | Publicaciones de equipos solares ya depuradas (185 registros): tipo, marca, potencias, capacidad de batería, precio en USD, municipio y observaciones. |
| `CSV_Solar_Alba_Precios_CUP.csv` | Los mismos precios convertidos a CUP con la tasa formal y la informal, con el enlace de cada tasa. |
| `Analisis_Salario_Estatal_La_Habana.xlsx` | Estadísticas del salario medio estatal de La Habana (2016-2025), salario por sector y fuentes. |
| `Accesibilidad_Panel_Solar_por_Sector.xlsx` | Cálculo de meses y años de salario necesarios para comprar un kit, por sector. |

## Fuentes

- Oficina Nacional de Estadística e Información (ONEI): *Salario medio en cifras. Cuba 2025* (edición 2026) e *Indicadores seleccionados del sistema empresarial y presupuestado*, agosto de 2026.
- Cubadebate: *Cuba en datos: El salario medio en el sistema empresarial y presupuestado durante el primer semestre de 2025*.
- Banco Central de Cuba, tasa de cambio: https://www.bc.gob.cu/tasas-de-cambio
- elTOQUE, tasa del dólar: https://eltoque.com/tasas-de-cambio-cuba/dolar

## Limitaciones

- Los datos del mercado vienen de publicaciones recopiladas, no de una muestra aleatoria, y muchos registros no especifican si el equipo es nuevo o usado.
- Los salarios por sector son promedios nacionales del sistema empresarial y presupuestado. No incluyen cuentapropistas, mipymes ni remesas, y no existe un desglose por sector específico de La Habana.
- El salario de La Habana de agosto de 2026 reportado por la prensa (6,815 pesos) no pudo verificarse en el boletín original de la ONEI, por eso no se usa en el cálculo principal.
- Los kits de referencia no se dimensionaron según el consumo de un hogar concreto, y el kit más barato es un sistema pequeño.
- Las cifras de salario son nominales: no están ajustadas por inflación.
- No se realizaron entrevistas. Entrevistar a trabajadores de cada sector queda como trabajo futuro.
