**Cómo agregar nodos manualmente en Divi Desktop – Tutorial para Windows**

*Asegúrate de que la aplicación de Divi Desktop esté cerrada antes de comenzar.*

¡Hola a todos! En el tutorial de hoy, te guiaré a través del proceso de agregar nodos manualmente a la billetera Divi Desktop utilizando Notepad. Esta es una solución temporal para aquellos que están experimentando problemas de sincronización. ¡Comencemos!

### Paso 1: Crear un nuevo documento de Notepad

1. **Abre Notepad** en tu computadora con Windows.
2. **Guarda el archivo** como `addnodes.txt`.  
   - Puedes guardar este archivo en cualquier lugar por ahora, solo asegúrate de que puedas encontrarlo más tarde.

3. **Agrega la siguiente línea en la parte superior** del documento:
   ```
   syncnodes=0
   ```

Este paso detiene la adición automática de nodos y nos permite ingresar manualmente la red descentralizada de peers necesarios.

---

### Paso 2: Obtener la lista de nodos activos

Ahora necesitamos obtener la lista más reciente de nodos activos desde el explorador de blockchain de Divi. Aquí te explico cómo hacerlo:

1. **Abre tu navegador web** y ve a [Divi Explorer en CryptoID](https://chainz.cryptoid.info/divi/).
   
2. En esa página, navega a la sección **Network**. También puedes ir directamente a este enlace:  
   [Información de la red Divi](https://chainz.cryptoid.info/divi/#!network).

3. Busca **Divi Core 3.0.0.0** y selecciona la opción **"Node List"**.

4. Esto mostrará una lista de nodos activos vistos en las últimas 24 horas.

5. **Copia la lista completa de nodos** resaltándola, luego haz clic derecho y selecciona "Copiar".

---

### Paso 3: Agregar nodos a tu archivo de texto

1. Vuelve a tu archivo `addnodes.txt`.

2. **Pega la lista** de nodos que acabas de copiar debajo de la línea `syncnodes=0`.  
   Asegúrate de que cada nodo esté en su propia línea. Aquí tienes un ejemplo de cómo debería verse:

   ```
   syncnodes=0
   addnode=IPADDRESS1
   addnode=IPADDRESS2
   addnode=IPADDRESS3
   ```

3. **Guarda** tu archivo `addnodes.txt`.

---

### Paso 4: Modificar el archivo `divi.conf`

1. Presiona **Windows Key + R** para abrir el cuadro de diálogo "Ejecutar".

2. En el cuadro de Ejecutar, escribe:
   ```
   %appdata%
   ```
   y presiona **Enter**.

3. Busca y abre la carpeta llamada **DIVI**.

4. Dentro de esta carpeta, localiza el archivo llamado `divi.conf` y **ábrelo con Notepad**.

5. Una vez abierto, **elimina todas las entradas addnode existentes** del archivo.

6. Vuelve a tu archivo `addnodes.txt`, **copia todo**, y luego pégalo en tu `divi.conf` debajo de la sección `## mndiviaddress`.

7. Guarda y cierra el archivo `divi.conf`.

---

### Paso 5: Iniciar Divi Desktop

1. Ahora, inicia la **aplicación Divi Desktop**.

2. La aplicación iniciará automáticamente el daemon, cargará el índice de bloques y comenzará a sincronizarse. Después de un corto tiempo, cargará la nueva lista de peers que acabamos de agregar.

¡Y eso es todo! Después de este proceso, tu billetera debería estar sincronizándose con los nodos correctos, y estarás de nuevo en marcha.

---

**Conclusión**

Si encontraste útil este tutorial, no olvides darle "Me gusta" y suscribirte para más consejos y trucos de Divi.

¡Como siempre, gracias por ver!
