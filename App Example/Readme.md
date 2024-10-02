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

**Boceto gráfico**

**Funcionalidad principal**

**Almacenamiento de la información**

**Consideración-Notas de las bases de datos**

| Nombre | URL | Notas | Encargado | Accesos |
| --- | --- | --- | --- | --- |
| Final Data | Sharepoint, Excel - **URL** | Base final donde tenemos toda la información | IT Name | Gerente: Edición |
|  |  |  |  |  |

**Flujo de información**



### Temas específicos (desarrollador)



#### Páginas


#### GUI - Atributos

**Imagen**


| No. | Nombre y objeto | Especificaciones | 
| --- | --- | --- |
| 1 |  |  |
| 2 |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |


**Variables y Funcinoes**



``` Java 
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
```

















