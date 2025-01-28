
---

# IgnTattoo - Social Platform for Tattoo Artists & Designers 🎨⚡

**IgnTattoo** es una **plataforma social móvil** diseñada exclusivamente para tatuadores y diseñadores de tatuajes. Permite a los artistas mostrar su trabajo, conectarse con clientes, gestionar citas y colaborar en proyectos. Desarrollada con tecnologías modernas como **React Native**, **Expo**, **Express.js** y **PostgreSQL**, ofrece una experiencia fluida y profesional.




---

## ✨ Características Principales
- **Portafolio de Artistas**: Subida de imágenes de alta calidad con metadatos específicos (estilo, ubicación en el cuerpo, tipo de tinta).
- **Descubrimiento de Artistas**: Búsqueda por ubicación, estilo (#Tradicional, #Acuarela, #Blackwork) y disponibilidad.
- **Interacción Social**: Sistema de likes, comentarios y mensajes directos entre usuarios.
- **Gestión de Citas**: Agendamiento de citas, recordatorios y seguimiento de estado.
- **Proyectos Colaborativos**: Espacios para diseñadores y tatuadores para colaborar en proyectos personalizados.
- **Autenticación Segura**: JWT con roles de usuario (artista/cliente).

---

## 🛠 Tecnologías Utilizadas
**Frontend**:  
- **React Native (Expo SDK)**: Desarrollo multiplataforma.
- **NativeWind**: Estilos con enfoque utility-first.
- **Reanimated/GestureHandler**: Animaciones fluidas.
- **Image Picker/Camera**: Manejo de imágenes y fotos.

**Backend**:  
- **Node.js + Express**: API RESTful.
- **PostgreSQL**: Base de datos relacional.
- **Cloudinary** (opcional): Almacenamiento de imágenes.
- **JWT**: Autenticación y autorización.

**DevOps**:  
- **GitHub Actions**: CI/CD Pipeline.
- **Expo Application Services**: Actualizaciones OTA.
- **Docker** (opcional): Contenerización.

---

## 🚀 Instalación

### 1. Clonar el repositorio
```bash
git clone https://github.com/bealed0n/Capstone.git
cd Capstone
```

### 2. Instalar dependencias

#### Backend
1. Navega a la carpeta del backend:
   ```bash
   cd backend-ign-tattoo-app
   ```
2. Instala las dependencias:
   ```bash
   npm install
   ```
3. Inicia el servidor de desarrollo:
   ```bash
   npm run dev
   ```

#### Frontend
1. Navega a la carpeta del frontend:
   ```bash
   cd ../frontend-ign-tattoo-app
   ```
2. Instala las dependencias:
   ```bash
   npm install
   ```
3. Inicia el proyecto Expo:
   ```bash
   npx expo start
   ```

---

## 🗃️ Estructura de la Base de Datos (PostgreSQL)

El proyecto utiliza **PostgreSQL** como base de datos. A continuación, se detallan las tablas principales:

### 1. Usuarios (`users`)
| Columna     | Tipo         | Descripción                           |
| ----------- | ------------ | ------------------------------------- |
| id          | SERIAL       | Identificador único del usuario       |
| username    | VARCHAR(50)  | Nombre de usuario                     |
| email       | VARCHAR(100) | Correo electrónico del usuario        |
| password    | VARCHAR(255) | Contraseña cifrada                    |
| bio         | TEXT         | Descripción del usuario               |
| profile_pic | VARCHAR(255) | URL de la imagen de perfil            |
| created_at  | TIMESTAMP    | Fecha de creación de la cuenta        |
| role        | VARCHAR(50)  | Rol del usuario (por ejemplo, 'user') |

### 2. Citas (`appointments`)
| Columna             | Tipo        | Descripción                                |
| ------------------- | ----------- | ------------------------------------------ |
| id                  | SERIAL      | Identificador único de la cita             |
| user_id             | INTEGER     | ID del usuario que agenda la cita          |
| tattoo_artist_id    | INTEGER     | ID del tatuador                            |
| date                | DATE        | Fecha de la cita                           |
| time                | TIME        | Hora de la cita                            |
| description         | TEXT        | Descripción de la cita                     |
| status              | VARCHAR(20) | Estado de la cita (por ejemplo, 'pending') |
| reference_image_url | TEXT        | URL de la imagen de referencia             |

### 3. Proyectos de Diseño (`designer_projects`)
| Columna      | Tipo          | Descripción                              |
| ------------ | ------------- | ---------------------------------------- |
| id           | SERIAL        | Identificador único del proyecto         |
| designer_id  | INTEGER       | ID del diseñador                         |
| title        | VARCHAR(255)  | Título del proyecto                      |
| description  | TEXT          | Descripción del proyecto                 |
| image        | VARCHAR(255)  | URL de la imagen del proyecto            |
| price        | DECIMAL(10,2) | Precio del proyecto                      |
| created_at   | TIMESTAMP     | Fecha de creación del proyecto           |
| currency     | VARCHAR(10)   | Moneda del precio                        |
| is_available | BOOLEAN       | Indica si el proyecto está disponible    |

---


## Estructura del Proyecto
```
Capstone/
│
├── backend-ign-tattoo-app/     # Código del servidor (Express.js)
├── frontend-ign-tattoo-app/    # Código del cliente (React Native)
│
└── README.md                   # Documentación del proyecto
```
