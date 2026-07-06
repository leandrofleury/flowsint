# 02 - Security Review

## Resumo de risco

O Flowsint deve ser tratado como uma aplicação de segurança com superfície sensível. Ele processa dados de investigação, depende de múltiplos serviços e pode ser integrado a fontes externas. Por isso, o risco principal não está apenas no código, mas no modelo de implantação.

## Principais pontos de atenção

### 1. Docker socket

Qualquer uso de `/var/run/docker.sock` dentro de container deve ser considerado risco alto por padrão. Se um processo dentro do container for comprometido, o socket pode permitir controle indireto do host Docker.

**Ação recomendada:**

- Validar se o socket é realmente necessário.
- Remover o mount se possível.
- Se não for possível remover, isolar o host.
- Não executar em servidor compartilhado com outros workloads sensíveis.

### 2. Secrets e credenciais

Arquivos `.env.example` e exemplos de configuração costumam conter valores fracos apenas para demonstração. O problema nasce quando alguém sobe produção com esses valores.

**Ação recomendada:**

- Trocar todos os secrets antes do primeiro uso real.
- Gerar chaves fortes e únicas.
- Nunca commitar `.env` real.
- Usar secret manager quando possível.

### 3. Exposição de rede

Aplicações OSINT/ASM podem conter dados sensíveis de clientes, domínios, achados e investigações.

**Ação recomendada:**

- Não expor diretamente à internet.
- Usar VPN, Zero Trust Access ou reverse proxy autenticado.
- Restringir origem por IP quando possível.
- Habilitar TLS.

### 4. Dados de investigação

O grafo pode revelar relações entre clientes, ativos, fornecedores, usuários e infraestrutura.

**Ação recomendada:**

- Separar ambientes por cliente.
- Definir política de retenção.
- Evitar misturar investigações de clientes diferentes no mesmo workspace sem segregação clara.
- Documentar consentimento e escopo.

### 5. Integrações externas

Integrações com APIs externas ampliam o valor, mas também criam risco operacional.

**Ação recomendada:**

- Usar chaves de API com menor privilégio possível.
- Monitorar consumo e logs.
- Evitar inserir tokens pessoais sem controle.
- Documentar cada integração habilitada.

## Risco consolidado

| Área | Risco | Observação |
|---|---:|---|
| Docker / Runtime | Médio / Alto | Depende do uso de Docker socket e privilégios. |
| Segredos | Médio | Exige rotação e saneamento de exemplos. |
| Exposição web | Médio / Alto | Não expor sem proxy e autenticação forte. |
| Dados sensíveis | Médio | Dados OSINT podem ter sensibilidade operacional. |
| Dependências | Médio | Exige varredura contínua. |

## Controles mínimos

- Rodar Trivy ou Grype nas imagens.
- Rodar Dependabot ou ferramenta equivalente.
- Proteger branch principal.
- Usar `.env` fora do controle de versão.
- Restringir acesso administrativo.
- Documentar escopo de uso.
- Rodar primeiro em lab isolado.

## Conclusão

A ferramenta é promissora, mas exige implantação disciplinada. Para uso pessoal ou laboratório, o risco é aceitável. Para uso corporativo ou multi-cliente, precisa de hardening e validação antes de qualquer exposição operacional.
