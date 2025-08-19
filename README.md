
# VDM Example - Cart System
Este repositório contém um **exemplo em VDM-SL** (Vienna Development Method - Specification Language) para modelagem formal de um **sistema de carrinho de compras**.  
O objetivo é demonstrar como usar especificações formais para garantir correção e consistência em sistemas simples.

---
## Problema

Modelar, em **VDM-SL**, um **carrinho de compras** com catálogo de produtos e um carrinho do usuário.  
Utilize o **VDMJ** como ferramenta de execução e verificação.  

### Requisitos Funcionais
- **RF01:** Cadastrar produtos no catálogo (id, nome, preço em centavos)  
- **RF02:** Adicionar, atualizar e remover itens no carrinho (quantidade inteira ≥ 0)  
- **RF03:** Calcular o total do carrinho  
- **RF04:** Listar itens do carrinho (nome, preço, quantidade, subtotal)  

### Regras de Negócio
- **RN01:** Preço do produto ≥ 0 (em centavos). Quantidades no carrinho > 0 quando chave existir  
- **RN02:** Um item só pode estar no carrinho se existir no catálogo  

---

## Estrutura
- `CartSyst.vdmsl` → Especificação formal do sistema de carrinho
- `README.md` → Documentação do projeto

---
## Como executar
### 1. Clone este repositório:
 ```bash
   git clone git@github.com:nathalia-acordi/vdm-example.git
   cd vdm-example
  ```

### 2. Verifique se você possui Java 8+ instalado:
```bash
  java -version
  ```
   
### 3. Execute o arquivo `.vdmsl` com o **VDMJ** (ver instruções abaixo)

---

## Instale o VDMJ
O VDMJ é um interpretador para a linguagem VDM (Vienna Development Method) escrito em Java.

### 1. Baixar
- Acesse o repositório oficial: https://github.com/nickbattle/vdm
- Vá em **Releases** e baixe a versão mais recente

### 2. Executar

- É necessário ter o **Java** instalado (Java 8 ou superior)
- Para rodar o **VDMJ**:
```bash
  java -jar vdmj-4.6.0.jar -vdmsl CartSyst.vdmsl
  ```

  ### 3. Usar 
  * Comando para **type-checking**:
  ```bash
  java -jar vdmj-4.6.0.jar -vdmsl -strict CartSyst.vdmsl
  ```

  * Comando para **executar operações** (modo interativo):
  ```bash
  java -jar vdmj-4.6.0.jar -vdmsl -i CartSyst.vdmsl
  ```

### 4. Gerar Obrigações de Prova (POs)
   * Para gerar proof obligations:
  ```bash
 java -jar vdmj-4.6.0.jar -vdmsl -p CartSyst.vdmsl
  ```
--- 
### 5. Exemplo de Execução (interativo no VDMJ)
   * Adicionar comandos reais que o usuário pode digitar no interpretador:
  ```bash
 AddProduct(1, mk_Product("Camisa", 50));
AddItem(1, 2);
GetTotal();
  ```

   * E mostrar a saída esperada:
  ```bash
 -- Total esperado: 100
  ```



