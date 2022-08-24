# Roteiro: Acesso remoto em outras máquinas
## 1 - Configurando o hostname
- Com a máquina ligada, crie um novo hostname com o comando

```bash
$ sudo hostnamectl set-hostname nome-do-hostname
```

## 2 - Conectando a máquina à internet

- Caso a máquina não esteja conectada à internet, siga os passos: 
  - Confira se as máquinas estão utilizando o Adaptador1 no modo NAT 
  - Abra o arquivo de configuração do Netplan utilizando o nano com o comando


```bash
$ sudo nano /etc/netplan/01-netcfg.yaml
```

- Comente as linhas de IP estático e ativo o DHCP4

```bash
network:
    ethernets:
            # addresses: [172.17.0.1/24]
            # gateway4: 172.17.0.1
            dhcp4: true
    version: 2
```

- Aplique as alterações feitas

```bash
$ sudo netplan apply
$ ifconfig -a
```

- Teste se suas máquinas estão conectadas à internet com o comando

```bash
$ ping www.google.com
```

## 3 - Instalando o SSH Server

```bash
$ sudo apt-get install openssh-server
```

- Verifique o status do ssh para saber se a instalação foi concluída com sucesso

```bash
$ systemctl status ssh
```

## 4 - Configurando o Firewall

- Permita a conexão remota via protocolo SSH na porta 22, utilizando o comando 

```bash
$ sudo ufw allow ssh.  
```

- Ative o firewall

```bash
$ sudo ufw enable
```

## 5 - Acessando uma máquina remotamente

- Configure o Netplan para o modo brigde novamente e aplique as alterações 
- Conecte os computadores utilizando cabos de rede
- Utilize o comando $ ssh ``<usuario>``@``<ip.do.servidor.remoto>`` para acessar remotamente uma outra máquina

## Exemplo
