# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: João Victor Viana Marcolino  
RA: 24001237
Data: 26-03-2026

---

# 1. Definição do MVP
Explique claramente:

- O que está **dentro** do MVP  
- O que está **fora** do MVP  
- Por que você fez essas escolhas
    A principio vejo como mais importante o modulo de compra, vendas, estoque e produtos, esses modulos são interligados e dependem diretamente um do outro.
    Incluiria desde o cadastro dos produtos, até a finalização da venda e geração do comprovante.
    Naturalmente deve haver a validação do estoque antes da confirmação da venda e a atualização do estoque em tempo real, principalmente por questões de vendas sem estoque.
    Os demais modulos viriam posteriormente para complementar o sistema, modulos como contas a pagar e receber.
    A tomada dessa decisão se baseia no levantamento de requisitos feito pela farmacia, conflitos em vendas e estoque podem levar um negócio ao desequilíbrio e consequentemente á falência. 

Exemplo de início:  
> “Meu MVP cobre o processo de venda desde a identificação/cadastro do cliente até a emissão do comprovante, incluindo tratamento de estoque insuficiente.”

---

# 2. Regras de Negócio (mínimo: 5)
Liste e descreva **cada RN** de forma clara.

**RN01 — Vendas de produtos só poderão ser feitas mediante confirmado saldo em estoque.**  
**RN02 — Quando um produto atingir uma quantidade minima no estoque deve ser gerado um aviso para os usuários**  
**RN03 — Processo de venda a prazo somente poderá ser utilizado quando o cliente tiver cadastro na farmácia - Pessoa juridica**  
**RN04 — Após feita uma nova aquisição de estoque os valores dos produtos devem ser ajustados conforme nova entrada**  
**RN05 — Assim que realizada uma venda o produto deve ter seu saldo ajustado de imediato para que não haja conflitos de estoque**  

(Adicione mais se quiser.)

---

# 3. Requisitos Funcionais (mínimo: 8)
Liste os requisitos funcionais do seu MVP.

**RF01 — O sistema deve permitir cadastro, consulta de atualização de produtos baseados nesses dados (nome, código de barras, fabricante)**  
**RF02 — Naturalmente quando um chegar ao fim no estoque o status dele deve ser mudado para inativo e notificar os usuários**  
**RF03 — O saldo do estoque deve ser ajustado assim que for realizada uma venda**  
**RF04 — O modulo de compras deve ser acessível somente aos responsáveis (setor financeiro)**  
**RF05 — O sistema deve gerar um comprovante cumpom de compra assim que o pagemento for confirmado**  
**RF06 — O gerente deve conseguir atualizar produtos, estoque e consultar relatórios**  
**RF07 — O sistema deve armazenar um registro das vendas e compras realizadas para fins de relatórios**  
**RF08 — O sistema deve permitir alterações como, devoluções e transferencias de estoque entre outras filiais**  

(Adicione mais se quiser.)

---

# 🛡 4. Requisitos Não Funcionais (mínimo: 4)
Liste os RNFs do sistema conforme seu MVP.

**RNF01 — O sistema deve exigir login e senha dos usuários para autenticação**  
**RNF02 — O sistema precisa ter uma alta disponibilidade (principalmente se a farmacia for 24hrs)**  
**RNF03 — As consultas de produtos não podem exceder 2 segundos**  
**RNF04 — Vendas e compras devem ajustar o estoque instantaneamente (tolerancia de 5 segundos)**  

(Adicione mais se quiser.)

---

# 5. Casos de Uso (mínimo: 10)
### Inserir **diagrama de casos de uso geral**, demonstrando claramente:
- os 10 casos
- relação entre eles e atores
- pelo menos 3 includes
- pelo menos 3 extends

<img width="525" height="601" alt="image" src="https://github.com/user-attachments/assets/5548f1dd-2f56-4766-9759-7b6411a289a3" />
<img width="545" height="334" alt="image" src="https://github.com/user-attachments/assets/cd68ba50-b96b-4096-82bc-edc591e2b7e4" />

---
# 6. Documentação dos Casos de Uso
Para **cada caso de uso**, utilize o template abaixo:
---

## **UC01 — LOGIN**
**Ator(es): Usuário**  
**Descrição: Login no sistema**  
**Pré-condições: Usuário ativo e válido**  
**Pós-condições: Conseguir acessar o sistema**  

### Fluxo Principal
1. Usuário acessa o sistema  
2. Fornece as credenciais 
3. Autentica no sistema 


### Fluxos Alternativos / Exceções
- FA01 — Falha no login 

### Relacionamentos
- sem relacionamento

### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.
### Diagrama de Atividade 01
<img width="380" height="398" alt="image" src="https://github.com/user-attachments/assets/1caeb876-7a91-441d-86be-b781036f7beb" />

---

## **UC02 — LOGIN E CONSULTA DE MEDICAMENTOS**
**Ator(es): Usuário**  
**Descrição: Login no sistema**  
**Pré-condições: Usuário ativo e válido**  
**Pós-condições: Conseguir consultar os remédios**  

### Fluxo Principal
1. Usuário acessa o sistema  
2. Fornece as credenciais 
3. Autentica no sistema
4. Consulta medicamentos


### Fluxos Alternativos / Exceções
- FA01 - Falha no login
- FA02 - Não localiza medicamento 

### Relacionamentos
- sem relacionamento

### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.
### Diagrama de Atividade 02
<img width="553" height="517" alt="image" src="https://github.com/user-attachments/assets/494627de-560d-45ac-82f5-f6d50b918e02" />

## **UC03 — LOGIN E CONSULTA DE MEDICAMENTOS E VENDA**
**Ator(es): Usuário**  
**Descrição: Login no sistema**  
**Pré-condições: Usuário ativo e válido**  
**Pós-condições: Conseguir consultar os remédios e realizar venda**  

### Fluxo Principal
1. Usuário acessa o sistema  
2. Fornece as credenciais 
3. Autentica no sistema
4. Consulta medicamentos
5. Realiza venda


### Fluxos Alternativos / Exceções
- FA01 - Falha no login
- FA02 - Não localiza medicamento
- FA03 - Medicamento sem estoque

### Relacionamentos
- sem relacionamento

### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.
### Diagrama de Atividade 03
<img width="570" height="550" alt="image" src="https://github.com/user-attachments/assets/5c5d247b-6ac0-4eb6-86e5-ce7475c3e1b4" />




