# Mini-Sistema-Concurso
#Enunciado:
#Desarrolla un sistema en Java que gestione la inscripción de participantes para un concurso de natación, aplicando los principios de la Programación Orientada a Objetos (POO).
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
• Crear una clase base Participante que contenga los atributos comunes y un método puedeParticipar() que valide la edad y condición de salud.
public class Participante {
    private String nombre;
    private int edad;
    private String genero; // Considerar usar un enum si los valores son fijos (ej. "M", "F", "Otro")
    private boolean buenaCondicionSalud;
    private String tipoEntidad; // Para identificar el tipo de entidad general

    public Participante(String nombre, int edad, String genero, boolean buenaCondicionSalud, String tipoEntidad) {
        this.nombre = nombre;
        this.edad = edad;
        this.genero = genero;
        this.buenaCondicionSalud = buenaCondicionSalud;
        this.tipoEntidad = tipoEntidad;
    }

    // Método para verificar si el participante cumple los requisitos generales
    public boolean cumpleRequisitos() {
        // Requisitos: entre 18 y 25 años y en buena condición de salud
        return (this.edad >= 18 && this.edad <= 25) && this.buenaCondicionSalud;
    }

    // Getters
    public String getNombre() {
        return nombre;
    }

    public int getEdad() {
        return edad;
    }

    public String getGenero() {
        return genero;
    }

    public boolean isBuenaCondicionSalud() {
        return buenaCondicionSalud;
    }

    public String getTipoEntidad() {
        return tipoEntidad;
    }

    // Setters (opcionales, dependiendo de si se permite modificar estos atributos después de la creación)
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public void setEdad(int edad) {
        this.edad = edad;
    }

    public void setGenero(String genero) {
        this.genero = genero;
    }

    public void setBuenaCondicionSalud(boolean buenaCondicionSalud) {
        this.buenaCondicionSalud = buenaCondicionSalud;
    }

    public void setTipoEntidad(String tipoEntidad) {
        this.tipoEntidad = tipoEntidad;
    }

    // Método toString para una representación fácil de imprimir
    @Override
    public String toString() {
        return "Nombre: " + nombre +
                ", Edad: " + edad +
                ", Género: " + genero +
                ", Salud: " + (buenaCondicionSalud ? "Buena" : "No buena") +
                ", Tipo de Entidad: " + tipoEntidad;
    }
}
• Crear al menos cuatro subclases que hereden de Participante:
- ParticipanteColegio
public class ColegioParticipante extends Participante {
    private String nombreColegio;

    public ColegioParticipante(String nombre, int edad, String genero, boolean buenaCondicionSalud, String nombreColegio) {
        super(nombre, edad, genero, buenaCondicionSalud, "Colegio"); // "Colegio" es el tipo de entidad general
        this.nombreColegio = nombreColegio;
    }

    public String getNombreColegio() {
        return nombreColegio;
    }

    public void setNombreColegio(String nombreColegio) {
        this.nombreColegio = nombreColegio;
    }

    @Override
    public String toString() {
        return super.toString() + ", Nombre del Colegio: " + nombreColegio;
    }
}
- ParticipanteUniversidad
public class UniversidadParticipante extends Participante {
    private String nombreUniversidad;

    public UniversidadParticipante(String nombre, int edad, String genero, boolean buenaCondicionSalud, String nombreUniversidad) {
        super(nombre, edad, genero, buenaCondicionSalud, "Universidad"); // "Universidad" es el tipo de entidad general
        this.nombreUniversidad = nombreUniversidad;
    }

    public String getNombreUniversidad() {
        return nombreUniversidad;
    }

    public void setNombreUniversidad(String nombreUniversidad) {
        this.nombreUniversidad = nombreUniversidad;
    }

    @Override
    public String toString() {
        return super.toString() + ", Nombre de la Universidad: " + nombreUniversidad;
    }
}
- ParticipanteEmpresa (debe indicar si es pública o privada)
public class EmpresaPublicaParticipante extends Participante {
    private String nombreEmpresaPublica;

    public EmpresaPublicaParticipante(String nombre, int edad, String genero, boolean buenaCondicionSalud, String nombreEmpresaPublica) {
        super(nombre, edad, genero, buenaCondicionSalud, "Empresa Pública"); // "Empresa Pública" es el tipo de entidad general
        this.nombreEmpresaPublica = nombreEmpresaPublica;
    }

    public String getNombreEmpresaPublica() {
        return nombreEmpresaPublica;
    }

    public void setNombreEmpresaPublica(String nombreEmpresaPublica) {
        this.nombreEmpresaPublica = nombreEmpresaPublica;
    }

    @Override
    public String toString() {
        return super.toString() + ", Nombre de la Empresa Pública: " + nombreEmpresaPublica;
    }
}
public class EmpresaPrivadaParticipante extends Participante {
    private String nombreEmpresaPrivada;

    public EmpresaPrivadaParticipante(String nombre, int edad, String genero, boolean buenaCondicionSalud, String nombreEmpresaPrivada) {
        super(nombre, edad, genero, buenaCondicionSalud, "Empresa Privada"); // "Empresa Privada" es el tipo de entidad general
        this.nombreEmpresaPrivada = nombreEmpresaPrivada;
    }

    public String getNombreEmpresaPrivada() {
        return nombreEmpresaPrivada;
    }

    public void setNombreEmpresaPrivada(String nombreEmpresaPrivada) {
        this.nombreEmpresaPrivada = nombreEmpresaPrivada;
    }

    @Override
    public String toString() {
        return super.toString() + ", Nombre de la Empresa Privada: " + nombreEmpresaPrivada;
    }
}
- ParticipanteSindicato
public class SindicatoParticipante extends Participante {
    private String nombreSindicato; // O tipoSindicato, según prefieras

    public SindicatoParticipante(String nombre, int edad, String genero, boolean buenaCondicionSalud, String nombreSindicato) {
        super(nombre, edad, genero, buenaCondicionSalud, "Sindicato"); // "Sindicato" es el tipo de entidad general
        this.nombreSindicato = nombreSindicato;
    }

    public String getNombreSindicato() {
        return nombreSindicato;
    }

    public void setNombreSindicato(String nombreSindicato) {
        this.nombreSindicato = nombreSindicato;
    }

    @Override
    public String toString() {
        return super.toString() + ", Nombre del Sindicato: " + nombreSindicato;
    }
}
import java.util.ArrayList;
import java.util.List;

public class GestionConcursoNatacion {
    private List<Participante> listaParticipantes;

    public GestionConcursoNatacion() {
        this.listaParticipantes = new ArrayList<>();
    }

    /**
     * Inscribe un participante en el concurso.
     * @param participante El objeto Participante a inscribir.
     */
    public void inscribirParticipante(Participante participante) {
        listaParticipantes.add(participante);
        System.out.println("Participante " + participante.getNombre() + " inscrito.");
    }

    /**
     * Obtiene una lista de participantes que cumplen con los requisitos para el concurso.
     * @return Una lista de objetos Participante calificados.
     */
    public List<Participante> obtenerParticipantesCalificados() {
        List<Participante> calificados = new ArrayList<>();
        for (Participante p : listaParticipantes) {
            if (p.cumpleRequisitos()) {
                calificados.add(p);
            }
        }
        return calificados;
    }

    /**
     * Muestra los detalles de una lista de participantes.
     * @param participantes La lista de participantes a mostrar.
     */
    public void mostrarDetalleParticipantes(List<Participante> participantes) {
        if (participantes.isEmpty()) {
            System.out.println("No hay participantes para mostrar.");
            return;
        }
        for (Participante p : participantes) {
            System.out.println(p); // Utiliza el método toString de cada Participante/subclase
        }
    }

    // Opcional: obtener todos los participantes
    public List<Participante> getListaParticipantes() {
        return listaParticipantes;
    }
}

























