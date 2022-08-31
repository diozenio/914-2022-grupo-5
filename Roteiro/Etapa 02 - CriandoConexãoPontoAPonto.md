# Projeto 2º Bimestre das disciplinas de Infraestrutura e Serviços de Redes (PRIR/SRED e ISRE)

## Criando Máquinas Virtuais (rede ponto a ponto)



* Configure as interfaces de rede dessas MVs como ilustra a topologia de Rede da figura 1
<p> Figura 1: Topologia de Rede Ponto a Ponto usando o VitualBox, com duas VMs com suas NICs em modo Rede Interna</center></p>   
   <img src="../Imagens/criandomv.1.png"


<br>

## Importando VMs no VirtualBox
  * Importe o arquivo .OVA para criar duas VMs
  
  * A Figura 2 Ilustra as configurações para a importação das VMs: VM-LAB01 e VM-LAB02

<p>Figura 2: Criando uma VM apartir de um arquivo OVA</p>   
<img src="../Imagens/IMG_4941.png" 
		 width="400" height="280" /> 
<img src="../Imagens/criandomv.2.png"/>
   </div>
	


* Instale o pacote Net Tools nas VMs
```bash
sudo apt intall net-tools -y
```
## Configure as NICs das VMs

* Selecione as configurações de Rede de cada VM para `rede interna` e defina o nome da rede, por exemplo `<labredes>`

* A Figura 3 ilustra as configurações para a importação das VMs: VM1-PC1-Carolina e VM2-PC1-Carolina 

<img src='../Imagens/criandomv.3.png '>
 <br> 
<<<<<<< HEAD

=======
<img src='../Imagens/Captura de tela de 2022-08-09 10-45-55.png'>

>>>>>>> dc12dd044d9fadc4b94b0dc6dccccac580ef9dc0
 ## Fazendo o login nas VMs
<<<<<<< HEAD
   * Abra as duas máquinas virtuais criadas 
   <img src='../Imagens/criandomv.4.png'>
=======
>>>>>>> dc12dd044d9fadc4b94b0dc6dccccac580ef9dc0

<<<<<<< HEAD
   * Usuário da VM: `administrador`
   * Senha da VM: `adminifal` 
   <img src='../Imagens/criandomv.5.png'>
=======
* Abra as duas máquinas virtuais criadas 
>>>>>>> dc12dd044d9fadc4b94b0dc6dccccac580ef9dc0

<img src='../Imagens/Captura de tela de 2022-08-09 10-45-55.png'><img src='../Imagens/Captura de tela de 2022-08-09 10-45-55.png'>

* Usuário da VM: `administrador`
* Senha da VM: `adminifal` 

<img src='../Imagens/Captura de tela de 2022-08-09 10-47-41.png'>

## Configuração estática de endereço IP na interface de rede
  ### Passo 1 - Acesse as interfaces de rede
  * Para configurar a interface, o ubuntu usa o arquivo YAML
  * Digite o comando `ls -la /etc/netplan/` para verificar o nome correto do arquivo no seu servidor.
   > __/etc/netplan/__ é a pasta onde o arquivo se encontra
  * No exemplo abaixo, foi utilizado o arquivo *01-netcfg.yaml*
  <img scr='../Imagens/Capture de tela de 2022-08-09 10-49-23.png'> 
  

### Passo 2 - Edite o arquivo 
  * Para editar o arquivo, digite o comando abaixo:
  ```bash
  $ sudo nano /etc/netplan/01-netcfg.yaml
  ```
  <img src='../Imagens/criandomv.6.png'>

## Na VM-PC1
  * Após a criação da tabela de Ip's, foi utilizado o IP da Carolina no exemplo: `192.168.14.65`
  ```bash
  network:
    version: 2
    renderer: networkd
    ethernets:
      enp0s3:
        addresses:[192.168.14.65/28]
        gateway4: 192.168.14.64
        dhcp4: false
  ```
  <img src='../Imagens/Captura de tela de 2022-08-09 10-59-30.png'> <br>
  
  * Digite `Ctrl + X` para salvar e sair do ambiente de edição do arquivo.
  
  * Após as alterações feitas, digite eo comando **netplan apply** para aplicar as configurações. Depois, veja a configuração das interfaces com o comando **ifconfig -a**

  ```bash
  $ sudo netplan apply
  $ ifconfig -a 
  ```
  <img src='../Imagens/Captura de tela de 2022-08-09 11-11-56.png'>

  ## Na VM-PC2
  * Após a criação da tabela de Ip's, foi utilizado o IP da Carolina no exemplo: `192.168.14.66`
  ```bash
  network:
    version: 2
    renderer: networkd
    ethernets:
      enp0s3:
        addresses:[192.168.14.66/28]
        gateway4: 192.168.14.64
        dhcp4: false
  ```
  <img src='../Imagens/Captura de tela de editado.png'> 
  
  * Digite `Ctrl + X` para salvar e sair do ambiente de edição do arquivo.
  
  * Após as alterações feitas, digite eo comando **netplan apply** para aplicar as configurações. Depois, veja a configuração das interfaces com o comando **ifconfig -a**

  ```bash
  $ sudo netplan apply
  $ ifconfig -a 
  ```
  
  <img src='../Imagens/Captura de tela editado.png'>
  
  ### Passo 3 - Colocar em modo bridge
   * Conectar os cabos Ethernet nos PCs e configurar a placa de rede para modo Bridge.
   
   <img src='../Imagens/placa modo bridge.png'>
   
  ### Passo extra - Ping das máquinas
  * Ping da VM1-PC1-Carolina para VM2-PC3-Ewerton
 
 
  ```bash
  $ ping 192.168.14.70
  ```
  
  * Ping da VM1-PC3-Ewerton para VM2-PC1-Carolina
  
  ```bash
  $ ping 192.168.14.66
  ```
  
   
