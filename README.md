# Mini-Sistema-Concurso
Desarrolla un sistema en Java que gestione la inscripcion de participantes para un concurso de natacion, aplicando los principios de la POO para consola. 
Enunciado:
Desarrolla un sistema en Java que gestione la inscripción de participantes para un concurso
de natación, aplicando los principios de la Programación Orientada a Objetos (POO).
Todos los participantes deben registrarse con los siguientes atributos comunes:
- Nombre
- Edad
- Género
- Condición de salud (buena o no)
- Tipo de entidad (colegio, universidad, empresa pública, empresa privada o sindicato)
Solo podrán participar personas que cumplan con los siguientes requisitos:
- Tener entre 18 y 25 años
- Estar en buena condición de salud
Cada tipo de entidad debe agregarse como una subclase de Participante, y debe incluir un
atributo propio (por ejemplo: nombre del colegio, nombre de la empresa, tipo de sindicato,
etc.).
Requisitos del sistema:
• Crear una clase base Participante que contenga los atributos comunes y un método
puedeParticipar() que valide la edad y condición de salud.
• Crear al menos cuatro subclases que hereden de Participante:
- ParticipanteColegio
- ParticipanteUniversidad
- ParticipanteEmpresa (debe indicar si es pública o privada)
- ParticipanteSindicato
• Cada subclase debe incluir su atributo adicional (ej. nombre del colegio o sindicato) y
sobrescribir un método getInfo() para mostrar los datos completos.
• Implementar getters y setters en las clases cuando sea necesario.
• Crear un menú interactivo por consola que permita:
- Registrar nuevos participantes
- Ver la lista de participantes registrados
- Ver solo los que sí pueden participar (según edad y salud)
• Validar correctamente:
- Que la edad esté entre 18 y 25 años
- Que la condición de salud sea “buena” (puede ser un booleano o un texto)
