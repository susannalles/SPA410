# Lunes, 13 septiembre 2021

Resumen: Amanda Visconti, "Creación de sitios estáticos con Jekyll y GitHub Pages", traducido por HD CAICYT Lab team, Gimena del Rio Riande, Nidia Hernández, Romina De León, Gabriel Calarco, y Raffaele Viglianti, The Programming Historian en español 5 (2021), [https://doi.org/10.46430/phes0050.](https://programminghistorian.org/es/lecciones/sitios-estaticos-con-jekyll-y-github-pages)

El otro día en clase, y creamos una [Cuenta de usuario de GitHub ](https://programminghistorian.org/es/lecciones/sitios-estaticos-con-jekyll-y-github-pages#cuenta-de-usuario-de-github-).

# Aplicación GitHub Desktop
- Descargaros la aplicación de GitHb Desktop, así os será más fácil interactuar con vuestro repositorio en GitHub.

![IMG12](/img/img12.png)

- Traslada el archivo descargado en "Applications," haz doble click, y sigue las instrucciones.
- Autoriza la aplicación desde tu navegador.

![IMG13](/img/img13.png)

- Y confirma tu password en el navegador.

![IMG14](/img/img14.png)

- La autorización hará que se te abra la ventana para la configuración de Git, haz click en "Finish":

![IMG15](/img/img15.png)

- En la pantalla "Let's get started" selecciona "Clone a Repository from the Internet" y selecciona el que has creado para tu portfolio. Por ejemplo, en mi caso será el que crée para la cuenta de dh-miami (puedes hacerlo a través de la URL). Clica en Clone:

![IMG16](/img/img16.png)

![IMG17](/img/img17.png)

- Verás una pantalla como esta:

![IMG18](/img/img18.png)

- Ve a "View the files of your repository in Finder" para ver cómo se han descargado los archivos de tu repositorio en GitHub en tu computadora. Es decir, ahora tienes una copia de tu repositorio (tu futuro portfolio) en loca.
- Ok, ahora ya estás listo para trabajar en tu computadora y subir nuevos archivos en GitHub.

# Editor de texto
- Puedes utilizar cualquier opción de las que te recomienda el tutorial. También es una buena opción, [Visual Studio Code](https://code.visualstudio.com/). Podrías utiliar Oxygen, però no es el mejor para utilizar Markdown.

# Línea de comandos
Es necesaria para instalar determinado software.
En Mac está: Applications > Utilities > Terminal
La podéis personalizar yendo a "Preferences".

# [Instalación de dependencias](https://programminghistorian.org/es/lecciones/sitios-estaticos-con-jekyll-y-github-pages#instalaci%C3%B3n-de-dependencias-)

Ejecuta paso a paso lo siguientes comandos en tu terminal (debes esperar que terminen para ejecutar el siguiente):

## 1. XCODE
`xcode-select --install`

Una vez haya terminado, haz la prueba...

`xcode-select -v`

Y debería aparecerte:

![IMG19](/img/img19.png)

## Homebrew

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

Te pedirá tu contraseña (recuerda que no aparece aunque ty la escribas, así que no la repitas) y también que hagas click en Enter.

![IMG20](/img/img20.png)

![IMG21](/img/img21.png)

 ## Ruby y Ruby Gems

 En el tutorial, indica que debes escribir `brew install ruby` pero puede que tu computadora todavía no esté configurada y os dé este error:

![IMG22](/img/img22.png)

El secreto ahora está en configurar el "path" de vuestro terminal con las indicaciones que se daban más arriba:

![IMG23](/img/img23.png)

Estas son las líneas que deberes ejecutar:

`echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/susannalles/.zprofile`

`eval "$(/opt/homebrew/bin/brew shellenv)"`

Una vez hecho esto, vuelve a intentar el comando anterior:

`brew install ruby`

![IMG24](/img/img24.png)

## NodeJS

`brew install node`

## Jekyll

`gem install jekyll`

# Configuración de Jekyll

- Localiza tu carpeta en el Finder, en principio deberías encontrarla en Documents > GitHub > username.github.io Ahí es donde la dejamos al configurar GitHub Desktop.
- En la línea de comandos dirígete a esa carpeta: `cd /Users/tu_nombre_de_usuario_en_tu_computadora/Documents/GitHub/`, por ejemplo en mi caso sería `cd /Users/susannalles/Documents/GitHub/`.
- Ejecuta: `gem install jekyll bundler`
- Si os aparece un error como este, simplemente hacedlo como orden `sudo gem install jekyll bundler`. Os pedira vuestra password (recuerda que no aparece) y clicad "Enter":

![IMG25](/img/img25.png)

- Al acabar os saldrá un largo mensaje que acaba así:

```
Done installing documentation for bundler after 1 seconds
27 gems installed
```

- Ejecuta: `jekyll new JekyllDemo`

NOTA: aquí a mi me dio problemas de permisos. El mensaje empezaba así:

```
jekyll new JekyllDemo
/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.4/lib/ffi/library.rb:275: [BUG] Bus Error at 0x0000000104cd8000
ruby 2.6.3p62 (2019-04-16 revision 67580) [universal.arm64e-darwin20]
```

 Después de buscar mucho en Google, lo arreglé dando permisos a las carpetas donde me indicaba error. En definitiva, deben darse permisos a las carpetas y sus descendientes con esta línea de comando:

 `sudo chmod -R 777 *`

 - Ejecuta: `cd JekyllDemo` para desplazarte dentro de la carpeta de trabajo del nuevo sitio. 

 # Ejecutar un sitio web localmente 

 - Ejecuta: `bundle exec jekyll serve --watch` 
 - `bundle exec jekyll serve --watch`
 - Para parar el servidor: control-c y para activarlo: `bundle exec jekyll serve --watch`
 - Para ver tu sitio en el servidor local: http://127.0.0.1:4000/ 
 

### Super resumen de los comandos:

`xcode-select --install`

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

`echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> /Users/susanna/.bash_profile`

`export LDFLAGS="-L/usr/local/opt/ruby/lib"` (optativo)

`export CPPFLAGS="-I/usr/local/opt/ruby/include"` (optativo)

`brew install ruby`

`brew install node`

`gem install jekyll`

`sudo chmod -R 777 /Library/Ruby/Gems/2.6.0`

`gem install jekyll`

`ls`

`cd Documents/GitHub/`

`gem install jekyll bundler`

`jekyll new Test`

`cd Test`

`bundle exec jekyll serve --watch`

# "Chuletas"

- Check version of xcode: `xcode-select -v` (debería ser: `xcode-select version 2384.`)
- Versión ruby: `ruby -v` (derbería ser: `ruby 2.6.3p62 (2019-04-16 revision 67580) [universal.x86_64-darwin20]`)
- Versión node: `node -v` (debería ser: `v16.9.1`)
- Versión Jekyll: `jekyll -v` (debería ser: `jekyll 4.2.0`)


