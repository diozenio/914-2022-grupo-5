# Projeto 2º Bimestre das disciplinas de Infraestrutura e Serviços de Redes (PRIR/SRED e ISRE)

## Apresentação do Projeto:

- Esse projeto é apresentado à disciplina de PRIR/SRED e ISRE do 4º ano matutino do curso de nível médio/integrado de informática do Instituto Federal de Alagoas - Campus Arapiraca, como requisito avaliativo, sob orientação do professor **Alaelson Jatobá**.

**Grupo 5 composto por:** 
- Carolina Fernandes
- Dionísio Barbosa
- Ewerton Barboza 
- Giovanna Correia

## Sobre o projeto:
- Esse projeto tem como objetivo a criação de uma infraestrutura de rede, criação de Máquinas Virtuais e manipulação com o sistema operacional Ubuntu. 

## Tabela

NOME            |  Descrição  |  IP  |  Hostname  |  FQDN  |  Aliase
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
Carolina  |  VM1-PC1-Carolina  | 192.168.14.65 | carol1 | grupo5-914.ifalara.net | carol1 | 
Carolina  |   VM2-PC1-Carolina  | 192.168.14.66 | carol2  | grupo5-914.ifalara.net | carol2 | 
Dionísio |    VM1-PC2-Dionísio  | 192.168.14.67 | dionisio1 | grupo5-914.ifalara.net  | dionisio1 | 
Dionísio   |   VM2-PC2-Dionísio  | 192.168.14.68 | dionisio2 | grupo5-914.ifalara.net  |  dionisio2 | 
Ewerton   |   VM1-PC3-Ewerton  | 192.168.14.69 | ewerton1 | grupo5-914.ifalara.net |  ewerton1 | 
Ewerton   |   VM2-PC3-Ewerton  | 192.168.14.70 | ewerton2 | grupo5-914.ifalara.net |  ewerton2 | 
Giovana   |   VM1-PC4-Giovana  | 192.168.14.71 | giovana1 | grupo5-914.ifalara.net |  giovana1 | 
Giovana   |   VM2-PC4-Giovana  | 192.168.14.72 | giovana2 | grupo5-914.ifalara.net  |  giovana2 | 

## Roteiro: Construindo uma infraestrutura de rede
### 1 - Acessando o usuário redes
- Abra o terminal do Linux
- Faça o login no usuário redes usando o comando 

```shell
# fazendo o login com no usuário redes
      su <user>
     # digite a senha
``` 

* logar com o usuário ``redes`` 
* senha ``admin@Lab92``

```bash
$ su redes
```
* utilize o comando ``sudo apt install net-tools`` para baixar o pacote **Net Tools**

    > **Net Tools** é um pacote com várias ferramentas úteis para uso na rede local.
    

### 2 - Manipulando arquivos

* Comando básicos:
```shell
 cd ~ #voltar ao diretório inicial
 pwd  #verificar o diretório 
 /home/redes
```
* Listar arquivos e pastas
```shell
 ls -la #listando todos os arquivos e pastas
 
 (adicionar informações)
 
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
 mkdir labredes/VM/9{turno,ano}
 mkdir labredes/VM/9{turno,ano}/<student> # substitua <student> pelo seu nome
```
* Adicione o usuário ``aluno`` ao grupo ``redes``
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

* Verifique se os arquivos existem no diretório /labredes/images/original
```bash
mini.iso
ubuntu-20.04.4-desktop-amd64.iso
ubuntu-22.04-live-server-amd64.iso
```

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

## 3 - Criação de Máquinas Virtuais (Rede Ponto a Ponto)

