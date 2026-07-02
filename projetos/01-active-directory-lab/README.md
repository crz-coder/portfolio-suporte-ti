# 🏢 Laboratório de Active Directory

## 📌 Visão Geral
Neste projeto, criei e configurei um ambiente de domínio corporativo simulado utilizando o **Windows Server 2022** como Controlador de Domínio (Domain Controller) e o **Windows 10/11** como cliente, rodando em máquinas virtuais no VirtualBox.

O objetivo foi demonstrar habilidades práticas na implantação e administração do Active Directory (AD), gestão de identidades e aplicação de políticas de segurança.

## 🛠️ Tecnologias e Ferramentas Utilizadas
- **Hipervisor:** Oracle VM VirtualBox
- **Sistemas Operacionais:** Windows Server 2022, Windows 10/11
- **Serviços de Rede:** Active Directory Domain Services (AD DS), DNS, DHCP

## 🚀 O Problema (Situação e Tarefa)
Muitas empresas dependem do Active Directory para gerenciar acessos de forma centralizada. Como técnico de suporte, é essencial saber criar usuários, alocar permissões e aplicar configurações massivas nas máquinas clientes. A tarefa foi construir essa infraestrutura do zero.

## ⚙️ Ação (Passo a Passo)

### 1. Configuração do Ambiente Virtual
- Criação das VMs em uma rede interna isolada para evitar conflitos com a rede física.
- Configuração de IP estático no Windows Server (`192.168.1.1/24`).

### 2. Promoção do Servidor a Controlador de Domínio
- Instalação das funções do AD DS e DNS.
- Configuração do novo domínio (ex: `empresa.local`).

### 3. Configuração do Servidor DHCP
- Criação de um escopo IP para as máquinas clientes (ex: `192.168.1.50` a `192.168.1.150`).

### 4. Estruturação do AD (OUs, Grupos e Usuários)
- Criação de Unidades Organizacionais (OUs) lógicas: `TI`, `RH`, `Financeiro`.
- Criação de grupos de segurança e usuários fictícios com base na estrutura organizacional.

### 5. Aplicação de GPOs (Group Policy Objects)
- Configuração de políticas de complexidade de senha e validade.
- Ocultação de itens do painel de controle para usuários não-administrativos.
- Mapeamento automático de unidades de rede no logon do usuário.

### 6. Ingresso da Máquina Cliente no Domínio
- Configuração da VM Windows 10/11 para receber IP via DHCP e ingressar no domínio `empresa.local`.
- Teste de login com diferentes usuários.

## 📈 Resultados
- O ambiente foi implantado com sucesso, simulando uma infraestrutura corporativa real.
- Foi possível validar que as restrições impostas por GPO funcionam perfeitamente na máquina cliente.
- Documentado um profundo entendimento sobre DHCP, resolução DNS interna e autenticação via protocolo Kerberos.

## 📸 Evidências (Screenshots)

