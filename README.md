# ShopFlow - API Gateway

## Descripción
Punto de entrada único para todos los microservicios de ShopFlow.
Enruta las peticiones del frontend hacia el servicio correspondiente.
Construido con Spring Cloud Gateway.

## Tecnologías
- Java 21
- Spring Boot 3.5
- Spring Cloud Gateway
- Spring Boot Actuator
- Maven

## Requisitos previos
- Java 21
- Maven 3.9+
- Los 3 microservicios corriendo:
  - user-service (puerto 8081)
  - product-service (puerto 8082)
  - order-service (puerto 8083)

## Configuración

### Variables de entorno
Creá un archivo `application.properties` basándote en `application.properties.example`:

```properties
USER_SERVICE_URL=http://localhost:8081
PRODUCT_SERVICE_URL=http://localhost:8082
ORDER_SERVICE_URL=http://localhost:8083
```

### Correr el servicio
```bash
mvn spring-boot:run
```

## Rutas disponibles

| Ruta | Servicio destino | Puerto |
|------|-----------------|--------|
| /api/users/** | user-service | 8081 |
| /api/products/** | product-service | 8082 |
| /api/orders/** | order-service | 8083 |

## Ejemplo de uso

En vez de llamar directamente a cada servicio:
GET http://localhost:8081/users
Se llama a través del gateway:
GET http://localhost:8080/api/users

## Repositorios relacionados
- [shopflow-user-service](https://github.com/Nelson-Salinas/shopflow-user-service)
- [shopflow-product-service](https://github.com/Nelson-Salinas/shopflow-product-service)
- [shopflow-order-service](https://github.com/Nelson-Salinas/shopflow-order-service)
- [shopflow-frontend](https://github.com/Nelson-Salinas/shopflow-frontend)