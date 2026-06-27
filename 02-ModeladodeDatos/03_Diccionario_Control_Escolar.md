#Diccionario de Datos de la base de datos de control escolar 
1. Informacion General 

| ELEMENTO | VALOR |
| :--- | :--- |
| Proyecto | Control Escolar |
| Version | 1.0 |
| Fecha | Junio 2026 |
| Elaboro | Ing. Angel Jesus Perez Contreras, MTI | 
| SGBD | SQLServer |   

2.Descripcion del sistema de Base de Datos 

EL sistema administra:
- Carreras
- Alumnos 
- Profesores
- Materias 
- Grupos 
- Incripciones

Permite controlar la Oferta academica y la INscripcion de estudiantes 

3. Catalogo de restricciones utilizadas

| CODIGO | SIGNIFICADO |
| :--- | :--- |
| PK | Primary Key |
| FK | Foreing Key |
| NN | NOT NULL |
| UQ | Unuique |
| AI | Auto Increment |
| CK | Check  |
| DF | Default |

4. Diccionario de Datos 
## Tabla: Carrera 
**Descripcion**
Almacena las carreras oferyadas 

| Categoría | Tipo de Dato | Descripción | Almacenamiento | Ejemplo de Uso |
| :--- | :--- | :--- | :--- | :--- |
| **Texto / Cadena** | `VARCHAR(n)` | Cadena de texto de longitud variable. | Según caracteres ($n$ bytes) | `VARCHAR(100)` para nombres |
| **Texto / Cadena** | `NVARCHAR(n)` | Texto variable compatible con Unicode (emojis, acentos). | El doble de caracteres ($2n$ bytes) | `NVARCHAR(200)` para correos |
| **Numérico** | `INT` | Número entero estándar (positivo o negativo). | 4 bytes | `INT` para IDs o contadores |
| **Numérico** | `DECIMAL(p,s)` | Número de precisión exacta (con decimales fijos). | Variable (5-17 bytes) | `DECIMAL(10,2)` para precios |
| **Fecha / Hora** | `DATETIME2` | Fecha y hora de alta precisión. | 6 a 8 bytes | `DATETIME2` para registro de auditoría |

| CAMPO | TIPO | LONGITUD | RESTRICCIONES | DESCRIPCION |
| :--- | :--- | :--- | :--- | :--- |
| id_carrera | INT | - | PK,AI,NN | identificador |
|  |  |  |  |  |
TIPOS DE DATOS EN MY SQL , MARIA DB , POSTGRES Y SEQL SERVER 

**DESCRIPCION**
| CAMPO | TIPO | LONGITUD | RESTRICCIONES | DESCRIPCION |
| :--- | :--- | :--- | :--- | :--- |
| id_Alumno | INT | - | PK,AI,NN | identificador unico del alumno |
| Matricula | Varchar | 10 | UQ, NN | Matricula Institucional |
| nombre | VARCHAR | 30 | NN | Nombre del alumno |
| apellido_paterno | VARCHAR | 50 | NN | Apellido Paterno |
| apellido_Materno | VARCHAR | 50 | NN | Apellido Materno |
| Correo | VARCHAR | 100 | NN | Correo Institucional |
| Fecha_Nacimiento | DATE | - | NN | Fecha de nacimiento |
| id_carrera | INT | - | FK, NN | carrera a la pertenencia |


--
5. Relaciones en la Dase de Datos

| Relacion | Cardinalidad | Descripcion |
| -------- | --------- | --------- |
| Carrera --> Alumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Akumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Akumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Akumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Akumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Akumno | 1:N | Una carrera tiene muchos alumnos |

----

6. Relaciones en la Dase de Datos

| Tabla | Campo FK | Referencia |
| -------- | --------- | --------- |
| Alumno | id_Carrera | Carrera (id carrera) |
| Materia | id_Carrera | Carrera (id_carrera) |5. Relaciones en la Dase de Datos

| Relacion | Cardinalidad | Descripcion |
| -------- | --------- | --------- |
| Carrera --> Alumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchas Materias |
| Profesor --> Grupo | 1:N | Una carrera puede impartir varios grupos |
| Materia --> Grupos | 1:N | Una materia puede abrirse en varios grupos  |
| Alumno --> Inscripcion | 1:N | Un alumno puede tener varias inscripciones |
| Grupos --> Inscripcion | 1:N | Un grupo puede tener muchos alumnos |

---

| Relacion | Cardinalidad | Descripcion |
| -------- | --------- | --------- |
| Carrera --> Alumno | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchos alumnos |
| Carrera --> Materia | 1:N | Una carrera tiene muchos alumnos |
----

7. Integridad Referencial

| Reglas | Descripcion |
| :--- | :--- |
| IR-01 | No se puede regristrar un alumno con una carrera inexistente |
| IR-02 | No se puede crear un grupopara una materia inexistente |
| IF-03 | no se puede crear un grupo para un profesor inexistente |
| IR-04 | no se puede inscribir un alumno en un grupo inexistente |
| IR-05 | no se puede eliminar una carrera que tenga alumnos asiociados sin antes registrarlos o eliminarlos  |
---
8.

| Codigo  | Regla |
| :--- | :--- |
| RN-01 | Un alumno pertenece a una sola carrera |
| RN-02 | Una carrera puede tener muchos alumnos |
| RN-03 | Una carrera puede tener muchas Materias |
| RN-04 | Un profesor puede impartir varios grupos |
| RN-05 | Un grupo solo puede tener un profesor asignado  |
| RN-06 | la califiacion debe estar entre 0.0 y 10.0  |


---
9. Diagrama Relacional



 ![Resultado Ejercicio 1](../img/Relacional/EJERCICIO1.jpg)

