# Apuntes del curso Lpic-1 Administración de Linux EXAMEN 102 

Estos son apuntes personales del curso ya mencionado,impartido por Antonio Sanchez Corbalan [Adquirir el curso aquí](https://www.udemy.com/share/1037bm3@mr3ZzuG44Kr-7Bw9ftg_dYG6dMK7vwGHUdTB9nSlY7uOmith_qw0hLHLwWtwEFSJ/)

En estos ejemplos que se llevarán a cabo los realizaré a través de un docker montado en linux 

fsp12@pop-os:~$ sudo docker --version
Docker version 20.10.17, build 100c701
fsp12@pop-os:~$

**Sentencia condicionales**
La sentencia case ejecutará unas instrucciones u otras en función del valor que encuentre en una variable o expresión

**case**

case valor in
    exp1) 

    ...
    
    ultimarden1;;
    
    exp2)
    
    ...
    
    ultimaorden2;;
    
    expN)
    
    ...
    ultimaordenN;;

esac

exp1)-<en las expresiones podemos usar los mismos comidines que en los nombres de los ficheros ? * [...]>
ultimaorde1;-> La última orden termina con doble punto y coma para indicar que termia el case

Ejemplo Case:
´´´
#!/bin/bash

#
# PROGRAMA PARA DECIR LAS NOTAS EN FUNCION DE UN NUMERO
#

read -p "Introduzca la nota numerica:" nota

case $nota in
	10)
		echo "Tienes un sobresaliente";;
	9)
		echo "Tienes un sobresaliente";;
	8)
		echo "Tienes un notable";;
	7)
                echo "Tienes un notable";;
	6)
                echo "Tienes un bien";;
	5)
                echo "Tienes un suspenso";;
	4)
                echo "Tienes un suspenso";;
	3)
                echo "Tienes un suspenso";;
	2)
                echo "Tienes un suspenso";;
	1)
                echo "Tienes un suspenso";;
esac
´´´


´´´
Mejorando el ejemplo anterior:
#!/bin/bash

#
# PROGRAMA PARA DECIR LAS NOTAS EN FUNCION DE UN NUMERO
#

read -p "Introduzca la nota numerica:" nota

case $nota in
	10|9)
		echo "Tienes un sobresaliente";;
	[87])
		echo "Tienes un notable";;
	6)
                echo "Tienes un bien";;
	5)
                echo "Tienes un suspenso";;
	[43210])
                echo "Tienes un suspenso";;
	*)
		echo "Nota incorrecta" ##no acepatará un digito fuera de 0 al 10
 esac


´´´




