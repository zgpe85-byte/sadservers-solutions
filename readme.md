# Soluciones de SadServers

## Reto 1: 'Saint John' - ¿Por qué no arranca el servidor?
- **Problema:** El servidor web no responde en el puerto 80.
- **Diagnóstico:** Al revisar con `sudo systemctl status nginx` o comprobar los logs, descubrí que el archivo de configuración tenía un error de sintaxis en la línea 12.
- **Solución:** Corregí el punto y coma faltante, guardé el archivo y reinicié el servicio con `sudo systemctl restart nginx`. El servidor volvió a la vida.
