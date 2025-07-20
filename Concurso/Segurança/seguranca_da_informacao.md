# Segurança da Informação

## 1. Conceito

Segurança da Informação (SI) é o conjunto de práticas, políticas, normas e tecnologias destinadas a proteger **informações** — em qualquer formato — contra acesso não autorizado, alteração, destruição ou divulgação indevida.

---

## 2. Princípios Fundamentais

| Princípio         | Definição                                    | Exemplo                                            |
| ----------------- | -------------------------------------------- | -------------------------------------------------- |
| Confidencialidade | Acesso apenas a quem tem autorização.        | Arquivos criptografados com controle de acesso.    |
| Integridade       | Protege contra alterações indevidas.         | Verificação com hash SHA-256 após backup.          |
| Disponibilidade   | Garante acesso quando necessário.            | Infraestrutura redundante e sistemas com failover. |
| Autenticidade     | Assegura que o emissor é legítimo.           | Assinatura digital em e-mail corporativo.          |
| Não-repúdio       | Impede que o autor negue uma ação realizada. | Logs com carimbo de tempo e assinatura digital.    |
| Privacidade       | Protege a identidade e os dados pessoais.    | Consentimento e anonimização em bancos de dados.   |

---

## 3. Ameaças Cibernéticas (com Exemplos Reais)

| Ameaça            | Definição e Atuação                                                               | Exemplo                                                                 |
| ----------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Phishing          | E-mail/site falso que tenta enganar a vítima para obter senhas ou dados pessoais. | "Atualize sua conta bancária clicando aqui" — imitação de bancos reais. |
| Spear Phishing    | Phishing altamente direcionado com dados específicos da vítima.                   | E-mail falso com nome da vítima, cargo e nome do gerente.               |
| Ransomware        | Malware que criptografa dados e exige resgate.                                    | Caso WannaCry em 2017: atingiu empresas e hospitais globalmente.        |
| Keylogger         | Captura tudo que é digitado no teclado.                                           | Instalado em lan houses para roubar senhas.                             |
| Engenharia Social | Manipulação psicológica para obter acesso ou dados.                               | Telefonema fingindo ser do suporte técnico pedindo senha.               |
| SQL Injection     | Injeção de código SQL malicioso em formulários.                                   | `SELECT * FROM users WHERE username = 'admin' OR 1=1;`                  |
| Exploit           | Código que explora vulnerabilidades específicas.                                  | CVE-2017-0144 (EternalBlue): explorado pelo WannaCry.                   |
| Botnet            | Rede de máquinas comprometidas controladas remotamente.                           | Ataques massivos a servidores DNS via milhares de dispositivos IoT.     |
| DoS/DDoS          | Sobrecarga do sistema por excesso de requisições simultâneas.                     | Ataque ao DynDNS (2016) causou queda de Netflix, Twitter e outros.      |
| Spyware           | Programa espião que monitora o usuário sem autorização.                           | Ferramentas ocultas em aplicativos gratuitos suspeitos.                 |

---

## 4. Vulnerabilidades e Gestão de Risco

Vulnerabilidade é uma falha em sistemas, softwares, redes ou configurações que pode ser explorada. A **gestão de vulnerabilidades** compreende:

1. **Identificação** (ex: scanners de segurança)
2. **Avaliação de criticidade** (baixa, média, alta)
3. **Correção ou mitigação** (patches, reconfiguração)
4. **Monitoramento contínuo**

### Tipos comuns de vulnerabilidades:

* **Zero-day**: desconhecida até então pelos fornecedores.
* **CVE (Common Vulnerabilities and Exposures)**: vulnerabilidades conhecidas e publicadas.
* **Misconfiguração**: erros de configuração como serviços sem senha ou portas abertas desnecessárias.

**Ferramentas úteis**: Nessus, OpenVAS, Qualys, Nikto.

---

## 5. Controles de Segurança

| Tipo de Controle | Objetivo                                 | Exemplos                                         |
| ---------------- | ---------------------------------------- | ------------------------------------------------ |
| Preventivo       | Evitar que incidentes ocorram.           | Firewall, criptografia, senhas fortes.           |
| Detectivo        | Identificar ocorrências ou tentativas.   | IDS, SIEM, logs de sistema.                      |
| Corretivo        | Minimizar impacto e restaurar operações. | Backup, plano de recuperação de desastres (DRP). |

---

## 6. Ferramentas e Tecnologias

| Ferramenta         | Utilização prática                                                |
| ------------------ | ----------------------------------------------------------------- |
| Firewall           | Regras que filtram o tráfego de entrada/saída.                    |
| IDS/IPS            | Detecção e prevenção de intrusões em rede (ex: Snort, Suricata).  |
| SIEM               | Agrega e correlaciona logs para alertas (ex: Splunk, ELK, Wazuh). |
| VPN                | Canal seguro criptografado entre redes públicas e privadas.       |
| WAF                | Protege aplicações web de ataques como XSS e SQLi.                |
| MFA (Autenticação) | Autenticação em dois fatores: senha + token ou biometria.         |
| EDR                | Proteção avançada de endpoint com resposta automatizada.          |

---

## 7. Governança de Segurança e Normas ISO

**Governança de Segurança** refere-se ao conjunto de políticas, normas e práticas que guiam a gestão da segurança em uma organização. Os principais elementos são:

* **PSI (Política de Segurança da Informação)**: define regras sobre acesso, responsabilidade e uso dos dados.
* **Plano de Continuidade de Negócio (PCN)**: garante o funcionamento mínimo em caso de incidentes.
* **Plano de Recuperação de Desastres (DRP)**: reestabelece a normalidade após falhas severas.
* **Pentest**: simulação de ataques reais para testar a robustez dos sistemas.

### Normas ISO mais relevantes:

| Norma             | Foco principal                                                                                                               |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **ISO/IEC 27001** | Estabelece os requisitos para criar, manter e melhorar um Sistema de Gestão de Segurança da Informação (SGSI). Certificável. |
| **ISO/IEC 27002** | Diretrizes de boas práticas em controles de segurança — complementa a 27001.                                                 |
| **ISO/IEC 27005** | Estrutura para gestão de riscos de segurança da informação.                                                                  |
| **ISO/IEC 27017** | Controles específicos para ambientes em nuvem.                                                                               |
| **ISO/IEC 27701** | Privacidade e proteção de dados — extensão da ISO 27001 para a LGPD/GDPR.                                                    |

A mais importante é a **ISO/IEC 27001**, pois define o padrão internacional para SGSI e é certificável — servindo como base para auditorias e regulamentações. A **27002** orienta como implementar os controles definidos na 27001. Já a **27005** ajuda na gestão de riscos, crucial para ambientes corporativos.

---