""" Trabajo Practico N°  7
Nombre y Apellido: Capurro Sofia
Comisión: Jueves - virtual
tips:
- para comentar codigo se usa # o comillas triples 
- si se usa vscode, se puede usar el comando ctrl+k, ctrl+c
"""

"""
Ejercicio 01: Escribir una clase llamada Rectángulo que contenga una base y una altura, y que contenga un método que devuelva el área
del rectángulo 
"""
# class Rectangulo:
#     def __init__(self, base, altura):
#         self.base = base
#         self.altura = altura

#     def area(self):
#         return self.base * self.altura

# rectangulo = Rectangulo(5, 10)
# print("El área del rectángulo es:", rectangulo.area())


"""
Ejercicio 02: Modelar una clase Mate que describa el funcionamiento de la conocida bebida tradicional argentina. La clase debe contener
como miembros:
o Un atributo para la cantidad de cebadas restantes hasta que se lava el mate (representada por un número).
o Un atributo para el estado (lleno o vacío).
o Un atributo n, que indica la cantidad máxima de cebadas.
o Un método cebar, que llena el mate con agua. Si se intenta cebar con el mate lleno, se debe lanzar una
excepción que imprima el mensaje ¡Cuidado! ¡Te quemaste!
o Un método beber, que vacía el mate y le resta una cebada disponible. Si se intenta beber un mate vacío, se
debe lanzar una excepción que imprima el mensaje: ¡El mate está vacío!
o Es posible seguir cebando y bebiendo el mate aunque no haya cebadas disponibles. En ese caso la cantidad
de cebadas restantes se mantendrá en 0, y cada vez que se intente beber se debe imprimir un mensaje de aviso:
“Advertencia: el mate está lavado.” pero no se debe lanzar una excepción.

"""
# class Mate:
#     def __init__(self, n):
#         self.n = n  
#         self.cantidad_cebadas = n  
#         self.estado = "vacío"  
    
#     def cebar(self):
#         if self.estado == "lleno":
#             raise Exception("¡Cuidado! ¡Te quemaste!")
#         else:
#             if self.cantidad_cebadas > 0:
#                 self.estado = "lleno"
    
#     def beber(self):
#         if self.estado == "vacío":
#             if self.cantidad_cebadas > 0:
#                 raise Exception("¡El mate está vacío!")
#             else:
#                 print("Advertencia: el mate está lavado.")
#         else:
#             if self.cantidad_cebadas > 0:
#                 self.cantidad_cebadas -= 1
#                 if self.cantidad_cebadas == 0:
#                     self.estado = "vacío"
#             else:

#                 self.estado = "vacío"
#                 print("Advertencia: el mate está lavado.")
    
#     def __str__(self):
#         return f"Mate(status={self.estado}, cebadas restantes={self.cantidad_cebadas}, max_cebadas={self.n})"

# if __name__ == "__main__":
#     mate = Mate(3)
#     print(mate)  
#     mate.cebar()  
#     print(mate)  
    
#     try:
#         mate.cebar()  
#     except Exception as e:
#         print(e)
    
#     mate.beber()  
#     print(mate)  
    
#     mate.beber()
#     mate.beber()  
#     mate.beber() 
    
#     try:
#         mate.beber()  
#     except Exception as e:
#         print(e)


"""
Ejercicio 03: Botella y Sacacorchos
 Escribir una clase Corcho, que contenga un atributo bodega (cadena con el nombre de la bodega).
 Escribir una clase Botella que contenga un atributo corcho con una referencia al corcho que la tapa, o None si está
destapada.
 Escribir una clase Sacacorchos que tenga un método destapar que le reciba una botella, le saque el corcho y se guarde
una referencia al corcho sacado. Debe lanzar una excepción en el caso en que la botella ya esté destapada, o si el
sacacorchos ya contiene un corcho.
 Agregar un método limpiar, que saque el corcho del sacacorchos, o lance una excepción en el caso en el que no haya
un corcho
"""
# class Corcho:
#     def __init__(self, bodega):
#         self.bodega = bodega  

#     def __str__(self):
#         return f"Corcho de la bodega {self.bodega}"


# class Botella:
#     def __init__(self, corcho=None):
#         self.corcho = corcho

#     def destapar(self):
#         if self.corcho is None:
#             raise Exception("¡La botella ya está destapada!")
#         corcho_sacado = self.corcho
#         self.corcho = None
#         return corcho_sacado

#     def __str__(self):
#         if self.corcho:
#             return f"Botella con {self.corcho}"
#         else:
#             return "Botella destapada"


# class Sacacorchos:
#     def __init__(self):
#         self.corcho_sacado = None  

#     def destapar(self, botella):
#         if botella.corcho is None:
#             raise Exception("¡La botella ya está destapada!")
#         if self.corcho_sacado is not None:
#             raise Exception("¡El sacacorchos ya contiene un corcho!")
        
#         self.corcho_sacado = botella.destapar()  
        
#     def limpiar(self):
#         if self.corcho_sacado is None:
#             raise Exception("¡El sacacorchos está vacío!")
#         self.corcho_sacado = None

#     def __str__(self):
#         if self.corcho_sacado:
#             return f"Sacacorchos con {self.corcho_sacado}"
#         else:
#             return "Sacacorchos vacío"


# if __name__ == "__main__":
#     corcho = Corcho("Bodega del Vino")
#     botella = Botella(corcho)
#     sacacorchos = Sacacorchos()
    
#     print(botella)  
    
#     sacacorchos.destapar(botella)
#     print(botella)  
#     print(sacacorchos)  

#     try:
#         sacacorchos.destapar(botella)  
#     except Exception as e:
#         print(e)
    
#     sacacorchos.limpiar()
#     print(sacacorchos) 

#     try:
#         sacacorchos.limpiar() 
#     except Exception as e:
#         print(e)


"""
Ejercicio 04: Una heladería es un tipo especial de restaurante. Cree una clase Restaurante, cuyo método __init__() guarde dos atributos:
restaurante_nombre y tipo_comida. Cree un método describir_restaurante() que muestre estas piezas de información, y un
método abrir_restaurante() que muestre un mensaje indicando que el restaurante ahora está abierto. Luego cree una clase
Heladeria que herede de Restaurante, y agregue a los existentes un atributo llamado sabores que almacene una lista de los
sabores de helado disponibles. Escriba también un método que muestre estos valores, cree una instancia de la clase y llame
al método
"""
# class Restaurante:
#     def __init__(self, restaurante_nombre, tipo_comida):
#         self.restaurante_nombre = restaurante_nombre
#         self.tipo_comida = tipo_comida
    
#     def describir_restaurante(self):
#         return f"Nombre del restaurante: {self.restaurante_nombre}\nTipo de comida: {self.tipo_comida}"
    
#     def abrir_restaurante(self):
#         return f"El restaurante {self.restaurante_nombre} ahora está abierto."


# class Heladeria(Restaurante):
#     def __init__(self, restaurante_nombre, sabores):
#         super().__init__(restaurante_nombre, "Helados")
#         self.sabores = sabores
    
#     def mostrar_sabores(self):
#         return "Sabores disponibles:\n" + "\n".join(self.sabores)
    
#     def describir_restaurante(self):
#         base_desc = super().describir_restaurante()
#         return f"{base_desc}\nSabores disponibles:\n{self.mostrar_sabores()}"

# if __name__ == "__main__":

#     mi_heladeria = Heladeria("Delicias Geladas", ["Vainilla", "Chocolate", "Fresa", "Menta"])
    
#     print(mi_heladeria.describir_restaurante())
    
#     print(mi_heladeria.abrir_restaurante())


"""
Ejercicio 05:Escribir una clase Personaje que contenga los atributos vida, posicion y velocidad, y los métodos recibir_ataque, que
reduzca la vida según una cantidad recibida y lance una excepción si la vida pasa a ser menor o igual que cero, y mover
que reciba una dirección y se mueva en esa dirección la cantidad indicada por velocidad.
 Escribir una clase Soldado que herede de Personaje, y agregue el atributo ataque y el método atacar, que reciba otro
personaje, al que le debe hacer el daño indicado por el atributo ataque.
 Escribir una clase Campesino que herede de Personaje, y agregue el atributo cosecha y el método cosechar, que
devuelva la cantidad cosechada
"""
# class Personaje:
#     def __init__(self, vida, posicion, velocidad):
#         self.vida = vida
#         self.posicion = posicion
#         self.velocidad = velocidad
    
#     def recibir_ataque(self, cantidad):
#         self.vida -= cantidad
#         if self.vida <= 0:
#             raise Exception("¡El personaje ha sido derrotado!")
    
#     def mover(self, direccion, cantidad):
#         if direccion == "arriba":
#             self.posicion[1] += cantidad
#         elif direccion == "abajo":
#             self.posicion[1] -= cantidad
#         elif direccion == "izquierda":
#             self.posicion[0] -= cantidad
#         elif direccion == "derecha":
#             self.posicion[0] += cantidad
#         else:
#             raise ValueError("Dirección no válida. Use 'arriba', 'abajo', 'izquierda', o 'derecha'.")
    
#     def __str__(self):
#         return f"Vida: {self.vida}, Posición: {self.posicion}, Velocidad: {self.velocidad}"


# class Soldado(Personaje):
#     def __init__(self, vida, posicion, velocidad, ataque):
#         super().__init__(vida, posicion, velocidad)
#         self.ataque = ataque
    
#     def atacar(self, otro_personaje):
#         if not isinstance(otro_personaje, Personaje):
#             raise TypeError("El objetivo debe ser una instancia de Personaje.")
#         otro_personaje.recibir_ataque(self.ataque)
    
#     def __str__(self):
#         return super().__str__() + f", Ataque: {self.ataque}"


# class Campesino(Personaje):
#     def __init__(self, vida, posicion, velocidad, cosecha):
#         super().__init__(vida, posicion, velocidad)
#         self.cosecha = cosecha
    
#     def cosechar(self):
#         return self.cosecha
    
#     def __str__(self):
#         return super().__str__() + f", Cosecha: {self.cosecha}"


# if __name__ == "__main__":

#     soldado = Soldado(100, [0, 0], 5, 20)
#     campesino = Campesino(50, [10, 10], 3, 30)
    
#     print(soldado)
#     print(campesino)
    
#     soldado.mover("derecha", 10)
#     print(soldado)
    
#     print(f"Cantidad cosechada por el campesino: {campesino.cosechar()}")

#     soldado.atacar(campesino)
#     print(campesino) 
   
#     try:
#         campesino.recibir_ataque(40) 
#     except Exception as e:
#         print(e)


"""
Ejercicio 06:Usuarios: Cree una clase Usuario. Cree también dos atributos nombre y apellido, así como otros atributos que típicamente
se guardan en un perfil de usuario. Escriba un método describir_usuario() que muestre un resumen de la información del
usuario. Escriba otro método saludar_usuario() que muestre un saludo personalizado al usuario.
Cree varias instancias que representen distintos usuarios y llame ambos métodos para cada uno
"""
# class Usuario:
#     def __init__(self, nombre, apellido, email, edad, ciudad):
#         self.nombre = nombre
#         self.apellido = apellido
#         self.email = email
#         self.edad = edad
#         self.ciudad = ciudad
    
#     def describir_usuario(self):
#         return (f"Nombre completo: {self.nombre} {self.apellido}\n"
#                 f"Correo electrónico: {self.email}\n"
#                 f"Edad: {self.edad}\n"
#                 f"Ciudad: {self.ciudad}")
    
#     def saludar_usuario(self):
#         return f"¡Hola, {self.nombre}! Bienvenido a tu perfil."


# if __name__ == "__main__":
  
#     usuario1 = Usuario("Juan", "Pérez", "juan.perez@example.com", 30, "Madrid")
#     usuario2 = Usuario("Ana", "Gómez", "ana.gomez@example.com", 25, "Barcelona")
#     usuario3 = Usuario("Carlos", "Sánchez", "carlos.sanchez@example.com", 40, "Valencia")

#     for usuario in [usuario1, usuario2, usuario3]:
#         print(usuario.describir_usuario())
#         print(usuario.saludar_usuario())
#         print()  

"""
Ejercicio 07: Admin: Un administrador es un tipo de usuario con privilegios especiales. Cree una clase Admin que herede de la clase
Usuario del ejercicio anterior y agréguele un atributo privilegios que almacene una lista de strings tales como “puede
postear en el foro”, “puede borrar un post”, “puede banear usuario”, etc. Escriba un método mostrar_privilegios() que
muestre el conjunto de privilegios del administrador, cree una instancia de la clase y llame al método.
"""

# class Usuario:
#     def __init__(self, nombre, correo):
#         self.nombre = nombre
#         self.correo = correo

#     def mostrar_info(self):
#         print(f"Nombre: {self.nombre}")
#         print(f"Correo: {self.correo}")


# class Admin(Usuario):
#     def __init__(self, nombre, correo, privilegios=None):
#         super().__init__(nombre, correo)  
#         if privilegios is None:
#             privilegios = []  
#         self.privilegios = privilegios

#     def mostrar_privilegios(self):
#         if self.privilegios:
#             print("Los privilegios del administrador son:")
#             for privilegio in self.privilegios:
#                 print(f"- {privilegio}")
#         else:
#             print("No hay privilegios disponibles.")

# admin1 = Admin("Carlos", "carlos@ejemplo.com", ["Puede postear en el foro", "Puede borrar un post", "Puede banear usuarios"])
# admin1.mostrar_info()         
# admin1.mostrar_privilegios()    


"""
Ejercicio 08: Privilegios: Escriba una clase Privilegios. La clase debería tener un atributo, privilegios, que almacene una lista de strings
con los privilegios de manera similar a la del ejercicio 7. Mueva el método mostrar_privilegios() de ese ejercicio a esta
clase, y haga que una instancia de esta clase sea un atributo de la clase Admin. Cree una nueva instancia de Admin y use
el método para mostrar privilegios.

"""
# Definimos la clase Privilegios
# class Privilegios:
#     def __init__(self, privilegios=None):
#         if privilegios is None:
#             privilegios = []
#         self.privilegios = privilegios

#     def mostrar_privilegios(self):
#         if self.privilegios:
#             print("Los privilegios del administrador son:")
#             for privilegio in self.privilegios:
#                 print(f"- {privilegio}")
#         else:
#             print("No hay privilegios disponibles.")

# class Admin:
#     def __init__(self, nombre, privilegios=None):
#         self.nombre = nombre
#         self.privilegios = Privilegios(privilegios)

#     def mostrar_privilegios(self):
#         self.privilegios.mostrar_privilegios()

# admin1 = Admin("Carlos", ["Acceso a todos los archivos", "Modificar configuraciones", "Eliminar cuentas"])
# admin1.mostrar_privilegios()


"""
Ejercicio 09: Restaurante importado: Escriba un programa que esté en otro archivo que la clase Restaurante del ejercicio 4, e impórtela
al módulo actual. Cree una instancia de Restaurante y llame a alguno de sus métodos para asegurarse que la importación
funcionó
"""

# from restaurante import Restaurante

# mi_restaurante = Restaurante("La Bella Italia", "Italiana")

# mi_restaurante.describir_restaurante()
# mi_restaurante.abrir_restaurante()


"""
Ejercicio 10: Ingrese aqui la consigna
"""
# from restaurante import Heladeria

# heladeria = Heladeria("Helados del Mundo", "Helados", ["Vainilla", "Chocolate", "Fresa", "Menta"])
# heladeria.describir_restaurante()  
# heladeria.abrir_restaurante()      
# heladeria.mostrar_sabores()        
