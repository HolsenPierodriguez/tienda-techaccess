# 🛒 TechAccess — Tienda Virtual de Accesorios Tecnológicos

Proyecto del curso **E-Business y Analítica Web** — UPN 2026  
Autor: Holsen Piero Rodriguez Bejarano

## 🛠️ Tecnologías
- WordPress 7.1 + WooCommerce 11.1
- Tema Astra
- MySQL / MariaDB
- XAMPP (Apache + PHP 8.2)

## 📦 Categorías de productos
- Audífonos, Cargadores, Cables
- Mouse y Teclados, Power Banks
- Fundas y Protectores

## 🚀 Instalación paso a paso

### 1️⃣ Instalar XAMPP
Descargar XAMPP 8.2 Linux desde: https://www.apachefriends.org/download.html  
Instalarlo en `/opt/lampp` siguiendo el instalador gráfico.

### 2️⃣ Clonar este repositorio
En tu carpeta de trabajo:
```bash
git clone https://github.com/HolsenPierodriguez/tienda-techaccess.git
```

### 3️⃣ Copiar archivos a XAMPP
```bash
sudo cp -r tienda-techaccess/. /opt/lampp/htdocs/miweb/
sudo chown -R daemon:daemon /opt/lampp/htdocs/miweb
sudo chmod -R 755 /opt/lampp/htdocs/miweb
```

### 4️⃣ Iniciar XAMPP
```bash
sudo /opt/lampp/lampp start
```
Verifica que aparezcan como "ok": Apache, MySQL y ProFTPD.

### 5️⃣ Crear la base de datos vacía
Abrir en el navegador: http://localhost/phpmyadmin
- Clic en **"Nueva"** (columna izquierda)
- Nombre de la base de datos: `miweb_db`
- Cotejamiento: `utf8mb4_unicode_ci`
- Clic **"Crear"**

⚠️ **Importante**: la BD debe estar VACÍA. No importes datos aún, solo créala.

### 6️⃣ Importar los datos del proyecto
Con la BD `miweb_db` ya creada y seleccionada:
- Clic en la pestaña **"Importar"** (arriba)
- Clic **"Elegir archivo"** y seleccionar: `/opt/lampp/htdocs/miweb/database/miweb_db.sql`
- Bajar al final y clic **"Importar"**
- Esperar el mensaje verde de éxito ✅

Este archivo trae:
- Los productos precargados (con precios, imágenes, SKU)
- Las 6 categorías (Audífonos, Cargadores, Cables, Mouse y Teclados, Power Banks, Fundas y Protectores)
- El usuario admin y la configuración del tema Astra

### 7️⃣ Acceder al sitio
- **Tienda pública:** http://localhost/miweb
- **Panel de administración:** http://localhost/miweb/wp-admin

## 👤 Credenciales de administrador
- **Usuario:** `holsen`
- **Contraseña:** contactar al autor por WhatsApp (no se comparte en el repo por seguridad)

## 📊 Estructura de tablas WooCommerce
- `wp_posts` — Productos (post_type = 'product')
- `wp_postmeta` — Precios, SKU, stock, dimensiones
- `wp_terms` + `wp_term_taxonomy` — Categorías
- `wp_wc_product_meta_lookup` — Tabla optimizada de WooCommerce

## 🔧 Solución de problemas

**Error: "Estableciendo la conexión con la base de datos"**  
→ MySQL no arrancó. Ejecutar `sudo /opt/lampp/lampp restart`

**Puerto 80 ocupado**  
→ Si tienes Apache instalado en Ubuntu: `sudo systemctl stop apache2`

**No puedo importar el .sql (archivo muy grande)**  
→ Editar `/opt/lampp/etc/php.ini` y aumentar `upload_max_filesize` y `post_max_size` a `64M`. Reiniciar XAMPP.
