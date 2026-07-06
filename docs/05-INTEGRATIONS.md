# 05 - Integrations

## Objetivo

Mapear integrações úteis para aumentar o valor operacional do Flowsint em fluxos de ASM, OSINT e Threat Intelligence.

## Integrações prioritárias

| Integração | Prioridade | Uso esperado |
|---|---:|---|
| Shodan | Alta | Enriquecimento de IPs, serviços e exposição externa. |
| WhoisXMLAPI | Alta | WHOIS, DNS e contexto de domínio. |
| Maigret | Média | Busca de perfis e identidades públicas. |
| Sherlock | Média | Busca de usernames e presença pública. |
| n8n | Alta | Automação de workflows e orquestração. |
| Neo4j | Alta | Persistência e consulta em grafo. |
| Amass | Média | Descoberta de subdomínios e enumeração externa. |
| Subfinder | Média | Descoberta rápida de subdomínios. |

## Integrações futuras desejáveis

- CISA KEV.
- EPSS.
- NVD / CVE.
- VirusTotal.
- URLScan.
- GreyNoise.
- MISP.
- OpenCTI.
- TheHive / Cortex.
- Teams / Slack para notificações.

## Cuidados com API keys

- Usar chaves específicas para o ambiente.
- Evitar token pessoal sem controle.
- Não commitar credenciais.
- Controlar custo e rate limit.
- Registrar finalidade de cada integração.

## Modelo recomendado de operação

1. Coletar entidade inicial.
2. Enriquecer com fontes externas.
3. Persistir relações no grafo.
4. Revisar manualmente os achados.
5. Exportar evidências para relatório.
6. Registrar hipóteses e nível de confiança.

## Observação

Quanto mais integrações forem ativadas, maior o valor investigativo. Porém, também aumenta o risco de vazamento de dados, consumo indevido de APIs e mistura de contextos entre clientes.
