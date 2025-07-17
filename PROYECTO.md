# Plantilla de Python (Python Boilerplate) ![status](https://github.com/pmareke/python-boilerplate/actions/workflows/app.yml/badge.svg)

Este repositorio es una **plantilla base (boilerplate)** para proyectos de Python diseñada para proporcionar un punto de partida rápido con herramientas de desarrollo modernas preconfiguradas.

## ¿Qué es este proyecto?

Esta plantilla te permite iniciar rápidamente el desarrollo de aplicaciones Python con las mejores prácticas ya configuradas, eliminando la necesidad de configurar desde cero todas las herramientas de desarrollo, testing y calidad de código.

## Características Principales

- **Python 3.12**: Utiliza la versión más reciente de Python
- **Gestión Moderna de Paquetes**: Usa `uv` para gestión rápida de dependencias
- **Testing Robusto**: Framework de pruebas completo con pytest
- **Calidad de Código**: Herramientas automáticas de linting y formateo
- **Verificación de Tipos**: Análisis estático con mypy
- **CI/CD Automatizado**: GitHub Actions preconfigurado
- **Git Hooks**: Validación automática antes de commits
- **Estructura Organizada**: Separación clara entre código fuente, tests y scripts

## Requisitos

- Solo necesitas tener instalado [uv](https://docs.astral.sh/uv).

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

## Comandos del Proyecto

El proyecto utiliza [Makefiles](https://www.gnu.org/software/make/manual/html_node/Introduction.html) para ejecutar las tareas más comunes:

### 🚀 Comandos de Configuración
- `help`: Muestra todos los comandos disponibles
- `local-setup`: Configura el entorno local (instala git hooks)
- `install`: Instala las dependencias del proyecto
- `update`: Actualiza las dependencias

### 🏃 Comandos de Ejecución
- `run`: Ejecuta la aplicación
- `test`: Ejecuta todas las pruebas
- `watch`: Ejecuta las pruebas en modo observación (se re-ejecutan automáticamente)

### 🔍 Comandos de Calidad de Código
- `check-format`: Verifica el formato del código
- `format`: Formatea el código automáticamente
- `check-lint`: Verifica el estilo del código
- `lint`: Corrige automáticamente problemas de estilo
- `check-typing`: Verifica los tipos con mypy
- `checks`: Ejecuta todas las verificaciones (formato, lint, tipado)

### 📦 Gestión de Paquetes
- `add-package package=XXX`: Instala el paquete XXX, ej: `make add-package package=requests`

### 🔄 Comandos de Utilidad
- `rename-project name=nuevo-nombre`: Renombra el proyecto
- `pre-commit`: Ejecuta todas las verificaciones (usado por git hooks)

**Importante: Ejecuta el comando `make local-setup` antes de empezar a programar.**

_Para crear un commit debes pasar la fase de pre-commit que ejecuta los comandos de verificación y test._

## Flujo de Desarrollo

### 1. Configuración Inicial
```bash
# Clona el repositorio
git clone <url-del-repositorio>
cd Python-boilerplate

# Configura el entorno local
make local-setup
```

### 2. Desarrollo Diario
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

### 3. Antes de Hacer Commit
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

## Herramientas y Tecnologías

### 🔧 Herramientas de Desarrollo

1. **[uv](https://docs.astral.sh/uv)**: Gestor de paquetes Python moderno y extremadamente rápido
2. **[pytest](https://docs.pytest.org/)**: Framework de testing más popular de Python
3. **[mypy](https://mypy.readthedocs.io/)**: Verificador de tipos estático
4. **[ruff](https://github.com/astral-sh/ruff)**: Linter y formateador rápido escrito en Rust

### 🧪 Herramientas de Testing

- **[pytest](https://docs.pytest.org/en/7.1.x/contents.html)**: Ejecutor de pruebas
- **[pytest-xdist](https://github.com/pytest-dev/pytest-xdist)**: Plugin de pytest para ejecutar pruebas en paralelo
- **[doublex](https://github.com/davidvilla/python-doublex)**: Framework poderoso para test doubles en Python
- **[expects](https://expects.readthedocs.io/en/stable/)**: Librería de aserciones expresiva y extensible para TDD/BDD
- **[doublex-expects](https://github.com/jaimegildesagredo/doublex-expects)**: Librería de matchers para la librería de aserciones Expects

### 🎨 Estilo de Código

- **[mypy](https://mypy.readthedocs.io/en/stable/)**: Verificador de tipos estático
- **[ruff](https://github.com/astral-sh/ruff)**: Linter de Python extremadamente rápido, escrito en Rust

### ⚙️ Configuración y Automatización

- **Makefile**: Comandos simplificados para tareas comunes
- **GitHub Actions**: CI/CD automático
- **Git Hooks**: Validación antes de commits
- **pyproject.toml**: Configuración moderna de proyectos Python

## Gestión de Paquetes

Este proyecto utiliza [uv](https://docs.astral.sh/uv) como gestor de paquetes.

## Ventajas de Esta Plantilla

### 🚀 Productividad
- **Inicio rápido**: Todo configurado desde el primer momento
- **Comandos simplificados**: Un solo comando para tareas complejas
- **Automatización**: Git hooks y CI/CD preconfigurados

### 🔒 Calidad
- **Verificación automática**: Imposible hacer commit con código de mala calidad
- **Testing robusto**: Framework completo para diferentes tipos de pruebas
- **Tipado estático**: Detección temprana de errores

### 🔧 Mantenibilidad
- **Estructura clara**: Separación de responsabilidades
- **Documentación**: Código autodocumentado y comentarios claros
- **Estándares**: Sigue las mejores prácticas de Python

### 🏢 Profesional
- **CI/CD integrado**: Pipeline profesional desde el día uno
- **Monitoreo**: Badge de estado en el README
- **Escalabilidad**: Estructura que crece con el proyecto

## Resumen Rápido

### ¿Qué es?
**Una plantilla lista para usar** que incluye todas las herramientas modernas de desarrollo Python preconfiguradas.

### ¿Para qué sirve?
- ✅ **Iniciar proyectos Python rápidamente** sin configurar herramientas desde cero
- ✅ **Garantizar calidad de código** con verificaciones automáticas
- ✅ **Seguir mejores prácticas** de desarrollo Python moderno
- ✅ **Tener CI/CD funcionando** desde el primer día

### ¿Cómo empezar?

1. **Prerequisito**: Instalar `uv`
2. **Configurar proyecto**: `make local-setup && make install`
3. **Probar que funciona**: `make run && make test && make checks`
4. **Para nuevo proyecto**: Renombrar y reemplazar código de ejemplo

### ¿Por qué usar esta plantilla?

- **🚀 Velocidad**: 5 minutos para tener un proyecto completo funcionando
- **🎯 Calidad Garantizada**: Imposible hacer commit con código malo
- **🏢 Profesional**: CI/CD completo desde día 1

## Contribuciones y Agradecimientos

Agradecimientos especiales a:
- [GoldraK](https://github.com/GoldraK)
- [Alex Lopez](https://github.com/alexlopezc)