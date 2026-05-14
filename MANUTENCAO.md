# Guia de Mensagens Personalizadas

Este guia mostra como publicar mensagens personalizadas na status page do **IDCerberus** usando o Upptime.

## Quando usar

Use este fluxo para comunicar:

- manutenção programada
- indisponibilidade planejada
- aviso de instabilidade
- atualização manual de incidente

## Onde criar

Abra uma issue no repositório:

- https://github.com/React-it/IDCerberus-Status-Page/issues

Depois clique em `New issue`.

## Manutenção programada

Para exibir uma mensagem de manutenção programada na status page, crie uma issue com:

1. um título claro
2. a mensagem para o cliente
3. o bloco HTML com `start`, `end` e `expectedDown`
4. a label `maintenance`

### Exemplo

```md
# Manutenção programada no Backoffice Produção

Estamos realizando uma manutenção programada no ambiente de produção.

Durante esta janela, o serviço pode apresentar indisponibilidade temporária.
Estamos trabalhando para o retorno no menor tempo possível.

<!--
start: 2026-05-14T22:00:00-03:00
end: 2026-05-14T23:30:00-03:00
expectedDown: backoffice-producao
-->
```

## Slugs disponíveis

Use os slugs abaixo em `expectedDown`:

- `landing-page`
- `backoffice-producao`
- `backoffice-homologacao`

Para vários serviços:

```md
expectedDown: landing-page, backoffice-producao, backoffice-homologacao
```

## Modelo curto

```md
# Manutenção programada

Estamos realizando uma manutenção programada.

Durante esta janela, o serviço pode apresentar indisponibilidade temporária.
Estamos trabalhando para o retorno no menor tempo possível.

<!--
start: AAAA-MM-DDTHH:MM:SS-03:00
end: AAAA-MM-DDTHH:MM:SS-03:00
expectedDown: SLUG_DO_SERVICO
-->
```

## Modelo corporativo

```md
# Manutenção programada no serviço

Estamos realizando uma janela de manutenção programada para atualização do ambiente.

Durante este período, o serviço poderá apresentar indisponibilidade temporária.
Nossa equipe está atuando para restabelecer a operação com segurança e no menor tempo possível.

<!--
start: AAAA-MM-DDTHH:MM:SS-03:00
end: AAAA-MM-DDTHH:MM:SS-03:00
expectedDown: SLUG_DO_SERVICO
-->
```

## Atualização manual de incidente

Se o incidente já existir e você quiser apenas adicionar uma mensagem personalizada:

1. abra a issue do incidente
2. adicione um comentário

### Exemplo de comentário

```md
Estamos cientes da indisponibilidade e já atuando na correção.
Próxima atualização prevista em 30 minutos.
```

## Diferença entre os tipos

- `maintenance`: para avisos planejados com data e hora
- comentário em incidente: para atualização de falha real já detectada
- `.upptimerc.yml`: para textos fixos da interface da status page

## Checklist rápido

- usar o slug correto
- informar `start` e `end`
- adicionar a label `maintenance`
- escrever mensagem curta, objetiva e sem termos internos
- informar previsão quando existir

## Referências

- https://upptime.js.org/docs/scheduled-maintenance
- https://upptime.js.org/docs/configuration
