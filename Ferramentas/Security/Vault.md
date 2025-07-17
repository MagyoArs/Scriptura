# Vault HashiCorp

## Sumário

* [1. O que é o Vault?](#1-o-que-é-o-vault)
  * [1.1. O que são segredos?](#11-o-que-são-segredos)
  * [1.2. Mecanismos e capacidades técnicas (como o Vault faz)](#12-mecanismos-e-capacidades-técnicas-como-o-vault-faz)
  * [1.3. Funções de gerenciamento (o que o Vault faz)](#13-funções-de-gerenciamento-o-que-o-vault-faz)
  * [1.4. Plugins](#14-plugins)
    * [1.4.1. Ciclo de vida de um plugin](#141-ciclo-de-vida-de-um-plugin)
    * [1.4.2. Plugins integrados](#142-plugins-integrados)
    * [1.4.3. Plugins externos](#143-plugins-externos)
    * [1.4.4. Plugins em contêineres](#144-plugins-em-contêineres)

---

## 1. O que é o Vault?

O [**Vault**](https://developer.hashicorp.com/vault) da HashiCorp é uma ferramenta de gerenciamento de **segredos** e **criptografia baseada em identidade**. Ele centraliza o armazenamento, controle de acesso e auditoria de informações sensíveis como senhas, chaves de API e certificados.

O Vault pode ser implantado em ambientes **on-premises**, na **nuvem** ou de forma **híbrida**. Seu design é **modular** e extensível, com suporte a plugins para autenticação, engines de segredos e backends de armazenamento.

<p align="center">
  <img src="https://github.com/user-attachments/assets/dfa21c72-949f-420f-a6de-ad324f698c96" alt="Arquitetura Centralizada" width="600">
</p>

<p align="center">
  <em>Vault como ponto central de controle e distribuição de segredos.</em><br>
  <small>Fonte: <a href="https://developer.hashicorp.com/vault/tutorials/get-started/why-use-vault" target="_blank">HashiCorp Vault - Why Use Vault</a></small>
</p>

---

### 1.1. O que são segredos?

Segredos são informações confidenciais e críticas para o funcionamento seguro de sistemas e aplicações. Exemplos:

* Senhas de banco de dados  
* Tokens de APIs  
* Chaves de criptografia  
* Certificados digitais  

---

### 1.2. Mecanismos e capacidades técnicas (como o Vault faz)

Para viabilizar suas funcionalidades, o Vault utiliza mecanismos internos especializados que permitem gerar, armazenar e proteger segredos de maneira dinâmica e escalável:

* **Mecanismos de segredos estáticos e dinâmicos**  
  *Ex: engines como `kv`, `database`, `pki`, `aws`, etc.*

* **Segurança baseada em identidade**  
  *Ex: integração com `oidc`, `ldap`, `kubernetes`, etc.*

* **Criptografia de dados**  
  *Ex: engine `transit` para criptografia em trânsito e em repouso*

* **Escalabilidade e alta disponibilidade**  
  *Ex: suporte a `namespaces`, replicação, HA, etc.*

* **Recuperação de desastres**  
  *Ex: estratégias de backup, clusters DR, snapshots, etc.*

---

### 1.3. Funções de gerenciamento (o que o Vault faz)

O Vault oferece funcionalidades voltadas à administração centralizada e segura de segredos, acessos e identidades:

#### • Gerenciar dados confidenciais

Armazena e protege segredos sensíveis como chaves, tokens e configurações privadas com controle de acesso e auditoria.

```bash
vault kv put secret/config db_password=supersecreta
````

#### • Gerenciar segredos estáticos

Segredos fixos como senhas e tokens são armazenados via engine KV com versionamento e TTL opcional.

```bash
vault secrets enable -path=secret kv-v2
```

#### • Gerenciar segredos de terceiros

Integra com provedores como AWS, Azure e GCP para gerar credenciais temporárias.

```bash
vault secrets enable aws
```

#### • Gerenciar certificados

Gera, renova e revoga certificados digitais com o engine PKI, reduzindo a gestão manual.

```bash
vault secrets enable pki
```

#### • Gerenciar identidades e autenticação

Permite login via LDAP, OIDC, Kubernetes e GitHub, tanto para humanos quanto para aplicações.

```bash
vault auth enable oidc
```

#### • Controle de acesso

Define políticas granulares que determinam quem pode acessar quais segredos.

#### • Acesso com limite de tempo

Credenciais e tokens podem expirar automaticamente para reduzir riscos de vazamento.

#### • Apoio à conformidade

Auditoria, rotação automática de segredos e segregação de permissões ajudam a atender normas como GDPR, HIPAA e ISO.

```bash
vault audit enable file file_path=/var/log/vault_audit.log
```

---

### 1.4. Plugins

O Vault adota uma arquitetura modular baseada em plugins que alimenta quase todas as suas funcionalidades. Isso garante flexibilidade e personalização.

Os plugins são usados em:

* **Engines de segredos**
  *Ex: `kv`, `database`, `pki`, `aws`*

* **Métodos de autenticação**
  *Ex: `oidc`, `ldap`, `approle`, `kubernetes`*

* **Backends de armazenamento**
  *Ex: `raft`, `consul`, `s3`, `gcs`, `dynamodb`*

<p align="center">
  <img src="https://github.com/user-attachments/assets/f7ffebf6-5616-4ccc-a76a-ffecba477c08" alt="Arquitetura de plugin do Vault" width="600">
</p>

<p align="center">
  <em>Arquitetura de plugin do Vault com exemplos de métodos de autenticação e mecanismos de segredos.</em><br>
  <small>Fonte: <a href="https://developer.hashicorp.com/vault/tutorials/get-started/discover-plugins" target="_blank">HashiCorp Vault - Discover Vault Plugins</a></small>
</p>

---

#### 1.4.1. Ciclo de vida de um plugin

Plugins externos seguem um ciclo de: instalação → registro → ativação.

```bash
# Registrar um plugin externo
vault plugin register -sha256=<CHECKSUM> \
  secret vault-plugin-meuplugin
```

<p align="center">
  <img src="https://github.com/user-attachments/assets/cd25491a-2f6a-49c6-8046-1dc17cec15e8" alt="Ciclo de vida de plugin" width="600">
</p>

---

#### 1.4.2. Plugins integrados

São fornecidos nativamente com o Vault, ativáveis via CLI ou API.
*Exemplos: `kv`, `transit`, `pki`, `ldap`, `oidc`, `github`.*

```bash
vault secrets enable transit
```

---

#### 1.4.3. Plugins externos

Permitem estender o Vault com funcionalidades personalizadas, como:

* Integração com bancos proprietários
* Engines de segredos customizados
* Autenticação com provedores internos

---

#### 1.4.4. Plugins em contêineres

Plugins podem rodar isoladamente em contêineres, trazendo:

* Atualizações independentes
* Maior segurança e isolamento
* Suporte nativo para Kubernetes

```hcl
plugin_processes {
  "vault-plugin-meuplugin" = {
    command = "/plugins/vault-plugin-meuplugin"
  }
}
