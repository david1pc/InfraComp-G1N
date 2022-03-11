# **Recuperar contraseña del usuario root - Fedora**

## Caracteristicas

- Permite la recuperacion de la contraseña del usuario root
- No requiere instalaciones previas al proceso
- Es compatible con Fedora

## Recomendaciones

- Realizar una toma instantanea de la maquina virtual.
- Realizar copia de seguridad de los archivos
- Seguir los pasos y configuraciones descritas.

## Pasos a seguir

- Oprimir una Tecla para detener el arranque en el grub y luego presionar **e**.

![](https://i.ibb.co/Wn7RbQZ/1.png)

- Buscar la linea linux o linux16 y reemplazar la sentencia **rhgb quiet** por **rd.break** y como último, presionar **Ctrl+x**.

![](https://i.ibb.co/DGzm7KK/2.png)
![](https://i.ibb.co/RzR1718/3.png)

- Aparecerá la siguiente vista, por tanto, se presionará **Enter** para acceder al mantenimiento.

![](https://i.ibb.co/yP0gbrV/4.png)

- Usar el comando `mount`, para ver las particiones o dispositivos montados.

![](https://i.ibb.co/hDLr3Gk/5.png)

- Luego, se buscará la partición o directorio sysroot para cambiar los permisos de solo lectura por lectura y escritura, con el siguiente comando.

`mount -o rw,remount /sysroot/`

![](https://i.ibb.co/MBbDndN/6.png)

- Luego de lo anterior, se vuelve a usar el comando `mount` y se valida de que el directorio o particion **sysroot** ya ha sido modificado.

![](https://i.ibb.co/2tmYV8p/7.png)

- Ahora, se accede a la carpeta sysroot a través de un directorio raíz simulado `chroot /sysroot/` y luego se cambia la contraseña del superusuario `passwd`.

![](https://i.ibb.co/DM6jmJp/8.png)

- Para que permanezca la nueva contraseña en el sistema se usa el siguiente comando.

`touch /.autorelabel`

![](https://i.ibb.co/6BJTQKX/9.png)

- Después, se sale del directorio root con el comando `exit` y como último se vuelve a usar `exit` para salir, por tanto, se espera a que cargue el sistema y una vez allí en la interfaz, se dará clic en la opción **“¿No está en la lista?”**

![](https://i.ibb.co/PQJ0XQq/10.png)

- Por último, se accede al usuario root con la nueva contraseña.

![](https://i.ibb.co/Pspy8vL/11.png)

![](https://i.ibb.co/W3Kr4Kx/12.png)
