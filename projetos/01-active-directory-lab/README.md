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
- Instalação das funções do AD DS, DHCP e DNS.
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

### 1. Configuração do Ambiente Virtual
<img width="1917" height="1078" alt="Captura de tela 2026-07-02 153817" src="https://github.com/user-attachments/assets/3f7fc026-5490-461e-af31-035084b437ff" />
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/1c6c7574-7424-4284-b185-acb87665d5ef" />

### 2. Promoção do Servidor a Controlador de Domínio
<img width="1023" height="770" alt="Captura de tela 2026-07-02 164243" src="https://github.com/user-attachments/assets/63ce5ed3-de91-40c3-adc0-6a794ad0b940" />
<img width="1023" height="771" alt="Captura de tela 2026-07-03 092023" src="https://github.com/user-attachments/assets/376dee84-0851-4c9a-973a-c9134293201b" />

### 3. Configuração do Servidor DHCP
<img width="1027" height="767" alt="Captura de tela 2026-07-03 094609" src="https://github.com/user-attachments/assets/9e3237d9-4b79-45c5-b80b-647752a99dcf" />




