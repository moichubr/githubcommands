## GitHub Commands

## Comenzar creando un repositorio desde VSC
<p>Puedes iniciar un nuevo repositorio Git en tu proyecto utilizando el siguiente comando:</p>
<p><b>git init</b></p>
<p>Esto creará un nuevo repositorio Git vacío en tu proyecto local. Luego, puedes agregar y confirmar tus archivos como lo harías normalmente:</p>
<p><b>git add .</b></p>
<p><b>git commit -m "Inicializar repositorio desde cero"</b></p>

<p>Para vincular este repositorio local a un repositorio de GitHub, crea un nuevo repositorio en GitHub (si aún no lo has hecho) y sigue las instrucciones. Esto generalmente implica ejecutar comandos como:</p>

**git remote add origin https://github.com/tu-usuario/tu-repositorio.git**
<br>
**git branch -M main**
<br>
**git push -u origin main**

## Agregar un repositorio remoto
<p>Con el siguiente comando podrás conectar tu proyecto local a un repositorio remoto ya creado: </p>
<b>git remote add origin https://github.com/tu-usuario/tu-repositorio.git</b>
<p>Debes reemplazar tu-usuario por tu nombre de usuario de GitHub y tu-repositorio con el nombre del repositorio al cual quieres vincular el proyecto.</p>

## Verificar la conexión al remoto
<p>Para checkear que se ha vinculado correctamente ejecuta: <b>git remote -v</b></p>
<p>Deberías ver algo como esto:</p>
<p>origin  https://github.com/tu-usuario/tu-repositorio.git (fetch)<br>
origin  https://github.com/tu-usuario/tu-repositorio.git (push)</p>

## ERROR: merge unrelated histories
<p>Esto suele suceder cuando tienes dos ramas con historias completamente diferentes, y Git no sabe cómo fusionarlas automáticamente.
Para resolver este problema seguir estos pasos: </p>
  <ol>
<li> <b>Crea una nueva rama local:</b> En lugar de fusionar las historias directamente en la rama principal (main), crea una nueva rama local y cambia a ella. Esto te dará un lugar limpio para integrar las historias. <em>COMANDO: git checkout -b la-nueva-rama </em>
</li>
    <li>
      <b>Realiza una fusión con la opción --allow-unrelated-histories</b>: Para fusionar la rama main del repositorio remoto con tu nueva rama local, permitiendo historias no relacionadas. <em>COMANDO: git merge --allow-unrelated-histories origin/main</em>   Esto debería traer los cambios que haya en la main remote.
    </li>
    <li>
      <b>Resuelve conflictos (si los hay):</b> Si Git encuentra conflictos durante la fusión, deberás resolverlos manualmente. Luego, realiza un git add para marcar los archivos como resueltos y un git commit para confirmar los cambios.
    </li>
    <li>
      <b>Cambiate a la rama main:</b> con <em>git checkout main</em>  y haz un <em>git merge la-nueva-rama-creada</em> para mergear localmente los cambios que trajiste antes.
    </li>
    <li>Ahora sí, subiremos al repo los cambios con <em>git add . </em> , <em>git commit -m "los-cambios-que-hiciste"</em>  y <em>git push origin main</em></li>
  </ol>

## Eliminar la vinculación a Git de un repositorio local creado con Git Init
<p>COMANDO: rm -rf .git </p>
<p> Este comando eliminará el directorio .git y su contenido, lo que equivale a <b>eliminar todo el historial de Git y las configuraciones asociadas al repositorio</b>. Después de hacerlo, podrás iniciar un nuevo repositorio con git init si lo deseas.</p>

