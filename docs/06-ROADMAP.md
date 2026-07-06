# 06 - Roadmap

## Fase 1 - Laboratório

- [ ] Subir ambiente local isolado.
- [ ] Trocar todos os secrets.
- [ ] Validar autenticação.
- [ ] Revisar portas expostas.
- [ ] Executar Trivy/Grype.
- [ ] Testar importação de entidades básicas.
- [ ] Validar persistência do grafo.

## Fase 2 - Avaliação técnica

- [ ] Testar fluxo domínio -> subdomínio -> IP -> ASN.
- [ ] Testar enriquecimento com Shodan.
- [ ] Testar enriquecimento com Whois/DNS.
- [ ] Testar integração com Maigret/Sherlock.
- [ ] Validar exportação de achados.
- [ ] Medir consumo de recursos.
- [ ] Identificar limitações operacionais.

## Fase 3 - Hardening

- [ ] Remover ou justificar Docker socket.
- [ ] Restringir acesso via reverse proxy.
- [ ] Habilitar TLS.
- [ ] Criar política de backup.
- [ ] Criar política de retenção.
- [ ] Separar workspaces por cliente.
- [ ] Documentar procedimento operacional.

## Fase 4 - Uso controlado

- [ ] Rodar piloto com alvo próprio/autorizado.
- [ ] Comparar resultados com Amass/Subfinder/Shodan.
- [ ] Criar template de relatório.
- [ ] Criar matriz de evidências.
- [ ] Definir critérios de falso positivo.
- [ ] Definir critérios de encerramento de investigação.

## Fase 5 - Automação futura

- [ ] Criar integração com pipeline de relatório.
- [ ] Criar export JSON/CSV padronizado.
- [ ] Integrar com dashboard de ASM/VM.
- [ ] Criar playbooks no n8n.
- [ ] Enviar achados críticos para Teams.

## Critério de aprovação

A ferramenta só deve avançar para uso recorrente se atender aos seguintes pontos:

- Instalação reproduzível.
- Risco de Docker socket aceito ou mitigado.
- Segredos protegidos.
- Dados segregados.
- Relatórios ou exportações úteis.
- Valor superior ao uso isolado de ferramentas CLI.
