# 🎫 Sistema de Help Desk (osTicket)

## 📌 Visão Geral
Implantação completa de uma solução open-source de Help Desk baseada na web (osTicket) em um ambiente **Linux (Ubuntu Server)**. O projeto simula o dia a dia de um suporte de TI, recebendo, triando e escalando tickets de acordo com Acordos de Nível de Serviço (SLAs).

## 🛠️ Tecnologias e Ferramentas Utilizadas
- **Sistema Operacional:** Ubuntu Server (Virtualizado)
- **Servidor Web e Banco de Dados:** Pilha LAMP (Linux, Apache, MySQL, PHP)
- **Sistema ITSM:** osTicket
- **Conceitos Empregados:** SLAs, Escalabilidade, Ciclo de Vida do Ticket

## 🚀 O Problema (Situação e Tarefa)
Para prestar um serviço de TI de qualidade, as solicitações dos usuários precisam ser registradas, categorizadas e acompanhadas. A tarefa foi instalar um sistema de tickets corporativo do zero em um servidor Linux e configurá-lo para uso prático, demonstrando compreensão de fluxos ITSM.

## ⚙️ Ação (Passo a Passo)

### 1. Preparação do Servidor
- Instalação e atualização do Ubuntu Server.
- Implantação da stack LAMP, essencial para rodar o osTicket.

### 2. Instalação e Configuração do osTicket
- Criação de banco de dados e usuário MySQL para a aplicação.
- Configuração inicial da plataforma via interface web.

### 3. Configuração de Negócio
- **Departamentos:** Criação de suporte Nível 1, Suporte Nível 2 e Redes.
- **Categorias (Help Topics):** "Acesso/Conta", "Falha de Hardware", "Problema de Rede", "Instalação de Software".
- **SLAs:** Definição de níveis de criticidade (Crítico - 1h, Alto - 4h, Normal - 8h).

### 4. Simulação Prática
- Criação de clientes (End Users) e Agentes de Suporte (Agents).
- Abertura de tickets simulando problemas comuns (ex: "Tela azul", "Não acesso a VPN").
- Demonstração do fluxo de trabalho: Recebimento, atribuição de técnico, registro de comunicação e resolução.

## 📈 Resultados
O sistema foi configurado com sucesso e documentou o fluxo exato que um ticket segue desde a criação até o encerramento. O projeto demonstrou não apenas a habilidade técnica de configurar um servidor web no Linux, mas também a competência em processos operacionais de TI.

## 📸 Evidências (Screenshots)
