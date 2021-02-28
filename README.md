<div align="center">
<h1>Aprenda comandos Huawei <img src="https://github.com/jadsnet/huawei_cli/blob/main/images/655076.png" align="center" width="270" height="200">
</h1>
</div>
<div align="center">
<i>Esse treinamento é quase de graça, basta deixar uma star ⭐ no <a href="https://github.com/jadsnet/huawei_cli">repositório</a>.</i>

<i>Destinado à área de Redes de computadores. A quem está iniciando estudos para certificação HCIA R&S.</i><br>
</div>
<br>

> <h4>Um tutorial interativo de linhas de comandos Huawei, destinado a ensinar praticas básicas sobre switch e routers.</h4>
><h4>Utilizo eve-ng como emulador</h4>
><h4>Ulitizo Vmware como virtualizador</h4>
><h4>Utilizo putty para cesso console</h4>
 
<i>🚨 🚧🚧 🛠... ⚙ ALGUNS TÓPICOS EM CONSTRUÇÃO ⚙ ...🛠 🚧🚧 🚨</i>

Então você quer usar o vrp, certo?


Nos exemplos, estou utilizando uma imagem baixada do site <a href="https://www.eve-ng.net/index.php/documentation/howtos/huawei-ar1000v/">eve-ng</a>.
O sistema VRP dessa imagem, após ser iniciada dentro do eve-ng, demora cerca de 10 minutos para poder iniciar.

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
Após digitar a senha, deverá aparecer um aviso, informando que sua senha expirou, para modificar pressione <i>y</i>.<br>
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

<h1>2 - Geral / Usuário </h1>

Repare que ao logar, aparece o nome do router/switch entre os simbolos de " <> ",<br>
isso significa que estamos logados no modo "user-view" ou modo usuário sem muitos privilégios.<br>
Repare também que sempre aparece alguma mensagem de log abaixo:

```
<Huawei>
Feb 28 2021 02:22:49+00:00 Huawei AAA/4/ ...
```

Nessa segunda etapa, é ideal utilizar um comando para desativar essas mensagens instantâneas,<br> 
pois em ambiente de produção pode ser que atrapalhe ao digitar alguma linha de comando.<br>
Mesmo no modo usuário, conseguiremos desabilitar essas mensagens com o comando:

```
<Huawei>undo terminal monitor
Info: Current terminal monitor is off.
```

Pressionando enter após cada comando, já significa que a linha digitada foi efetivada.<br>
Agora, podemos configurar algumas opções de usuário, pra que facilite na utilização do vrp.<br>
Só que para isso temos que entrar no modo de usuário com privilégios da seguinte forma:

```
<Huawei>system-view
Enter system view, return user view with Ctrl+Z.
[Huawei]
```

Repare que após o comando, aparece uma mensagem indicamos que entramos no modo privilegiado<br>
e se quisermos retornar para mod <i>"user-view"</i> pressionamos <i>"Ctrl + Z"</i><br>

Repare também que no final o nome do router está entre " [] " , indicando que já estamos no modo <i>system-view</i><br>
Já que estamos no modo system iremos configurar algumas opções de usuário.<br>

Entrando nas configurações do usuário console:

```
[Huawei]user-interface console 0
[Huawei-ui-console0]
```

Sempre que entramos em algum submenu do vrp, é adicionando entre " [ ] " o nome da instancia em que estamos.<br>
Para evitar que o sistema fique deslogando, vamos configurar os minutos que podemos ficar "ociosos" sem digitar<br>
nenhum comando no console e o sistema não nos deslogue:

```
[Huawei-ui-console0]idle-timeout 2000
```








