# ARSW - Parcial 1: Product API

## Descripción

Este proyecto implementa un servicio **REST API con Spring Boot** para la gestión de productos de una tienda en línea.
La persistencia se maneja en memoria usando una lista (`List<Product>`), sin necesidad de base de datos.

* Uso de **Java 17** y **Spring Boot**.
* Endpoints REST (`GET` y `POST`).
* Uso de **inyección de dependencias** con `@Service` y `@Autowired`.
* Persistencia en memoria.
* Organización en paquetes (`controller`, `model`, `service`).

## Requisitos previos

* **Java 17**
* **Maven 3.8+**
* **IntelliJ IDEA** (o cualquier IDE compatible con Spring Boot)

## Estructura del proyecto

```
src/main/java/ARSWparcial1/
│── ProductApiApplication.java      
│
├── controller/
│   └── ProductController.java      
│
├── model/
│   └── Product.java               
│
└── service/
    └── ProductService.java         
```

## Instalación y ejecución

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/AngeLCuervo/ARSW-Parcial1.git
   cd ARSW-Parcial1
   ```

2. Descargar dependencias Maven:

   ```bash
   mvn clean install
   ```
   
3. Ejecutar con Maven:

   ```bash
   mvn spring-boot:run
   ```

4. La API estará disponible en:

   ```
   http://localhost:8080/productos
   ```

---

## Endpoints disponibles

### 1. Crear un producto

**POST** `/productos`

Ejemplo (desde consola de IntelliJ / PowerShell):

```powershell
Invoke-RestMethod -Uri "http://localhost:8080/productos" -Method Post -Headers @{ "Content-Type"="application/json" } -Body '{"nombre":"Laptop","precio":1200.50}'
```

Respuesta esperada:

```json
{
  "id": 1,
  "nombre": "Laptop",
  "precio": 1200.5
}
```

---

### 2. Listar todos los productos

**GET** `/productos`

Ejemplo:

```powershell
Invoke-RestMethod -Uri "http://localhost:8080/productos" -Method Get
```

Respuesta esperada:

```json
[
  {
    "id": 1,
    "nombre": "Laptop",
    "precio": 1200.5
  },
  {
    "id": 2,
    "nombre": "Mouse",
    "precio": 150.0
  }
]
```

---

### 3. Obtener un producto por ID

**GET** `/productos/{id}`

Ejemplo:

```powershell
Invoke-RestMethod -Uri "http://localhost:8080/productos/1" -Method Get
```

Respuesta esperada:

```json
{
  "id": 1,
  "nombre": "Laptop",
  "precio": 1200.5
}
```

---
## Autor
👤 [AngeLcuervo](https://github.com/AngeLCuervo)
