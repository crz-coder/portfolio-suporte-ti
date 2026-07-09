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
(Configuração das duas VMs para atuarem em uma rede interna, separando o laboratório da minha rede wi-fi pessoal.)
<img width="1917" height="1078" alt="Captura de tela 2026-07-02 153817" src="https://github.com/user-attachments/assets/3f7fc026-5490-461e-af31-035084b437ff" />

(Configuração de um endereço IP estático na VM com Windows Server e definição do endereço de loopback (127.0.0.1) como servidor DNS, permitindo que o próprio servidor resolva internamente as consultas do Active Directory.)
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/1c6c7574-7424-4284-b185-acb87665d5ef" />

### 2. Promoção do Servidor a Controlador de Domínio
(Implantação das funções AD DS, DNS Server e DHCP Server no Windows Server.)
<img width="1023" height="770" alt="Captura de tela 2026-07-02 164243" src="https://github.com/user-attachments/assets/63ce5ed3-de91-40c3-adc0-6a794ad0b940" />

(Promoção do servidor a Controlador de Domínio (Domain Controller), com a criação de uma nova floresta e de um domínio do Active Directory.)
<img width="1023" height="771" alt="Captura de tela 2026-07-03 092023" src="https://github.com/user-attachments/assets/376dee84-0851-4c9a-973a-c9134293201b" />

### 3. Configuração do Servidor DHCP
(Criação e configuração de um escopo DHCP para distribuição automática de endereços IP na rede do domínio.)
(Nesta etapa, uma faixa de endereços IP pode ser reservada para dispositivos que necessitam de IP fixo, garantindo que o servidor DHCP distribua apenas os endereços destinados aos clientes da rede.)
<img width="1027" height="767" alt="Captura de tela 2026-07-03 094609" src="https://github.com/user-attachments/assets/9e3237d9-4b79-45c5-b80b-647752a99dcf" />

### 4. Estruturação do AD (OUs, Grupos e Usuários)
(Criação de UOs para organizar os grupos e usuários com os seus respectivos setores.)
<img width="1022" height="768" alt="Captura de tela 2026-07-04 135520" src="https://github.com/user-attachments/assets/5f4fa154-dd5b-4ffd-8837-f471cfeb2309" />

(Criação de Grupos para organizar os usuários com suas respectivas funções.)
<img width="1027" height="770" alt="Captura de tela 2026-07-04 133657" src="https://github.com/user-attachments/assets/fc468b3b-f8b8-47b9-9345-5cd9339c65b9" />

### 5. Aplicação de GPOs (Group Policy Objects)
(Configuração da segurança das senhas da empresa, alterando o período máximo de validade das senhas, exigindo maior complexidade na criação de senhas e alterando o comrpimento mínimo das senhas para 8 caracteres.) (Fizemos essas alterações no Default Domain Policy para abranger todos os usuários.)
<img width="1025" height="768" alt="Captura de tela 2026-07-08 163800" src="https://github.com/user-attachments/assets/bdaefc66-5d9a-4dbe-9a84-c6cbdbbd94f1" />

(Configuração da GPO para restringir o acesso de usuários de determinadas Unidades Organizacionais (UOs) a itens do Painel de Controle e outras configurações do sistema.) (Após a configuração, a GPO foi vinculada às UOs desejadas para que as restrições fossem aplicadas apenas aos usuários definidos.)
<img width="1026" height="766" alt="Captura de tela 2026-07-08 165547" src="https://github.com/user-attachments/assets/a4411f8f-1cd1-4f7e-b978-29cc10504405" />

(Configuração da GPO para montar automáticamente o disco com a pasta compartilhada do domínio.)
<img width="1023" height="768" alt="Captura de tela 2026-07-09 135009" src="https://github.com/user-attachments/assets/3e314ab9-938a-47e4-9f64-29e8845ab964" />

### 6. Ingresso da Máquina Cliente no Domínio
(Ingressando a máquina do usuário no domínio.)
<img width="1025" height="766" alt="Captura de tela 2026-07-09 170348" src="https://github.com/user-attachments/assets/f9b62d8a-cbf9-4b92-a592-8085f7152a96" />

(Verificando a resposta da conexão do cliente com o servidor.)
<img width="1023" height="762" alt="Captura de tela 2026-07-09 170621" src="https://github.com/user-attachments/assets/c5e8214f-07ab-4c03-873d-82ee2dccc82a" />

(Teste logado com um Usuário da UO Financeiri tentando acessar o Painel de Controle.)
<img width="1025" height="767" alt="Captura de tela 2026-07-09 172751" src="https://github.com/user-attachments/assets/4f3e599b-0f0b-4a19-b766-1fe85c877f78" />









