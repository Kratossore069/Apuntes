### Crear usuarios y eliminarlos.

# encoding: utf-8

puts "Bienvenido al programa de creación y eliminación de usuarios."

puts "Estos son los usuarios que existen en el sistema."

home = `ls /home/`

puts "#{home}"

puts "* C, para CREAR usuarios"

puts "* E, para ELIMINAR eliminarlos"

puts "* S, para SALIR del programa."

el = gets.chomp

if el == "c" || el == "C"

    puts "Nombre del usuario a crear: "

    nom = gets.chomp

    `useradd #{nom}`

    `passwd #{nom}`

    `mkdir /home/#{nom}`

    `chown -R #{nom} /home/#{nom}`

    #puts "#{cre}, #{pa}, #{fu}, #{kj}"

    puts "Usuario #{nom} creado."


elsif el == "e" || el == "E"

    puts "Nombre del usuario a eliminar: "

    nom = gets.chomp

    del = `userdel -r #{nom}`

    puts "#{del}"

    puts "Usuario #{nom} eliminado."


elsif el == "s" || el == "S"

    puts "Saliendo..."

end

puts "Así queda la carpeta /home/."

casa = `ls /home/`

puts "#{casa}"

### Crear usuarios (versión 2).

# encoding: utf-8

elec = ARGV[0].to_s

def crear

  nombre = ARGV[1].to_s

  puts "Creando usuario #{nombre}."

  `useradd #{nombre}`

  `passwd #{nombre}`

  `mkdir /home/#{nombre}`

  `chown -R #{nombre} /home/#{nombre}`

  puts "Usuario #{nombre} creado."

end

def eliminar

  nombre = ARGV[1].to_s

  puts "Eliminando usuario #{nombre}."

  `userdel -r #{nombre}`

  puts "Usuario #{nombre} eliminado."

end

if elec == "crear" || elec == "on"

  crear

elsif elec == "eliminar" || elec == "off"

  eliminar

else

  puts "Salir. Comando no conocido."

end

todos = `ls /home/`

puts "Así queda la lista de usuarios."

puts "#{todos}"

### Crear y eliminar carpetas.

# encoding: utf-8

puts "1 para crear y 2 para eliminar. 3 para salir."

elecc = gets.chomp.to_i

if elecc == 1

	puts "Introduzca el nombre de la carpeta a crear."

	pa = gets.chomp

	la = `mkdir #{pa}`

	puts "#{la}"

	puts "Carpeta #{pa} creada"

elsif elecc == 2

	puts "Nombre de la carpeta a eliminar."

	yu = gets.chomp

	re = `rmdir #{yu}`

	puts "#{re}"

	puts "Carpeta #{yu} eliminada."

elsif elecc == 3

	puts "Saliendo..."

end
