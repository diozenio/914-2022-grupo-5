# Projeto 2º Bimestre das disciplinas de Infraestrutura e Serviços de Redes (PRIR/SRED e ISRE)

## Criando Máquinas Virtuais (rede ponto a ponto)

* Verifique a existência do VirtualBox
  - Caso não haja, acesse o link e faça o download: https://www.virtualbox.org/wiki/Downloads


* Configure as interfaces de rede dessas MVs como ilustra a topologia de Rede da figura 1
<p> Figura 1: Topologia de Rede Ponto a Ponto usando o VitualBox, com duas VMs com suas NICs em modo Rede Interna</center></p>   
   <img src="../Imagens/Captura de tela de 2022-08-09 11-17-18.png" alt=""
	title="Figura 1: Topologia de Rede Ponto a Ponto" width="800" height="280" />

<br>

## Importando VMs no VirtualBox
  * Importe o arquivo .OVA para criar duas VMs
  
  * A Figura 2 Ilustra as configurações para a importação das VMs: VM-LAB01 e VM-LAB02

<p>Figura 2: Criando uma VM apartir de um arquivo OVA</p>   
   <img src="../Imagens/import-ova1.png" alt=""
	title="Figura 2a: Clique em Arquivo/Importar Apliance" width="400" height="280"/> 
   <img src="../Imagens/import-ova2.png" alt=""
	title="Figura 2b: configurações de importação"
/>

* Instale o pacote Net Tools nas VMs
```bash
sudo apt intall net-tools -y
```
## Configure as NICs das VMs

* Selecione as configurações de Rede de cada VM para `rede interna` e defina o nome da rede, por exemplo `<labredes>`

* A Figura 3 ilustra as configurações para a importação das VMs: VM1-PC1-Carolina e VM2-PC1-Carolina 

<img src='../Imagens/Captura de tela de 2022-08-09 11-17-18.png '>
 