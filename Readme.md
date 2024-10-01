# Notas

+ Siempre utilizar un lenguaje conciso y simple
+ Añadir ejemplos y capturas de pantalla
+ Ilustrar las funciones principales 



## Consideraciones para crear una aplicación

**Qué hace la aplicación - Objetivo principal**

**Cómo usar la aplicación**

**Cómo instalar la aplicación**

**Para hacer maquetas de la aplicación** se pueden usar herramientas como Figma o Sketch, que nos sirven para buscar una forma de distribuir gráficamente la aplicación, así como algunos componentes visuales. Puede ser muy útil para saber cómo comenzar. 

**Para hacer manuales de la aplicación** Podemos hacer uso de herrmientas como MarkDown o WordPress, en este caso, dado que son aplicaciónes basadas en Power Platform de Microsoft podemos hacer uso de otras herramientas del mismo ambiente como lo es **Sharepoint Site** o **Pages** lo que igualmente nos ayudaría bastante con compartir el conocimiento. 

Siempre enfocada al cliente - Función misma o desarrolladores



## Documentación

### Portada 

+ Nombre de la aplicación
+ Desarrollador
+ Propietario del proyecto
+ Fecha de inicio de desarrollo
+ Función/Departamento/Cliente
+ Gestor del Proyecto


### Temas generales (función)

Se describen de forma general una justificación para desarrollar la aplicación.

Imformación sobre: 

+ Bases de datos utilizadas 
+ Dónde se encuentran las bases de datos 
+ Usuarios (Administradores, Propietarios, Usuarios finales)
+ + Descripción de roles de los usuarios
+ Un boceto de la visualización o visualizaciones de las interfaces de usuario. 



### Temas específcos (Desarrollador)

#### Tablas

Aquí vamos a colocar las tablas existentes en la aplicaión así como una descripción sencilla de su uso dentro de la aplicación

| Nombre | Lugar | Descripción | Notas adicionales |
| --- | --- | --- | --- |
| Trabajadores | Sharepoint_url ó Dataverse | Almacena el nombre de los trabajadores | Tiene permisos de accesibilidad solo para los propietarios |

> Columnas

Aquí vamos a colocar las columnas dentro de cada tabla así como una descripción de su uso dentro de la aplicación y configuración avanzada importante.

| Nombre | Tabla | Configurazión | Notas | 
| --- | --- | --- | --- |
| FechaInicioVacaciones | Trabajadores | **Incluir Hora:** No. **Esta columna debe contener información:** Si. **Aplicar valores únicos:** No  **Agregar a todos los tipos de contenido**: Si | NA | 


#### Páginas 

**Titulo de página**

Tenemos que colocar una visualización de la página así como enumerar cada parte importante y colocar de bajo una tabla en donde describiremos la funcionalidad o descripción de cada elemento

**Foto**

| Elemento | Página | Función | Notas adicionales | 
| --- | --- | --- | --- | 
| 1: Boton Atrás | Página 2 . Formulario para añadir registro | Retroceder a la página principal | **OnSlect**: *Navigate(MainPage)* . **Visible**: *IF(Description; True; False)* | 
|  |  |  |  |  | 


#### Variables 

Aquí tenemos que colocar información sobre nuestras variables

The second Item reflexes a variable to create a Json with information from other **Input Text**, this is usefull when you want to send this information to a page to create a QR code at the end.

| Categoría | Npmbre | Inicialización | Función | Código | Uso en |
| --- | --- | --- | --- | --- | --- |
| Global | varNombreUser | Iniciando la aplicación | Tener registrado el nombre del usuario que está iniciando la aplicación | En App -> **OnStart**:*Set(varUsuarioNombre;User().FullName)* | Página: Página2, Galeria: Registro |
| Global | varCode | Al presionar el botón **Generar QR** | Almacenar información de los InputText en un Json | 1 | Página: MainScreen |
|  |  |  |  |  |  |
|  |  |  |  |  |  |

1:

``` JAVA
Set(
    varCode; 
    "Organizador : " & inOrganizador.Text & Char(10) &
    "Lugar : " & inLugar.SelectedText.Value & Char(10) & 
    "Departamento : " & inDepartamento.SelectedText.Value & Char(10) &
    "Motivo : " & inMotivo.SelectedText.Value & Char(10) & 
    "Fecha : " & inFecha.SelectedDate & Char(30)
)
//This creates a Json to send the information as a JSON to the QR generator page
```


### Firmas 

| Project owner | Project Manager  | Key user | 
| --- | --- | --- |
| singature | signature | signature | 



## Notas adicionales

La documentación debe contener información sobre: 

+ Los diferentes escenarios de usuario
+ Diferentes estadus
+ Diferentes casos de uso
+ Flujos de usuario
+ Datos simulados
+ Marcadores de posición
+ Ventanas emergentes
+ Información sobre herramientas y alertas



## Proceso para crear una aplicación

Primero es necesario tener una cuenta de Microsoft que nos permita dsarrollar aplicaciones, así como acceso al Data Verse

Lo primero que tenemos que tener en cuenta es el requerimiento del cliente, considerar la necesidad real de desarrollar una aplicación para saber qué preguntar, conocer las expectativas del cliente y tener una estimación de tiempo de entrega. 

Posterioemente tenemos que ver la distribuci´´on de la información, los agentes y entidades que intervienen. En ocaciones las bases de datos ya están creadas pero en ocaciones no, y es necesario hacer un análisis para tener una estructura que nos brinde escalabilidad y rapidez a la hora de hacer las consultas de información. 

> Para esto podemos haer uso de **Análisis de Requisitos Funcionales**, básicamente es hacer un análisis de qué información va a estar anejando la aplicación. 

> + Lista de funcionalidades: Especifica todas las funcionalidades que la aplicación debe ofrecer
> + Identificación de entidades clave: Identifica las entidades principales que manejará tu aplicación (por ejemplo, usuarios, productos, pedidos, etc.).
> + Determina las relaciones: Define las relaciones entre esas entidades (por ejemplo, un usuario puede tener varios pedidos).


Luego es necesario hacer los bocetos de las interfaces gráficas. Pueden ser dibujos hechos a mano o, en caso de que sea requerido por el cliente, desarrollar una propuesta usando un software especializado (Figma).

Crear el entorno de desarrollo (aplica solamente para desarrollos con código). Dado que el repo es para el uso de Power Apps, se puede considerar a Power Platform como la plataforma de desarrollo. Solamente si es importante considerar en dónde se van a alojar las bases de datos y la forma en cómo se va a consultar la información.

Luego es necesario crear un entorno de Despliegue - Power Platform - Es necesario considerar la realización d los tests unitarios o tests integrados con la finalidad de asegurar la calidad de la información y la solución final. 

> Nota: Otra parte importante ya fuera del desarrollo pero parte de la solución completa es el tema de la **Retroalimentación del cliente** para mejorar algún aspecto o considerar migraciones de información, la retroalimentación es durante y al final del desarrollo de la solución, [UAT]












