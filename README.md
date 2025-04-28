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
Como dije antes el modelo conceptual no me preocupa mucho lo unico en lo que tengo que pensar son en las relaciones que poseen mis atributos los cuales no son muy complejos siendo asi como simplemente pensado podemos averiguar relacones como la de estudiante clase, siendo un ejemplo como un estudiante puede estar en multiples clases igual que este un profesor puede impartir multiples clases y un curso puede posser muchas clases asociadas en cambio una clase solo esta en un curso y solo la da un profesor.

4.-MODELO RACIONAL:
Para el modelo relacional me fui a draw.io para empezar a hacer el esquema primero defini los atributos principales y luego me puse a meterle en base a el anterior modelo sus subatributos y sus id personalizando con colores, tambien definiendo la relaciones que posen mediante las flechas.

5.-IMPLEMENTACION MYSQL:
Para implementarlo en Mysql me fui a la cracion de modelos y cree mi proyecto de base de datos, luego empeze pasando mi racional a este modelo lo unico en lo que tuve que pensar fue en cuando poner en cada subatributo su calificativo y de que tipo eran, marque los id defini cuando eran not null y cuando no, puse un limite a las palabras que se pueden poner en determinados subatributos y luego cuando my modelo quedo igual lo sincronize y lo traspase a el Mysql normal.

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
nombre (VARCHAR(255), NOT NULL)
descripcion (VARCHAR(255))

Asistencia:
id asistencia (INT, PRIMARY KEY, AUTO_INCREMENT)
id estudiante (INT)
id clase (INT)
fecha (DATETIME)
estado (BOOLEAN)

Podemos ver como cada uno de estos nuevos atributos se relacionan con los anterios atributos para complementarlos.

8.-VISTAS Y TRIGGERS.
E creado dos vistas y un trigger, las vistas que e crado sirven para simplificar el acceso a la informacion sobre los cursos que estan tomando los estudieantes, para esto uni las tablas de matricula, clase y curso, utilize uniones para para relacionar estudiantes con las clases en la que estan, la otra vista sirve para que se vea de forma mas sencilla las clases que dan los profesores y por ultimo el trigger que estoy utilizando sirve para manterner un ultimo registro de cuando se actualiza por ultima vez la informacion de un estudiante añadi directamente una nueva columna para esta funcion.

9.-PRUEBAS Y VALIDACION:
Para probar todas las cosas que cree atras le e agrado valores aleaatorios a la tabla, le di valor a todos los atributos, cuando tuve todos los valores empeze a comprovar cada una de las tablas, consultas, vistas y triggers, ahora que le agregue datos puede ver que mis tablas estan funcionando bien, mis consultas igual no me salto ningun error, luego en las vistas y trigger igual estan perfectamente implementadas, en los triggers tambien comprobe que la seguridad estuviera bien y que solo las personas autorisadas puedan acceder.

10.-CONCLUSION:
En conclusion este proyecto de base de datos fue creado en base a una hipotetica institucion la cual gestiona sus alumnos, profesores, etc...Para esto seleccione unos atributos en concreto y empeze a trabajar en el modelo conceptual, para esto lo mas dificil que pense fue hallar las relaciones entre mis atributos, tambien dejando mi modelo conceptual lo mas limpio posible, luego para el modelo relacional decidi hacerlo directamente en Mysql workbech y de paso completaba mas facil la implementacion en Mysql, para este modelo tuve que pensar sobre todo en que valores le pondria a mis atributos, siendo asi como defini los id, los varchar, los not null, etc...Luego para las consultas pense en las cosas mas utilez como son listar atributos y buscar cosas en concreto, para esto trate de hacerlo lo mas sencillo posible siendo asi como no son consultas muy complejas, ahora para la ampliacion de la base de datos no solo añadi nuevos atributos como son los antes puesto sino que tambien empeze a implementar valores inventados y aleatorios en mis atributos ya que luego los tendria que utilizar, para las vistas y triggers busque bastante y al final decidi utilizar vistas que sirven para simplificar informacion y para el trigger le puse algo para manterner el registro de las ultimas actualizaciones y por ultimo para validar y probar mi proyecto trabaje mas que en cualquier otra parte, para esto tuve que terminar de definir los valores de cada uno de mis atributos, luego solo tuve que poner los comandos para combrovar mis tablas, luego mis consultas, mis validaciones y mis triggers, poniendo ejemplos cuando es necesario y comprobando la seguridad de mi trigger.

11.-ANEXOS:

1:Estudiante
CREATE TABLE Estudiante (
    id_estudiante INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    fecha_nacimiento DATE,
    direccion VARCHAR(100),
    telefono VARCHAR(15),
    fecha_ultima_actualizacion DATETIME
);

2.Profesor
CREATE TABLE Profesor (
    id_profesor INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    apellido VARCHAR(50),
    asignatura VARCHAR(50),
    telefono VARCHAR(15),
    email VARCHAR(100)
);

3.:Curso
CREATE TABLE Curso (
    id_curso INT AUTO_INCREMENT PRIMARY KEY,
    nombre_curso VARCHAR(50),
    id_profesor INT,
    anio_escolar INT,
    FOREIGN KEY (id_profesor) REFERENCES Profesor(id_profesor)
);

4. Tabla: Clase
CREATE TABLE Clase (
    id_clase INT AUTO_INCREMENT PRIMARY KEY,
    id_estudiante INT,
    fecha DATE,
    hora TIME,
    id_curso INT,
    FOREIGN KEY (id_estudiante) REFERENCES Estudiante(id_estudiante),
    FOREIGN KEY (id_curso) REFERENCES Curso(id_curso)
);

5.Matricula:
CREATE TABLE Matricula (
    id_matricula INT AUTO_INCREMENT PRIMARY KEY,
    id_estudiante INT,
    id_curso INT,
    estado VARCHAR(20),
    fecha_matricula DATE,
    FOREIGN KEY (id_estudiante) REFERENCES Estudiante(id_estudiante),
    FOREIGN KEY (id_curso) REFERENCES Curso(id_curso)
);

6.Asignaturas:
CREATE TABLE Asignaturas (
    id_asignatura INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50),
    descripcion TEXT
);

7. Tabla: Asistencia
CREATE TABLE Asistencia (
    id_asistencia INT AUTO_INCREMENT PRIMARY KEY,
    id_estudiante INT,
    clave_asignatura INT,
    fecha DATE,
    estado VARCHAR(20),
    FOREIGN KEY (id_estudiante) REFERENCES Estudiante(id_estudiante),
    FOREIGN KEY (clave_asignatura) REFERENCES Asignaturas(clave_asignatura)
);

 
1. Vista: Vista_Cursos_Estudiantes
sql
Run
Copy code
CREATE VIEW Vista_Cursos_Estudiantes AS
SELECT 
    e.id_estudiante,
    e.nombre AS nombre_estudiante,
    c.id_curso,
    c.nombre_curso,
    cl.fecha AS fecha_clase,
    cl.hora AS hora_clase
FROM 
    Matricula m
JOIN 
    Clase cl ON m.id_matricula = cl.id_matricula
JOIN 
    Curso c ON m.id_curso = c.id_curso
JOIN 
    Estudiante e ON m.id_estudiante = e.id_estudiante;
   
2. Vista: Vista_Clases_Profesores
sql
Run
Copy code
CREATE VIEW Vista_Clases_Profesores AS
SELECT 
    p.id_profesor,
    p.nombre AS nombre_profesor,
    cl.id_clase,
    cl.fecha AS fecha_clase,
    cl.hora AS hora_clase
FROM 
    Profesor p
JOIN 
    Clase cl ON p.id_profesor = cl.id_profesor;

3. Trigger
Trigger: Actualizar_Fecha_Ultima_Actualizacion

DELIMITER //

CREATE TRIGGER Actualizar_Fecha_Ultima_Actualizacion
BEFORE UPDATE ON Estudiante
FOR EACH ROW
BEGIN
    SET NEW.fecha_ultima_actualizacion = NOW();
END;
//

DELIMITER ;
