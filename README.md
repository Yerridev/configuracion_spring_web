# Configuracion de Spring Boot Web con JSPs

## Stack de desarroolo utiliza
1. Inteliij IDEA Ultimate


### Creación del proyecto
- New project:
    - Generator/Spring Boot
    - Maven
    - Java 21


### Dependencias
- Spring Web
- Spring Data JPA (Java Persisten API)
- Lombok (Libreria Anotaciones)
- MySql Driver / JDBC Driver Sql Serve

### Dependencias al Instalar proyecto `/pom.xml`
- Dependencia manejar JSPs
    ```xml
        <dependency>
                <groupId>org.apache.tomcat.embed</groupId>
                <artifactId>tomcat-embed-jasper</artifactId>
        </dependency>
    ```

- JSTL (Libreria de Etiquetas)
    ```xml
        <dependency>
            <groupId>jakarta.servlet.jsp.jstl</groupId>
            <artifactId>jakarta.servlet.jsp.jstl-api</artifactId>
        </dependency>
    ```

### Configuracnion Base de Datos `/application.propertis`
[Archivo de configuracion Spring Boot](application.properties)

### Creaccion de vista JSP (ejemplo) `/main/webapp/WEB-INF`
Lecutra solo de archivos `.jsp` sirve para leer codigo java dentro de html.



