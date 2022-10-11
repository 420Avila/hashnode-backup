# Función en la zshrc para crear directorios automáticamente.

Para poder crear una serie de directorios para tener una mejor organización al momento de realizar alguna actividad.
Los directorios son los siguientes:

- nmap → se ubican los resultados del reconocimiento y escaneo de la máquina víctima.
- content → se ubican los archivos y la información encontrada en la máquina víctima.
- exploits → se ubican los exploits utilizados.
- scripts -> se ubican los scriptsutilizados. 

Utilizando las personalizaciones de la zsh se realiza el siguiente función:
    

   # Functions:

la anterior función se colocará en el archivo de configuración situado bajo ~/.zshrc:    
   
    function mkt(){
		  mkdir {nmap,content,exploits,scripts}
     }

