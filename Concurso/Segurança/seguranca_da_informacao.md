# Segurança da Informação

## 1. Introdução e Conceito

Segurança da Informação (SI) é o conjunto de práticas, políticas, normas e tecnologias aplicadas para proteger as **informações** — em qualquer formato — contra ameaças, garantindo que seus **pilares fundamentais** sejam respeitados: **confidencialidade**, **integridade**, **disponibilidade**, **autenticidade**, **não-repúdio** e **privacidade**.

A SI se aplica em todos os níveis — do uso pessoal de dispositivos a corporações e instituições públicas. Seu foco está na proteção de **dados sensíveis** e na continuidade dos negócios.

---

## 2. Princípios Fundamentais da Segurança da Informação

| Princípio         | Definição                                                           | Exemplo                                                         |
| ----------------- | ------------------------------------------------------------------- | --------------------------------------------------------------- |
| Confidencialidade | Garante que somente pessoas autorizadas tenham acesso à informação. | Documento criptografado com acesso restrito por login.          |
| Integridade       | Assegura que a informação não foi alterada indevidamente.           | Verificação de hash SHA-256 após transferência de arquivos.     |
| Disponibilidade   | Garante que os dados estejam disponíveis quando necessários.        | Sistema com balanceamento de carga e failover automático.       |
| Autenticidade     | Confirma a identidade de quem acessa a informação.                  | Autenticação com biometria ou token OTP.                        |
| Não-repúdio       | Impede que o autor de uma ação negue sua autoria.                   | Assinatura digital com carimbo de tempo em contrato eletrônico. |
| Privacidade       | Assegura que os dados pessoais sejam protegidos.                    | Anonimização de dados conforme a LGPD.                          |

---

## 3. Ameaças e Tipos de Malware

### 3.1. Ameaças Cibernéticas Comuns

| Tipo           | Definição                                                            | Exemplo                                                         |
| -------------- | -------------------------------------------------------------------- | --------------------------------------------------------------- |
| Phishing       | Tentativa de obter dados sensíveis por meio de e-mails/sites falsos. | E-mail imitando banco solicitando "atualização de dados".       |
| Spear Phishing | Phishing direcionado e personalizado para a vítima.                  | E-mail para o RH com nome da vítima e anexo malicioso.          |
| Ransomware     | Sequestra dados com criptografia e exige resgate.                    | WannaCry (2017): afetou hospitais e empresas globalmente.       |
| Keylogger      | Registra teclas digitadas para roubar senhas/dados.                  | Instalado via malware em dispositivos públicos.                 |
| Worm           | Se replica automaticamente e se espalha por redes.                   | Conficker (2008): infectou milhões de PCs via vulnerabilidades. |
| Trojan         | Apresenta-se como software legítimo, mas contém código malicioso.    | Crack de software com backdoor.                                 |
| Adware         | Exibe propagandas indesejadas e pode coletar dados do usuário.       | Aplicativos de celular com anúncios invasivos.                  |
| Spyware        | Espiona atividades do usuário em segredo.                            | Aplicativos ocultos que monitoram localização e conversas.      |
| Rootkit        | Se oculta no sistema para manter acesso privilegiado.                | Rootkits de firmware que impedem a detecção de antivírus.       |
| Botnet         | Conjunto de máquinas infectadas controladas remotamente.             | Ataques DDoS massivos coordenados por dispositivos IoT zumbis.  |
| Cryptojacker   | Usa recursos do sistema para minerar criptomoedas sem permissão.     | Script oculto em site que usa CPU do visitante.                 |
| SQL Injection  | Envia comandos SQL maliciosos por formulários.                       | `OR '1'='1` permite login sem senha.                            |
| XSS            | Injeção de scripts em páginas web.                                   | Campo de comentários com JavaScript malicioso.                  |

---

## 4. Vulnerabilidades e Gestão de Vulnerabilidades

### 4.1. O que é uma Vulnerabilidade?

Vulnerabilidade é qualquer **falha de segurança** (de software, hardware, rede ou processos) que pode ser explorada para comprometer a confidencialidade, integridade ou disponibilidade das informações.

**Exemplos:**

- Serviços desatualizados com falhas conhecidas.
- Permissões excessivas concedidas a usuários.
- Senhas fracas ou reutilizadas.

### 4.2. Tipos de Vulnerabilidades

| Tipo            | Definição                                                                        |
| --------------- | -------------------------------------------------------------------------------- |
| Zero-day        | Descoberta recente, sem correção disponível.                                     |
| CVE             | Vulnerabilidades públicas listadas na base Common Vulnerabilities and Exposures. |
| Misconfiguração | Erros de configuração, como serviços sem autenticação.                           |

### 4.3. Ciclo de Vida da Gestão de Vulnerabilidades

1. **Identificação** – via scanners (Nessus, OpenVAS).
2. **Avaliação** – classificar severidade (CVSS).
3. **Correção** – aplicar patches ou mitigação.
4. **Validação** – testar a correção aplicada.
5. **Monitoramento contínuo** – manter vigilância por SIEM, logs e auditorias.

---

## 5. Controles de Segurança da Informação

| Tipo       | Função                                        | Exemplos                                             |
| ---------- | --------------------------------------------- | ---------------------------------------------------- |
| Preventivo | Evitar que o incidente ocorra.                | Firewall, autenticação forte, políticas de acesso.   |
| Detectivo  | Identificar eventos em andamento ou passados. | SIEM, IDS, monitoramento de logs, honeypots.         |
| Corretivo  | Restaurar sistemas após incidente.            | Backup, plano de recuperação de desastres, failover. |

**Controles podem ser:**

- **Físicos**: câmeras, biometria.
- **Lógicos**: criptografia, firewall, MFA.
- **Administrativos**: normas, políticas e treinamentos.

---

## 6. Ferramentas e Tecnologias

| Ferramenta                                           | Descrição e Aplicação                                                                    |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **Firewall**                                         | Controla tráfego de rede com base em regras. Pode ser perimetral ou pessoal.             |
| **WAF (Web Application Firewall)**                   | Protege aplicações web contra XSS, SQLi, etc.                                            |
| **IDS (Intrusion Detection System)**                 | Detecta atividade suspeita, sem bloquear.                                                |
| **IPS (Intrusion Prevention System)**                | Detecta e bloqueia automaticamente intrusões.                                            |
| **EDR (Endpoint Detection and Response)**            | Monitoramento contínuo e resposta automática em estações de trabalho.                    |
| **SIEM (Security Information and Event Management)** | Centraliza, correlaciona e analisa eventos de segurança. Ex: Splunk, Wazuh, ELK.         |
| **VPN (Virtual Private Network)**                    | Estabelece conexão segura e criptografada entre redes.                                   |
| **Failover**                                         | Mecanismo automático de transferência de serviços para sistema reserva em caso de falha. |

---

## 7. Backup, Continuidade e Recuperação

| Conceito                               | Definição e Aplicação                                                         |
| -------------------------------------- | ----------------------------------------------------------------------------- |
| Backup                                 | Cópia dos dados feita periodicamente. Pode ser local, em nuvem ou em SAN/NAS. |
| Restore                                | Processo de restauração do backup.                                            |
| SAN (Storage Area Network)             | Armazenamento em rede dedicado, de alta performance.                          |
| NAS (Network Attached Storage)         | Armazenamento em rede compartilhado, acessível como unidade de rede.          |
| PCN (Plano de Continuidade de Negócio) | Garante funcionamento mínimo após falha.                                      |
| DRP (Disaster Recovery Plan)           | Plano de resposta pós-incidente severo. Ex: queda de datacenter.              |

---

## 8. Normas ISO Relacionadas à Segurança da Informação

| Norma ISO     | Objetivo Principal                                                           |
| ------------- | ---------------------------------------------------------------------------- |
| ISO/IEC 27001 | Requisitos para um Sistema de Gestão de Segurança da Informação (SGSI).      |
| ISO/IEC 27002 | Boas práticas para controles de segurança definidos na 27001.                |
| ISO/IEC 27005 | Gestão de riscos aplicada à Segurança da Informação.                         |
| ISO/IEC 27017 | Segurança em ambientes de computação em nuvem.                               |
| ISO/IEC 27701 | Gestão da privacidade e dados pessoais (complementa a 27001 para LGPD/GDPR). |

**Importância:** A ISO 27001 é a base para auditorias e certificações de segurança em nível organizacional.
