# Projeto 2º Bimestre das disciplinas de Infraestrutura e Serviços de Redes (PRIR/SRED e ISRE)

## Serviço de Nomes Estático

### Passo 1 - Acessar os hospedeiros da máquina

- Utilizar o comando

```bash
$ sudo nano /etc/hosts
```

### Passo 2 - Inserir o endereço IP, Hostname, Domínio e Apelido que estão na tabela de cada membro

<div align="center">
  <p>Figura 1: Configurando os nomes do host estático</p>
  <img src='../Imagens/etapa7-IP-hostname-Dom-Apel.png'>
  <br><br>
</div>
	
* Faz-se necessário inserir em cada VM tais dados, afim de utilizar o comando:
	
	```bash
	$ ssh <user>@<hostname|fqdn|alias>
	```
	### Passo 3 - Inserir os usuários de todos os membros
	
	* Para realizar essa ação, usa-se o comando:
	
	```bash
	$ sudo adduser <Nomeintegrante>
	```
	
	* Abaixo estão explicitadas esta inserção:
	
	<div align="center">
	  <p>Figura 2: Inserindo o usuário Dionísio</p>
	  <img src='../Imagens/etapa7-usuario-dionísio.png'>
	  <br><br>
        </div>
	
	<div align="center">
	  <p>Figura 3: Inserindo o usuário Giovana</p>
	  <img src='../Imagens/etapa7-usuario-giovana.png'>
	  <br><br>
        </div>
	
	<div align="center">
	  <p>Figura 4: Inserindo o usuário Carolina</p>
	  <img src='../Imagens/etapa7-usuario-carolina.png'>
	  <br><br>
        </div>
	
	<div align="center">
	  <p>Figura 5: Inserindo o usuário Ewerton</p>
	  <img src='../Imagens/etapa7-usuario-ewerton.png'>
	  <br><br>
        </div>
	
	### Passo 4 - Verificar os usuários criados
	
	* Para isso utiliza-se o comando:
	
	```bash
	$ sudo cat /etc/passwd
	```
	
	* Segue a seguir exemplo do uso do comando:
	
        <div align="center">
	  <p>Figura 6: Consultando os usuários adicionados</p>
	  <img src='../Imagens/etapa7-consultando-usuarios-add.png'>
	  <br><br>
        </div>
	
	## Utilizando o SSH na prática via Domínio
	
	### Passo 1 - Para conectar-se com os usuários de outras máquinas virtuais deve-se utilizar o comando:
	
	```bash
	$ ssh <NomeDoUsuario>@<hostname|fqdn>
	```
	<div align="center">
	  <p>Figura 7: Acessando o usuário Carolina da VM1 do PC3-Ewerton</p>
	  <img src='../Imagens/etapa7-acess-usu-carolina-do-pc3.png'>
	  <br><br>
        </div>
	
	<br>
	
	> ## <a href="https://github.com/diozenio/914-2022-grupo-5">Voltar ao início<a/>  
