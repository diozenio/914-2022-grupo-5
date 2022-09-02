# Roteiro: Construindo uma infraestrutura de rede
## 1 - Adicionando o usuário redes
- Abra o terminal do Linux
- Utilize o comando ```sudo adduser redes```
- Faça o login no usuário redes usando o comando 

```shell
# fazendo o login com no usuário redes
      su <user>
     # digite a senha
``` 

* logar com o usuário ``redes`` 
* senha ``admin@Lab92`` (para alunos do IFAL)

```bash
$ su redes
```
* utilize o comando ``sudo apt install net-tools`` para baixar o pacote **Net Tools**

    > **Net Tools** é um pacote com várias ferramentas úteis para uso na rede local.
    

## 2 - Manipulando arquivos

* Comando básicos:
```shell
 cd ~ #voltar ao diretório inicial
 pwd  #verificar o diretório 
 /home/redes
```
* Listar arquivos e pastas
```shell
 ls -la #listando todos os arquivos e pastas
```
* Crie pastas no diretório raiz e subpastas
 - nome da pasta ``labredes``
 - raiz ``/``
```bash
 sudo mkdir /labredes 
 cd /
 ls -la #verifique se a pasta foi criada
```
* Digite essa série de comandos
```bash
 cd /labredes
 mkdir images
 cd images
 mkdir original
 cd original
 ls -la
```
* Crie diretórios e subdiretórios
```bash
 cd /
 mkdir labredes/VM
```
* Adicione o usuário ``aluno`` (ou o seu usuário) ao grupo ``redes``
```bash
 sudo usermod -aG redes aluno
```
* Modifique as permissões de arquivos e pastas
  


  - ``chown`` 


    > __chown__ modifica o dono da pasta labredes para o usuário _nobody_ e grupo _nogroup_ 

  - ``chgrp``


    > __chgrp__ altera o proprietário de grupo do diretório ``/labredes`` para o grupo ``redes``


  - ``chmod``

    >__chmod__ altera as permissões do diretório
    

* Utilize os comandos:
```bash
sudo chown -R nobody:nogroup /labredes
sudo chgrp -R redes /labredes
sudo chmod -R 711 /labredes
ls -la #vericando as modificações feitas
getent group #lista os grupos
```

## 3 - Download dos arquivos necessários

### Passo 1 - Adquirindo o VirtualBox

- Verifique a existência do VirtualBox
  - Caso não haja, acesse o link e faça o download: https://www.virtualbox.org/wiki/Downloads

### Passo 1 - Obter o arquivo .OVA

- Caso não possua o arquivo .OVA, acesse o link para download: https://we.tl/t-VnOe7GAP3U
  - **OBS: Você será direcionado para o `WeTransfer` onde encontrará o arquivo para executar o download.**

### Outra forma de fazer:

- Verifique se os arquivos existem no diretório /labredes/images/original
  - `mini.iso`<br>
  - `ubuntu-20.04.4-desktop-amd64.iso`<br>
  - `ubuntu-22.04-live-server-amd64.iso`<br>

### Pelo Terminal

```shell
# scp faz uma cópia de um arquivo em um computador remoto para um diretório em um computador local
# sintaxe: <user>@<server>:<path>/<file>
# user: aluno
# senha: aluno
# server: 192.168.101.10
# diretório do server: ~/Public/iso-images/
# diretório de destino: /labredes/images/original

cd /labredes/images/original
ls -la #verifique no resultado a existência dos arquivos .iso

# Se não houver os arquivos iso na pasta /labredes/images/original deve-se copiá-los com os comandos:
scp aluno@192.168.101.10:~/Public/iso-images/mini.iso /labredes/images/original
scp aluno@192.168.101.10:~/Public/iso-images/ubuntu-20.04.4-desktop-amd64.iso /labredes/images/original
scp aluno@192.168.101.10:~/Public/iso-images/ubuntu-22.04-live-server-amd64.iso /labredes/images/original

```

> ## <a href="./Etapa-02.md">Próxima etapa</a>