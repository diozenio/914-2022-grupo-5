# Projeto 2º Bimestre das disciplinas de Infraestrutura e Serviços de Redes (PRIR/SRED e ISRE)

## Arquivos necessários

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

> ## <a href="./Etapa 01 - Ambiente.md">Próxima etapa<a/>
