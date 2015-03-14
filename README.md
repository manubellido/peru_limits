# peru_limits

Profit.
- Datos originales del Minam: http://geoservidor.minam.gob.pe/geoservidor/download.aspx
- Simplificados (reducción de puntos sin perder forma)
- Exportados a geojson.
=======
## Extraer datos de INEI 2007
Datos censales están publicados como hojas en MS Excel
<http://censos.inei.gob.pe/cpv2007/tabulados/>

La base de datos se puede acceder usando el cgi ``Tabla.asp`` y los parámetros:

* proyecto: ``proy``: 001-008
* ubigeo: ``u`: aparentemente 0000 incluye a todos; 0000-2500
* cuadro: ``cuadro``: 001-039
* exportar: ``xls``

Este link funciona
<http://censos.inei.gob.pe/cpv2007/tabulados/Tabla.asp?proy=001&u=0000&cuadro=001&exportar=xls>

### Comando para descargar los datos
El cgi Tabla.asp tiene límites para emitir datos. En muchos caos no es posible obtener la info
para todo un departamento. Es necesario hacer la descarga por departamento y
por provincia.

> ``curl -o 'proy#1_u#2#3_cuadro#4.xls' 'http://censos.inei.gob.pe/cpv2007/tabulados/Tabla.asp?proy=[001-008]&u=[01-25][01-20]&cuadro=[001-039]&exportar=xls'``

Convertir XLS a CSV usando comando de Gnumeric:

> ``ls 2007/ | parallel -I {} ssconvert 2007/{} 2007_csv/{.}.csv > log 2>&1``

