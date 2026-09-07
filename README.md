# 🛒 TechAccess — Tienda Virtual de Accesorios Tecnológicos

Proyecto del curso **E-Business y Analítica Web** — UPN 2026  
Autor: Holsen Piero Rodriguez Bejarano

## 🛠️ Tecnologías utilizadas
- WordPress 7.1
- WooCommerce 11.1
- Tema Astra
- MySQL/MariaDB
- XAMPP (Apache + PHP 8.2)

## 📦 Categorías de productos
- Audífonos
- Cargadores
- Cables
- Mouse y Teclados
- Power Banks
- Fundas y Protectores

## 🚀 Instalación (para compañeros)

### 1. Instalar XAMPP
Descargar XAMPP 8.2 Linux desde: https://www.apachefriends.org/download.html

### 2. Clonar este repositorio
```bash
git clone https://github.com/HolsenPierodriguez/tienda-techaccess.git
```

### 3. Copiar archivos a XAMPP
```bash
sudo cp -r tienda-techaccess/. /opt/lampp/htdocs/miweb/
sudo chown -R daemon:daemon /opt/lampp/htdocs/miweb
```

### 4. Crear base de datos
- Abrir `http://localhost/phpmyadmin`
- Crear nueva BD llamada `miweb_db` con cotejamiento `utf8mb4_unicode_ci`

### 5. Importar la base de datos
- En phpMyAdmin, seleccionar `miweb_db`
- Pestaña "Importar" → subir `database/miweb_db.sql`

### 6. Iniciar XAMPP
```bash
sudo /opt/lampp/lampp start
```

### 7. Acceder
- **Tienda:** http://localhost/miweb
- **Admin:** http://localhost/miweb/wp-admin

## 👤 Credenciales de administrador
Usuario: `holsen`  
Contraseña: (contactar al autor)
