# 04 - Use Cases

## 1. ASM inicial de cliente

### Objetivo
Mapear relações externas básicas de uma organização antes de um assessment.

### Entradas
- Domínio principal.
- Subdomínios conhecidos.
- IPs públicos.
- ASNs.
- E-mails corporativos públicos.

### Saídas esperadas
- Grafo de relações.
- Entidades relevantes.
- Pivôs para investigação.
- Lista de ativos para validação manual.

## 2. Investigação de domínio suspeito

### Objetivo
Entender infraestrutura relacionada a um domínio suspeito ou recém-identificado.

### Entradas
- Domínio.
- IP.
- Certificados.
- WHOIS quando disponível.

### Saídas esperadas
- Relações com outros domínios.
- Infraestrutura compartilhada.
- Possíveis padrões de campanha.
- Pivôs adicionais para enriquecimento.

## 3. Enriquecimento de Threat Intelligence

### Objetivo
Complementar indicadores técnicos com relações visuais.

### Entradas
- IOC.
- IP.
- URL.
- Domínio.
- E-mail.

### Saídas esperadas
- Relações entre indicadores.
- Priorização de entidades.
- Hipóteses de investigação.

## 4. Apoio a Red Team autorizado

### Objetivo
Apoiar a fase de reconhecimento dentro de escopo formal.

### Entradas
- Escopo aprovado.
- Domínios e ativos autorizados.
- Regras de engajamento.

### Saídas esperadas
- Mapa de exposição.
- Pivôs documentados.
- Possíveis caminhos de investigação.

## 5. Apoio ao SOC / Blue Team

### Objetivo
Ajudar analistas a contextualizar infraestrutura externa associada a alertas.

### Entradas
- IP observado.
- Domínio observado.
- E-mail remetente.
- URL em alerta.

### Saídas esperadas
- Contexto externo.
- Relações suspeitas.
- Base para triagem.

## Regras de uso

- Usar apenas dentro de escopo autorizado.
- Documentar fonte dos dados.
- Separar investigações por cliente.
- Não tratar resultado OSINT como prova definitiva sem validação.
- Cruzar achados com ferramentas independentes.
