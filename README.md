<div align="center">
<h1>Aprenda comandos Huawei</h1>
<i>Esse treinamento é quase de graça, basta deixar uma star ⭐ no <a href="https://github.com/jadsnet/huawei_cli">repositório</a>.</i>

<i>Destinado à area de Redes de computadores. A quem está iniciando estudos para certificação HCIA R&S.</i><br>
</div>
<br>

> <h4>Um tutorial interativo de linhas de comandos Huawei, destinado a ensinar praticas basicas sobre switch e routers.</h3>

Então você quer usar o vrp, certo?


🚨 🚧🚧 🛠... ⚙ EM CONSTRUÇÃO ⚙ ...🛠 🚧🚧 🚨

Nos exemplos , estou utilizano uma umagem baixada do site <a href="https://www.eve-ng.net/index.php/documentation/howtos/huawei-ar1000v/">eve-ng</a>.
Osistema VRP dessa imagem, após ser iniciada dentro do eve-ng, demora cerca de 10 minutos para poder inniciar.

![image](https://user-images.githubusercontent.com/48611984/109405469-86731b80-794f-11eb-97eb-f4ca04e5becf.png)

<h1>1 - Login</h1>

Nessa primeira parte vamos precisar de entrar com usuário <i>super</i> e senha <i>super</i>.<br>
Lembrando que ao digitar a senha, os caracteres não aparecem:
<br>

```
      Press any key to get started
     
Login authentication

Username:super
Password:
```
Após digitar a senha, deverá apreceer um aviso, informando que sua senha expirou, para modificar pressione <i>y</i>.<br>
Digite a senha antiga e depois a nova senha e repita a senha:

 ```
 Warning: The password is already expired.
The password needs to be changed. Change now? [Y/N]: y
Please enter old password:
Please enter new password:
Please confirm new password:
The password has been changed successfully.
```

Após logar deverá aparecer a seguinte mensagem:

```
<Huawei>
Feb 28 2021 02:22:49+00:00 Huawei AAA/4/ChangePasswordAlarm:OID 1.3.6.1.4.1.2011.5.2.2.2.0.112 Local account password has been modified.(TYPE:-- User-name:super)
<Huawei>
Feb 28 2021 02:22:49+00:00 Huawei LINE/4/USERLOGIN:OID 1.3.6.1.4.1.2011.5.25.207.2.2 A user login. (UserIndex=0, UserName=super, UserIP=Console0, UserChannel=CON0)
<Huawei>
```

<h1>2 - Geral / Usuario </h1>

Repare que ao logar, aparece o nome do router/switch entre os simbolos de " <> ",<br>
isso signifca que estamos logados no modo "user-view" ou modo usuário sem muitos privilégios.
Repare também que sempre aparece alguma mensagem de log abaixo:

```
<Huawei>
Feb 28 2021 02:22:49+00:00 Huawei AAA/4/ ...

```

Nessa segunda etapa, é ideal utilizar um comando para desativar essas mensagens instantaneas,<br> 
pois em ambiente de produção pode ser que atrapalhe ao difgitar alguma linha de comando.
Mesmo no modo usuario, conseguiremos desabilitar esses mensagems com o comando:

```
<Huawei>undo terminal monitor 
```

Pressionando enter após cada comando, já significa que a linha digitadda foi efetivada.


