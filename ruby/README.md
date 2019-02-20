# Crear usuarios.

# encoding: utf-8

puts "Bienvenido al programa de creación y eliminación de usuarios."

puts "Y para crear usuarios, N para eliminarlos, S para salir del programa."

el = gets.chomp

if el == "y"

	puts "Nombre del usuario a crear: "

	nom = gets.chomp

	cre = `useradd #{nom}`

	pa = `passwd #{nom}`

	fu = `mkdir /home/#{nom}`

	kj = `chown -R #{nom} /home/#{nom}`

	puts "#{cre}, #{pa}, #{fu}, #{kj}"

	puts "Usuario #{nom} creado."

elsif el == "n"

	puts "Nombre del usuario a eliminar: "

	nom = gets.chomp

	del = `userdel -r #{nom}`

	puts "#{del}"

	puts "Usuario #{nom} eliminado."

elsif el == "s"

	puts "Saliendo..."
  
end
