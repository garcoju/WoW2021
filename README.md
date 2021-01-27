# WoW2021
Desafío #WoW2021 #PowerBI

http://www.workout-wednesday.com/power-bi-challenges/

W01 - Semana 1 WoW2021-w01.pbix | Conexión y modelado de datos

http://www.workout-wednesday.com/pbi-2021-w01/

***Lectura recomendada: https://twitter.com/alexdupler/status/1346711889493934081?s=20 Solución propuesta Alex Dupler
                        https://datawarehouse.es/2015/desatascar-la-cargas-hechos-claves-subrogadas.html

- Conexión origen de datos data.world
- Clave subrogada dimensión conference. Sustituir clave de texto por entero (fbs_conference en finances) ***Ventajas claves subrogadas: https://bmegias.wordpress.com/2011/01/31/%C2%BFclaves-primarias-naturales-o-subrogadas/
- Limpiar dimensiones (conference y school) ***Buenas prácticas: https://radacad.com/remove-duplicate-doesnt-work-in-power-query-for-power-bi-here-is-the-solution
- Modelo de datos (estrella) ***Buenas prácticas: Ocultar campos de relación (Ejemplo: Conference ID)

W02 - Semana 2 WoW2021-w02.pbix | Informe KPI básico

http://www.workout-wednesday.com/pbi-2021-w02/

- Columna calculada (Total Profits) en Power Query
- Convertir entero en fecha (year en finances)
- Tabla calculada (Calendario) en DAX ***Patrón estándar DAX SQLBI: https://www.daxpatterns.com/standard-time-related-calculations/
- Modelo de datos (Relación Calendario - finances)
- Tabla contenedor de medidas
- Medidas DAX: Ingresos Totales, Gastos Totales, Beneficios Totales ***Buenas prácticas: Ocultar campos total_revenues, total_expenses y Total Profits ¡¡¡No queremos medidas implícitas!!!
- Visualización: Tarjeta, Gráfico de líneas, Gráfico de barras ***Formato condicional en tarjeta y gráfico de barras de Beneficios Totales
- Agregar fondo de página (Resumen.png) ***Buenas prácticas: https://data-mozart.com/how-i-speed-up-my-power-bi-report-5x/

W03 - Semana 3 WoW2021-w03.pbix | Interactividad informe

http://www.workout-wednesday.com/pbi-2021-w03/

- Segmentación (año) ***Tip: Orden descendente (es más habitual consultar datos recientes que históricos)
- Interacción slicer (año)
- Interacción gráficos de barra (ingresos, gastos y beneficios)
- Visualización: Gráficos de líneas -> Gráficos de área
- Visualización: Colores (ingresos y gastos)

W04 - Semana 4 WoW2021-w04.pbix | Drill Trough (obtención de detalles)

http://www.workout-wednesday.com/pbi-2021-w04/

***Lectura recomendada: https://docs.microsoft.com/es-es/power-bi/guidance/dax-selectedvalue

- Página Detalle School (duplicado página Resumen) ***Tip: Ocultar páginas de detalle (navegación vía Drill Trough)
- Acción botón "Back". Modificar acción por defecto "Atrás" por "Navegación de páginas" = 'Resumen' 
- Agregar fondo de página (Conference.png)
- Visualización: Gráficos de barras por School (cambio eje Y y título del gráfico)
- Medidas DAX: Conference seleccionada y Año seleccionado. ***Tip: Ocultar medida año para selección múltiple o sin selección. https://www.sqlbi.com/articles/using-the-selectedvalue-function-in-dax/
- Agrupar medidas DAX en carpeta 0 - Filtros ***Tip: "Un sitio para cada cosa y cada cosa en su sitio". Prueba a tener un modelo con muchas medidas 🚀
- Visualización: Tarjetas (Conference y Año)
- Visualización: Botón "Back" 🏛 ***🎩: Utilizar emojis para mostrar en lugar de texto en los botones. Combinación teclas Windows + "."

NOTA: Requerimiento NO sincronizar slicer año entre página resumen y página detalle
***¿Por qué NO hacerlo?
Mostrar el slicer año en la página detalle resulta confuso al no disponer de sincronización. El usuario puede ver la página detalle filtrada por uno o varios años y el slicer año seguiría mostrando "Todas". Ver página "Detalle School" del informe
La sincronización del slicer año proporcionaría al usuario informacion del año o años seleccionados en la página detalle, evitando la necesidad de la medida DAX año seleccionado, reduciendo el número de consultas y visuales mostrados en la página y mejorando el rendimiento del informe. Ver página "Detalle School Propuesta"

NOTA: Gráficos de líneas en página detalle
En caso de navegar a la página detalle filtrando por 1 sólo año, los gráficos de líneas pueden quedar reducidos a un único punto de datos, mostrando la misma información que las tarjetas. Recomendación: Analizar las necesidades/operativa de los usuarios
