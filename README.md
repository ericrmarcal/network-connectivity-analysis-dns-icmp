# 🌐 Investigação de Rede: Falha de Conectividade DNS e ICMP

## 📝 Visão Geral do Incidente
Este projeto documenta a análise de um incidente técnico iniciado às 13:24:32, onde usuários não conseguiam acessar o site yummyrecipesforme.com. O objetivo foi identificar por que a comunicação entre o navegador e o servidor estava sendo interrompida.

## 🔍 Análise Técnica dos Logs
Através da análise de pacotes com o tcpdump, foram identificados os seguintes pontos críticos:

* **Protocolo UDP:** Utilizado na tentativa de contato com o servidor DNS (IP 203.0.113.2) na Porta 53.
* **Erro ICMP:** O log revelou a mensagem "udp port 53 unreachable", confirmando que o serviço de DNS não estava aceitando conexões.
* **Sintoma:** O navegador falhou ao transformar o nome do site em um endereço IP, impossibilitando o carregamento da página.

## 🛠️ Metodologia de Investigação
* **Captura de Dados:** Uso do tcpdump para isolar o tráfego de saída e resposta.
* **Identificação de Erros:** Mapeamento de mensagens ICMP de "destino inalcançável".
* **Causa Provável:** Suspeita de ataque de Negação de Serviço (DoS) ou erro crítico de configuração no firewall bloqueando a porta 53.

## 🛡️ Próximas Etapas e Remediação
* **Verificar disponibilidade:** Confirmar se o serviço de DNS no servidor de destino está ativo.
* **Auditoria de Firewall:** Analisar as regras de firewall para permitir tráfego legítimo na porta 53.

## 📂 Arquivos
* [📄 Relatório Técnico de Conectividade (PDF)](./analise-dns-icmp.pdf)
