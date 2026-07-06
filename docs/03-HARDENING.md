# 03 - Hardening

## Objetivo

Este documento define um baseline mínimo para executar o Flowsint com mais segurança em ambiente de laboratório, avaliação interna ou operação controlada.

## Baseline recomendado

### 1. Não expor diretamente na internet

Evite publicar a aplicação diretamente em porta pública.

Preferir:

- VPN.
- Reverse proxy com autenticação forte.
- Zero Trust Access.
- Allowlist de IPs.

### 2. Trocar todos os secrets

Antes de subir qualquer ambiente real:

- Alterar `AUTH_SECRET`.
- Alterar senhas de banco e serviços auxiliares.
- Alterar chaves de vault.
- Garantir que `.env` real não esteja versionado.

### 3. Revisar Docker socket

Se houver mount de `/var/run/docker.sock`, trate como exceção, não como padrão.

Medidas:

- Remover se não for obrigatório.
- Rodar em host dedicado.
- Não misturar com workloads críticos.
- Monitorar uso do Docker daemon.

### 4. Restringir binds de rede

Serviços internos como banco, cache, filas e Neo4j devem ficar restritos a localhost ou à rede interna do Docker.

Evitar:

- Banco exposto em `0.0.0.0`.
- Painéis administrativos públicos.
- Portas auxiliares abertas sem necessidade.

### 5. Atualizar dependências

Criar rotina de atualização e verificação:

```bash
trivy fs .
trivy image <imagem>
grype .
```

### 6. Logs e retenção

Definir:

- Onde os logs ficam.
- Quem acessa.
- Por quanto tempo são mantidos.
- Se podem conter dados de clientes.

### 7. Separação por cliente

Para uso multi-cliente, evitar misturar dados no mesmo ambiente sem controle.

Preferir:

- Workspace separado por cliente.
- Ambiente separado por cliente sensível.
- Política de retenção clara.

### 8. Backup

Para uso contínuo, validar backup de:

- Banco relacional.
- Neo4j.
- Configurações.
- Workspaces.

## Checklist rápido

| Item | Status |
|---|---|
| Secrets trocados | Pendente |
| `.env` real fora do Git | Pendente |
| TLS habilitado | Pendente |
| Acesso restrito | Pendente |
| Docker socket revisado | Pendente |
| Banco não exposto publicamente | Pendente |
| Trivy/Grype executado | Pendente |
| Política de retenção definida | Pendente |
| Backup validado | Pendente |

## Recomendação final

Para laboratório, pode rodar com isolamento básico. Para uso corporativo, aplicar este hardening antes de qualquer demonstração com dados reais de cliente.
