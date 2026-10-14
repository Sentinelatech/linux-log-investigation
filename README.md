# linux-log-investigation

Investigação de uma tentativa de acesso indevido a um servidor Linux. Em um laboratório próprio, uma máquina sofre um ataque de força bruta por SSH; o projeto reconstrói o que aconteceu a partir dos logs, automatiza a análise com um script e aplica as correções (hardening).

> Projeto 2 de 7 do laboratório [sentinelatech](https://github.com/sentinelatech). Área: **Linux e SOC básico**.

## Por que isso importa em segurança

Investigar logs é o trabalho diário de quem atua em SOC e em resposta a incidentes. Força bruta por SSH é um dos ataques mais comuns contra servidores expostos, e os rastros ficam nos logs de autenticação.

## Objetivo

A partir dos logs de um servidor próprio, identificar a tentativa de força bruta, medir sua extensão, escrever um script que resume o ataque e documentar as medidas que o teriam impedido.

## Estrutura

```
docs/especificacao.md   escopo e critério de aceite
docs/conceitos.md       autenticação no Linux, auth.log, journald
scripts/                script de análise de log (Python ou Bash)
relatorio/              o relatório de investigação, com a linha do tempo
dados/                  amostra de log anonimizada
```

## Laboratório

Duas VMs no VirtualBox na mesma rede interna: um servidor Ubuntu com SSH e uma máquina de origem. O ataque é gerado por você, contra a sua própria VM. Cabe folgado em 12 GB livres.

## Ferramentas

VirtualBox · Ubuntu Server · OpenSSH · `grep`, `awk`, `journalctl` · Python · Fail2ban (no hardening).

## Resultado

<!-- Preencher ao fim -->

## Aviso

Todo o ataque ocorre entre máquinas virtuais próprias, isoladas em rede interna. Nenhum host de terceiros é alvo. Os logs publicados são anonimizados.
