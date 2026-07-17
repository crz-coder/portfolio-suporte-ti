# 💻 Ambiente Virtualizado Multi-Plataforma

## 📌 Visão Geral
Este projeto demonstra a habilidade de criar e gerenciar um ambiente heterogêneo operando de forma colaborativa, utilizando máquinas virtuais em hipervisores. É a demonstração prática de conceitos de conectividade entre diferentes famílias de Sistemas Operacionais.

## 🛠️ Tecnologias e Ferramentas Utilizadas
- **Hipervisor:** Oracle VM VirtualBox (Pode-se usar Hyper-V)
- **Sistemas Operacionais:** Windows 10/11, Ubuntu Desktop, Ubuntu Server
- **Protocolos de Acesso e Transferência:** SSH, RDP, SCP, SMB (Samba)

## 🚀 O Problema (Situação e Tarefa)
Muitos ambientes corporativos operam com desktops Windows para os usuários, mas possuem servidores, aplicações de backend e ferramentas de monitoramento em Linux. O técnico de suporte deve ser fluente em transitar entre esses mundos, acessar máquinas remotamente e transferir arquivos. A tarefa foi construir esse ambiente cruzado e documentar as integrações.

## ⚙️ Ação (Passo a Passo)

### 1. Preparação das Máquinas
- Deploy de 3 Máquinas Virtuais (1 Windows, 2 Linux).
- Configuração de rede (VirtualBox Internal Network / NAT Network) permitindo visibilidade entre elas.

### 2. Acesso Remoto Multi-OS
- **De Windows para Linux:** Utilização do PowerShell com cliente OpenSSH embutido ou PuTTY para gerenciar os servidores Ubuntu (`ssh usuario@IP`).
- **De Linux para Windows:** Utilização de ferramentas como Remmina para estabelecer conexões RDP para gerenciamento gráfico do Windows.

### 3. Transferência e Compartilhamento
- Utilização do protocolo **SCP** (Secure Copy) via terminal para copiar configurações ou logs do Windows para o Linux de forma criptografada.
- Instalação e configuração do serviço **Samba** no Linux para disponibilizar um diretório de arquivos acessível nativamente pelo Gerenciador de Arquivos do Windows via caminho UNC (`\\IP_do_Linux\Share`).

### 4. Sistemas de Arquivos (Filesystems)
- Demonstração da montagem de um disco adicional recém adicionado ao Linux.
- Exploração do arquivo `/etc/fstab` para montagem persistente (garantindo que os diretórios compartilhados não caiam após um reboot).

## 📸 Evidências (Screenshots)
