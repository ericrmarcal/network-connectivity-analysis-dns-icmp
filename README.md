# 🌐 Análise de Conectividade de Rede: Diagnóstico DNS e ICMP

## 📝 Visão Geral
Este projeto foca na investigação de um incidente onde usuários não conseguiam aceder ao site `yummyrecipesforme.com`. Através da análise de logs de tráfego, identifiquei uma falha crítica na comunicação com o servidor DNS.

## 🔍 Descobertas Principais (Análise de Logs)
* [cite_start]**Protocolo UDP:** Identificado na tentativa de contacto com o servidor DNS (IP `203.0.113.2`) na **Porta 53**.
* [cite_start]**Erro ICMP:** Os logs revelaram a mensagem `udp port 53 unreachable`, indicando que o serviço de DNS não estava a aceitar conexões.
* [cite_start]**Sintoma Técnico:** O navegador não conseguia converter o nome do domínio em um endereço IP, resultando em erro de carregamento para os clientes.

## 🛠️ Ferramentas e Metodologia
* [cite_start]**Packet Sniffing:** Utilização do `tcpdump` para capturar e analisar pacotes em tempo real[cite: 42].
* [cite_start]**Análise de Timestamp:** O incidente foi mapeado com início às **13:24:32**, conforme registado nos logs[cite: 42].
* [cite_start]**Diagnóstico de Causa Raiz:** Suspeita de ataque de **Negação de Serviço (DoS)** ou erro de configuração de firewall bloqueando a porta 53[cite: 42].

## 🛡️ Próximas Etapas Recomendadas
1. [cite_start]Verificar a disponibilidade do serviço de DNS no servidor de destino[cite: 42].
2. [cite_start]Auditar as regras de firewall para garantir que o tráfego na porta 53 (UDP) não esteja a ser bloqueado indevidamente[cite: 42].

## 📂 Arquivos do Projeto
* [📄 Relatório de Análise DNS/ICMP (PDF)](./analise-dns-icmp.pdf)
