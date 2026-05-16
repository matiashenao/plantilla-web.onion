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
   
2. **Configurar el Servidor Web (Nginx):**
Mover el archivo index.html a /var/www/html y configurar Nginx para que solo escuche en la interfaz local (127.0.0.1:80), bloqueando el acceso desde la IP pública del servidor.

3. **Configurar Tor (/etc/tor/torrc):**
Descomentar o añadir las siguientes líneas para apuntar al servidor local:

Plaintext
HiddenServiceDir /var/lib/tor/hidden_service/
HiddenServicePort 80 127.0.0.1:80
Iniciar Servicios:

   ```bash
sudo systemctl restart nginx
sudo systemctl restart tor
Obtener la dirección .onion:
   ```
   ```bash
sudo cat /var/lib/tor/hidden_service/hostname
   ```
---

### Próximo paso para tu Git
Basta con que crees esos dos archivos dentro de tu carpeta, abras tu terminal y ejecutes los comandos clásicos para subirlo a tu perfil:

```bash
git init
git add .
git commit -m "Estructura inicial de servicio oculto seguro"
git remote add origin TU_URL_DE_GITHUB
git branch -M main
git push -u origin main
