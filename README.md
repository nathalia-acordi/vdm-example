
# VDM Example - Cart System

Este repositório contém um **exemplo em VDM-SL** (Vienna Development Method - Specification Language) para modelagem formal de um **sistema de carrinho de compras**.  
O objetivo é demonstrar como usar especificações formais para garantir correção e consistência em sistemas simples.

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

