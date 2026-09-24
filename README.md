# 🌾 CEBADA360

Repositorio de trabajo del equipo para el **Reto AgroCebada – Datathlon FIRA 2026**.

Este README explica cómo configurar el proyecto por primera vez, ejecutarlo y subir cambios a GitHub.

---

# 💻 Opción recomendada: VS Code

Cada integrante del equipo tendrá una copia local del repositorio en su computadora.

## 1. Instalar Git

Descargar e instalar Git:

https://git-scm.com/downloads

Después de instalarlo, abrir PowerShell y comprobar:

```powershell
git --version
```

Debe aparecer algo similar a:

```text
git version 2.x.x
```

---

## 2. Instalar Python 3.12

El proyecto utilizará **Python 3.12** para que todos trabajemos con la misma versión.

Descargar Python 3.12 desde:

https://www.python.org/downloads/

En Windows también puede instalarse desde Microsoft Store.

Comprobar las versiones instaladas:

```powershell
py -0p
```

Comprobar específicamente Python 3.12:

```powershell
py -3.12 --version
```

Debe aparecer:

```text
Python 3.12.x
```

No importa si también tienen otras versiones de Python instaladas.

---

## 3. Instalar Visual Studio Code

Descargar:

https://code.visualstudio.com/

Una vez instalado, abrir VS Code.

En la sección **Extensions** instalar:

- Python
- Jupyter

Ambas extensiones son de Microsoft.

---

# 📥 Clonar el repositorio

No descargar el proyecto como ZIP.

Cada integrante debe clonarlo con Git.

Abrir PowerShell o la terminal de VS Code y moverse a la carpeta donde quiera guardar el proyecto.

Por ejemplo:

```powershell
cd Desktop
```

Clonar:

```powershell
git clone URL_DEL_REPOSITORIO
```

Entrar al proyecto:

```powershell
cd cebada360
```

Abrirlo en VS Code:

```powershell
code .
```

---

# 🐍 Crear el entorno de Python

Cada integrante debe crear su propio entorno virtual.

El entorno `.venv` NO se descarga desde GitHub.

Desde la carpeta raíz del proyecto:

```powershell
py -3.12 -m venv .venv
```

Activarlo:

```powershell
.\.venv\Scripts\Activate.ps1
```

Si funcionó, la terminal debe mostrar algo parecido a:

```text
(.venv) PS C:\...\cebada360>
```

Comprobar la versión:

```powershell
python --version
```

Debe aparecer:

```text
Python 3.12.x
```

---

# 📦 Instalar las librerías

Con `.venv` activado:

```powershell
python -m pip install --upgrade pip
```

Después:

```powershell
pip install -r requirements.txt
```

Esto instalará las mismas librerías utilizadas por el resto del equipo.

---

# ⚙️ Seleccionar Python en VS Code

Presionar:

```text
Ctrl + Shift + P
```

Buscar:

```text
Python: Select Interpreter
```

Seleccionar:

```text
.venv (Python 3.12.x)
```

La ruta debe ser aproximadamente:

```text
.\.venv\Scripts\python.exe
```

---

# 📁 Datos del proyecto

⚠️ Los datasets originales NO están almacenados en GitHub.

Cada integrante debe conseguir los archivos oficiales del reto y colocarlos localmente dentro de:

```text
data/raw/
```

Por ejemplo:

```text
cebada360/
│
├── data/
│   ├── raw/
│   │   ├── Conjunto_datos_BASICO_AgroCebada2026.csv
│   │   ├── Conjunto_datos_PRO_AgroCebada.csv
│   │   ├── ID_area_rendimiento_70_30_Reto_AgroCebada.csv
│   │   └── ...
│   │
│   ├── interim/
│   └── processed/
│
└── ...
```

Los archivos de `data/` están ignorados por Git.

Por lo tanto:

**NO hacer `git add` manualmente sobre los datasets.**

Los datos originales dentro de:

```text
data/raw/
```

no deben modificarse.

---

# 📓 Ejecutar los notebooks

Los notebooks se encuentran en:

```text
notebooks/
```

Para abrir uno:

1. Abrir el archivo `.ipynb` en VS Code.
2. En la parte superior derecha seleccionar el Kernel.
3. Elegir el entorno `.venv`.
4. Ejecutar las celdas.

También puede iniciarse Jupyter desde la terminal:

```powershell
jupyter notebook
```

---

# 🌿 Trabajar con Git y GitHub

## IMPORTANTE

No trabajar directamente sobre `main` para desarrollar nuevas partes del proyecto.

Antes de comenzar a trabajar, actualizar el repositorio:

```powershell
git checkout main
```

```powershell
git pull origin main
```

Después crear una rama.

Ejemplo:

```powershell
git checkout -b feature/auditoria-datos
```

Otros ejemplos:

```text
feature/satelite
feature/clima
feature/topografia
feature/modelado
feature/app
```

---

# 💾 Guardar cambios

Primero revisar qué cambió:

```powershell
git status
```

Agregar los cambios:

```powershell
git add .
```

Volver a comprobar:

```powershell
git status
```

Crear el commit:

```powershell
git commit -m "Descripción de los cambios"
```

Ejemplo:

```powershell
git commit -m "Agrega análisis inicial de variables satelitales"
```

Subir la rama a GitHub:

```powershell
git push -u origin NOMBRE_DE_LA_RAMA
```

Por ejemplo:

```powershell
git push -u origin feature/satelite
```

Después entrar a GitHub y crear un **Pull Request** hacia `main`.

---

# 🔄 Si ya existe la rama

Después del primer `push`, normalmente basta con:

```powershell
git add .
git commit -m "Descripción del cambio"
git push
```

---

# 🔃 Antes de empezar a trabajar otro día

Siempre actualizar primero `main`:

```powershell
git checkout main
git pull origin main
```

Después regresar a su rama:

```powershell
git checkout NOMBRE_DE_LA_RAMA
```

Por ejemplo:

```powershell
git checkout feature/clima
```

Para incorporar los cambios recientes de `main`:

```powershell
git merge main
```

Si Git indica conflictos, resolverlos antes de continuar.

---

# 🌱 Crear una nueva rama desde main actualizado

Cuando se termine una tarea y se vaya a comenzar otra:

```powershell
git checkout main
git pull origin main
git checkout -b feature/nueva-tarea
```

---

# 🆘 Comandos útiles de Git

Ver estado:

```powershell
git status
```

Ver ramas:

```powershell
git branch
```

Cambiar de rama:

```powershell
git checkout NOMBRE_RAMA
```

Ver historial:

```powershell
git log --oneline
```

Descargar cambios de GitHub:

```powershell
git pull
```

Subir commits:

```powershell
git push
```

---

# ☁️ Opción alternativa: Google Colab

También se pueden utilizar algunos notebooks desde Google Colab.

Esta opción puede ser útil para análisis rápidos o si alguien no puede configurar Python localmente.

Para clonar el repositorio desde una celda de Colab:

```python
!git clone URL_DEL_REPOSITORIO
```

Entrar a la carpeta:

```python
%cd cebada360
```

Instalar las dependencias:

```python
!pip install -r requirements.txt
```

---

## Repositorio privado en Colab

Como el repositorio es privado, GitHub necesita autenticar al usuario.

**NO escribir tokens, contraseñas o credenciales directamente dentro de un notebook.**

Una alternativa sencilla es abrir el notebook desde GitHub utilizando la integración de Colab y autorizar el acceso a repositorios privados cuando Colab lo solicite.

---

## Datos en Google Colab

Los archivos de `data/raw/` no están en GitHub.

Por lo tanto, en Colab será necesario subirlos durante la sesión o utilizar Google Drive.

Para montar Google Drive:

```python
from google.colab import drive
drive.mount('/content/drive')
```

Los datos pueden almacenarse en Drive y accederse desde Python utilizando su ruta correspondiente.

⚠️ Las rutas de Drive serán diferentes a las utilizadas localmente.

---

# ⚠️ VS Code vs Google Colab

Para este proyecto recomendamos utilizar:

**VS Code + Git + Python 3.12**

como entorno principal.

Google Colab puede utilizarse para experimentos o notebooks puntuales.

El proyecto utiliza información:

- CSV
- geoespacial
- shapefiles
- rasters
- archivos climáticos
- archivos topográficos

por lo que mantener una estructura local consistente facilita el procesamiento y la reproducibilidad.

---

# 📂 Estructura del repositorio

```text
cebada360/
│
├── app/
│
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
│
├── docs/
│
├── models/
│
├── notebooks/
│
├── outputs/
│   ├── figures/
│   └── tables/
│
├── src/
│   ├── data/
│   ├── features/
│   └── models/
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

# 🚀 Configuración rápida

Para alguien que ya tenga **Git, VS Code y Python 3.12**, la configuración completa se resume en:

```powershell
git clone URL_DEL_REPOSITORIO
cd cebada360

py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1

python -m pip install --upgrade pip
pip install -r requirements.txt

code .
```

Después colocar los datasets oficiales en:

```text
data/raw/
```

Y listo. 🌾
