# Modelo Relacional de Bases de Datos 6



## Descripción



Este documento detalla el esquema y la estructura del modelo relacional de bases de datos para un sistema de gestión de proyectos, enfocado en el control de proyectos, fases, tareas, empleados, asignación de tareas, recursos materiales y asignación de recursos.

---

## Estructura de Tablas y Atributos



### 1. Proyecto



* **PK (Clave Primaria):** `codigo_proyecto`


* **Atributos:**
* `Fecha_de_finalización`


* `Nombre_comercial`


* `Decripción_de_objetiivo`


* `Fecha_de_inicio`


* `Presupuesto_Asignado`





### 2. Fase



* **PK (Clave Primaria):** `id_Fase`


* **Atributos:**
* `Nombre`


* `Descripción`


* `Estimación_de_hora`


* `Estado`





### 3. Tarea



* **PK (Clave Primaria):** `id_Tarea`


* **Atributos:**
* `Prioridad`


* `Estado_T`


* `descripción_T`


* `Horas_estimadas`





### 4. Empleado



* **PK (Clave Primaria):** `legajo`


* **Atributos:**
* `Categoria_laboral`


* `DNI`


* `Nombre`


* `Perfil_técnico`





### 5. Asignación_Tarea



* **PK (Clave Primaria):** `id_asignacion`


* **Atributos:**
* `Rol_en_tareas`


* `Estado_Asignación`




* **FK (Claves Foráneas):**
* `id_Tarea` (asociado a la tabla Tarea)


* `legajo` (asociado a la tabla Empleado)





### 6. Recuros_Material



* **PK (Clave Primaria):** `Nr_inventraio`


* **Atributos:**
* `marca`


* `tipo_recurso`


* `Estado_R`


* `descripción_R`


* `Numero_de_serie`





### 7. Asignación_Recurso



* **PK (Clave Primaria):** `asignacion_recurso`


* **Atributos:**
* `Fecha_devolución`


* `observacion`




* **FK (Claves Foráneas):**
* `Nr_inventraio` (asociado a la tabla Recuros_Material)


* `codigo_proyecto` (asociado a la tabla Proyecto)





---

## Relaciones Principales



* **Proyecto y Fase:** Un proyecto se divide en diferentes fases organizativas.


* **Fase y Tarea:** Cada fase agrupa un conjunto de tareas concretas a realizar.


* **Tarea y Empleado (Asignación_Tarea):** La asignación de personal a tareas específicas se gestiona mediante la tabla `Asignación_Tarea`, utilizando `id_Tarea` y `legajo`.


* **Proyecto y Recuros_Material (Asignación_Recurso):** La asignación de insumos/equipamiento a cada proyecto se administra a través de `Asignación_Recurso`, vinculando `codigo_proyecto` y `Nr_inventraio`.
