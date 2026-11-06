# RestaurantCLD

RestaurantCLD - Sistema Web para Gestión de Restaurantes

Requisitos:
- Python 3.10+
- Django 5.2.6
- SQLite3 (incluido por defecto)

Instalación y ejecución:
1. Clonar el repositorio:
   git clone https://github.com/JuanPreciadoR/INVENTABLE-main.git

2. Entrar en la carpeta del proyecto:
   cd INVENTABLE

3. Crear y activar el entorno virtual (Windows PowerShell):
   python -m venv .venv
   .venv\Scripts\Activate.ps1

4. Instalar dependencias:
   pip install -r requirements.txt

5. Ejecutar migraciones:
   python manage.py migrate

6. Iniciar el servidor de desarrollo:
   python manage.py runserver 127.0.0.1:8001

7. Abrir en el navegador:
   http://127.0.0.1:8001/

   La ruta raíz redirige automáticamente a la pantalla de inicio de sesión de usuarios.

Estructura del proyecto:
- clientes/      -> gestión de clientes
- usuarios/      -> administración de personal
- reservas/      -> gestión de reservas
- pedidos/       -> creación y seguimiento de pedidos
- menu/          -> catálogo de productos
- panelAdmin/    -> panel administrativo

Notas importantes:
- El proyecto usa SQLite y guarda la base de datos en `db.sqlite3`.
- Si ya existe un entorno virtual, active ese entorno en lugar de crear uno nuevo.
- No hay app `reportes` en este repositorio.
- Si necesita rehacer la base de datos en desarrollo, puede eliminar `db.sqlite3` y ejecutar de nuevo `python manage.py migrate`.

Credenciales de prueba (creadas automáticamente):
- Django admin: username=`admin`, password=`AdminPass123` (accede en `/admin/`)
- Empleado para login de la app: `codigo` = `admin123` (rol `admin`)

Acceso a la base de datos SQLite:
- Archivo: `db.sqlite3` en la raíz del proyecto.
- Recomiendo usar "DB Browser for SQLite" (https://sqlitebrowser.org/) para abrir, ver y editar las tablas.

Crear usuario administrador manualmente (si lo prefieres):
```powershell
python manage.py createsuperuser
```

Crear un `Empleado` para probar el login desde Django shell:
```powershell
.venv\Scripts\Activate.ps1
python manage.py shell
from usuarios.models import Empleado
Empleado.objects.create(nombre='Admin', codigo='admin123', rol='admin', activo=True)
```

Uso rápido — comandos copiados:
```powershell
cd INVENTABLE
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver 127.0.0.1:8001
# Abrir en el navegador: http://127.0.0.1:8001/
```

