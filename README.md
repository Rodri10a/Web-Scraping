# 📚 Books Detective - Web Scraping Challenge

> *Proyecto de web scraping y análisis de datos de Books to Scrape con integración a Google Books API*

## 🎯 Descripción del Proyecto

Books Detective es un proyecto integral de web scraping que extrae información de **1000 libros** de 50 categorías diferentes desde [Books to Scrape](https://books.toscrape.com/), enriquece los datos con la API de Google Books, y almacena toda la información en una base de datos relacional SQLite para realizar análisis avanzados mediante consultas SQL.

## ✨ Características Principales

- 🕷️ **Web Scraping Completo**: Extracción automatizada de 1000 libros en 50 categorías
- 🔍 **Enriquecimiento de Datos**: Integración con Google Books API para obtener información detallada de autores
- 💾 **Base de Datos Relacional**: Diseño normalizado con relaciones muchos-a-muchos
- 📊 **Análisis SQL Avanzado**: Consultas con window functions y subconsultas complejas
- ⚡ **Optimización**: Implementación de índices y análisis de rendimiento
- 📈 **Exportación CSV**: Datos completos exportados para análisis adicionales

## 🛠️ Tecnologías Utilizadas

```python
- Python 3.12
- BeautifulSoup4 - Web scraping y parseo HTML
- Requests - Peticiones HTTP
- SQLite3 - Base de datos relacional
- Pandas - Manipulación y análisis de datos
- Google Books API - Enriquecimiento de datos
- ThreadPoolExecutor - Procesamiento paralelo
```

## 📋 Requisitos

Las dependencias del proyecto están listadas en `requirements.txt`:

```
beautifulsoup4==4.14.3
requests==2.32.5
pandas==3.0.0
numpy==2.4.1
```

## 🚀 Instalación y Uso

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/books-detective.git
cd books-detective
```

### 2. Crear entorno virtual (recomendado)
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

### 3. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 4. Ejecutar el proyecto
```bash
jupyter notebook inicio.ipynb
```

## 📊 Estructura de la Base de Datos

El proyecto utiliza un modelo relacional normalizado con las siguientes tablas:

### Tablas Principales

**📖 Libros**
- `id` (PRIMARY KEY)
- `titulo`
- `precio`
- `rating` (1-5 estrellas)
- `en_stock`
- `categoria_id` (FOREIGN KEY)
- `descripcion`

**✍️ Autores**
- `id` (PRIMARY KEY)
- `nombre`

**📂 Categorías**
- `id` (PRIMARY KEY)
- `nombre`

**🔗 Libros_Autores** (Tabla de relación)
- `libro_id` (FOREIGN KEY)
- `autor_id` (FOREIGN KEY)

## 🔎 Funcionalidades del Proyecto

### Web Scraping
- Extracción automática de 50 categorías
- Navegación paginada por categoría
- Extracción de datos: título, precio, rating, stock, descripción
- Manejo de errores y reintentos

### Integración API
- Consultas a Google Books API
- Búsqueda de autores por título
- Manejo de respuestas y fallbacks
- Procesamiento paralelo con ThreadPoolExecutor

### Análisis de Datos
El proyecto incluye 5 consultas SQL avanzadas:

1. **Top 10 Autores Prolíficos**: Autores con más libros usando window functions
2. **Libros Caros por Categoría**: Precios comparados con promedio de categoría
3. **Autores Versátiles**: Autores que escriben en múltiples géneros
4. **Análisis de Precios**: Distribución de precios con percentiles
5. **Mejores Libros Económicos**: Libros de alta calificación a bajo precio

### Optimización
- Implementación de índices en columnas clave
- Análisis antes/después de indexación
- Medición de tiempos de ejecución
- Mejora documentada del rendimiento

## 📁 Archivos del Proyecto

```
books-detective/
│
├── inicio.ipynb                           # Notebook principal con todo el código
├── requirements.txt                       # Dependencias del proyecto
├── books_detective.db                     # Base de datos SQLite generada
├── books_detective_complete_data.csv      # Datos exportados en CSV
├── README.md                              # Este archivo
└── .gitignore                             # Archivos ignorados por Git
```

## 📈 Resultados

El proyecto procesa exitosamente:
- ✅ 1000 libros scrapeados
- ✅ 50 categorías únicas
- ✅ 600+ autores identificados
- ✅ Datos enriquecidos con API
- ✅ Base de datos relacional completa
- ✅ Consultas optimizadas con índices

## 🎓 Aprendizajes

Este proyecto demuestra competencias en:
- Web scraping ético y responsable
- Diseño de bases de datos relacionales
- Integración de APIs externas
- Optimización de consultas SQL
- Procesamiento paralelo en Python
- Análisis y visualización de datos

