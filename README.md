# Python Boilerplate ![status](https://github.com/leonelmarinaro/Python-boilerplate/actions/workflows/app.yml/badge.svg)

This repository is a **Python boilerplate template** designed to provide a fast starting point for Python projects with modern development tools pre-configured.

## Features

- **Python 3.12**: Uses the latest Python version
- **Modern Package Management**: Uses `uv` for fast dependency management
- **Robust Testing**: Complete testing framework with pytest
- **Code Quality**: Automatic linting and formatting tools
- **Type Checking**: Static analysis with mypy
- **Automated CI/CD**: GitHub Actions pre-configured
- **Git Hooks**: Automatic validation before commits
- **Organized Structure**: Clear separation between source code, tests, and scripts

## Requirements

- You only need to have [uv](https://docs.astral.sh/uv) installed.

## Folder structure

```
Python-boilerplate/
├── src/                    # Source code of the application
│   ├── __init__.py
│   └── dummy_class.py     # Example simple class
├── tests/                 # Project tests
│   ├── __init__.py
│   └── test_dummy_class.py # Example test
├── scripts/               # Automation scripts
│   ├── hooks/            # Git hooks
│   ├── local-setup.sh    # Local environment setup
│   └── pre-requirements.sh # Prerequisites verification
├── .github/
│   └── workflows/
│       └── app.yml       # CI/CD pipeline
├── main.py               # Application entry point
├── pyproject.toml        # Project configuration and dependencies
├── Makefile             # Automation commands
├── mypy.ini             # Type checker configuration
└── README.md            # Documentation
```

## Project commands

The project uses [Makefiles](https://www.gnu.org/software/make/manual/html_node/Introduction.html) to run the most common tasks:

### 🚀 Setup Commands
- `help`: Shows all available commands
- `local-setup`: Sets up the local environment (installs git hooks)
- `install`: Installs the app packages
- `update`: Updates the app packages

### 🏃 Execution Commands
- `run`: Runs the app
- `test`: Run all the tests
- `watch`: Run all the tests in watch mode

### 🔍 Code Quality Commands
- `check-format`: Checks the code format
- `format`: Formats the code
- `check-lint`: Checks the code style
- `lint`: Lints the code
- `check-typing`: Runs a static analyzer over the code to find issues
- `checks`: Run all checks (format, lint, typing)

### 📦 Package Management
- `add-package package=XXX`: Installs the package XXX in the app, ex: `make add-package package=requests`

### 🔄 Utility Commands
- `rename-project name=new-name`: Rename the project
- `pre-commit`: Execute all verifications (used by git hooks)

**Important: Please run the `make local-setup` command before starting with the code.**

_In order to create a commit you have to pass the pre-commit phase which runs the check and test commands._

## Development Workflow

### 1. Initial Setup
```bash
# Clone the repository
git clone <repository-url>
cd Python-boilerplate

# Set up local environment
make local-setup
```

### 2. Daily Development
```bash
# Run the application
make run

# Run tests
make test

# Check code quality
make checks

# Development with automatic tests
make watch
```

### 3. Before Committing
The project has configured git hooks that automatically:
- Check code format
- Run the linter
- Check types with mypy
- Run all tests

If any verification fails, the commit will be rejected.

## Continuous Integration (CI/CD)

The project includes a GitHub Actions pipeline (`.github/workflows/app.yml`) that:

1. **Runs automatically** on every push and pull request
2. **Sets up the environment** with Python 3.12 and uv
3. **Installs project dependencies**
4. **Runs all code quality checks**
5. **Runs all project tests**

## How to Use This Template

### For a New Project:

1. **Create a new repository** based on this template
2. **Clone** the new repository
3. **Rename the project**:
   ```bash
   make rename-project name=my-new-project
   ```
4. **Set up environment**:
   ```bash
   make local-setup
   ```
5. **Replace example code**:
   - Remove `src/dummy_class.py`
   - Remove `tests/test_dummy_class.py`
   - Modify `main.py` with your main logic
   - Add your own classes in `src/`
   - Add your own tests in `tests/`

6. **Update documentation**:
   - Modify `README.md`
   - Update `pyproject.toml` with your project information

### Example Usage:

The project includes a simple example:
- `src/dummy_class.py`: A class that adds two numbers
- `tests/test_dummy_class.py`: Test for the above class
- `main.py`: Usage demonstration

```python
# src/dummy_class.py
class Dummy:
    def add(self, first: int, second: int) -> int:
        return first + second

# main.py
from src.dummy_class import Dummy

dummy_class = Dummy()
result = dummy_class.add(1, 2)
print(result)  # Prints: 3
```

## Tools and Technologies

### 🔧 Development Tools

1. **[uv](https://docs.astral.sh/uv)**: Modern and extremely fast Python package manager
2. **[pytest](https://docs.pytest.org/)**: Most popular Python testing framework
3. **[mypy](https://mypy.readthedocs.io/)**: Static type checker
4. **[ruff](https://github.com/astral-sh/ruff)**: Fast linter and formatter written in Rust

### 🧪 Testing Tools

- **pytest-xdist**: Parallel test execution
- **doublex**: Framework for creating test doubles (mocks, stubs, etc.)
- **expects**: Expressive assertion library for TDD/BDD
- **doublex-expects**: Matchers for the expects library

### ⚙️ Configuration and Automation

- **Makefile**: Simplified commands for common tasks
- **GitHub Actions**: Automatic CI/CD
- **Git Hooks**: Pre-commit validation
- **pyproject.toml**: Modern Python project configuration

## Package Management

This project uses [uv](https://docs.astral.sh/uv) as the package manager.

### Testing

- [pytest](https://docs.pytest.org/en/7.1.x/contents.html): Testing runner.
- [pytest-xdist](https://github.com/pytest-dev/pytest-xdist): Pytest plugin to run the tests in parallel.
- [doublex](https://github.com/davidvilla/python-doublex): Powerful test doubles framework for Python.
- [expects](https://expects.readthedocs.io/en/stable/): An expressive and extensible TDD/BDD assertion library for Python.
- [doublex-expects](https://github.com/jaimegildesagredo/doublex-expects): A matchers library for the Expects assertion library.

### Code style

- [mypy](https://mypy.readthedocs.io/en/stable/): A static type checker.
- [ruff](https://github.com/astral-sh/ruff): An extremely fast Python linter, written in Rust.

## Advantages of This Template

### 🚀 Productivity
- **Fast start**: Everything configured from the first moment
- **Simplified commands**: One command for complex tasks
- **Automation**: Git hooks and CI/CD pre-configured

### 🔒 Quality
- **Automatic verification**: Impossible to commit bad quality code
- **Robust testing**: Complete framework for different types of tests
- **Static typing**: Early error detection

### 🔧 Maintainability
- **Clear structure**: Separation of responsibilities
- **Documentation**: Self-documented code and clear comments
- **Standards**: Follows Python best practices

### 🏢 Professional
- **Integrated CI/CD**: Professional pipeline from day one
- **Monitoring**: Status badge in README
- **Scalability**: Structure that grows with the project

## Contributors

Special thanks to:
- [GoldraK](https://github.com/GoldraK).
- [Alex Lopez](https://github.com/alexlopezc)
