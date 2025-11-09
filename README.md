# 🐄 Sistema de Registro de Veterinaria

Aplicación web para registrar información de ordeño y estado productivo de vacas. Desarrollada con **Python (Flask)**, **HTML**, **CSS** y almacenamiento en **Excel**. Las fotografías ahora se guardan directamente como **base64 dentro del archivo Excel** (no se usa carpeta de uploads).

## 📋 Características

- Formulario web para capturar:
  - Nombre del ordeñador
  - ID de la vaca
  - Nombre de la vaca
  - Litros de leche producidos
  - Foto de la vaca
- Almacenamiento de datos en archivo Excel
- Imágenes embebidas como base64 (evita problemas de rutas y facilita portabilidad)
- Interfaz responsive y moderna
- Dashboard de estadísticas (producción, estados, top productoras, ordeñadores)

## 🚀 Instalación

### 1. Instalar las dependencias

```powershell
pip install -r requirements.txt
```

### 2. Ejecutar la aplicación

```powershell
python app.py
```

### 3. Abrir en el navegador

Navega a: `http://127.0.0.1:5000`

## 📁 Estructura del proyecto

```
Veterinaria/
│
├── app.py                      # Servidor Flask
├── requirements.txt            # Dependencias de Python
├── registros_vacas.xlsx       # Archivo Excel con datos + imágenes en base64
│
├── templates/                 # Vistas HTML (Jinja2)
│   ├── inicio.html            # Menú inicial
│   ├── formulario.html        # Formulario de registro
│   ├── registros.html         # Consulta de registros
│   └── estadisticas.html      # Panel de estadísticas
│
└── static/
  ├── common.css             # Estilos compartidos
  ├── inicio.css             # Estilos página inicio
  ├── formulario.css         # Estilos formulario por secciones
  ├── registros.css          # Estilos tabla y modal fotos
  └── estadisticas.css       # Estilos dashboard
```

## 💾 Datos guardados

Los datos se guardan en `registros_vacas.xlsx` con las siguientes columnas (orden actual):

1. Fecha y Hora
2. Nombre del Ordeñador
3. ID de la Vaca
4. Nombre de la Vaca
5. Litros de Leche
6. Imagen (base64)
7. Edad
8. Estado productivo
9. Vaca parida
10. Vaca seca
11. Número de crías
12. Número de parto

Las fotos ya NO se guardan como archivos sueltos; se convierten a JPEG reducido y se codifican en base64 para almacenarse directamente.

## 🛠️ Tecnologías utilizadas

- **Backend:** Python con Flask
- **Frontend:** HTML5 y CSS3
- **Base de datos:** Excel (openpyxl)
- **Procesamiento de imágenes:** Pillow (redimensionado y compresión)

## 📝 Notas

- Tamaño máximo de subida: 16MB (validado por Flask config)
- Formatos de imagen permitidos: PNG, JPG, JPEG, GIF, WEBP
- El archivo Excel debe existir antes de iniciar (ya no se autogenera en este flujo) o créalo manualmente con las cabeceras.

## 🧪 Cabeceras esperadas en el Excel
Si necesitas crear el Excel desde cero, usa la primera fila con:
```
Fecha y Hora | Nombre del Ordeñador | ID de la Vaca | Nombre de la Vaca | Litros | Imagen Base64 | Edad | Estado productivo | Vaca parida | Vaca seca | Numero crías | Numero parto
```

## 📦 Dependencias principales
Ver `requirements.txt` (incluye Flask, openpyxl, Pillow, Werkzeug).


