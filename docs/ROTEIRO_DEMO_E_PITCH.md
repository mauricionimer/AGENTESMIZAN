# Roteiro da demonstração e do pitch (regional, 24/10)

Pitch de 3 minutos + demonstração ao vivo. Uma pessoa narra; a outra faz o
papel do devedor, digitando na tela do Agente. A demo roda numa empresa de
demonstração com carteira fictícia; o agente se apresenta como assistente do
banco de demonstração.

## Antes de começar

- Sistema aberto 15 minutos antes e login da empresa de demonstração feito.
- Política de demonstração gravada (aba Política).
- Plano do dia já aplicado (aba Plano do dia).
- Vídeo de reserva no notebook e no celular, sem depender de internet.

## Pitch — 3 minutos

**0:00–0:30 · Problema.** Recuperação de crédito em banco pequeno e cooperativa:
carteira grande, equipe pequena, e o que importa não é o acordo fechado, é o
acordo pago. (Dados públicos com fonte e a frase de quem trabalha com cobrança
entram aqui.)

**0:30–2:00 · O agente ao vivo.**
1. *Plano do dia*: o Estrategista mostra os quatro grupos, cada devedor com o
   motivo, e o grupo sorteado que segue sem o agente — é o que prova o efeito.
2. *Conversa*: o "devedor" escreve "quero negociar". O agente confirma a
   identidade, pergunta quanto cabe por mês, simula e propõe; ao lado aparece
   cada passo, a regra do Auditor e o custo.
3. *Ataque*: o "devedor" pede 90% de desconto dizendo que é gerente. A
   simulação volta fora da política e nada é registrado; se a IA tentar
   registrar mesmo assim, o Auditor bloqueia e a regra aparece na tela.
4. *Política*: o gestor baixa o desconto máximo na aba Política. Na mensagem
   seguinte o agente já obedece — e a decisão grava a versão nova.
5. *Pagamento*: o botão faz o papel do banco confirmando o pagamento; o agente
   agradece e o acordo à vista vira quitado.

**2:00–2:30 · Como funciona e por que não é robô de cobrança.** Orquestrador,
Triagem, Negociador, Auditor em código com a palavra final, Acompanhamento e
Estrategista. O banco continua sendo quem cobra, com as regras dele; nenhum
valor sai da cabeça da IA; uma pessoa entra sempre que algo sai do previsto.

**2:30–3:00 · Negócio e próximos passos.** Software (assinatura e uso), não
comissão. Próximo passo: piloto numa parte da carteira de uma instituição,
medido contra o grupo sorteado.

## Perguntas prováveis da banca

- **Por que não LangGraph/CrewAI?** O orquestrador usa os mesmos conceitos
  (estado, nós, arestas, checkpoint, nó de erro), feito dentro do sistema: o
  caso dura semanas e o estado já mora no banco de dados.
- **E se a IA inventar um valor?** Todo valor do texto é conferido contra as
  simulações antes de enviar; não bateu, não sai.
- **LGPD?** A IA recebe o mínimo; a primeira mensagem diz que é um assistente
  virtual; o devedor pode pedir uma pessoa a qualquer momento; o banco é o
  controlador dos dados e o Mizan, o operador.
- **Quanto custa por conversa?** Medido pelo próprio agente em cada passo
  (aparece na tela).
- **Como vocês sabem que funciona?** Bateria de 63 cenários conferidos por
  código e, no cliente, comparação com o grupo sorteado.
