# 01 - Executive Summary

## Visão geral

O Flowsint é uma plataforma moderna para investigação OSINT e ASM orientada a grafo. A proposta é permitir que o analista navegue por relações entre ativos, identidades e infraestrutura externa de forma visual e extensível.

Na prática, ele pode apoiar investigações envolvendo domínios, IPs, ASNs, e-mails, websites, subdomínios, tecnologias e outros indicadores úteis para reconhecimento e enriquecimento.

## Valor para operação de segurança

O maior valor está em transformar investigação dispersa em um fluxo visual. Isso reduz perda de contexto, facilita pivôs e ajuda a explicar relações técnicas para outros analistas.

## Onde ele entra bem

- Pré-assessment de superfície externa.
- Apoio a investigações OSINT.
- Mapeamento de entidades relacionadas a clientes, marcas e infraestrutura.
- Complemento para Shodan, Whois, Maigret, Sherlock, Amass, Subfinder e ferramentas similares.
- Construção de trilhas de investigação reutilizáveis.

## Onde ele não entra bem

- Não substitui scanner de vulnerabilidades.
- Não substitui EDR/XDR.
- Não substitui SIEM.
- Não é ferramenta de resposta forense completa.
- Não deve ser exposto publicamente sem hardening.

## Veredito

**Manter e testar.**

A ferramenta tem aderência forte para ASM, OSINT e Threat Intelligence. O uso deve começar em laboratório e avançar somente depois de validação de segurança, principalmente por envolver containers, serviços auxiliares, dados sensíveis de investigação e possível exposição de superfície administrativa.
