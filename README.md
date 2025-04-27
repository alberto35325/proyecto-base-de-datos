PROYECTO ESCUELA
                                            
indice:
1.-Introduccion.
2.-Anlisis y opinion del enunciado.
3.-Modelo conceptual.
4.-Modelo racional.
5.-Implementacion en Mysql.
6.-Consultas propuestas.
7.-Ampliacion de la base de datos.
8.-Vistas y Triggers.
9.-Pruebas y Validacion.                                            
10.-Conclusiones.
11.-Anexos.
                                              
1.-INTRODUCCION:
Para este proyecto e tomado la decicion de emplear una base de datos la cual ara referencia a una institucion promedio poseyendo por ende alumnos, cursos, profesores, tambien pondre matriculas y porsupuesto clases, empezare con esto, luego ampliare mas este esquema.

2.-ANALISIS Y OPINION DEL ENUNCIADO:
Ya e leido muchas veces el enunciado y las tareas que tengo que sobrellevar y me parecen bastantes, pero con calma yo creo que lo hare de forma correcta probablemente me la pase revisando la teoria y los ejemplos tratados en clase, pero con el principio no creo q posee mucho problema ya que el modelo conceptual y racional lo lllevo bastante bien y no  me parece muy dificil, luego el implementarlo en Mysql tampoco creo que tarde mucho, con las consultas tardare mas, luego ampliare la base de datos lo cual no creo que sea un problema mas alla de que no se me ocurra datos suficentes, las pruebas y los triggers si quen me preocupan pero ya eso junto  a las pruebas  y validacion serian casi lo ultimo asi que  no tendre prisa y ire poco a poco avanzandolo.

3.-MODELO CONCEPTUAL:
Como dije antes el modelo conceptual no me preocupa mucho lo unico en lo que tengo que pensar son en las relaciones que poseen mis atributos los cuales no son muy complejos siendo asi como simplemente pensado podemos averiguar relacones como la de estudiante clase, siendo un ejemplo como un estudiante puede estar en multiples clases igual que este un profesor puede impartir multiples clases y un curso puede posser muchas clases asociadas en cambio una clase solo esta en un curso y solo la da un profesor, deduciendo asi facilmente el tipo de relacion entre estos atributos y porsupuesto a cada atributo le añadi datos indispensables como son:

Estudiante
ID estudiante.
Nombre.
Apellido.
Fecha de Nacimiento.
Dirección.
Teléfono.
Email.

Profesor:
ID profesor.
Nombre.
Apellido.
Especialidad.
Teléfono.
Email.

Curso:
ID curso.
Nombre del Curso.
Descripción.
Créditos.

Clase:
ID clase.
Curso ID.
Profesor ID.
Horario.
Aula.

Matricula:
ID matricula.
Estudiante ID.
Clase ID.
Fecha de Matrícula.

lo unico es tratar de dejar el modelo conceptual lo mas limpio posible.

4.-MODELO RACIONAL:
Ahora para el modelo racional me fui a mysql y me puse a hacer el modelo como ya tenia marcado sus relaciones no me fue muy dificil solo fue crear las tablas y poner en cada atributo las cosas que nesesitaba, marcando los id de los atributos como auto incrementales poniendo las fechatiempo en datatime, poniendo los varchar con un limite de doscientas palabras de tope y para las mas pequeñas como pueden ser y email y telefono poniendole veinte, solo tueve que unisr las tablas que tenian relacions con las flechitas dandole asi el id alos atributos que lo adquirian.

5.-IMPLEMENTACION MYSQL:
Como ya habia planteado my modelo relacional directamente en mysql workbench no tuve el mayor problema en este punto y solo tuve que sincronizar my modelo.

6.-CONSULTAS PROPUESTAS:
Las consultas que yo voy a proponer va a ser cuatro las cuales no van a ser especialmente conplejas, estas cuatro van a hacer funciones utiles como pueden ser:

1.-Listar los alumnos matriculados en un curso especifico.
2.-Obtener el numero de estudiantes matriculados en cada curso.
3.-Listar los profesores y los cursos que estos imparten.
4.-Encontrar todas las clases que se imparten en un aula especifica.

para el primero se puede ver como se utilizan los uniones joins en las tablas matriculas, estudieante, clase y curso, para luego filtrar por el curso que deseamos, luego en el segundo ejemplo volvemos a unir tablas las cuales serian curso, clase y matricula, agrupamos los resultados por el nombre del curso y luego se utiliza count para calcular el numero de estudiante de cada curso matriculado, luego en el tercero volvemos a unir tablas las cuales serian profesor, clase y curso despues se seleciona los nombres de los profesor y el curso que imparten, por ultimo volvemos a unir de nuevo tablas las cuales son clase y curso, luego filtramos por aula especifica esto nos permitira poseer los cursos y horarios.

7.-AMPLIACION DE LA BASE DE DATOS:
Para ampliar la base de datos e decidido añadir tres nuevos atributos estos atributos son 
Agregar una Tabla de Asignaturas:

Asignatura:
id asignatura (INT, PRIMARY KEY, AUTO_INCREMENT)
nombreasignatura (VARCHAR(255), NOT NULL)
id_curso (INT)
id_profesor (INT)

Calificacion:
id calificacion (INT, PRIMARY KEY, AUTO_INCREMENT)
id estudiante (INT)
id clase (INT)
calificacion (DECIMAL(5,2))
fecha_calificacion (DATETIME)

Asistencia:
id asistencia (INT, PRIMARY KEY, AUTO_INCREMENT)
id estudiante (INT)
id clase (INT)
fecha (DATETIME)
presente (BOOLEAN)

Podemos ver como cada uno de estos nuevos atributos se relacionan con los anterios atributos para complementarlos.

8.-VISTAS Y TRIGGERS.
E creado dos vistas y un trigger, las vistas que e crado sirven para simplificar el acceso a la informacion sobre los cursos que estan tomando los estudieantes, para esto uni las tablas de matricula, clase y curso, utilize uniones para para relacionar estudiantes con las clases en la que estan, la otra vista sirve para que se vea de forma mas sencilla las clases que dan los profesores y por ultimo el trigger que estoy utilizando sirve para manterner un ultimo registro de cuando se actualiza por ultima vez la informacion de un estudiante añadi directamente una nueva columna para esta funcion.

9.-PRUEBAS Y VALIDACION:
Para probar todas las cosas que cree atras le e agrado valores aleaatorios a la tabla, le di valor a todos los atributos, cuando tuve todos los valores empeze a comprovar cada una de las tablas, consultas, vistas y triggers, ahora que le agregue datos puede ver que mis tablas estan funcionando bien, mis consultas igual no me salto ningun error, luego en las vistas y trigger igual estan perfectamente implementadas, en los triggers tambien comprobe que la seguridad estuviera bien y que solo las personas autorisadas puedan acceder.

10.-CONCLUSION:
En conclusion este proyecto de base de datos fue creado en base a una hipotetica institucion la cual gestiona sus alumnos, profesores, etc...Para esto seleccione unos atributos en concreto y empeze a trabajar en el modelo conceptual, para esto lo mas dificil que pense fue hallar las relaciones entre mis atributos, tambien dejando mi modelo conceptual lo mas limpio posible, luego para el modelo relacional decidi hacerlo directamente en Mysql workbech y de paso completaba mas facil la implementacion en Mysql, para este modelo tuve que pensar sobre todo en que valores le pondria a mis atributos, siendo asi como defini los id, los varchar, los not null, etc...Luego para las consultas pense en las cosas mas utilez como son listar atributos y buscar cosas en concreto, para esto trate de hacerlo lo mas sencillo posible siendo asi como no son consultas muy complejas, ahora para la ampliacion de la base de datos no solo añadi nuevos atributos como son los antes puesto sino que tambien empeze a implementar valores inventados y aleatorios en mis atributos ya que luego los tendria que utilizar, para las vistas y triggers busque bastante y al final decidi utilizar vistas que sirven para simplificar informacion y para el trigger le puse algo para manterner el registro de las ultimas actualizaciones y por ultimo para validar y probar mi proyecto trabaje mas que en cualquier otra parte, para esto tuve que terminar de definir los valores de cada uno de mis atributos, luego solo tuve que poner los comandos para combrovar mis tablas, luego mis consultas, mis validaciones y mis triggers, poniendo ejemplos cuando es necesario y comprobando la seguridad de mi trigger.

11.-ANEXOS:

CREATE TABLE Estudiantes (
    id_estudiante INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    fecha_nacimiento DATE,
    grado VARCHAR(10),
    direccion VARCHAR(100),
    telefono VARCHAR(15),
    ultima_actualizacion DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

CREATE TABLE Profesores (
    id_profesor INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    asignatura VARCHAR(50),
    telefono VARCHAR(15),
    email VARCHAR(100)
);

CREATE TABLE Curso (
    id_curso INT AUTO_INCREMENT PRIMARY KEY,
    nombre_curso VARCHAR(100),
    grado VARCHAR(10),
    id_profesor INT,
    anio_escolar VARCHAR(10),
    FOREIGN KEY (id_profesor) REFERENCES Profesores(id_profesor)
);

CREATE TABLE Clases (
    id_clase INT AUTO_INCREMENT PRIMARY KEY,
    id_estudiante INT,
    fecha DATE,
    hora TIME,
    FOREIGN KEY (id_estudiante) REFERENCES Estudiantes(id_estudiante)
);

CREATE TABLE Matriculas (
    id_matricula INT AUTO_INCREMENT PRIMARY KEY,
    id_estudiante INT,
    año_escolar VARCHAR(10),
    estado VARCHAR(20),
    fecha_matricula DATE,
    FOREIGN KEY (id_estudiante) REFERENCES Estudiantes(id_estudiante)
);

INSERT INTO Estudiantes (nombre, apellido, fecha_nacimiento, grado, direccion, telefono) VALUES
('Juan', 'Pérez', '2005-05-15', '10', 'Calle Falsa 123', '555-1234'),
('María', 'López', '2006-08-22', '9', 'Avenida Siempre 456', '555-5678');

INSERT INTO Profesores (nombre, apellido, asignatura, telefono, email) VALUES
('Ana', 'García', 'Matemáticas', '555-8765', 'ana@escuela.com'),
('Luis', 'Martínez', 'Historia', '555-4321', 'luis@escuela.com');

INSERT INTO Curso (nombre_curso, grado, id_profesor, anio_escolar) VALUES
('Matemáticas Avanzadas', '10', 1, '2023-2024'),
('Historia Moderna', '9', 2, '2023-2024');

INSERT INTO Clases (id_estudiante, fecha, hora) VALUES
(1, '2023-09-01', '08:00:00'),
(2, '2023-09-01', '09:00:00');

INSERT INTO Matriculas (id_estudiante, año_escolar, estado, fecha_matricula) VALUES
(1, '2023-2024', 'Matriculado', '2023-06-15'),
(2, '2023-2024', 'Matriculado', '2023-06-20');

ELECT e.nombre, e.apellido
FROM Estudiantes e
JOIN Matriculas m ON e.id_estudiante = m.id_estudiante
JOIN Curso c ON m.año_escolar = c.anio_escolar
WHERE c.nombre_curso = 'Matemáticas Avanzadas';

SELECT c.nombre_curso, COUNT(m.id_estudiante) AS numero_estudiantes
FROM Curso c
LEFT JOIN Matriculas m ON c.anio_escolar = m.año_escolar
GROUP BY c.nombre_curso;

SELECT p.nombre AS nombre_profesor, p.apellido AS apellido_profesor, c.nombre_curso
FROM Profesores p
JOIN Curso c ON p.id_profesor = c.id_profesor;

SELECT c.fecha, c.hora, e.nombre, e.apellido
FROM Clases c
JOIN Estudiantes e ON c.id_estudiante = e.id_estudiante
WHERE c.aula = 'Aula 101'; 

SELECT id_estudiante, nombre, ultima_actualizacion
FROM Estudiantes
WHERE id_estudiante = 1; 

DELIMITER //

CREATE TRIGGER Actualizar_Ultima_Actualizacion
BEFORE UPDATE ON Estudiantes
FOR EACH ROW
BEGIN
    SET NEW.ultima_actualizacion = NOW();
END;
//

DELIMITER ;

RANT SELECT ON Estudiantes TO 'usuario'@'localhost';
GRANT SELECT ON Vista_Cursos_Estudiantes TO 'usuario'@'localhost';
GRANT SELECT ON Vista_Clases_Profesores TO 'usuario'@'localhost';

GRANT UPDATE ON Estudiantes TO 'usuario'@'localhost';
