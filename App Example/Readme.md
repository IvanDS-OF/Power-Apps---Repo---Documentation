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

;;
// Extraer el valor "Motivo"

;;
// Extraer el valor "Departamento"

;;
// Extraer el valor "Fecha"

;;
//

;;
//
```

Personal	Lugar	Motivo	Organizador	Departamento	Fecha de Junta








## Aplicación 2: Registro de asistencia - Meetings: Users





















