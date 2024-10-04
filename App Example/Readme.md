# Proyecto

## Notas Iniciales

El proyecto consiste en el desarrollo de dos aplicaciones para una empresa que requiere que sus empleados asistan a reuniones en diferentes zonas de la planta industrial. Es importante el desarrollo de las aplicaciones ya que la asistencia es de caracter auditable. 

## Aplicación 1: Generador de QR - Meetings: Admin

### Portada: 

+ Nombre de la aplicación: Meeting: Admin
+ Desarrollador: Ivpan Duran Santos
+ Propietario del proyecto: Producción
+ Inicio de desarrollo: **Fecha**
+ Departamento: **Producción**
+ Gestor de Prooyecto: Solutions Architect


### Temas generales (función)

**Justificación:** Esta aplicación va a ser un generaor de códigos QR que va a almacenar la información sobre la junta que se va a llevar a acabo, la configuración de la información va a ser tarea del Gerente o del responsable de la reunión. Esta aplicación solamente va a ser habilitada en los dispositivos de los gerentes y personas encargadas de realizar reunioes. Es preferible que la aplicación sea utilizada con el uso de un ordenador potatil en lugar de un celular. 

**Boceto gráfico**

**Funcionalidad principal**

Tendremos diversos campos editables en donde colocaremos la información relevante de las reuniones. 

| Nave | Departamento | Motivo |
| --- | --- | --- |
| Nave 1 | Logistica | Workshop | 
| Nave 2 | Ingenieria | Shopfloor |
| Nave 3 | Investigación y Desarrollo | Revisión de Calidad |
| Nave 4 | IT | Auditoria de Calidad |
| Nave 5 | Producción |  | 
| Nave 6 | Mantenimiento |  |
| Nave 7 | Calidad |  |
| Nave 8 | Compras |  |
| Nave 9 |  |  | 
| Nave 10 |  |  |


**Almacenamiento de la información:** La información que se muestra en los Dropdown de la aplicación se va a encontrar en la base de datos *Data Admin*. 

**Consideración-Notas de las bases de datos**

| Nombre | URL | Notas | Encargado | Accesos |
| --- | --- | --- | --- | --- |
| Data Admin | Sharepoint, Excel - **URL** | Funciona como BASE para los Dropdowns | IT Name | NA |
|  |  |  |  |  |

**Flujo de información** [Uso de Visio]

Excel de Sharepoint -> Applicación

### Temas específicos (desarrollador)

#### Páginas - GUI - Atributos

**Imagen**


| No. | Nombre y objeto | Especificaciones | 
| --- | --- | --- |
| 1 | Label2_4: Etiqueta de Texto | **Text:** "Organizador" |
| 2 | Label2: Etiqueta de Texto | **Text:** "Lugar" |
| 3 | Label2_3: Etiqueta de Texto | **Text:** "Departamento" |
| 4 | Label2_2: Etiqueta de Texto | **Text:** "Motivo" |
| 5 | Label2_1: Etiqueta de Texto | **Text:** "Fecha" |
| 6 | InOrganizador: Entrada de Texto | **Default:** User().FullName |
| 7 | InLugar: Lista desplegable | **Items:** Table1.Nave |
| 8 | InDepartamento: Lista desplegable | **Items:** Table1.Departamento |
| 9 | InMotivo: Lista desplegable | **Items:** Table1-Motivo |
| 10 | InFecha: Selector de fecha | **Default:** Today() |
| 11 | Botón3: Botón | **Text:** "Limpiar" - **OnSelect:** Set(varCode;Blank()) |
| 12 | Boton1: Botón | **Text:** "Generar QR" - **OnSelect:** *varCode_R1* |
| 13 | Image1: Imágen | **Image:** "http://quickchart.io/qr?text=" & varCode |
| 14 | Label4: Etiqueta de texto | **Text:** "El texto contenido es el siguiente: " & varCode |
| 15 |  |  |
|  |  |  |


**Variables y Funcinoes**

**varCode_R1**
``` JAVA
Set(
    varCode; 
    "Organizador : " & inOrganizador.Text & Char(10) &
    "Lugar : " & inLugar.SelectedText.Value & Char(10) & 
    "Departamento : " & inDepartamento.SelectedText.Value & Char(10) &
    "Motivo : " & inMotivo.SelectedText.Value & Char(10) & 
    "Fecha : " & inFecha.SelectedDate & Char(30)
)
```








**********









## Aplicación 2: Registro de asistencia - Meetings: Users



### Portada: 

+ Nombre de la aplicación: Meeting: User
+ Desarrollador: Ivpan Duran Santos
+ Propietario del proyecto: Producción
+ Inicio de desarrollo: **Fecha**
+ Departamento: **Producción**
+ Gestor de Prooyecto: Solutions Architect

### Temas generales (función)

**Justificación:** Esta aplicación va a ser utilizada por los usuarios que en ente caso serían las personas requeridas en la reunión como los Especialistas de Calidad, los Especialistas de Geometría, los Especialistas de componentes de interiores, etc. Usando esta aplicación van a tener la habilidad de escanear un código QR el cual previamente el Organizador debió haber creado, una bez escaneado el código QR ocn la información específica, se mostrará un formulario con la información escaneada para poder enviarla a la base de datos y así registrar su asistencia a la reunión. 

**Boceto gráfico**

[IMAGEN]

**Funcionalidad principal**

Tendremos diversos campos editables en donde colocaremos la información relevante de las reuniones. 

| Personal | Lugar | Motivo | Organizador | Departamento | Fecha | 
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  | 



**Almacenamiento de la información:** La información que se muestra en los Dropdown de la aplicación se va a encontrar en la base de datos *Final Data*. 

**Consideración-Notas de las bases de datos**

| Nombre | URL | Notas | Encargado | Accesos |
| --- | --- | --- | --- | --- |
| Final Data | Sharepoint, Excel - **URL** | Base final donde tenemos toda la información | IT Name | Gerente: Edición |
|  |  |  |  |  |

**Flujo de información** [Uso de Visio para crear el gráfico con las especificaciones]

Aplicación -> Base de datos de Excel.


### Temas específicos (desarrollador)

#### Páginas

Solo existe una sola página. 

#### GUI - Atributos

**Imagen**

> NOTA: La aplicación contiene un formulario, que consta de los campos de las columnas de la basse de datos en donde se almacena esta información. Pero los campos visuales van a ser considerados de forma individual en la documentación porque tienen configuraciones individuales. Pero es importante recordar que están dentro de un Formulario.

| No. | Nombre y objeto | Especificaciones | 
| --- | --- | --- |
| 1 | Departamento_DataCard3: FormObject | **Default:** departamento , **DisplayMode:** Parent.DisplayMode.View  , **Required** true |
| 2 | Fecha de Junta_DataCard1: FormObject | **Default:** fecha , **DisplayMode:** Parent.DisplayMode.View  , **Required** true |
| 2.1 | DataCard_Value2: Entrada de Texto | **Format:** "dd/mm/yyyy" |
| 3 | Lugar_DataCard1: FormObject | **Default:** lugar , **DisplayMode:** Parent.DisplayMode.View  , **Required** true |
| 4 | Motivo_DataCard1: FormObject | **Default:** motivo , **DisplayMode:** Parent.DisplayMode.View  , **Required** true |
| 5 | Organizador_DataCard1: FormObject | **Default:** organizador , **DisplayMode:** Parent.DisplayMode.View  , **Required** true |
| 6 | Personal_DataCard1: FormObject | **Default:** User().FullName , **DisplayMode:** Parent.DisplayMode.View  , **Required** true |
| 7 | BarcodeReader1: Lector de código de barras | **BeepOnScan:** false, **OnScan:** *varCode_R2*,  **Text:** "Escanar QR ara llenar información" |
| 8 | Botón1_1: Botón | **Text:** "Limpiar Datos" , **OnSelect:** ResetForm(Form1) |
| 9 | Botón1: Botón | **Text:** "Enviar", **OnSelect:** SubmitForm(Form1) |
| 10 |  |  |
|  |  |  |

OTROS

| Nombre y Objeto | Especificccaciones | Notas| 
| --- | --- | --- |
| App | **OnStart:** NewForm(Form1) | Sirve para inicializar el formulario cuando se inicie la aplicación. | 


**Variables y Funcinoes**

**varCode_R2** Estas variables sirven para hacer manipulación de datos, sirve para descomponer el JSON de la información que nos ofrece el QR y así llenar de forma automática los campos requeridos para lenar el formulario de asistencia sin la intervención de las personas para introducir texto. 

``` JAVA
// Texto original
Set(TextScanned;First(BarcodeReader1.Barcodes).Value & Char(100))
;;
// Extraer el valor de "Organizador"
Set(organizador; Mid(TextScanned; 
Find("Organizador : "; TextScanned) + Len("Organizador : "); 
(Find("Lugar :"; TextScanned) - 1) - (Find("Organizador : "; TextScanned) + Len("Organizador : "))
))
;;
// Extraer el valor "Lugar"
Set(lugar; Mid(TextScanned; 
Find("Lugar : "; TextScanned) + Len("Lugar : "); 
(Find("Departamento :"; TextScanned) - 1) - (Find("Lugar : "; TextScanned) + Len("Lugar : "))
))
;;
// Extraer el valor "Motivo"
Set(motivo; Mid(TextScanned; 
Find("Motivo : "; TextScanned) + Len("Motivo : "); 
(Find("Fecha :"; TextScanned) - 1) - (Find("Motivo : "; TextScanned) + Len("Motivo : "))
))
;;
// Extraer el valor "Departamento"
Set(departamento; Mid(TextScanned; 
Find("Departamento : "; TextScanned) + Len("Departamento : "); 
(Find("Motivo :"; TextScanned) - 1) - (Find("Departamento : "; TextScanned) + Len("Departamento : "))
))
;;
// Extraer el valor "Fecha"
Set(fecha; Mid(TextScanned; 
Find("Fecha : "; TextScanned) + Len("Fecha : "); 
(Len(TextScanned)) - (Find("Fecha : "; TextScanned) + Len("Fecha : "))
))
;;
// Creamos un nuevo formulario pero ya con la información dentro. 
NewForm(Form1)
```
















