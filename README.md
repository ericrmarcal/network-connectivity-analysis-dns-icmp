# 🌐 Investigação de Rede: Falha de Conectividade DNS e ICMP

## 📝 Visão Geral do Incidente
[cite_start]Este projeto documenta a análise de um incidente técnico iniciado às **13:24:32**, onde usuários não conseguiam acessar o site `yummyrecipesforme.com`[cite: 42]. [cite_start]O objetivo foi identificar por que a comunicação entre o navegador e o servidor estava sendo interrompida[cite: 42].

## 🔍 Análise Técnica dos Logs
Através da análise de pacotes com o `tcpdump`, foram identificados os seguintes pontos críticos:

* [cite_start]**Protocolo UDP:** Utilizado na tentativa de contato com o servidor DNS (IP `203.0.113.2`) na **Porta 53**[cite: 40].
* [cite_start]**Erro ICMP:** O log revelou a mensagem `udp port 53 unreachable`, confirmando que o serviço de DNS não estava aceitando conexões[cite: 40].
* [cite_start]**Sintoma:** O navegador falhou ao transformar o nome do site em um endereço IP, impossibilitando o carregamento da página[cite: 40].

## 🛠️ Metodologia de Investigação
* [cite_start]**Captura de Dados:** Uso do `tcpdump` para isolar o tráfego de saída e resposta[cite: 42].
* [cite_start]**Identificação de Erros:** Mapeamento de mensagens ICMP de "destino inalcançável"[cite: 40].
* [cite_start]**Causa Provável:** Suspeita de ataque de **Negação de Serviço (DoS)** ou erro crítico de configuração no firewall bloqueando a porta 53[cite: 42].

## 🛡️ Próximas Etapas e Remediação
* [cite_start]**Verificar disponibilidade:** Confirmar se o serviço de DNS no servidor de destino está ativo[cite: 42].
* [cite_start]**Auditoria de Firewall:** Analisar as regras de firewall para permitir tráfego legítimo na porta 53[cite: 42].

## 📂 Arquivos
* [📄 Relatório Técnico de Conectividade (PDF)](./analise-dns-icmp.pdf)
