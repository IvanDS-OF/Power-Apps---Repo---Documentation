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

Lo rimero que tenemos que pensar es en la estructura de la información, ya que primero se crea una tabla [dentro del dataverse] y lueo se crea la aplicación. CREAMOS LA TABLA

Para esto podemos haer uso de **Análisis de Requisitos Funcionales**, básicamente es hacer un análisis de qué información va a estar anejando la aplicación. 

+ Lista de funcionalidades: Especifica todas las funcionalidades que la aplicación debe ofrecer
+ Identificación de entidades clave: Identifica las entidades principales que manejará tu aplicación (por ejemplo, usuarios, productos, pedidos, etc.).
+ Determina las relaciones: Define las relaciones entre esas entidades (por ejemplo, un usuario puede tener varios pedidos).









