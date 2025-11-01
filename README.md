# Ataque de Brute Force de Senhas com Medusa e Kali Linux Simulado

## Sumário
1. [Visão Geral](#visão-geral)  
2. [Escopo](#escopo)
3. [Objetivos](#objetivos)  
4. [Ambiente de Teste](#ambiente-de-teste)  
5. [Ferramentas](#ferramentas)     
6. [Recomendações de Remediação e Mitigação](#recomendações-de-remediação-e-mitigação)     
7. [Detecção e Monitoramento](#detecção-e-monitoramento)  
8. [Notas Finais](#notas-finais)

---

## Visão Geral
Descrição curta do propósito do exercício: avaliar a resistência de controles de autenticação frente a tentativas automatizadas de adivinhação de credenciais (força bruta) em **um ambiente autorizado e controlado**. Este repositório documenta escopo e resultados observados, recomendações de segurança e evidências do exercício.

**Importante:** Todo teste descrito neste documento foi (ou deve ser) conduzido somente com autorização explícita e em ambientes de teste ou com contrato de pentest claro.


## Escopo  
- **Ambiente alvo (descrição):** `VM isolada`
- **OS Utilizada para o ataque**: Kali Linux
- **OS Utilizada para o alvo**: Ubuntu (Metasploitable2)


## Objetivos
- Avaliar controles de autenticação contra tentativas de adivinhação de senhas.  
- Medir a presença e efetividade de proteções (ex.: bloqueio, throttling, MFA).  
- Identificar usuários com senhas fracas ou com políticas de senha desatualizadas.  


## Ambiente de Teste
Descreva aqui a configuração do laboratório ou ambiente controlado: 
- VMs utilizadas: Oracle Virtual Box.  
- Configurações de isolamento: _host-only_.  

> **Boas práticas:** trabalhar em redes isoladas para evitar impacto em produção.


## Ferramentas
Lista das ferramentas citadas para inventário e rastreio (sem parâmetros ou instruções de uso):
- `Medusa` — ferramenta de acesso remoto/avaliação de autenticação.  
- `NMAP` — ferramenta utilizada para a enumeração. 
- `enum4linux` — ferramenta utilizada para a enumeração Windows e Samba
 


## Recomendações de Remediação e Mitigação
Lista de mitigadores gerais e defensivos:
- **Política de senhas:** exigir senhas fortes e tamanho mínimo adequado; proibir senhas triviais e senhas reutilizadas.  
- **Mecanismos de bloqueio/throttling:** aplicar limitações de taxa por IP/usuário e bloqueio progressivo após tentativas falhas.  
- **Autenticação multifator (MFA):** habilitar MFA para contas privilegiadas e, quando possível, para usuários normais.  
- **Monitoramento e alertas:** configurar alertas para picos de tentativas de login e padrões anômalos (geolocalização, volume por minuto).  
- **Registro e retenção de logs:** garantir logs de autenticação centralizados e protegidos, com retenção adequada para investigação.  
- **Hardening:** assegurar que contas padrão sem uso sejam desativadas, e que contas com permissões elevadas tenham controles adicionais.  
- **Educação e políticas:** treinar usuários sobre criação e armazenamento seguro de credenciais (gestores de senha).  


## Detecção e Monitoramento
Sugestões práticas e genéricas para detecção:
- Monitorar padrões de falhas de autenticação por usuário/IP.  
- Correlacionar tentativas de login com eventos anômalos (horário, origem, repetição).  
- Gerar alertas de volume significativo de tentativas em curto período.  
- Implantar análise comportamental para detectar bruteforce distribuído.  

## Notas Finais
Este repositório destina-se à documentação e rastreio de um exercício de segurança educativo.