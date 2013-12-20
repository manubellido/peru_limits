# peru_limits

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

> ``curl -o 'proy#1_u#2_cuadro#3.xls' 'http://censos.inei.gob.pe/cpv2007/tabulados/Tabla.asp?proy=[001-008]&u=[000-2500]&cuadro=[001-039]&exportar=xls'``
