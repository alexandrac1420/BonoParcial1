# Bono Parcial 1

Este proyecto implementa una calculadora reflexiva que utiliza la clase `Math` de Java mediante reflexión y un algoritmo de ordenamiento Bubble Sort, todo dentro de un sistema distribuido con arquitectura basada en sockets. El cliente interactúa con la aplicación enviando comandos para realizar cálculos matemáticos o ejecutar el algoritmo de ordenamiento.

---

## Instalación

1. **Clona el repositorio y navega al directorio del proyecto:**

    ```sh
    git clone https://github.com/alexandrac1420/BonoParcial1.git
    cd BonoParcial1
    ```

2. **Compila el proyecto:**

    ```sh
    mvn package
    ```

    Deberías ver una salida similar a esta:

    ```sh
    [INFO] --- jar:3.3.0:jar (default-jar) @ BonoParcial ---
    [INFO]  C:\Users\alexandra.cortes.LABINFO\Desktop\BonoParcial\target\BonoParcial-1.0-SNAPSHOT.jar
    [INFO] BUILD SUCCESS
    ```

3. **Ejecuta la aplicación:**

    - Primero, ejecuta el servidor backend:
    
      ```sh
      java -cp target/BonoParcial-1.0-SNAPSHOT.jar edu.escuelaing.arep.CalcReflexBEServer
      ```

      Deberías ver el mensaje:

      ```sh
      Listo para recibir
      ```

    - Luego, ejecuta el servicio de fachada en otra terminal o máquina virtual:

      ```sh
      java -cp target/BonoParcial-1.0-SNAPSHOT.jar edu.escuelaing.arep.CalcReflexFacade
      ```

      Deberías ver nuevamente el mensaje:

      ```sh
      Listo para recibir
      ```

4. **Accede a la interfaz web en tu navegador:**

    - Ahora puedes acceder a la página [http://localhost:35000/](http://localhost:35000/).

---

## Ejemplo de uso

1. Abre tu navegador y accede a la interfaz web en [http://localhost:35000/](http://localhost:35000/).
2. Ingresa una operación en el formato `comando(param1,param2)`, como `pow(2,3)` o `random()`.
3. Presiona el botón "Calcular" y el resultado aparecerá en pantalla.

### Nota importante:
- Si ingresas un número decimal (por ejemplo, `2.0`), debes utilizar el **punto decimal** (`.`) y no la coma.
- La **coma** (`,`) se utiliza para separar los parámetros cuando se requieren más de uno, y **no debe haber espacios** entre los parámetros. Por ejemplo:
  - Para ingresar un número decimal en el cálculo de un máximo, usar: `max(2.3,8.5)`.

### Ejemplos de uso en la interfaz:
- **Función sin parámetro**: `random()`
  ![image](https://github.com/user-attachments/assets/03a2baed-2c3b-4ab6-a2d0-275c31894f9d)
  
- **Función con un parámetro**: `sin(valor)`
  ![image](https://github.com/user-attachments/assets/597a57a0-cd30-48e9-90ea-61d4ba91ef5b)

- **Función con dos parámetros**: `max(valor1, valor2)`
  ![image](https://github.com/user-attachments/assets/339bfad4-4733-4032-a059-6ef653fe9dae)

- **Bubble Sort**: `bbl(Lista de números)`
  ![image](https://github.com/user-attachments/assets/bd9330b7-9b89-4dec-a7b5-86a58272b710)


## Diagrama de Clases

Este es el diagrama de clases que muestra las principales clases del proyecto y sus interacciones:
![image](https://github.com/user-attachments/assets/03a2baed-2c3b-4ab6-a2d0-275c31894f9d)

### 1. **CalcReflexBEServer**
   - Es el servidor backend que maneja los cálculos y la lógica de ordenamiento **Bubble Sort**.
   - **Métodos principales**:
     - `computeMathCommand`: Invoca los métodos de la clase `Math` utilizando reflexión.
     - `bubbleSort`: Implementa el algoritmo de **Bubble Sort** para ordenar listas de números.

### 2. **CalcReflexFacade**
   - Es el intermediario que recibe las solicitudes desde el navegador web y las envía al servidor backend.
   - **Métodos principales**:
     - `getHtmlClient`: Genera el HTML que se muestra al cliente en el navegador.
     - `getRequestURI`: Analiza la primera línea de la solicitud para obtener la URI del comando.

### 3. **HttpConnectionExample**
   - Es responsable de enviar las solicitudes desde la fachada al backend utilizando sockets.
   - **Método principal**:
     - `getResponse`: Realiza la solicitud al backend y devuelve la respuesta.

---

## Diagrama de Arquitectura

A continuación se presenta el diagrama de arquitectura que describe cómo interactúan los diferentes componentes del sistema:
![image](https://github.com/user-attachments/assets/03a2baed-2c3b-4ab6-a2d0-275c31894f9d)

### 1. **Cliente (Browser)**:
   - El cliente utiliza una interfaz HTML y JavaScript para enviar comandos al servidor a través de **Sockets**.
   - Envía comandos como `pow(2,3)` o `bbl(5,3,8,4,2)` y recibe el resultado calculado en la interfaz web.

### 2. **Fachada Web (CalcReflexFacade)**:
   - Recibe los comandos del cliente y utiliza la clase **HttpConnectionExample** para comunicarse con el backend.
   - Procesa las respuestas del backend y las muestra en el navegador.

### 3. **Servidor Backend (CalcReflexBEServer)**:
   - Procesa los comandos enviados por la fachada utilizando reflexión en la clase `Math` o ejecutando el algoritmo **Bubble Sort**.
   - Devuelve el resultado a la fachada para que sea presentado al cliente.


## Construido con

* [Maven](https://maven.apache.org/) - Gestión de dependencias
* [Git](http://git-scm.com/) - Sistema de control de versiones

## Versionado

Utilizo [GitHub](https://github.com/) para el control de versiones. Para ver las versiones disponibles, consulta los [tags en este repositorio](https://github.com/alexandrac1420/BonoParcial1.git).

## Autores

* **Alexandra Cortes Tovar** - [alexandrac1420](https://github.com/alexandrac1420)
