# Proyecto de Git

Este documento describe los pasos seguidos para trabajar con Git en el proyecto.

## 1. Inicialización del repositorio

- **Comando**: `git init tallerGit`
- **Descripción**: Se inicializa un nuevo repositorio de Git en la carpeta `tallerGit`.

### 2. Configuración de usuario global

- **Comandos**:
  - `git config --global user.name CarlosR99`
  - `git config --global user.email jose.carlos.silva@correounivalle.edu.co`
- **Descripción**: Se configuran el nombre y el correo del usuario para los commits a nivel global.

### 3. Creación de la rama `master`

- **Comandos**:
  - `cd TallerGit`
  - `git checkout -b master`
- **Descripción**: Se cambia al directorio `TallerGit` y se crea la rama `master`.

### 4. Commit inicial en `master`

- **Comandos**:
  - `echo "# Mi Proyecto" > README.md`
  - `git add README.md`
  - `git commit -m "Commit inicial en master"`
- **Descripción**: Se crea un archivo `README.md` con el título del proyecto, se agrega al área de stage y se realiza un commit.

### 5. Creación y trabajo en la rama `feature`

- **Comandos**:
  - `git checkout -b feature`
  - `echo "Texto inicial" > archivo.txt`
  - `git add archivo.txt`
  - `git commit -m "Commit inicial"`
  - `echo "Texto agregado en feature" >> archivo.txt`
  - `git commit -am "Segundo commit en feature"`
  - `echo "Tercer texto agregado en feature" >> archivo.txt`
  - `git commit -am "Tercer commit en feature"`
- **Descripción**: Se crea la rama `feature` y se realizan tres commits con cambios en el archivo `archivo.txt`.

### 6. Fusión de `feature` en `master`

- **Comandos**:
  - `git checkout master`
  - `git merge feature`
- **Descripción**: Se fusiona la rama `feature` en `master`.

### 7. Uso de `reset` y `rebase`

- **Comandos**:
  - `git reset --hard HEAD~1`
  - `git rebase feature`
- **Descripción**: Se deshace el último commit en `master` y se realiza un rebase desde `feature`.

### 8. Creación de la rama `hotfix` y solución de problema urgente

- **Comandos**:
  - `git checkout -b hotfix`
  - `echo "Corrección urgente" >> archivo.txt`
  - `git commit -am "Hotfix"`
- **Descripción**: Se crea la rama `hotfix` para realizar una corrección urgente y se realiza un commit.

### 9. Aplicación del `hotfix` en `master` y busqueda de commit perdido

- **Comandos**:
  - `git checkout master`
  - `git cherry-pick hotfix`
  - `git reflog`
  - `git checkout ca232c3`
- **Descripción**: Se aplica el commit de la corrección de `hotfix` en la rama `master` y se busco un commit perdido con el y se ingreso a este `ca232c3`.

### 10. Conflicto al fusionar `feature` en `master`

- **Comandos**:
  - `git checkout feature`
  - `echo "Cambio en feature" > conflicto.txt`
  - `git commit -am "Cambio en feature"`
  - `git checkout master`
  - `echo "Cambio en master" > conflicto.txt`
  - `git commit -am "Cambio en master"`
  - `git merge feature`
  - `nano conflicto.txt`
  - `git add conflicto.txt`
  - `git commit -m "Resuelto conflicto en conflicto.txt durante fusión de feature a master"`
- **Descripción**: Se crea un conflicto en el archivo `conflicto.txt` al intentar fusionar la rama `feature` en `master`. El conflicto se resuelve manualmente editando el archivo.

### 11. Revisión del estado del repositorio

- **Comando**: `git status`
- **Descripción**: Verifica el estado del repositorio después de las operaciones realizadas.
