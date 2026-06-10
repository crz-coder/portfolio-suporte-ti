# 🌐 Documentação de Troubleshooting de Rede

## 📌 Visão Geral
Como técnico de suporte, grande parte do tempo é investido diagnosticando falhas de conectividade e acesso. Este projeto consiste na criação de **guias de diagnóstico passo a passo** (formato STAR - Situação, Tarefa, Ação, Resultado) baseados nos conceitos fundamentais do modelo OSI, TCP/IP, DNS e DHCP.

## 🛠️ Ferramentas Utilizadas
- **Comandos de Linha:** `ping`, `tracert`, `nslookup`, `ipconfig` (Windows) / `dig`, `ifconfig` (Linux)
- **Análise Avançada:** Wireshark e `tcpdump` para captura de pacotes

## 🚀 Os Guias Práticos

### Guia 1: "O usuário relata que não tem internet"
**Situação:** Máquina relata ausência de conectividade total com a rede externa.
**Ação:** 
1. Verificação de cabo físico e luzes de link na placa.
2. `ipconfig` no terminal para verificar se a máquina está recebendo um IP válido ou um APIPA (`169.254.x.x`).
3. Caso haja IP válido, realizar `ping` no gateway padrão (Roteador).
4. Caso responda, realizar `ping 8.8.8.8` para checar saída para internet.
5. Caso responda, realizar `nslookup google.com` para testar resolução de nomes (DNS).
**Resultado:** O diagnóstico rápido e sistemático isola o problema (Físico vs DHCP vs Gateway vs DNS) em poucos minutos.

### Guia 2: Erro "IP Conflict / Conflito de Endereço IP"
**Situação:** O sistema operacional emite um alerta de que outro dispositivo na rede está usando o mesmo IP.
**Ação:**
1. Desconexão imediata da máquina da rede para evitar instabilidade.
2. Verificação no servidor DHCP do escopo de locações ativas e limpeza caso haja leases conflitantes.
3. Utilização da tabela ARP (`arp -a`) em um equipamento na mesma rede para descobrir o endereço MAC do dispositivo ofensor.
**Resultado:** O dispositivo conflitante é bloqueado via MAC address no switch/firewall até que sua configuração estática indevida seja revertida.

### Guia 3: Pasta de Rede Compartilhada (SMB) Inacessível
**Situação:** O usuário acessava a pasta de rede `\\Servidor\Arquivos` ontem, mas hoje dá erro de permissão.
**Ação:**
1. Verificação se a máquina alcança o servidor (`ping Servidor`).
2. Verificação do login do usuário para constatar bloqueios no Active Directory.
3. Análise das permissões Share (Compartilhamento) e NTFS no arquivo ou diretório de destino.

## 📈 Resultados
Essa documentação comprova um conhecimento estruturado, saindo do modelo de "tentativa e erro" para um modelo de "diagnóstico e engenharia de rede". Mostra profundo entendimento sobre como os protocolos se comportam nas diversas camadas do Modelo OSI.
