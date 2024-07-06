# def-login-backend
validacion de credenciales
# Funcion para definir las listas de usuarios, contraseñas y roles
def bd_container():
    users = ["jguadamuz", "rruiz", "yperalta", "ncarrillo", "mbencomo"]
    passwords = ["037679", "a12345_", "a4321_", "a54321_", "51234_"] 
    roles = ["administrador", "user", "user", "user", "user"]
    return users, passwords, roles

# Función de inicio de sesión
def login():
    users, passwords, roles = bd_container()

    username = input("Enter your username: ")
    password = input("Enter your password: ")
    
    # Verificar si el usuario existe en la lista de usuarios
    if username in users:
        # Obtener el índice del usuario
        index = users.index(username)
        
        # Verificar si la contraseña coincide
        if passwords[index] == password:
            print(f'Welcome {username}, Rol: {roles[index]}')
        else:
            print('Incorrect password. Please try again.')
            espacio()
            login()
    else:
        print('Username not found. Please try again.')
        espacio()
        login()

# Función para imprimir un espacio
def espacio():
    print("*********************************************")        
    
    
# Intentos de inicio de sesión

login()
espacio()
login()
