# Resumo – Aula 07: Testes Automatizados

Resumo da aula do Prof. Me. Deivison S. Takatu (Fatec), abordando testes automatizados, pipelines de CI, tipos de testes, qualidade de código e a atividade proposta.

---

## 1. Introdução aos Testes Automatizados

### O que são
Verificações executadas automaticamente por ferramentas para validar o comportamento esperado de uma aplicação, sem depender da execução manual de cada cenário pelo desenvolvedor. Podem rodar durante o desenvolvimento e ser integradas às pipelines de **Integração Contínua (CI)**, identificando falhas antes da entrega.

### Por que automatizar

| Benefício | Descrição |
|---|---|
| Reduzir erros humanos | Menos dependência de verificações manuais e repetitivas |
| Aumentar a velocidade | Várias verificações em segundos ou minutos |
| Identificar falhas rapidamente | Problemas detectados logo após a alteração no código |
| Garantir consistência | Os mesmos cenários executados sempre que necessário |
| Aumentar a confiabilidade | Verificação contínua de que as funcionalidades existentes seguem funcionando |

---

## 2. Pipeline

### Estrutura de pipeline
Sequência de validações automatizadas executadas durante o ciclo de entrega do software. Princípios:

- **Build uma única vez:** o mesmo artefato é promovido entre ambientes.
- **Mesmo deploy em todos os ambientes:** Desenvolvimento → Homologação → Produção.
- **Falhou? Para tudo:** nenhuma etapa continua após um erro.

**Exemplo da aula:** um desenvolvedor altera a tela de login e envia o código ao GitHub. O pipeline inicia sozinho:
1. Baixa o código atualizado
2. Compila a aplicação
3. Executa testes automáticos
4. Verifica a qualidade do código
5. Gera uma nova versão da aplicação
6. Publica em ambiente de homologação

### Pipeline de testes
Executa validações automaticamente **após o build**, com o objetivo de garantir que novas alterações não quebrem funcionalidades existentes. Funções principais: execução automática de testes, validação contínua da aplicação e identificação rápida de falhas.

### Pipeline de qualidade
Realiza verificações automatizadas para avaliar se o código atende aos padrões definidos **antes de avançar** para as próximas etapas, identificando problemas de qualidade, inconsistências e possíveis falhas de forma antecipada.

### GitHub Actions Marketplace
Catálogo de Actions, ferramentas e extensões usadas nos workflows do GitHub Actions. Oferece soluções prontas para build, testes, qualidade, segurança, deploy, cache e outras etapas, desenvolvidas pelo GitHub, por parceiros ou pela comunidade.
Link: https://github.com/marketplace?type=actions&category=testing

---

## 3. Situação-Problema (projeto de exemplo)

**Problema:** vendedores de uma loja de roupas calculavam descontos manualmente, gerando erros humanos (valores cobrados divergentes) e inconsistência (cada vendedor aplicava de um jeito), com clientes insatisfeitos, retrabalho e perda de confiança.

**Solução:** um sistema web ("Sistema Comercial") que calcula descontos automaticamente, com regras padronizadas:
- Compras **abaixo** de R$ 100 → **10%** de desconto
- Compras **iguais ou superiores** a R$ 100 → **5%** de desconto

### Estrutura do projeto (`src/`)
| Item | Função |
|---|---|
| `components/DiscountDashboard.jsx` | Interface do usuário |
| `services/discountService.js` | Regras de desconto |
| `tests/unit/` | Testes unitários |
| `tests/integration/` | Testes de integração |
| `tests/performance/` | Testes de performance |
| `App.jsx` | Estrutura principal da aplicação |
| `main.jsx` | Ponto de entrada da aplicação |

Repositório de referência: https://github.com/deivisontakatu/projeto-pipeline-testes

---

## 4. Tipos de Testes

Os três tipos atuam em conjunto para garantir qualidade, confiabilidade, estabilidade e alinhamento aos requisitos (Pires e Militão, 2019).

### 4.1 Testes Unitários
- **Foco:** pequenas partes do sistema (funções, métodos, componentes isolados).
- **Características:** rápidos e automatizados; detectam falhas durante o desenvolvimento, antes da integração completa.
- **Vantagens:** facilitam a manutenção, aumentam a confiabilidade e reduzem custos com correções futuras.
- **Exemplo prático:** alterar a regra de desconto para 15%. O teste falha porque o sistema esperava 10% ou 5%.

### 4.2 Testes de Integração
- **Foco:** comunicação e funcionamento conjunto entre módulos, serviços, APIs e bancos de dados.
- **Características:** encontram falhas na troca de informações entre componentes que funcionam bem isoladamente.
- **Vantagens:** maior estabilidade, validando fluxos completos e reduzindo inconsistências em produção.
- **Exemplo prático:** alterar o texto do botão para "Calcular". O teste falha porque não encontra o botão "Calcular Desconto" durante a interação.

### 4.3 Testes de Performance
- **Foco:** comportamento da aplicação sob carga, tempo de resposta e consumo de recursos.
- **Características:** identificam gargalos e lentidão antes da implantação em produção.
- **Vantagens:** garantem estabilidade, escalabilidade e melhor experiência do usuário.
- **Exemplo prático:** alterar o tempo máximo de resposta esperado para 1 ms. O teste falha porque a aplicação não responde dentro do tempo configurado.

### Comparativo

| Tipo | O que valida | Exemplo de falha da aula |
|---|---|---|
| Unitário | Funções/métodos isolados | Regra mudou para 15%, esperado 10% ou 5% |
| Integração | Comunicação entre módulos/interface | Botão renomeado não é encontrado |
| Performance | Velocidade e estabilidade sob carga | Limite de 1 ms não é atendido |

---

## 5. Qualidade e Validação Automatizada

### Conceito de qualidade
Capacidade do sistema de atender requisitos, necessidades do usuário e objetivos do negócio com eficiência. Um software de qualidade apresenta **confiabilidade, estabilidade, facilidade de manutenção e capacidade de evolução**. Em ambientes DevOps, a qualidade deixa de ser responsabilidade exclusiva dos testes e passa a integrar todo o ciclo de desenvolvimento, entrega e operação ("Qualidade deve fazer parte do processo" – Humble e Priklandnicki, 2013).

### ESLint: verificador de qualidade
Ferramenta de **análise estática** para JavaScript que identifica problemas de padronização, qualidade e inconsistências. Na pipeline de CI, funciona como validação automatizada, impedindo a integração de código fora dos padrões do projeto (Moraes, 2015).
- **Exemplo prático:** adicionar `const x=1;` gera o erro `no-unused-vars` (variável criada e nunca utilizada).

### O que acontece quando um teste falha
Quando uma etapa identifica um problema, o processo pode ser interrompido para evitar que uma versão inválida avance. Consequências:
- A alteração não avança para as próximas etapas.
- A equipe recebe feedback sobre o problema.
- O código pode ser corrigido antes da entrega.
- Reduz-se o risco de levar uma versão com falhas para outro ambiente.

### Conclusão da situação-problema
Com DevOps e CI, a aplicação ficou mais confiável, segura e preparada para mudanças constantes. A automação de testes, validações e builds reduziu falhas, aumentou a qualidade das entregas e acelerou o desenvolvimento.

| Ferramenta/Teste | Papel |
|---|---|
| Testes unitários | Garantia da lógica individual |
| Integração | Validação entre módulos |
| Performance | Monitoramento de carga |
| ESLint | Qualidade e padronização |

---

## 6. Atividade

1. **Criar um novo projeto** que integre três tipos de testes automatizados: **unitário, integração e performance**, organizado para que cada tipo possa ser **executado e analisado de forma independente**.
2. **Criar uma pipeline de CI** com um arquivo `.yml` no **GitHub Actions**, configurada para rodar automaticamente a **cada push na branch `main`**.
3. A pipeline deve **instalar as dependências**, **executar os três tipos de testes** e **apresentar os resultados**.

---

## Referências da aula

- HUMBLE, J.; PRIKLADNICKI, R. *Entrega Contínua: Como Entregar Software de Forma Rápida e Confiável*. São Paulo: Bookman, 2013.
- MORAES, G. *Caixa de Ferramentas DevOps*. São Paulo: Casa do Código, 2015.
- PIRES, A.; MILITÃO, J. *Integração Contínua com Jenkins*. São Paulo: Casa do Código, 2019.
- MUNIZ, A. et al. *Jornada DevOps*. São Paulo: Brasport, 2019.
- SATO, D. *DevOps na prática*. São Paulo: Casa do Código, 2014.
- KIM, G.; HUMBLE, J.; DEBOIS, P.; WILLIS, J. *Manual de DevOps*. São Paulo: Alta Books, 2018.
- Demais referências: Silva (2016), Arundel e Domingus (2019), Vitalino e Castro (2018), Silverman (2019).