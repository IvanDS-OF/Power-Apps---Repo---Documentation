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


**Almacenamiento de la información**

**Consideración-Notas de las bases de datos**

| Nombre | URL | Notas | Encargado | Accesos |
| --- | --- | --- | --- | --- |
| Data Admin | Sharepoint, Excel - **URL** | Funciona como BASE para los Dropdowns | IT Name | NA |
| Final Data | Sharepoint, Excel - **URL** | Base final donde tenemos toda la información | IT Name | Gerente: Edición |
|  |  |  |  |  |

**Flujo de información**



### Temas específicos (desarrollador)



#### Páginas


#### GUI - Atributos

**Imagen**


| No. | Nombre y objeto | Especificaciones | 
| --- | --- | --- |
| 1 | Label2_4: Etiqueta de texto | Text: "Organizador" |
| 2 | inOrganizador: Entrada de Texto | Default: User().FullName |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |


**Variables y Funcinoes**






## Aplicación 2: Registro de asistencia - Meetings: Users



### Portada: 

+ Nombre de la aplicación: Meeting: Admin
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
| Data Admin | Sharepoint, Excel - **URL** | Funciona como BASE para los Dropdowns | IT Name | NA |
| Final Data | Sharepoint, Excel - **URL** | Base final donde tenemos toda la información | IT Name | Gerente: Edición |
|  |  |  |  |  |

**Flujo de información**



### Temas específicos (desarrollador)



#### Páginas


#### GUI - Atributos

**Imagen**


| No. | Nombre y objeto | Especificaciones | 
| --- | --- | --- |
| 1 | Label2_4: Etiqueta de texto | Text: "Organizador" |
| 2 | inOrganizador: Entrada de Texto | Default: User().FullName |
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

















