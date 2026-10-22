# Especificação — linux-log-investigation

**Semana:** 30/10 a 05/11/2026
**Entrega final:** relatório de investigação + script de análise

## Contexto

Um servidor Linux do laboratório ficou com o SSH exposto e recebeu uma enxurrada de tentativas de login. Você foi encarregado de reconstruir o incidente a partir dos logs, dizer o que aconteceu e recomendar o que impede a repetição.

## Escopo

1. **Montar o cenário** — servidor Ubuntu com SSH em uma VM; gerar, a partir de outra VM sua, uma sequência de tentativas de login que falham (por exemplo com `hydra` contra a sua própria máquina, ou um laço de `ssh` com senhas erradas).
2. **Investigar** — nos logs de autenticação (`/var/log/auth.log` ou `journalctl`), identificar: as tentativas que falharam, os usuários tentados, a origem e a janela de tempo.
3. **Automatizar** — um script que lê o log e resume: total de falhas, top usuários tentados, top origens e se houve algum sucesso.
4. **Corrigir (hardening)** — aplicar e documentar medidas: desativar login por senha e por root, mover a porta não resolve sozinho, instalar e configurar o Fail2ban, e registrar o antes e depois.

## Critério de aceite

- [ ] Linha do tempo do ataque, com horários e números extraídos do log
- [ ] Script versionado em `scripts/`, que roda sobre a amostra em `dados/`
- [ ] Amostra de log anonimizada (IPs e nomes de host mascarados)
- [ ] Lista de medidas de hardening, cada uma com o porquê
- [ ] README com o resultado em uma linha

## Fora de escopo

Qualquer ataque fora das suas VMs. O `hydra` só aponta para o seu próprio servidor de laboratório.

## Fases (issues da semana)

| Dia | Fase | Entrega do dia |
|---|---|---|
| Sex 30/10 | VMs e SSH exposto | Servidor e origem conversando por SSH |
| Seg 02/11 | Gerar e capturar as tentativas | Log com as falhas registradas |
| Ter 03/11 | Investigação manual | Linha do tempo do ataque, em rascunho |
| Qua 04/11 | Script de análise e amostra limpa | Script resumindo o log + amostra anonimizada em `dados/` |
| Qui 05/11 | Hardening e fechamento | Medidas aplicadas, relatório final e README |
