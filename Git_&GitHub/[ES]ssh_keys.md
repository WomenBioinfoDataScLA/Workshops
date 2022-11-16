Ahora autentiquemos su cuenta y creemos una conexión entre el git de su máquina y su cuenta de Github.

Primero, verifiquemos si ya tiene claves SSH en su máquina:

```bash
ls -al ~/.ssh
```

Si recibe un error que dice que ~/.ssh no existe, no tiene claves SSH, por lo que debemos crear una nueva con el siguiente comando. Tenga en cuenta que su dirección de correo electrónico debe estar entre comillas.

```bash
ssh-keygen -t rsa -C "<su email>"
```

Cuando se le solicite "Ingrese el archivo en el que guardar la clave", presione Entrar para aceptar la ubicación predeterminada para guardar el archivo con la clave. Luego se le pedirá que "Ingrese la frase de contraseña", y en la terminal, ingrese una contraseña segura.

Entre los mensajes que se mostrarán en la pantalla, uno indicará dónde se guardó la clave. Busque algo como:

```
Your public key has been saved in <ruta al archivo .pub>
```

Ahora abra el archivo que contiene la clave, **seleccione** todo su contenido y **cópielo** en su **clipboard**.

```bash
cat <ruta al archivo donde está la clave> 
```

¡Listo! Ahora solo necesitamos agregar esta clave a su cuenta de Github. Para hacer esto, vaya a [la configuración de su cuenta de github] (https://github.com/settings/profile), haga clic en "Claves SSH y GPG" a la izquierda, luego "Nueva clave SSH" a la derecha. Agregue una etiqueta a la clave como "Mi computadora personal" y luego pegue la clave en la ubicación indicada.

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/paste_ssh_es.png)

Probemos la conexión, solo para ver si todo salió bien. En la terminal, ejecuta:

```bash
ssh -T git@github.com
```

Deberías ver una advertencia como esta:

```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)?
```

Escribe `yes`. Si dice algo como lo siguiente, funcionó:

```
Hi <su login>! You've successfully authenticated, but Github does
not provide shell access.
```
