# Importar los módulos necesarios
from datetime import datetime
from flask import Flask, request

app = Flask(__name__)

# Configurar la información del bot
nombre_usuario = ""
numero_bot = "1 (773) 467-3678"
creador_bot = "══⋆♛cєвя3y1♛⋆══"
version_actual = "1.0 Vers > Próxima 1.5 Vers"

# Ruta principal del bot
@app.route('/')
def main():
    return "¡Bienvenido(a) al bot de Termux Wasap!"

# Ruta para la información del usuario
@app.route('/informacion', methods=['POST'])
def informacion():
    fecha_actual = datetime.now().strftime("%d/%m/%Y")
    tiempo_activo = datetime.now().strftime("%H:%M:%S")
    usuario = request.form['usuario']
    
    respuesta = f"Información:\n"
    respuesta += f"Nombre del Usuario: {nombre_usuario}\n"
    respuesta += f"Fecha: {fecha_actual}\n"
    respuesta += f"Tiempo Activo: {tiempo_activo}\n"
    respuesta += f"Usuario: {usuario}\n"
    
    return respuesta

# Ruta para los datos e información
@app.route('/datos', methods=['POST'])
def datos():
    fecha_actual = datetime.now().strftime("%d/%m/%Y")
    tiempo_activo = datetime.now().strftime("%H:%M:%S")
    usuario = request.form['usuario']
    
    respuesta = f"Datos e Información:\n"
    respuesta += f"Nombre del Usuario: {nombre_usuario}\n"
    respuesta += f"Fecha: {fecha_actual}\n"
    respuesta += f"Tiempo Activo: {tiempo_activo}\n"
    respuesta += f"Usuario: {usuario}\n"
    
    return respuesta

# Ruta para las estadísticas
@app.route('/estadisticas')
def estadisticas():
    nivel = 1
    experiencia = "0/10"
    estatus = "Novato"
    
    respuesta = f"Estadísticas:\n"
    respuesta += f"Nivel: {nivel}\n"
    respuesta += f"Experiencia: {experiencia}\n"
    respuesta += f"Estatus: {estatus}\n"
    
    return respuesta

# Iniciar el bot
if __name__ == '__main__':
    app.run()
