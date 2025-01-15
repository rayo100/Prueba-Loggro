# API para Gestión de Imágenes

Esta API permite subir imágenes y realizar diversas consultas relacionadas con las imágenes subidas, como filtrar imágenes por fecha y obtener la cantidad de imágenes subidas por hora.

## Funcionalidades
1. **Subir una imagen**: Permite al usuario subir una imagen al servidor y obtener un enlace para acceder a ella.
2. **Filtrar imágenes por fechas**: Permite consultar las imágenes que fueron subidas entre dos fechas específicas.
3. **Contar imágenes subidas por hora**: Muestra cuántas imágenes fueron subidas en cada hora.

## Requisitos

Antes de ejecutar la aplicación, asegúrate de tener lo siguiente instalado:

- [Node.js](https://nodejs.org/en/) (v12 o superior)
- [MongoDB](https://www.mongodb.com/) corriendo localmente o en la nube (es necesario para almacenar las imágenes y sus metadatos).

## Configuración del proyecto

1. **Clona este repositorio**

   Abre tu terminal y ejecuta el siguiente comando:

   ```bash
   git clone https://github.com/tu_usuario/tu_repositorio.git

2. **Instalar dependencias**

   Navega al directorio del proyecto y ejecuta el siguiente comando para instalar las dependencias:

  ```bash
  cd tu_repositorio
  npm install
  ```

3. **Configuración de MongoDB**

  Si no tienes MongoDB instalado en tu máquina, puedes usar una base de datos en la nube como MongoDB Atlas o instalar MongoDB localmente.

  Si estás usando MongoDB local, asegúrate de que esté corriendo en el puerto 27017.

4. **Configurar la conexión a la base de datos**

  Si estás utilizando MongoDB Atlas, deberás configurar la cadena de conexión en el archivo config/database.js.

  Si estás usando una instalación local de MongoDB, no necesitas realizar ningún cambio en la configuración por defecto.

    mongoose.connect('mongodb://localhost:27017/nombre_base_datos', {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    });
    
## Ejecutar la API 
1. **Iniciar el servidor**

  Una vez que hayas configurado el proyecto y las dependencias, puedes iniciar el servidor con:

```bash
npm start
```
El servidor debería iniciarse en http://localhost:5000.

2. **Probar las rutas de la API**

  La API tiene las siguientes rutas disponibles:

  **POST** /uploads: Permite subir una imagen.

      Parámetros:
      - file: La imagen a subir (se debe enviar como un archivo en el cuerpo de la solicitud).
      - nombrePersona: El nombre de la persona que sube la imagen.
      
  **Respuesta:**
  Mensaje de éxito y la URL de la imagen subida.
  
  **GET** /api/images: Filtra las imágenes subidas entre dos fechas.

      Parámetros:
      - startDate: Fecha de inicio en formato YYYY-MM-DD.
      - endDate: Fecha de fin en formato YYYY-MM-DD.
      
  **Respuesta:**
  Un listado de las imágenes subidas en ese rango de fechas.
  
  **GET** /api/images-by-hour: Obtiene la cantidad de imágenes subidas por hora.

  **Respuesta:**
  Un listado con la cantidad de imágenes subidas agrupadas por hora.
  
## Uso del Frontend
Si deseas usar la interfaz de usuario proporcionada en el frontend (React), sigue estos pasos:
  
1.**Navega a la carpeta del frontend**

En tu terminal, ve a la carpeta del frontend:
    
    cd frontend

2. **Instalar dependencias**

Ejecuta el siguiente comando para instalar las dependencias del frontend:

    npm install

3. **Ejecutar el frontend**

Para iniciar el frontend, usa el siguiente comando:

    npm start
    
Esto abrirá el frontend en http://localhost:3000 en tu navegador.

## Contribuciones
Si deseas contribuir a este proyecto, por favor sigue estos pasos:

  1. Haz un fork de este repositorio.
  2. Crea una nueva rama para tu característica (git checkout -b feature/nueva-caracteristica).
  3. Haz commit de tus cambios (git commit -am 'Añadir nueva característica').
  4. Haz push a tu rama (git push origin feature/nueva-caracteristica).
  5. Abre un pull request para que podamos revisar tus cambios.
