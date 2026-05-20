# Posts prontos — GitHub Discussions — EasyFleet

Crie as categorias em **Discussions → Categories** antes de postar:
`Organização · Frota · Locação · Prestação · Motoristas · Abastecimento · Pneus · Manutenção · TCO · Depreciação · Pedágios · Multas · Frete · Integrações · Alertas`

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

## CATEGORIA: Locação

---

### Post L1

**Título:**
```
A frota tem veículos locados? Qual o volume em relação à frota própria?
```

**Corpo:**
```
Veículos locados têm um modelo de TCO diferente dos veículos próprios.

Na locação, a mensalidade substitui depreciação, manutenção e seguro —
que geralmente estão inclusos no contrato com a locadora.
O custo variável mais relevante passa a ser o km excedente
(valor cobrado por km rodado acima da franquia contratada).

Precisamos entender o perfil da frota para modelar corretamente
o banco de dados e os cálculos de TCO.

Usem os comentários para descrever:
- Quais locadoras são utilizadas hoje
- Se existe portal ou API de acesso aos dados do contrato
```

**Pergunta do Poll:**
```
Qual o perfil da frota da empresa?
```

**Opções do Poll:**
```
100% própria
100% locada
Mista — maioria própria
Mista — maioria locada
```

---

### Post L2

**Título:**
```
Quais dados do contrato de locação devem ser cadastrados na plataforma?
```

**Corpo:**
```
Para calcular o TCO de um veículo locado e gerar alertas precisos,
a plataforma precisa dos dados do contrato.

Dados propostos para o cadastro:
- Locadora (Localiza, Movida, Unidas, LM Frotas, outra)
- Número do contrato
- Valor da mensalidade (R$)
- Franquia de km mensal (km inclusos no contrato)
- Custo por km excedente (R$/km)
- O que está incluso: manutenção preventiva, corretiva, pneus, seguro
- Data de início e data de vencimento do contrato

O custo de km excedente é o principal custo variável de uma frota locada
e o que mais impacta o TCO quando não monitorado.

Usem os comentários para indicar se existem outros campos
relevantes nos contratos atuais da empresa.
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais dados do contrato são essenciais no cadastro?
```

**Opções do Poll:**
```
Valor da mensalidade
Franquia de km mensal e custo por km excedente
Data de vencimento do contrato
O que está incluso (manutenção, seguro, pneus)
```

---

### Post L3

**Título:**
```
O sistema deve alertar quando o veículo se aproxima da franquia de km mensal?
```

**Corpo:**
```
Em frotas locadas, ultrapassar a franquia de km contratada
gera cobrança por km excedente — que pode ser significativa
na escala de uma frota inteira.

Exemplo:
Contrato com franquia de 2.000 km/mês a R$ 0,90/km excedente.
Um veículo que roda 2.400 km gera R$ 360 de custo extra.
Em uma frota de 20 veículos, isso pode somar R$ 7.200/mês.

Fluxo proposto:
Sistema monitora o km registrado no mês → ao atingir X% da franquia
→ alerta o gestor para redistribuir uso ou negociar a franquia.

Usem os comentários para indicar qual percentual da franquia
deve disparar o alerta (80%? 90%?).
```

**Pergunta do Poll:**
```
Alerta de franquia de km deve estar no MVP?
```

**Opções do Poll:**
```
Sim — é o principal alerta de uma frota locada, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — controlamos isso manualmente hoje e está bom
```

---

### Post L4

**Título:**
```
Manutenção e seguro do veículo locado são responsabilidade de quem?
```

**Corpo:**
```
Essa definição impacta diretamente o que entra no TCO do veículo locado.

Cenários comuns:

Contrato full service:
Mensalidade inclui manutenção preventiva, corretiva, pneus e seguro.
→ TCO = mensalidade + abastecimento + pedágios + multas

Contrato básico:
Mensalidade cobre só o veículo. Manutenção e seguro por conta da empresa.
→ TCO = mensalidade + manutenção + seguro + abastecimento + pedágios + multas

O modelo do contrato define quais categorias de custo
a plataforma precisa rastrear para esse veículo.

Usem os comentários para descrever o modelo dos contratos atuais.
```

**Pergunta do Poll:**
```
Como é o contrato de locação utilizado hoje?
```

**Opções do Poll:**
```
Full service — manutenção e seguro inclusos na mensalidade
Básico — só o veículo, manutenção e seguro por conta da empresa
Misto — depende do contrato e da locadora
Ainda não utilizamos locação
```

---

### Post L5

**Título:**
```
Quais locadoras devem ser integradas na plataforma?
```

**Corpo:**
```
A integração com portais de locadoras permite importar automaticamente:
- Extratos mensais do contrato
- Km rodado por veículo (quando disponível via API)
- Cobranças de km excedente
- Histórico de manutenções cobertas pelo contrato

Locadoras com presença em frotas corporativas no Brasil:
- Localiza Meoo — maior rede, portal corporativo consolidado
- Movida Gestão de Frotas — forte em médias empresas
- Unidas — forte em transportadoras e frotas pesadas
- LM Frotas — focado em gestão de frotas corporativas

Usem os comentários para indicar:
- Qual locadora a empresa já utiliza
- Se já existe acesso ao portal ou documentação de API
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais locadoras integrar no MVP?
```

**Opções do Poll:**
```
Localiza Meoo
Movida Gestão de Frotas
Unidas
LM Frotas
Sem preferência — integrar conforme disponibilidade de API
```

---

## CATEGORIA: Prestação

---

### Post P1

**Título:**
```
A frota tem veículos financiados? Qual o volume em relação à frota total?
```

**Corpo:**
```
Veículo financiado é diferente de locado:
a empresa é proprietária (ou será ao fim do contrato),
mas paga parcelas mensais ao banco ou financeira.

Isso impacta o TCO porque o financiamento gera um custo
financeiro mensal que precisa entrar no cálculo — assim como
a depreciação continua sendo monitorada via FIPE,
já que o veículo é patrimônio da empresa.

TCO de veículo financiado inclui:
- Prestação mensal (capital + juros)
- Depreciação (via FIPE)
- Manutenção
- Seguro
- IPVA e licenciamento
- Abastecimento
- Pedágios e multas

Usem os comentários para indicar quais bancos ou financeiras
são utilizados e se existe portal ou API de acesso ao extrato.
```

**Pergunta do Poll:**
```
Qual o perfil de aquisição de veículos da frota?
```

**Opções do Poll:**
```
Maioria própria (pagos à vista)
Maioria financiados (prestação)
Maioria locados
Misto entre os três modelos
```

---

### Post P2

**Título:**
```
Quais dados do financiamento devem ser cadastrados na plataforma?
```

**Corpo:**
```
Para incluir o custo do financiamento no TCO e gerar alertas
de vencimento de parcelas, a plataforma precisa dos dados do contrato.

Dados propostos:
- Banco ou financeira (ex: Bradesco, Itaú, BV Financeira, Banco Toyota)
- Número do contrato
- Valor financiado (R$)
- Valor da parcela mensal (R$)
- Número total de parcelas
- Parcelas pagas / parcelas restantes
- Taxa de juros (% a.m.)
- Data da primeira parcela
- Data do último pagamento (quitação)
- Saldo devedor atualizado

Com esses dados, a plataforma calcula o custo financeiro total
do veículo e projeta o momento de quitação — ponto em que
o custo mensal do veículo cai significativamente.

Usem os comentários para indicar se a empresa já tem
esse controle em algum sistema financeiro ou ERP.
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais dados do financiamento são essenciais no cadastro?
```

**Opções do Poll:**
```
Valor da parcela mensal e número de parcelas restantes
Data de quitação do financiamento
Taxa de juros e saldo devedor
Banco ou financeira responsável
```

---

### Post P3

**Título:**
```
O sistema deve alertar sobre parcelas próximas do vencimento?
```

**Corpo:**
```
Para frotas com muitos veículos financiados, controlar os
vencimentos de parcelas manualmente é propenso a erros
e atrasos que geram juros adicionais.

Fluxo proposto:
Plataforma monitora a data de vencimento de cada parcela
→ X dias antes, alerta o financeiro da empresa
→ Registro da parcela paga atualiza o saldo devedor automaticamente

O alerta é especialmente útil quando o contrato está próximo
da quitação — momento ideal para avaliar renovação ou
substituição do veículo.

Usem os comentários para indicar:
- Com quantos dias de antecedência o alerta deve ser enviado
- Se o alerta deve ir para o gestor de frota, para o financeiro ou para ambos
```

**Pergunta do Poll:**
```
Alertas de vencimento de parcela entram no MVP?
```

**Opções do Poll:**
```
Sim — essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — o financeiro já controla isso separadamente
```

---

### Post P4

**Título:**
```
Como o custo do financiamento deve aparecer no TCO?
```

**Corpo:**
```
Duas abordagens possíveis:

Abordagem A — Custo financeiro separado:
A parcela mensal entra como categoria "Financiamento" no TCO,
separada de manutenção, abastecimento etc.
O gestor vê claramente quanto do custo é custo financeiro.

Abordagem B — Custo por km rodado:
Além da categoria, o sistema calcula o custo do financiamento
por km rodado no mês (parcela / km do mês).
Permite comparar diretamente com veículos locados e próprios.

Usem os comentários para indicar qual visão ajuda mais
nas decisões de renovação e substituição de veículos.
```

**Pergunta do Poll:**
```
Como o financiamento deve aparecer no TCO?
```

**Opções do Poll:**
```
Como categoria de custo separada (R$/mês)
Como custo por km rodado (R$/km)
Ambos — categoria mensal e custo por km
Não precisa aparecer no TCO, é custo financeiro separado
```

---

## CATEGORIA: Motoristas

---

### Post M1

**Título:**
```
Quais dados do motorista são obrigatórios no cadastro?
```

**Corpo:**
```
Para vincular motoristas a veículos, custos e multas,
a plataforma precisa de um cadastro mínimo de cada condutor.

Dados propostos:
- Nome completo
- CPF
- Matrícula interna (se aplicável)
- Tipo de vínculo: CLT, terceiro, autônomo
- Número da CNH
- Categoria da CNH (A, B, C, D, E)
- Validade da CNH
- Veículo fixo vinculado (se aplicável)

Usem os comentários para indicar:
- Se a empresa já tem esse cadastro em algum sistema de RH
- Se existe integração possível para importar dados existentes
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais dados do motorista são obrigatórios no MVP?
```

**Opções do Poll:**
```
Nome, CPF e matrícula interna
CNH (número, categoria e validade)
Tipo de vínculo (CLT, terceiro, autônomo)
Veículo fixo vinculado
```

---

### Post M2

**Título:**
```
A plataforma deve monitorar o vencimento da CNH dos motoristas?
```

**Corpo:**
```
CNH vencida é um risco jurídico e operacional para a empresa.
Se o motorista causar um acidente com CNH vencida,
a seguradora pode negar a cobertura e a empresa pode ser responsabilizada.

Fluxo proposto:
Plataforma monitora a data de validade de cada CNH cadastrada
→ X dias antes do vencimento, alerta o gestor e o motorista
→ Registro da renovação após apresentação do novo documento.

Usem os comentários para indicar:
- Com quantos dias de antecedência o alerta deve ser disparado
- Se o alerta deve ir só para o gestor ou também para o motorista
```

**Pergunta do Poll:**
```
Monitoramento de vencimento de CNH entra no MVP?
```

**Opções do Poll:**
```
Sim — é essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — controlamos isso via RH, não precisa na plataforma
```

---

### Post M3

**Título:**
```
A plataforma deve consultar a pontuação e situação da CNH no DETRAN?
```

**Corpo:**
```
Além do vencimento, é possível integrar com o SENATRAN/DETRAN
para consultar automaticamente:

- Pontuação acumulada na CNH (limite: 20 pontos em 12 meses)
- Situação: ativa, suspensa, cassada ou em processo de suspensão
- Infrações registradas na habilitação

Motoristas próximos do limite de pontos ou com CNH suspensa
representam risco imediato para a operação da frota.

Essa consulta pode ser feita por CPF + número da CNH
via APIs de despachantes ou diretamente pelo portal Gov.br (com OAuth).

Usem os comentários para indicar se esse nível de monitoramento
é necessário para o perfil de clientes da plataforma.
```

**Pergunta do Poll:**
```
Consulta automática de pontuação e situação da CNH entra no escopo?
```

**Opções do Poll:**
```
Sim — essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — monitoramento de vencimento é suficiente
```

---

### Post M4

**Título:**
```
O motorista tem veículo fixo ou pode usar qualquer veículo da frota?
```

**Corpo:**
```
Essa decisão impacta como os custos são atribuídos:

Veículo fixo por motorista:
→ Abastecimento, multas e pedágios são atribuídos automaticamente ao condutor

Motorista rotativo (qualquer veículo):
→ O sistema precisa registrar quem usou qual veículo em qual período
   para conseguir atribuir custos e multas corretamente

Usem os comentários para descrever como funciona hoje
na operação — veículos são dedicados ou compartilhados?
```

**Pergunta do Poll:**
```
Como o vínculo motorista-veículo funciona na frota?
```

**Opções do Poll:**
```
Fixo — cada motorista tem um veículo dedicado
Rotativo — motoristas usam qualquer veículo disponível
Misto — parte da frota fixa, parte rotativa
```

---

### Post M5

**Título:**
```
A plataforma deve registrar o comportamento de direção do motorista?
```

**Corpo:**
```
Com integração de telemetria (rastreador GPS), é possível
monitorar eventos de comportamento de direção por motorista:

- Frenagem brusca
- Aceleração agressiva
- Excesso de velocidade
- Curvas em alta velocidade
- Tempo com o veículo parado (motor ligado)

Esse dado permite:
- Ranking de motoristas por perfil de direção
- Correlacionar comportamento com custo de manutenção e combustível
- Identificar necessidade de treinamento

Essa funcionalidade depende de integração com rastreadores
(Sascar, Onixsat, Cobli, Autotrac) e é mais relevante
para frotas de caminhões e veículos de carga.

Usem os comentários para indicar se a frota já utiliza rastreadores.
```

**Pergunta do Poll:**
```
Monitoramento de comportamento de direção entra no escopo?
```

**Opções do Poll:**
```
Sim — essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — não é relevante para o nosso perfil de frota
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

## CATEGORIA: Depreciação

---

### Post 17

**Título:**
```
O cadastro do veículo deve incluir o código FIPE?
```

**Corpo:**
```
Para monitorar a depreciação do veículo ao longo do tempo,
a plataforma precisa consultar mensalmente o valor de mercado
pelo código FIPE correspondente ao modelo exato do veículo.

Sem o código FIPE vinculado ao veículo, não é possível
automatizar a busca do valor de mercado — o gestor precisaria
informar manualmente a cada mês.

Campos de depreciação no cadastro do veículo:
- Código FIPE (ex: 038003-9)
- Valor de compra (R$)
- Data de compra
- Quilometragem no momento da compra

Com esses dados, a plataforma calcula automaticamente
a depreciação total e mensal ao longo da vida útil do veículo.
```

**Pergunta do Poll:**
```
O código FIPE deve ser campo obrigatório no cadastro do veículo?
```

**Opções do Poll:**
```
Sim — obrigatório, depreciação automática é essencial
Sim — obrigatório apenas para veículos com controle de TCO ativo
Opcional — o gestor preenche se quiser monitorar depreciação
Não — depreciação não é prioridade para o nosso perfil de cliente
```

---

### Post 18

**Título:**
```
Como a depreciação do veículo deve ser monitorada pela plataforma?
```

**Corpo:**
```
Modelo proposto de monitoramento automático de depreciação:

Fonte de dados:
A plataforma consulta mensalmente a tabela FIPE pelo código
do veículo cadastrado, obtendo o valor de mercado atualizado.

Histórico salvo por mês:
Para cada veículo, a plataforma mantém um snapshot mensal com:
- Valor de mercado FIPE no mês de referência
- Quilometragem registrada no período
- Idade do veículo em meses
- Depreciação acumulada desde a compra (%)
- Depreciação no mês (%)

Cálculos automáticos:
- Depreciação total (%) = (valor de compra − valor FIPE atual) / valor de compra × 100
- Depreciação mensal (%) = variação do valor FIPE mês a mês
- Custo de depreciação por km rodado = depreciação do mês / km rodados no mês

Arquitetura:
Rotina automática mensal → Consulta API FIPE → Salva histórico
→ Calcula indicadores → Disponibiliza no dashboard do TCO

Usem os comentários para indicar:
- Com que frequência o gestor precisa ver esse dado (mensal é suficiente?)
- Se existe valor de compra disponível para a frota atual
- Se já existe algum controle de depreciação nos sistemas atuais
```

**Pergunta do Poll:**
```
Com que frequência a depreciação do veículo deve ser atualizada?
```

**Opções do Poll:**
```
Mensal — snapshot da tabela FIPE no primeiro dia de cada mês
Trimestral — a cada 3 meses é suficiente
Sob demanda — o gestor solicita a atualização quando precisar
Não precisamos monitorar depreciação automaticamente
```

---

### Post 19

**Título:**
```
Qual o principal indicador de depreciação para o gestor de frota?
```

**Corpo:**
```
A depreciação pode ser apresentada de diferentes formas.
O indicador escolhido define como o gestor toma decisões
sobre renovação e descarte de veículos.

Exemplos de indicadores:

Depreciação total acumulada (%):
Ex: "Este veículo perdeu 42% do valor de compra em 3 anos"
→ Indica quando considerar a troca do veículo

Custo de depreciação por km rodado (R$/km):
Ex: "Este veículo custa R$ 0,18/km só de depreciação"
→ Permite comparar veículos e calcular o TCO real por km

Valor de mercado atual vs. valor de compra (R$):
Ex: "Comprado por R$ 120.000 — vale hoje R$ 69.600"
→ Útil para seguros, financiamentos e negociações de troca

Usem os comentários para indicar qual decisão de gestão
esse dado precisa apoiar (renovação, seguro, comparativo entre veículos...).
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais indicadores de depreciação são essenciais no dashboard?
```

**Opções do Poll:**
```
Custo de depreciação por km rodado (R$/km)
Depreciação total acumulada desde a compra (%)
Valor de mercado atual vs. valor de compra (R$)
Comparativo de depreciação entre veículos da frota
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

## CATEGORIA: Multas

---

### Post 21

**Título:**
```
Controle de multas de trânsito entra no MVP?
```

**Corpo:**
```
O EasyFleet pode integrar com plataformas de gestão de multas
para importar automaticamente as infrações por veículo,
identificar o condutor responsável e acompanhar o status de pagamento.

Dois players disponíveis no mercado:
- Frota 162 — gestão de multas para transportadoras
- Beemon / Bee2Go — plataforma de autogestão de multas para frotas

Sem integração, o gestor precisaria acompanhar multas
manualmente via DETRAN, o que é ineficiente para frotas grandes.
```

**Pergunta do Poll:**
```
Gestão de multas entra no MVP?
```

**Opções do Poll:**
```
Sim — integração automática com provedor no MVP
Sim — consulta manual no MVP, integração depois
Não — fica para versão seguinte ao MVP
```

---

### Post 22

**Título:**
```
Quais provedores de gestão de multas integrar?
```

**Corpo:**
```
Players identificados no mercado:

- Frota 162: focado em transportadoras, gestão completa de multas
- Beemon / Bee2Go: autogestão de multas, indicação do condutor, recursos

Usem os comentários para indicar:
- Se a empresa já usa algum desses serviços hoje
- Se existe contato comercial ou documentação de API disponível
- Outros provedores que conhecem
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais provedores de multas integrar?
```

**Opções do Poll:**
```
Frota 162
Beemon / Bee2Go
Consulta direta ao DETRAN (sem provedor intermediário)
Sem preferência — avaliar conforme disponibilidade de API
```

---

### Post 23

**Título:**
```
A multa é atribuída ao veículo ou ao condutor responsável?
```

**Corpo:**
```
Quando uma multa é identificada, ela pode ser:

- Atribuída ao veículo: o custo fica no histórico do carro independente de quem dirigia
- Atribuída ao condutor: o sistema identifica quem estava dirigindo no momento
  da infração e registra a responsabilidade no perfil do motorista

A atribuição ao condutor exige cruzamento de dados
(quem usou o veículo naquele horário) e impacta o fluxo de indicação.
```

**Pergunta do Poll:**
```
Como a multa deve ser atribuída?
```

**Opções do Poll:**
```
Ao veículo (custo no histórico do carro)
Ao condutor responsável (identificado pelo sistema)
Ao veículo com opção de indicar o condutor manualmente
```

---

### Post 24

**Título:**
```
O sistema deve gerenciar o recurso de multas?
```

**Corpo:**
```
Além de registrar a multa, o sistema pode apoiar o processo de recurso:

- Alerta de prazo para recurso antes de vencer
- Registro do status (aguardando julgamento, deferido, indeferido)
- Histórico de recursos por veículo

Esse fluxo aumenta o valor da plataforma mas adiciona
complexidade ao bounded context de Multas.
```

**Pergunta do Poll:**
```
Gestão de recursos de multas entra no escopo?
```

**Opções do Poll:**
```
Sim — essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — só registro e custo são suficientes
```

---

### Post 25

**Título:**
```
A consulta de multas deve ser feita por placa ou por CNPJ?
```

**Corpo:**
```
No Brasil existem dois tipos de consulta:

Por placa (DETRAN/SENATRAN):
Retorna multas de trânsito do veículo — infrações de velocidade,
estacionamento, semáforo, documentação do veículo, etc.

Por CNPJ (ANTT):
Retorna multas aplicadas à empresa transportadora — infrações
de peso, excesso de jornada do motorista, documentação de carga,
falta de licença de operação, etc.

Frotas de transportadoras precisam monitorar os dois tipos.
Frotas corporativas (carros leves) geralmente só precisam da consulta por placa.
```

**Pergunta do Poll:**
```
Qual tipo de consulta de multas é necessário?
```

**Opções do Poll:**
```
Somente por placa (multas de trânsito — DETRAN)
Somente por CNPJ (multas de transporte — ANTT)
Ambos — por placa e por CNPJ
```

---

### Post 26

**Título:**
```
A frota precisa monitorar multas da ANTT?
```

**Corpo:**
```
A ANTT (Agência Nacional de Transportes Terrestres) fiscaliza
o transporte rodoviário de cargas e passageiros.

Multas comuns da ANTT:
- Excesso de peso do veículo
- Motorista sem descanso obrigatório (jornada)
- Documentação de carga irregular
- Transporte sem autorização ou licença
- Tacógrafo adulterado ou ausente

Essas multas são aplicadas à empresa (CNPJ), não ao veículo,
e podem ser de valores muito mais altos que multas de trânsito comuns.

Esse tipo de controle é mais relevante para transportadoras
do que para frotas corporativas de carros leves.
```

**Pergunta do Poll:**
```
Monitoramento de multas ANTT entra no escopo?
```

**Opções do Poll:**
```
Sim — essencial para nosso perfil de cliente, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — nossos clientes não são transportadoras
Depende — oferecer como módulo opcional
```

---

### Post 27

**Título:**
```
Multas entram no cálculo de TCO?
```

**Corpo:**
```
As multas de trânsito representam um custo real da operação da frota.

Incluir no TCO permite ao gestor visualizar o impacto financeiro
das infrações e comparar o comportamento de diferentes veículos ou condutores.

Usem os comentários para indicar se existe orçamento previsto
para multas ou se é tratado como custo extraordinário.
```

**Pergunta do Poll:**
```
Multas entram no cálculo de TCO?
```

**Opções do Poll:**
```
Sim — entra como categoria de custo no TCO
Não — é tratado separadamente, fora do TCO
Sim, mas só como informativo (não soma no TCO principal)
```

---

## CATEGORIA: Frete

---

### Post F1

**Título:**
```
A plataforma deve registrar os fretes realizados por cada veículo?
```

**Corpo:**
```
Para frotas de transporte de carga, o frete é a unidade de negócio
que justifica todos os custos da operação.

Registrar os fretes permite cruzar receita com custo operacional
e calcular a lucratividade real por viagem ou por veículo.

Exemplo:
Veículo A realizou 8 fretes no mês → gerou R$ 24.000 de receita
→ TCO operacional do veículo no mês: R$ 9.500
→ Margem bruta por veículo: R$ 14.500 (60,4%)

Esse dado transforma o EasyFleet de uma plataforma de custo
para uma plataforma de gestão de resultado operacional.

Usem os comentários para indicar se a empresa já registra
os fretes em algum sistema (TMS, planilha, ERP).
```

**Pergunta do Poll:**
```
Registro de fretes entra no escopo da plataforma?
```

**Opções do Poll:**
```
Sim — essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — nossos clientes não são transportadoras
Depende — oferecer como módulo opcional
```

---

### Post F2

**Título:**
```
Quais dados do frete devem ser registrados?
```

**Corpo:**
```
Dados propostos por frete realizado:

Identificação:
- Número do frete / CT-e (Conhecimento de Transporte Eletrônico)
- Data de início e data de entrega
- Veículo e motorista responsável

Rota:
- Origem (cidade/UF)
- Destino (cidade/UF)
- Distância percorrida (km)

Carga:
- Tipo de carga
- Peso (toneladas)
- Valor da carga (para seguro e responsabilidade)

Financeiro:
- Valor do frete cobrado (receita R$)
- Valor do frete pago ao motorista (se autônomo)

Com esses dados é possível calcular:
- Custo por km por frete
- Receita por km
- Margem por frete
- Produtividade por veículo e por motorista

Usem os comentários para indicar quais campos são indispensáveis
e quais podem ser opcionais no cadastro inicial.
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais dados do frete são obrigatórios no registro?
```

**Opções do Poll:**
```
Origem, destino e distância (km)
Valor do frete (receita)
Veículo e motorista responsável
CT-e (Conhecimento de Transporte Eletrônico)
```

---

### Post F3

**Título:**
```
O sistema deve calcular a lucratividade por frete?
```

**Corpo:**
```
Com o custo operacional do veículo (TCO) e a receita do frete registrados,
a plataforma pode calcular automaticamente:

- Receita do frete (R$)
- Custo operacional proporcional ao frete (combustível, pedágio, motorista)
- Margem bruta do frete (R$ e %)
- Custo por km do frete
- Receita por km do frete

Esse cruzamento permite ao gestor identificar:
- Rotas mais lucrativas vs. rotas deficitárias
- Motoristas com melhor relação custo/receita
- Veículos com custo operacional acima da média da frota

Usem os comentários para indicar se esse nível de análise
é necessário para o perfil de clientes da plataforma.
```

**Pergunta do Poll:**
```
Cálculo de lucratividade por frete entra no escopo?
```

**Opções do Poll:**
```
Sim — essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — análise financeira é feita em outro sistema
```

---

### Post F4

**Título:**
```
Quais sistemas de frete integrar com o EasyFleet?
```

**Corpo:**
```
A integração com sistemas de TMS (Transportation Management System)
ou marketplaces de frete permite importar automaticamente
os fretes realizados, sem lançamento manual.

Plataformas relevantes no Brasil:
- TruckPad — marketplace de fretes, forte em autônomos
- Frete.com — plataforma de cotação e contratação de fretes
- Intelipost — TMS para e-commerce e varejo
- Axia TMS — TMS para transportadoras
- Omnilink / Sascar — telemetria + gestão de frete

Usem os comentários para indicar:
- Qual sistema de frete a empresa já utiliza hoje
- Se existe API disponível ou documentação conhecida
```

**Pergunta do Poll:** **(múltipla escolha)**
```
Quais sistemas de frete integrar?
```

**Opções do Poll:**
```
TruckPad
Frete.com
Intelipost
Axia TMS
Sem preferência — avaliar conforme disponibilidade de API
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
