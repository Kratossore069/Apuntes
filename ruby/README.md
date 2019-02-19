# Crear usuarios.

# encoding: utf-8

puts "Nombre del usuario a crear: "
nom = gets.chomp
cre = `useradd #{nom}`
pa = `passwd #{nom}`
fu = `mkdir /home/#{nom}`
kj = `chown -R #{nom} /home/#{nom}`
puts "#{cre}"
puts "#{pa}"
puts "#{fu}"
puts "#{kj}"

# Eliminar usuarios.

# encoding: utf-8

puts "Nombre del usuario a eliminar: "
nom = gets.chomp
del = `userdel -r #{nom}`
puts "#{del}"
