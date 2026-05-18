# Posts prontos — GitHub Discussions — EasyFleet

Crie as categorias abaixo em **Discussions → Categories** antes de postar:
`Organização · Frota · Abastecimento · Pneus · Manutenção · TCO · Integrações · Alertas`

Para cada post: cole o **Título** no campo de título, o **Corpo** no campo de texto e adicione o **Poll** usando o botão "Add poll" do GitHub Discussions.

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

Considerem o cenário mais comum dos nossos clientes-alvo.
```

**Poll — opções:**
```
Uma conta = uma empresa (um CNPJ)
Uma conta pode ter múltiplas empresas/filiais
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
Usem os comentários para descrever o que cada perfil pode ou não pode fazer.
```

**Poll — opções (múltipla escolha):**
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
da "Frota de Carros Executivos" como grupos distintos?

Isso impacta diretamente como organizamos veículos e relatórios no banco.
```

**Poll — opções:**
```
Sim — cada empresa pode ter várias frotas separadas
Não — uma empresa = uma frota única
Ainda não sei, precisa de mais análise
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
que foi gerado quando o veículo estava na frota anterior?
```

**Poll — opções:**
```
Sim — migra e mantém todo o histórico vinculado ao veículo
Sim — migra mas o histórico fica na frota anterior
Não — veículo é fixo na frota (deve ser desativado e recadastrado)
```

---

### Post 5

**Título:**
```
Quais atributos são obrigatórios no cadastro de um veículo?
```

**Corpo:**
```
Listem nos comentários quais campos são obrigatórios e quais são opcionais.

Sugestão inicial para discussão:
- Placa (obrigatório?)
- Chassi / RENAVAM (obrigatório?)
- Marca, Modelo, Ano (obrigatório?)
- Tipo de combustível (obrigatório?)
- Capacidade do tanque (obrigatório?)
- Km inicial (obrigatório?)
- Cor (opcional?)
- Foto do veículo (opcional?)

Votem na importância do hodômetro:
```

**Poll — opções:**
```
Hodômetro é obrigatório e vem da integração com o provedor
Hodômetro é obrigatório e é inserido manualmente pelo motorista
Hodômetro é opcional no MVP
Não precisamos de hodômetro
```

---

## CATEGORIA: Abastecimento

---

### Post 6

**Título:**
```
O cartão de abastecimento é vinculado ao veículo ou ao motorista?
```

**Corpo:**
```
Essa decisão define como linkamos as transações de abastecimento
ao histórico de custo correto.

- Vinculado à placa: qualquer motorista usa o cartão do carro
- Vinculado ao motorista: o motorista leva o cartão para qualquer veículo
- Ambos: o cartão tem as duas informações
```

**Poll — opções:**
```
Vinculado ao veículo (placa)
Vinculado ao motorista (CPF/matrícula)
Vinculado aos dois (veículo + motorista por transação)
Depende do provedor — cada um tem um modelo diferente
```

---

### Post 7

**Título:**
```
Quais provedores de abastecimento devem ser integrados?
```

**Corpo:**
```
Marquem os provedores prioritários para o MVP e os que ficam para depois.
Usem os comentários para indicar se já temos documentação de API ou contato comercial com o provedor.
```

**Poll — opções (múltipla escolha):**
```
Ticket Log — MVP
TruckPad — MVP
Repom — MVP
Ticket Log — futuro
TruckPad — futuro
Repom — futuro
Outro (comentar abaixo)
```

---

### Post 8

**Título:**
```
O sistema deve detectar abastecimentos suspeitos automaticamente?
```

**Corpo:**
```
Ex: volume abastecido maior que a capacidade do tanque do veículo,
abastecimento em posto fora da rota habitual, dois abastecimentos
em menos de X horas.

Isso impacta a complexidade do motor de regras no MVP.
```

**Poll — opções:**
```
Sim — é essencial, entra no MVP
Sim — importante, mas fica para depois do MVP
Não — não é necessário por enquanto
```

---

## CATEGORIA: Pneus

---

### Post 9

**Título:**
```
Controle de pneus entra no MVP?
```

**Corpo:**
```
O bounded context de Pneus é um dos mais complexos.
Antes de detalhar as regras, precisamos decidir se entra no primeiro lançamento.
```

**Poll — opções:**
```
Sim — entra no MVP completo
Sim — entra no MVP de forma simplificada (só custo, sem lifecycle)
Não — fica para a versão seguinte ao MVP
```

---

### Post 10

**Título:**
```
Qual nível de rastreamento de pneus é necessário?
```

**Corpo:**
```
Nível 1 — Só custo: registro de quanto foi gasto com pneus por veículo/período
Nível 2 — Eventos: instalação, troca, descarte com data e km
Nível 3 — Lifecycle completo: cada pneu tem ID, posição no veículo, histórico de rodízio

Qual nível atende o gestor de frota?
```

**Poll — opções:**
```
Nível 1 — Só custo (mais simples)
Nível 2 — Eventos por veículo
Nível 3 — Lifecycle completo por pneu individual
```

---

## CATEGORIA: Manutenção

---

### Post 11

**Título:**
```
Manutenção entra no MVP?
```

**Corpo:**
```
Assim como pneus, manutenção tem alta complexidade (OS, aprovação, fornecedores).
Precisamos alinhar o escopo antes de modelar.
```

**Poll — opções:**
```
Sim — entra no MVP completo (OS, preventiva, corretiva)
Sim — entra no MVP simplificado (só registro de custo)
Não — fica para depois do MVP
```

---

### Post 12

**Título:**
```
O gestor precisa aprovar a Ordem de Serviço antes da execução?
```

**Corpo:**
```
Fluxo com aprovação: Oficina abre OS → Gestor aprova → Oficina executa → Gestor fecha
Fluxo sem aprovação: Oficina executa → Registra no sistema → Gestor visualiza

O fluxo com aprovação é mais seguro mas aumenta a complexidade do sistema.
```

**Poll — opções:**
```
Sim — aprovação obrigatória antes de executar
Sim — aprovação opcional (configurável por empresa)
Não — registro pós-execução é suficiente
```

---

## CATEGORIA: TCO

---

### Post 13

**Título:**
```
Quais categorias de custo compõem o TCO?
```

**Corpo:**
```
Marquem todas as categorias que devem entrar no cálculo de TCO.
Usem os comentários para indicar se alguma categoria tem regra especial de cálculo.
```

**Poll — opções (múltipla escolha):**
```
Abastecimento (combustível)
Pneus (compra, troca, manutenção)
Manutenção (OS preventiva e corretiva)
Depreciação do veículo
Seguro (obrigatório e opcional)
IPVA e licenciamento
Multas e infrações
Pedágios
```

---

### Post 14

**Título:**
```
O TCO é calculado por veículo, por frota ou pelos dois?
```

**Corpo:**
```
- Por veículo: o gestor vê o custo total de cada veículo individualmente
- Por frota: o gestor vê o custo agregado de toda a frota
- Ambos: drill-down da frota até o veículo individual
```

**Poll — opções:**
```
Somente por veículo
Somente por frota (agregado)
Ambos — frota com drill-down por veículo
```

---

### Post 15

**Título:**
```
Qual o período padrão de análise do TCO?
```

**Corpo:**
```
Como o gestor vai analisar os custos normalmente?
```

**Poll — opções:**
```
Mensal fixo (janeiro, fevereiro...)
Livre — gestor escolhe data início e fim
Ambos — mensal como padrão, com opção de período livre
Anual com comparativo mensal
```

---

## CATEGORIA: Integrações

---

### Post 16

**Título:**
```
Como o gestor conecta um provedor na plataforma?
```

**Corpo:**
```
Dois modelos possíveis:

Modelo A — Self-service: o gestor insere a própria chave de API do contrato que tem com o provedor
Modelo B — Centralizado: a FFKD tem contrato master com o provedor e o gestor só seleciona e autoriza

O Modelo A é mais simples de desenvolver mas exige que o cliente já tenha contrato com o provedor.
O Modelo B tem mais valor mas exige acordos comerciais da FFKD com cada provedor.
```

**Poll — opções:**
```
Modelo A — gestor insere a própria chave de API (MVP)
Modelo B — FFKD centraliza os contratos (MVP)
Modelo A no MVP, migrar para Modelo B depois
```

---

### Post 17

**Título:**
```
A sincronização com os provedores deve ser automática ou manual?
```

**Corpo:**
```
- Automática: o sistema sincroniza periodicamente sem ação do gestor (ex: todo dia às 2h)
- Manual: o gestor clica em "Sincronizar agora" quando quiser atualizar os dados
- Ambos: automática com opção de forçar sync manual
```

**Poll — opções:**
```
Automática (agendada, sem ação do gestor)
Manual (gestor aciona quando quiser)
Ambos — automática + opção de sync manual
```

---

## CATEGORIA: Alertas

---

### Post 18

**Título:**
```
Por quais canais o gestor deve receber alertas?
```

**Corpo:**
```
Marquem os canais que são essenciais para o MVP.
```

**Poll — opções (múltipla escolha):**
```
Notificação dentro da plataforma web
Push notification no app mobile
E-mail
WhatsApp
SMS
```

---

### Post 19

**Título:**
```
Quais situações devem gerar alerta automático?
```

**Corpo:**
```
Marquem as situações prioritárias. Usem os comentários para sugerir
limites/thresholds (ex: "custo acima de quanto?").
```

**Poll — opções (múltipla escolha):**
```
Custo mensal do veículo acima do orçamento definido
Abastecimento suspeito detectado
Pneu próximo do limite de troca (por km)
Manutenção preventiva vencida ou próxima do vencimento
Falha na sincronização com um provedor
OS sem conclusão após X dias
```
