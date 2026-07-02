# 📜 Scripts de Automação (PowerShell & Bash)

## 📌 Visão Geral
Este diretório contém uma coleção de scripts desenvolvidos em **PowerShell** (para ambientes Windows) e **Bash** (para ambientes Linux) com o objetivo de automatizar tarefas comuns e repetitivas de administração de sistemas e suporte técnico.

A automação reduz falhas humanas, garante padronização e economiza tempo precioso da equipe de TI.

## 🛠️ Tecnologias e Ferramentas Utilizadas
- PowerShell ISE / Visual Studio Code
- CMDlets do PowerShell (Get-Process, Get-Service, WMI)
- Bash Scripting e comandos nativos Linux (`grep`, `awk`, `df`, `top`)

## 🚀 Os Scripts (O que foi feito)

*(Observação: Este repositório incluirá os arquivos `.ps1` e `.sh` futuramente. Aqui documentei o que eles fazem.)*

### 1. `SystemHealthCheck.ps1`
**Situação:** Necessidade de verificar o status de várias máquinas de usuários de forma rápida, em busca de problemas de lentidão.
**Ação:** Desenvolvido script que audita: uso de disco (alertando caso tenha menos de 20GB livres), uso atual de RAM e CPU, e coleta o tempo de atividade do sistema (uptime). 

### 2. `BulkUserCreationAD.ps1`
**Situação:** O RH envia planilhas semanais com dezenas de novos funcionários para integrar na empresa.
**Ação:** Criado script que lê um arquivo `.csv`, conecta-se ao Active Directory e cria todos os usuários em suas respectivas OUs, definindo senha temporária e exigindo alteração no próximo login.

### 3. `NetworkDiagnosis.ps1`
**Situação:** Quando o usuário reclama que a rede está lenta, os mesmos comandos são sempre executados.
**Ação:** Script que realiza teste de ping no gateway padrão e no DNS externo, limpa o cache de DNS (`ipconfig /flushdns`), exporta um tracert básico e salva em log para análise do Nível 2.

### 4. `LinuxSysInfo.sh`
**Situação:** Gerenciamento rápido de um servidor Linux sem interface gráfica.
**Ação:** Um script simples em Bash que mostra o "Load Average", uso de disco em partições vitais e identifica se serviços cruciais (como apache ou sshd) estão ativos.

## 📈 Resultados
