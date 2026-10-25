# Soluciones de SadServers

## Reto: 'San Juan' (Saint John) - Programa llenando el archivo de registro
- **Problema:** Un programa de prueba escribe continuamente en el archivo de registro `/var/log/bad.log` y está llenando el disco de forma crítica.
- **Descripción:** El escenario requiere encontrar el programa ejecutor y terminarlo sin eliminar el archivo de log.
- **Diagnóstico:** Utilicé el comando `sudo lsof /var/log/bad.log` (o `sudo fuser -v /var/log/bad.log`) para identificar el Identificador de Proceso (PID) del script que mantenía abierto el archivo en segundo plano.
- **Solución:** Ejecuté `sudo kill -9 [PID]` para terminar de forma forzada el proceso colgado de Python/Bash. Se verificó con `ls -lh /var/log/bad.log` que el tamaño del archivo se congeló y dejó de aumentar, deteniendo la fuga de almacenamiento con éxito.

