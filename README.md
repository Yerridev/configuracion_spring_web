# Configuracion de Spring Boot Web con JSPs

## Stack de desarroolo utiliza

1. Inteliij IDEA Ultimate

### Creación del proyecto

-   New project:
    -   Generator/Spring Boot
    -   Maven
    -   Java 21

### Dependencias

-   Spring Web
-   Spring Data JPA (Java Persisten API)
-   Lombok (Libreria Anotaciones)
-   MySql Driver / JDBC Driver Sql Serve

### Dependencias al Instalar proyecto `/pom.xml`

-   Dependencia manejar JSPs

    ```xml
        <dependency>
                <groupId>org.apache.tomcat.embed</groupId>
                <artifactId>tomcat-embed-jasper</artifactId>
        </dependency>
    ```

-   JSTL (Libreria de Etiquetas)
    ```xml
        <dependency>
            <groupId>jakarta.servlet.jsp.jstl</groupId>
            <artifactId>jakarta.servlet.jsp.jstl-api</artifactId>
        </dependency>
    ```

### Configuracnion Base de Datos `/application.propertis`

[Archivo de configuracion Spring Boot](application.properties)

#### Configuracion con SQL Serve

```
    spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=empleados;encrypt=false;trustServerCertificate=true
    spring.datasource.username=AdminStore
    spring.datasource.password=admin
    spring.datasource.driver-class-name=com.microsoft.sqlserver.jdbc.SQLServerDriver

    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
```

#### Configuración con MySql
```
    spring.datasource.url=jdbc:mysql://localhost:3306/nombre_bd?createDatabaseIfNotExist=true
    spring.datasource.username=root
    spring.datasource.password=
    spring.datasource.driver-class-name=con.mysql.cj.jdbc.Driver
    spring.jpa.hibernate.ddl-auto=update //si la base de datos NO esta creada
    spring.jpa.show-sql=true 

```

_base de datos esta creada_
```
    spring.datasource.url=jdbc:mysql://localhost:3306/nombre_bd
    spring.jpa.hibernate.ddl-auto=none //si la base de datos ya esta creada
```

### Creaccion de vista JSP (ejemplo) `/main/webapp/WEB-INF`

Lecutra solo de archivos `.jsp` sirve para leer codigo java dentro de html.

Para agregar las libreria en el archivo jsp
`<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>`

Expression Language = _lenguaje de expresion de JSPs para acceder a variables y mas caracteristicas_ `${}`

- Agregar las url de las aplicaciones

```
    //forma 1
    <c:set var="urlInicio">
        <c:url value="${application.contextPath}/" />
    </c:set>

    //forma2
    <%-- Agregar las URL de las aplicaciones --%>
    <c:set var="urlInicio" value="${pageContext.request.contextPath}/" />
    <c:set var="urlAgregar" value="${pageContext.request.contextPath}/agregar" />
```
