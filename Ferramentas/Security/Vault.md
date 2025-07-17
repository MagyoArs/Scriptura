# Vault HashiCorp

## Sumário

* [1. O que é o Vault?](#1-o-que-é-o-vault)
  * [1.1. O que são segredos?](#11-o-que-são-segredos)
  * [1.2. Funções de gerenciamento (o que o Vault faz)](#12-funções-de-gerenciamento-o-que-o-vault-faz)
  * [1.3. Mecanismos e capacidades técnicas (como o Vault faz)](#13-mecanismos-e-capacidades-técnicas-como-o-vault-faz)

---

## 1. O que é o Vault?

O [**Vault**](https://developer.hashicorp.com/vault) da HashiCorp é uma ferramenta de gerenciamento de **segredos** e criptografia baseada em identidade. Ele centraliza o armazenamento, controle de acesso e auditoria de informações sensíveis, como senhas, chaves de API, certificados, entre outros.  
O Vault pode ser implantado em ambientes **on-premises**, na **nuvem** ou de forma **híbrida**. Seu design é **modular**, baseado em plugins para autenticação, engines de segredos e backends de armazenamento.

<p align="center">
  <img src="https://github.com/user-attachments/assets/dfa21c72-949f-420f-a6de-ad324f698c96" alt="Arquitetura Centralizada" width="600">
</p>

<p align="center">
  <em>Vault como ponto central de controle e distribuição de segredos entre usuários, aplicações e serviços externos.</em><br>
  <small>Fonte: <a href="https://developer.hashicorp.com/vault/tutorials/get-started/why-use-vault" target="_blank">HashiCorp Vault - Why Use Vault</a></small>
</p>

### 1.1. O que são segredos?
Segredos são informações confidenciais e críticas para o funcionamento seguro de sistemas e aplicações. Exemplos:

* Senhas de banco de dados
* Tokens de APIs
* Chaves de criptografia
* Certificados digitais

---

### 1.2. Funções de gerenciamento (o que o Vault faz)

O Vault oferece diversas funcionalidades voltadas à **administração segura de informações sensíveis**, permitindo centralizar e controlar o acesso a segredos de forma eficiente:

* **Gerenciar dados confidenciais:**
* **Gerenciar segredos estáticos:**
* **Gerenciar segredos de terceiros:**
* **Gerenciar certificados:**
* **Gerenciar identidades e autenticação:**
* **Autenticação humana e de máquina:**
* **Controle de acesso:**
* **Acesso com limite de tempo:**
* **Apoiar a conformidade regulatória:**

---

### 1.3. Mecanismos e capacidades técnicas (como o Vault faz)

Para viabilizar suas funcionalidades, o Vault utiliza **mecanismos internos especializados** que permitem gerar, armazenar e proteger segredos de maneira dinâmica e escalável:

* **Mecanismos de segredos para segredos estáticos e dinâmicos**
  *Ex: engines como KV (Key-Value), Database, PKI, AWS, etc.*
* **Segurança baseada em identidade**
  *Ex: integração com OIDC, LDAP, Kubernetes, etc.*
* **Criptografia de dados**
  *Ex: uso do engine Transit para criptografia de dados em trânsito e em repouso*
* **Escala de desempenho**
  *Ex: suporte a namespaces, replicação, alta disponibilidade, etc.*
* **Suporte para recuperação de desastres**
  *Ex: estratégias de backup, DR clusters, snapshots, etc.*

---

