# Plantilla de Python (Python Boilerplate) 

## ¿Qué es este proyecto?

Este repositorio es una **plantilla base (boilerplate)** para proyectos de Python que te permite iniciar rápidamente el desarrollo de aplicaciones Python con las mejores prácticas ya configuradas.

## Propósito y Características

### 🎯 **Objetivo Principal**
Proporcionar un punto de partida rápido y profesional para proyectos Python, eliminando la necesidad de configurar desde cero todas las herramientas de desarrollo, testing y calidad de código.

### ✨ **Características Principales**

- **Python 3.12**: Utiliza la versión más reciente de Python
- **Gestión Moderna de Dependencias**: Usa `uv` como gestor de paquetes (más rápido que pip)
- **Testing Robusto**: Framework de pruebas completo con pytest
- **Calidad de Código**: Herramientas automáticas de linting y formateo
- **Verificación de Tipos**: Análisis estático con mypy
- **CI/CD Automatizado**: GitHub Actions preconfigurado
- **Git Hooks**: Validación automática antes de commits
- **Estructura Organizada**: Separación clara entre código fuente, tests y scripts

## Estructura del Proyecto

```
Python-boilerplate/
├── src/                    # Código fuente de la aplicación
│   ├── __init__.py
│   └── dummy_class.py     # Ejemplo de clase simple
├── tests/                 # Pruebas del proyecto
│   ├── __init__.py
│   └── test_dummy_class.py # Ejemplo de test
├── scripts/               # Scripts de automatización
│   ├── hooks/            # Git hooks
│   ├── local-setup.sh    # Configuración del entorno local
│   └── pre-requirements.sh # Verificación de prerequisitos
├── .github/
│   └── workflows/
│       └── app.yml       # Pipeline de CI/CD
├── main.py               # Punto de entrada de la aplicación
├── pyproject.toml        # Configuración del proyecto y dependencias
├── Makefile             # Comandos de automatización
├── mypy.ini             # Configuración del verificador de tipos
└── README.md            # Documentación en inglés
```

## Tecnologías y Herramientas

### 🔧 **Herramientas de Desarrollo**

1. **[uv](https://docs.astral.sh/uv)**: Gestor de paquetes Python moderno y extremadamente rápido
2. **[pytest](https://docs.pytest.org/)**: Framework de testing más popular de Python
3. **[mypy](https://mypy.readthedocs.io/)**: Verificador de tipos estático
4. **[ruff](https://github.com/astral-sh/ruff)**: Linter y formateador rápido escrito en Rust

### 🧪 **Herramientas de Testing**

- **pytest-xdist**: Ejecución de tests en paralelo
- **doublex**: Framework para crear test doubles (mocks, stubs, etc.)
- **expects**: Librería de aserciones expresiva para TDD/BDD
- **doublex-expects**: Matchers para la librería expects

### ⚙️ **Configuración y Automatización**

- **Makefile**: Comandos simplificados para tareas comunes
- **GitHub Actions**: CI/CD automático
- **Git Hooks**: Validación antes de commits
- **pyproject.toml**: Configuración moderna de proyectos Python

## Comandos Disponibles

El proyecto utiliza `make` para simplificar las tareas comunes:

### 🚀 **Comandos de Configuración**
```bash
make help          # Muestra todos los comandos disponibles
make local-setup   # Configura el entorno local (instala git hooks)
make install       # Instala las dependencias del proyecto
make update        # Actualiza las dependencias
```

### 🏃 **Comandos de Ejecución**
```bash
make run           # Ejecuta la aplicación principal
make test          # Ejecuta todas las pruebas
make watch         # Ejecuta las pruebas en modo observación (se re-ejecutan automáticamente)
```

### 🔍 **Comandos de Calidad de Código**
```bash
make check-format  # Verifica el formato del código
make format        # Formatea el código automáticamente
make check-lint    # Verifica el estilo del código
make lint          # Corrige automáticamente problemas de estilo
make check-typing  # Verifica los tipos con mypy
make checks        # Ejecuta todas las verificaciones
```

### 📦 **Gestión de Paquetes**
```bash
make add-package package=nombre_paquete  # Instala un nuevo paquete
```

### 🔄 **Comandos de Utilidad**
```bash
make rename-project name=nuevo-nombre    # Renombra el proyecto
make pre-commit    # Ejecuta todas las verificaciones (usado por git hooks)
```

## Flujo de Desarrollo

### 1. **Configuración Inicial**
```bash
# Clona el repositorio
git clone <url-del-repositorio>
cd Python-boilerplate

# Configura el entorno local
make local-setup
```

### 2. **Desarrollo Diario**
```bash
# Ejecuta la aplicación
make run

# Ejecuta las pruebas
make test

# Verifica la calidad del código
make checks

# Desarrollo con pruebas automáticas
make watch
```

### 3. **Antes de Hacer Commit**
El proyecto tiene configurados git hooks que automáticamente:
- Verifican el formato del código
- Ejecutan el linter
- Verifican los tipos con mypy
- Ejecutan todas las pruebas

Si alguna verificación falla, el commit será rechazado.

## Integración Continua (CI/CD)

El proyecto incluye un pipeline de GitHub Actions (`.github/workflows/app.yml`) que:

1. **Se ejecuta automáticamente** en cada push y pull request
2. **Configura el entorno** con Python 3.12 y uv
3. **Instala las dependencias** del proyecto
4. **Ejecuta todas las verificaciones** de calidad de código
5. **Ejecuta todas las pruebas** del proyecto

## Cómo Usar Esta Plantilla

### Para un Nuevo Proyecto:

1. **Crear un nuevo repositorio** basado en esta plantilla
2. **Clonar** el nuevo repositorio
3. **Renombrar el proyecto**:
   ```bash
   make rename-project name=mi-nuevo-proyecto
   ```
4. **Configurar el entorno**:
   ```bash
   make local-setup
   ```
5. **Reemplazar el código de ejemplo**:
   - Eliminar `src/dummy_class.py`
   - Eliminar `tests/test_dummy_class.py`
   - Modificar `main.py` con tu lógica principal
   - Agregar tus propias clases en `src/`
   - Agregar tus propias pruebas en `tests/`

6. **Actualizar la documentación**:
   - Modificar `README.md`
   - Actualizar `pyproject.toml` con la información de tu proyecto

### Ejemplo de Uso:

El proyecto incluye un ejemplo simple:
- `src/dummy_class.py`: Una clase que suma dos números
- `tests/test_dummy_class.py`: Test para la clase anterior
- `main.py`: Demostración de uso

```python
# src/dummy_class.py
class Dummy:
    def add(self, first: int, second: int) -> int:
        return first + second

# main.py
from src.dummy_class import Dummy

dummy_class = Dummy()
result = dummy_class.add(1, 2)
print(result)  # Imprime: 3
```

## Ventajas de Esta Plantilla

### 🚀 **Productividad**
- **Inicio rápido**: Todo configurado desde el primer momento
- **Comandos simplificados**: Un solo comando para tareas complejas
- **Automatización**: Git hooks y CI/CD preconfigurados

### 🔒 **Calidad**
- **Verificación automática**: Imposible hacer commit con código de mala calidad
- **Testing robusto**: Framework completo para diferentes tipos de pruebas
- **Tipado estático**: Detección temprana de errores

### 🔧 **Mantenibilidad**
- **Estructura clara**: Separación de responsabilidades
- **Documentación**: Código autodocumentado y comentarios claros
- **Estándares**: Sigue las mejores prácticas de Python

### 🏢 **Profesional**
- **CI/CD integrado**: Pipeline profesional desde el día uno
- **Monitoreo**: Badge de estado en el README
- **Escalabilidad**: Estructura que crece con el proyecto

## Prerequisitos

**Único requisito**: Tener instalado [uv](https://docs.astral.sh/uv/getting-started/installation/)

Todo lo demás se instala automáticamente.

## Contribuciones y Agradecimientos

Este proyecto fue creado como una plantilla de uso general. Agradecimientos especiales a:
- [GoldraK](https://github.com/GoldraK)
- [Alex Lopez](https://github.com/alexlopezc)

---

**¡Importante!** Recuerda ejecutar `make local-setup` antes de empezar a desarrollar para configurar correctamente los git hooks.