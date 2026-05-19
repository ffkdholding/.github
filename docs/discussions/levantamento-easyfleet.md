# Posts prontos — GitHub Discussions — EasyFleet

Crie as categorias em **Discussions → Categories** antes de postar:
`Organização · Frota · Abastecimento · Pneus · Manutenção · TCO · Integrações · Alertas`

Cada post tem 4 campos:
- **Título** → campo de título do Discussion
- **Corpo** → campo de texto (descrição/contexto)
- **Pergunta do Poll** → campo "Ask a question" dentro do Poll
- **Opções do Poll** → cada linha é uma opção

Onde aparecer **(múltipla escolha)** → ative o toggle **"Allow multiple answers"** no poll.

---

## CATEGORIA: Organização

---

### Post 1

**Título:**
```
Uma conta na plataforma representa quantas empresas?
```

**Corpo:**
```
Precisamos entender a estrutura de acesso para modelar corretamente
o banco de dados e as permissões.

Exemplos:
- Uma conta = um CNPJ (empresa única)
- Uma conta = grupo empresarial com várias filiais
- Uma conta = uma filial (cada filial tem sua própria conta)

Considerem o cenário mais comum dos nossos clientes-alvo e usem
os comentários para explicar o raciocínio.
```

**Pergunta do Poll:**
```
Como uma conta se relaciona com as empresas?
```

**Opções do Poll:**
```
Uma conta = uma empresa (um CNPJ)
Uma conta pode ter múltiplas empresas ou filiais
Uma conta = uma filial (cada filial tem sua própria conta)
```

---

### Post 2

**Título:**
```
Quais perfis de acesso devem existir na plataforma?
```

**Corpo:**
```
Quem acessa o EasyFleet e o que cada perfil pode fazer?

Marquem todos os perfis que fazem sentido para o negócio.
Usem os comentários para descrever o que cada perfil pode
ou não pode fazer dentro da plataforma.
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais perfis de acesso são necessários?
```

**Opções do Poll:**
```
Administrador (controle total da conta)
Gestor de frota (gerencia veículos e relatórios)
Financeiro (acesso somente a custos e TCO)
Motorista (acesso mobile limitado)
Visualizador (somente leitura)
```

---

## CATEGORIA: Frota

---

### Post 3

**Título:**
```
Uma empresa pode ter múltiplas frotas?
```

**Corpo:**
```
Por exemplo: uma transportadora pode separar a "Frota de Caminhões"
da "Frota de Carros Executivos" como grupos distintos com relatórios separados?

Essa decisão impacta diretamente como organizamos veículos,
custos e relatórios de TCO no banco de dados.
```

**Pergunta do Poll:**
```
Como frotas se relacionam com a empresa?
```

**Opções do Poll:**
```
Uma empresa tem uma única frota
Uma empresa pode ter múltiplas frotas separadas
Ainda não sei — precisa de mais análise
```

---

### Post 4

**Título:**
```
Um veículo pode migrar entre frotas?
```

**Corpo:**
```
Ex: um veículo começa na "Frota SP" e é transferido para a "Frota RJ".

O que acontece com o histórico de custos (abastecimento, manutenção, TCO)
gerado quando o veículo estava na frota anterior?

Usem os comentários para dar exemplos reais do negócio.
```

**Pergunta do Poll:**
```
O que acontece quando um veículo muda de frota?
```

**Opções do Poll:**
```
Migra e mantém todo o histórico vinculado ao veículo
Migra mas o histórico fica registrado na frota anterior
Veículo é fixo na frota — deve ser desativado e recadastrado
```

---

### Post 5

**Título:**
```
Quais campos são obrigatórios no cadastro de um veículo?
```

**Corpo:**
```
Listem nos comentários quais campos são obrigatórios e quais são opcionais
para o cadastro inicial de um veículo na plataforma.

Sugestão para discussão:
- Placa
- Chassi / RENAVAM
- Marca, Modelo, Ano de fabricação
- Tipo de combustível
- Capacidade do tanque (litros)
- Quilometragem inicial
- Cor
- Foto do veículo

A votação abaixo é específica sobre a quilometragem (hodômetro).
```

**Pergunta do Poll:**
```
Como o hodômetro do veículo deve ser registrado?
```

**Opções do Poll:**
```
Obrigatório — vem automaticamente da integração com o provedor
Obrigatório — inserido manualmente pelo motorista
Opcional no MVP
Não precisamos rastrear hodômetro
```

---

### Post 6

**Título:**
```
Existe o conceito de veículo terceirizado na plataforma?
```

**Corpo:**
```
Algumas empresas utilizam veículos que não são próprios —
locados, de funcionários ou de parceiros.

O gestor precisa visualizar e rastrear custos de veículos
que não pertencem à empresa?
```

**Pergunta do Poll:**
```
A plataforma deve suportar veículos terceirizados?
```

**Opções do Poll:**
```
Sim — com controle completo igual ao veículo próprio
Sim — somente visualização de custo, sem gestão
Não — apenas veículos próprios no MVP
```

---

## CATEGORIA: Abastecimento

---

### Post 7

**Título:**
```
O cartão de abastecimento é vinculado ao veículo ou ao motorista?
```

**Corpo:**
```
Essa decisão define como as transações de abastecimento
são linkadas ao histórico de custo correto.

- Vinculado à placa: qualquer motorista usa o cartão do carro
- Vinculado ao motorista: o motorista leva o cartão para qualquer veículo
- Ambos: cada transação registra veículo e motorista

Usem os comentários para explicar como funciona hoje no processo atual.
```

**Pergunta do Poll:**
```
A qual entidade o cartão de abastecimento é vinculado?
```

**Opções do Poll:**
```
Ao veículo (placa)
Ao motorista (CPF ou matrícula)
Aos dois — veículo e motorista por transação
Depende do provedor — cada um tem um modelo diferente
```

---

### Post 8

**Título:**
```
Quais provedores de abastecimento integrar no MVP?
```

**Corpo:**
```
Marquem os provedores prioritários para o primeiro lançamento.

Usem os comentários para indicar:
- Se já temos documentação da API do provedor
- Se já existe contato comercial com o provedor
- Qualquer restrição técnica conhecida
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais provedores entram no MVP?
```

**Opções do Poll:**
```
Ticket Log
TruckPad
Repom
Sem preferência — integrar o que tiver API disponível primeiro
```

---

### Post 9

**Título:**
```
O sistema deve detectar abastecimentos suspeitos?
```

**Corpo:**
```
Exemplos de situações suspeitas:
- Volume abastecido maior que a capacidade do tanque do veículo
- Dois abastecimentos completos em menos de X horas
- Abastecimento em posto muito distante da rota habitual

Essa funcionalidade aumenta a segurança mas adiciona
complexidade ao motor de regras do MVP.
```

**Pergunta do Poll:**
```
Detecção de abastecimentos suspeitos entra no MVP?
```

**Opções do Poll:**
```
Sim — é essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — não é necessário por enquanto
```

---

## CATEGORIA: Pneus

---

### Post 10

**Título:**
```
Controle de pneus entra no MVP?
```

**Corpo:**
```
O bounded context de Pneus é um dos mais complexos da plataforma.

Antes de detalhar as regras de negócio, precisamos alinhar
se entra no primeiro lançamento e com qual profundidade.
```

**Pergunta do Poll:**
```
Qual o escopo de pneus no MVP?
```

**Opções do Poll:**
```
MVP completo — lifecycle por pneu, eventos, alertas
MVP simplificado — só registro de custo por veículo
Fora do MVP — versão seguinte ao lançamento
```

---

### Post 11

**Título:**
```
Qual nível de rastreamento de pneus é necessário?
```

**Corpo:**
```
Três níveis possíveis de controle:

Nível 1 — Custo: quanto foi gasto com pneus por veículo/período
Nível 2 — Eventos: instalação, troca e descarte com data e km
Nível 3 — Lifecycle: cada pneu tem ID próprio, posição no veículo
            e histórico completo de rodízio e recapagem

Qual nível atende o gestor de frota no dia a dia?
```

**Pergunta do Poll:**
```
Qual nível de rastreamento de pneus é necessário?
```

**Opções do Poll:**
```
Nível 1 — Só custo
Nível 2 — Eventos por veículo
Nível 3 — Lifecycle completo por pneu individual
```

---

## CATEGORIA: Manutenção

---

### Post 12

**Título:**
```
Manutenção entra no MVP?
```

**Corpo:**
```
Manutenção tem alta complexidade — Ordens de Serviço, aprovação,
fornecedores cadastrados, planos preventivos.

Precisamos alinhar o escopo antes de modelar o banco de dados.
```

**Pergunta do Poll:**
```
Qual o escopo de manutenção no MVP?
```

**Opções do Poll:**
```
MVP completo — OS, preventiva, corretiva, aprovação
MVP simplificado — só registro de custo
Fora do MVP — versão seguinte ao lançamento
```

---

### Post 13

**Título:**
```
O gestor precisa aprovar a Ordem de Serviço antes da execução?
```

**Corpo:**
```
Dois fluxos possíveis:

Com aprovação:
Oficina identifica problema → Gestor aprova o orçamento → Oficina executa → OS fechada

Sem aprovação:
Oficina executa o serviço → Registra no sistema → Gestor visualiza e valida

O fluxo com aprovação protege o gestor de custos não autorizados
mas exige que a oficina use a plataforma antes de iniciar o serviço.
```

**Pergunta do Poll:**
```
Como funciona o fluxo de aprovação de OS?
```

**Opções do Poll:**
```
Aprovação obrigatória antes de executar
Aprovação opcional — configurável por empresa
Sem aprovação — registro pós-execução é suficiente
```

---

## CATEGORIA: TCO

---

### Post 14

**Título:**
```
Quais categorias de custo compõem o TCO?
```

**Corpo:**
```
Marquem todas as categorias que devem entrar no cálculo de TCO.

Usem os comentários para:
- Indicar se alguma categoria tem regra especial de cálculo
- Informar se já existe essa informação nos sistemas atuais
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais categorias entram no cálculo de TCO?
```

**Opções do Poll:**
```
Abastecimento (combustível)
Pneus (compra, troca, recapagem)
Manutenção (OS preventiva e corretiva)
Depreciação do veículo
Seguro (obrigatório e opcional)
IPVA e licenciamento
Multas e infrações
Pedágios
```

---

### Post 15

**Título:**
```
O TCO é calculado por veículo, por frota ou pelos dois?
```

**Corpo:**
```
- Por veículo: o gestor vê o custo total de cada veículo individualmente
- Por frota: o gestor vê o custo agregado de toda a frota
- Ambos: visão da frota com possibilidade de detalhar por veículo (drill-down)

Usem os comentários para descrever como o gestor analisa
os custos hoje, antes da plataforma.
```

**Pergunta do Poll:**
```
Como o TCO deve ser visualizado?
```

**Opções do Poll:**
```
Somente por veículo
Somente por frota (agregado)
Ambos — frota com drill-down por veículo
```

---

### Post 16

**Título:**
```
Qual o período padrão de análise do TCO?
```

**Corpo:**
```
Como o gestor normalmente analisa os custos da frota?
Por mês fechado ou com liberdade de escolher qualquer período?

Usem os comentários para descrever a frequência de análise atual.
```

**Pergunta do Poll:**
```
Qual o período padrão de análise do TCO?
```

**Opções do Poll:**
```
Mensal fixo (janeiro, fevereiro...)
Livre — gestor escolhe data de início e fim
Ambos — mensal como padrão com opção de período livre
Anual com comparativo mensal
```

---

## CATEGORIA: Pedágios

---

### Post 17

**Título:**
```
Controle de pedágios entra no MVP?
```

**Corpo:**
```
O EasyFleet pode integrar com provedores de tag de pedágio
(Sem Parar, Veloe, ConectCar) para importar automaticamente
os gastos com pedágios por veículo.

Sem integração, o gestor precisaria lançar os custos manualmente.

Essa decisão impacta o cálculo de TCO e a completude dos relatórios de custo.
```

**Pergunta do Poll:**
```
Pedágios entram no MVP?
```

**Opções do Poll:**
```
Sim — integração automática com provedor de tag no MVP
Sim — lançamento manual no MVP, integração depois
Não — fica para versão seguinte ao MVP
```

---

### Post 18

**Título:**
```
Quais provedores de pedágio devem ser integrados?
```

**Corpo:**
```
Provedores de tag de pedágio disponíveis no Brasil:

- Sem Parar — maior base de clientes, aceito em todas as praças
- Veloe — forte em SP e RJ, boa API
- ConectCar — forte em frotas corporativas
- TagPlus — regional

Usem os comentários para indicar qual provedor a empresa já utiliza
e se já temos documentação de API ou contato comercial.
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais provedores de pedágio integrar?
```

**Opções do Poll:**
```
Sem Parar
Veloe
ConectCar
TagPlus
Sem preferência — integrar o que tiver API disponível primeiro
```

---

### Post 19

**Título:**
```
A tag de pedágio é vinculada ao veículo ou ao motorista?
```

**Corpo:**
```
Assim como o cartão de abastecimento, a tag pode estar
associada ao veículo ou ao motorista.

- Vinculada ao veículo: a tag fica fixada no para-brisa do carro
- Vinculada ao motorista: o motorista leva a tag para qualquer veículo

Essa decisão define como os custos de pedágio são atribuídos
no histórico e no TCO.
```

**Pergunta do Poll:**
```
A tag de pedágio é vinculada a qual entidade?
```

**Opções do Poll:**
```
Ao veículo (tag fixada no carro)
Ao motorista (tag pessoal)
Depende do provedor — cada um tem um modelo diferente
```

---

### Post 20

**Título:**
```
O gestor precisa ver o detalhamento de cada passagem de pedágio?
```

**Corpo:**
```
Dois níveis de detalhe possíveis:

Nível 1 — Resumo: total gasto em pedágios por veículo/período
Nível 2 — Detalhado: cada passagem com data, hora, praça e valor

O nível detalhado permite auditar rotas e identificar
desvios de percurso, mas exige mais armazenamento e
depende da granularidade da API do provedor.
```

**Pergunta do Poll:**
```
Qual nível de detalhe de pedágios é necessário?
```

**Opções do Poll:**
```
Nível 1 — Só o total por veículo/período
Nível 2 — Detalhamento por passagem (data, praça, valor)
Ambos — resumo com opção de drill-down por passagem
```

---

## CATEGORIA: Integrações

---

### Post 17

**Título:**
```
Como o gestor conecta um provedor na plataforma?
```

**Corpo:**
```
Dois modelos possíveis:

Modelo A — Self-service:
O gestor insere a própria chave de API do contrato que já tem com o provedor.
Mais simples de desenvolver. Exige que o cliente já tenha contrato próprio.

Modelo B — Centralizado:
A FFKD tem contrato master com o provedor.
O gestor só seleciona e autoriza. Mais valor agregado mas
exige acordos comerciais da FFKD com cada provedor.
```

**Pergunta do Poll:**
```
Qual modelo de conexão com provedores adotar?
```

**Opções do Poll:**
```
Modelo A — gestor insere a própria chave de API
Modelo B — FFKD centraliza os contratos com os provedores
Modelo A no MVP, evoluir para Modelo B depois
```

---

### Post 18

**Título:**
```
A sincronização com os provedores deve ser automática ou manual?
```

**Corpo:**
```
- Automática: o sistema sincroniza periodicamente sem ação do gestor
  (ex: todo dia às 2h da manhã)
- Manual: o gestor clica em "Sincronizar agora" quando quiser atualizar
- Ambos: sincronização automática com opção de forçar manualmente

Usem os comentários para indicar a frequência ideal de atualização
dos dados (a cada hora, diário, semanal?).
```

**Pergunta do Poll:**
```
Como deve funcionar a sincronização com provedores?
```

**Opções do Poll:**
```
Automática — agendada sem ação do gestor
Manual — gestor aciona quando precisar
Ambos — automática com opção de sync manual
```

---

## CATEGORIA: Alertas

---

### Post 19

**Título:**
```
Por quais canais o gestor deve receber alertas?
```

**Corpo:**
```
Marquem os canais essenciais para o MVP.

Usem os comentários para indicar qual canal o público-alvo
usa no dia a dia (WhatsApp? E-mail? App?).
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais canais de alerta são essenciais no MVP?
```

**Opções do Poll:**
```
Notificação dentro da plataforma web
Push notification no app mobile
E-mail
WhatsApp
SMS
```

---

### Post 20

**Título:**
```
Quais situações devem gerar alerta automático?
```

**Corpo:**
```
Marquem as situações prioritárias.

Usem os comentários para sugerir limites e thresholds:
- "Custo acima de quanto?"
- "Quantos dias sem conclusão da OS?"
- "A quantos km do limite avisar sobre o pneu?"
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais situações geram alerta automático?
```

**Opções do Poll:**
```
Custo do veículo acima do orçamento definido
Abastecimento suspeito detectado
Pneu próximo do limite de troca por km
Manutenção preventiva vencida ou próxima do vencimento
Falha na sincronização com um provedor
OS sem conclusão após prazo definido
```
