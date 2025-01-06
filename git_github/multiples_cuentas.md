# Multiples cuentas de github en una sola computadora

1. Creamos llaves ssh para cada cuenta. Por ejemplo una para el trabajo y otra personal
2. En cada cuenta agregamos su respectiva llave ssh publica(.pub)
3. En la carpeta ~/.ssh, vamos a crear un archivo llamado config(sin extension) y vamos a poner los siguientes valores:
   - Host github.com-trabajo
   - Hostname github.com
   - IdentityFile ~/.ssh/id_rsa_trabajo
   - IdentitiesOnly yes
   - User git

En caso de que queramos agragar una cuenta personal, agregariamos valores como estos en nuestro archivo config.

    - Host github.com-personal
    - Hostname github.com
    - IdentityFile ~/.ssh/id_rsa_personal
    - IdentitiesOnly yes
    - User git

`Host github.com-trabajo` este va a ser el nombre que vamos a poner en la url del repo al conectarnos por medio de ssh por ejemplo, en vez de tener algo como esto "git@github.com:TheMayanCitizen/Basic-RestServer-Structure.git" vamos a tener algo como "git@github.com-trabajo:TheMayanCitizen/test.git" observa la diferencia entre `@github.com` y `@github.com-trabajo`.

`IdentityFile ~/.ssh/id_rsa_trabajo` aqui vamos a poner la url de la llave ssh privada que github va a usar para conectarse a nuestro repo de trabajo.

Los demas valores del archivo config quedan igual.

No te olvide de cambiar los valores de `user.name` y `user.email` ya sea de tu trabajo o personal.

Cuando vayas a hacer un push al repositorio remoto verifica que `@github.com` tenga la ruta correcta, `@github.com-trabajo` o `@github.com-personal`.

Recuerda que puedes buscar en YT como "multiple github accounts in a computer"

Acuerdate que tus hosts son

- `github.com` para TheMayanCitizen
- `github.com-channel` para SMO 

```
Host github.com-channel
Hostname github.com
IdentityFile ~/.ssh/id_rsa
IdentitiesOnly yes
User git

Host github.com
Hostname github.com
IdentityFile ~/.ssh/mayan-citizen
IdentitiesOnly yes
User git
```
