# Agentes do Mizan

Projeto do **AKCIT Camp 2026 — Agentes de IA**.

O Mizan é um software de recuperação de crédito para bancos e cooperativas. Ele
já prioriza a carteira, estima quanto cada dívida deve recuperar e mede o
resultado. Nesta etapa ganha agentes que **executam** a cobrança dentro das
regras do banco.

> O Mizan decide, mede e prova; o agente executa dentro das regras do banco.

O Mizan não é uma cobradora. O banco continua dono da relação com o cliente e
das regras; o Mizan é a ferramenta que aplica essas regras e registra cada
decisão.

## Os agentes

| Agente | O que faz | Tipo |
|---|---|---|
| Orquestrador | Recebe os eventos, decide quem age e guarda o estado de cada caso | Código |
| Triagem | Entende a intenção da mensagem do devedor | IA (modelo barato) |
| Estrategista | Divide a carteira em grupos e separa um grupo de controle sorteado | Código + modelo |
| Negociador | Conversa com o devedor e propõe acordos usando ferramentas | IA |
| Auditor | Confere cada ação contra a política do banco e tem a palavra final | Código |
| Acompanhamento | Cuida de datas, lembretes e pagamentos | Código |
| Aprendizado | Aprende com o dinheiro que entrou de fato, não com promessas | Código |
| Pessoa | Recebe o caso sempre que algo sai do previsto | Humano |

## Regras de projeto

- **Só o Negociador fala com o devedor**, e só com valores calculados pelo
  sistema: nenhum número no texto sai da cabeça da IA.
- **O Auditor é código, não IA.** Toda ação passa por ele e fica registrada a
  regra que permitiu ou bloqueou.
- **Na dúvida, uma pessoa.** Falha, contestação ou pedido do devedor levam o
  caso para uma pessoa, com resumo.
- **LGPD:** a IA recebe o mínimo (primeiro nome, valores, datas); o devedor
  pode pedir uma pessoa a qualquer momento; a primeira mensagem diz que é um
  assistente virtual.
- **Custo controlado:** teto diário por empresa; acima dele o agente para.

## Andamento

| Parte | Data | Situação |
|---|---|---|
| 1. Base: estado do caso, cliente de IA, rastreio e orquestrador | 16/10 | Feita, com testes |
| 2. Auditor, ferramentas, Triagem e Negociador | 17–18/10 | A fazer |
| 3. Telas e primeira conversa real | 19/10 | A fazer |
| 4. Demonstração de ponta a ponta | 20/10 | A fazer |
| 5. Acompanhamento e Estrategista | 21/10 | A fazer |
| 6. Bateria de cenários e documentação do fluxo | 22/10 | A fazer |

O código do Mizan fica em repositório privado. Este repositório reúne a
documentação, o fluxo dos agentes e as entregas do AKCIT Camp.
