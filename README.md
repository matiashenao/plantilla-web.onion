# Base de Servicio Oculto Tor (.onion)

Este repositorio contiene la estructura básica, minimalista y segura para desplegar un servicio oculto dentro de la red Tor. Diseñado específicamente bajo principios de auditoría de seguridad y mitigación de vectores de ataque en la capa de aplicación.

## Características de Seguridad
- **Cero JavaScript:** Mitiga ataques de desanonimización del lado del cliente.
- **Diseño Monolítico (Single Archive):** Todo el CSS está embebido para evitar peticiones HTTP concurrentes que puedan ser utilizadas para análisis de tráfico.
- **Estilo Sencillo:** Optimizado para los tiempos de respuesta y latencia nativos del enrutamiento de .Onion.

## Guía de Despliegue Rápido (En el Servidor de Destino)

Si se desea montar este archivo en un entorno Linux local para pruebas de auditoría, se siguen estos pasos:

1. **Instalar dependencias:**
   ```bash
   sudo apt update
   sudo apt install nginx tor -y
