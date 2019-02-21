### Crear usuarios y eliminarlos.

puts "Bienvenido al programa de creación y eliminación de usuarios."

puts "C para crear usuarios."

puts "E para eliminarlos."

puts "S para salir del programa."

el = gets.chomp

if el == "C" || el == "c"

	puts "Nombre del usuario a crear: "

	nom = gets.chomp

	`useradd #{nom}`

	`passwd #{nom}`

	`mkdir /home/#{nom}`

	`chown -R #{nom} /home/#{nom}`

	puts "Usuario #{nom} creado."

elsif el == "E" || el == "e"

	puts "Nombre del usuario a eliminar: "

	nom = gets.chomp

	`userdel -r #{nom}`

	puts "Usuario #{nom} eliminado."

elsif el == "s" || el == "S"

	puts "Saliendo..."

end

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
