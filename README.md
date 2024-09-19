# Parcial

### Instalación

1. Clona el repositorio y navega al directorio del proyecto:
    ```sh
    git clone https://github.com/alexandrac1420/BonoParcial1.git
    cd BonoParcial1
    ```

2. Compila el proyecto:
    ```sh
    mvn package
    ```

    Deberías ver una salida similar a esta:
    ```sh
    [INFO] --- jar:3.3.0:jar (default-jar) @ BonoParcial ---
    [INFO]  C:\Users\alexandra.cortes.LABINFO\Desktop\BonoParcial\target\BonoParcial-1.0-SNAPSHOT.jar
    [INFO] BUILD SUCCESS
    ```

3. Ejecuta la aplicación:
    ```sh
    java -cp target/BonoParcial-1.0-SNAPSHOT.jar edu.escuelaing.arep.CalcReflexBEServer 
    ```

    Al ejecutar la aplicación, deberías ver el siguiente mensaje:

    ```
    Listo para recibir
    ```

    Luego ejecuta el servicio de fachada en otra terminal o máquina virtual:

     ```sh
    java -cp target/BonoParcial-1.0-SNAPSHOT.jar edu.escuelaing.arep.CalcReflexFacade 
    ```

    Al ejecutar la aplicación, deberías ver el siguiente mensaje:

    ```
    Listo para recibir
    ```

    Ahora puedes acceder a la página `http://localhost:35000/`

    ## Ejemplo de uso


1. Accede a la interfaz web en tu navegador a través de [http://localhost:35000/](http://localhost:35000/).
2. Ingresa una operación en el formato `comando(param1,param2)`, como `pow(2,3)` o `random()`.
3. Presiona el botón "Calcular" y verás el resultado en pantalla.
![image](https://github.com/user-attachments/assets/03a2baed-2c3b-4ab6-a2d0-275c31894f9d)
![image](https://github.com/user-attachments/assets/597a57a0-cd30-48e9-90ea-61d4ba91ef5b)
![image](https://github.com/user-attachments/assets/339bfad4-4733-4032-a059-6ef653fe9dae)
![image](https://github.com/user-attachments/assets/bd9330b7-9b89-4dec-a7b5-86a58272b710)






