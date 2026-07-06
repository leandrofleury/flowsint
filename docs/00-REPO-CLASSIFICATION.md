# 00 - Repository Classification

## Resumo executivo

O **Flowsint** fica classificado como ferramenta de **ASM / OSINT / Threat Intelligence**, com foco em investigação visual, enriquecimento de entidades e mapeamento de relações entre domínios, IPs, ASNs, e-mails, websites e artefatos correlatos.

Este fork deve ser tratado como repositório de **avaliação controlada**. Ele tem bom potencial para uso em laboratório, pesquisa interna e apoio a investigações, mas não deve ser exposto diretamente à internet sem hardening.

## Classificação

| Campo | Valor |
|---|---|
| Categoria principal | ASM / OSINT / Threat Intelligence |
| Subcategoria | Reconhecimento visual / Investigação por grafo |
| Status | Manter e avaliar |
| Prioridade | Alta |
| Valor técnico | Alto |
| Valor operacional | Alto |
| Risco técnico | Médio |
| Prontidão para produção | Laboratório / Ambiente controlado |
| Uso recomendado | Plataforma complementar de investigação |
| Substitui scanner de vulnerabilidade | Não |

## Casos de uso principais

- Gestão de superfície externa de ataque.
- Investigação OSINT baseada em pivôs.
- Enriquecimento de Threat Intelligence.
- Mapeamento visual de relações entre entidades.
- Apoio à fase de reconhecimento autorizada.
- Documentação de trilhas investigativas.

## Aderência por domínio

| Domínio | Aderência | Observação |
|---|---:|---|
| ASM | Alta | Bom para mapear relações externas e entidades expostas. |
| Threat Intelligence | Alta | Útil para pivôs e enriquecimento contextual. |
| Vulnerability Management | Média | Ajuda no contexto, mas não substitui scanner. |
| Red Team | Média | Útil em reconhecimento autorizado. |
| Blue Team / SOC | Média | Útil para enriquecimento e investigação. |
| DFIR | Baixa / Média | Apoia pivôs de infraestrutura, mas não é ferramenta forense. |
| GRC / Executivo | Baixa | Exige camada própria de relatório. |

## Recomendação

Manter o fork e usar em ambiente controlado. Antes de qualquer uso próximo de produção, revisar Docker socket, secrets, autenticação, exposição de rede, persistência de dados e modelo de operação multi-cliente.
