# P2-VolumesApache
**1.Comproba que a tes a imaxe httpd**

Para comprobar que temos a imaxen httpd, usaremos o comando `docker images` , que no meu caso si a tiña. No  caso de non tela, usaría o comando `docker pull httpd`.

**2.Crea un contenedor de nome 'asir_httpd'.**

Para crear un novo contendor , usamos o comando `docker run -dit --name asir_httpd httpd`, onde se iniciará coa imaxen httpd.

**3.Mapea o porto 80 do contenedor có 8080 da túa máquina.**

Para mapear o porto, usaremos o comando `docker run -d p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd`.

**4.Mostra unha páxina html aloxada no apache2 dende o teu navegador.**

Para mostrar unha páxina html debemos engadir un aruqivo html (no meu caso chamado index.html) na carpeta htdocs, onde previamente tuvimos que dar permisos para engadir ficheiros nesta carpeta. Unha vez feito, iremos a un navegador e buscaremos **localhost8080**, e poderemos observar o html que engadimos.

**5.Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000**

Neste caso poderemos xuntar os paso 2 e 3 nun solo comando, neste caso o comando sería `docker run -d --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd`.

**6.Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.**

Como no exercicio anterior, empregaremos o anterior comando pero cambiando as cousas necesarios, onde o comando quedaría `docker run -d --name asir_web2 -p 8090:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd`.

**Comproba que los dous servidores mostran a mesma páxina**

Para comprobar que mostran a misma páxina, buscaremos no navegador **localhost8000** e **localhost8090**, e poderemos observar que mostran a misma páxina html.
