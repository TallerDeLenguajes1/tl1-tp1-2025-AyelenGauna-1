# Introducción a .gitignore 🚀

El archivo .gitignore, es un archivo de texto que le dice a Git qué archivos o carpetas ignorar en un proyecto.

Un archivo local .gitignore generalmente se coloca en el directorio raíz de un proyecto. También puedes crear un archivo global .gitignore, y cualquier entrada en ese archivo se ignorará en todos tus repositorios de Git.

Para crear un archivo .gitignore local, crea un archivo de texto y asígnale el nombre ".gitignore" (recuerda incluir el . al principio). Luego, edita este archivo según sea necesario. Cada nueva línea debe incluir un archivo o carpeta adicional que quieras que Git lo ignore.

## ¿Por qué es conveniente incluirlo? 📋

El archivo .gitignore le dice a Git qué archivos o carpetas **NO debe rastrear ni incluir en los commits**.
Es útil porque:

- Evita subir archivos innecesarios (archivos temporales, compilados, de configuración personal).

- Previene que archivos con información sensible (como contraseñas o claves de API) sean subidos por error.

- Mantiene el repositorio limpio y organizado.

### ¿Cuándo se debe hacer? 🔧

Lo ideal es crearlo antes de hacer el primer commit para evitar que Git rastree archivos que luego tendrías que eliminar. Sin embargo, si te olvidaste, puedes crearlo en cualquier momento y luego actualizar el índice de Git.

### ¿Cómo configurarlo? 🛠️

**1. Crear el archivo** _.gitignore_ en la raíz del proyecto: 

```
touch .gitignore
```
O simplemente crearlo desde un editor de texto.

**2. Agregar reglas dentro del** _.gitignore_, por ejemplo:

- **Ignorar archivo específicos:**
```
archivo.txt
```

- **Ignorar una carpeta completa:**
``` 
/carpetaPrivada/
```

- **Ignorar archivos por extensión:**
```
*.log  # Todos los archivos .log
*.tmp  # Archivos temporales
```

- **Ignorar archivos de configuración y dependencias:**
```
.env   # Variables de entorno
node_modules/  # Dependencias de Node.js
vendor/  # Dependencias de PHP
```

- **Ignorar archivos generados por el sistema:**
```
.DS_Store  # MacOS
Thumbs.db  # Windows
```

 **3. Si ya habías subido archivos antes de agregar** _.gitignore_, puedes hacer que Git los deje de rastrear con:

```
git rm --cached -r archivos_o_carpeta
```
**IMPORTANTE:**
 Si el archivo que agregaste a .gitignore ya había sido subido antes al repositorio, Git seguirá rastreándolo. Para solucionarlo, elimínalo del índice antes de hacer commit:

```
git rm --cached nombre_del_archivo
git commit -m "Ignorar nombre_del_archivo"
git push origin main
```
Después de esto, Git dejará de rastrear el archivo, pero seguirá existiendo en tu máquina local.