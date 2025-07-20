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

### 3.1. Tipos de Ameaças Cibernéticas

| Tipo           | Definição                                                            | Exemplo                                                          |
| -------------- | -------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Phishing       | Tentativa de obter dados sensíveis por meio de e-mails/sites falsos. | E-mail imitando banco solicitando "atualização de dados".        |
| Spear Phishing | Phishing direcionado e personalizado para a vítima.                  | E-mail para o RH com nome da vítima e anexo malicioso.           |
| Pharming       | Redireciona a vítima para site falso mesmo digitando URL correta.    | Manipulação do DNS para simular site bancário real.              |
| Spoofing       | Falsificação de identidade (e-mail, IP, ARP).                        | E-mail com remetente falso fingindo ser o presidente da empresa. |

### 3.2. Tipos de Malware

| Tipo         | Definição                                                  | Exemplo                                                   |
| ------------ | ---------------------------------------------------------- | --------------------------------------------------------- |
| Ransomware   | Sequestra dados com criptografia e exige resgate.          | WannaCry (2017): afetou hospitais e empresas globalmente. |
| Keylogger    | Registra teclas digitadas para roubar senhas/dados.        | Instalado via malware em dispositivos públicos.           |
| Worm         | Se replica automaticamente e se espalha por redes.         | Conficker (2008): infectou milhões de PCs.                |
| Trojan       | Software malicioso disfarçado de legítimo.                 | Crack de software com backdoor.                           |
| Adware       | Exibe propagandas indesejadas e coleta dados.              | Aplicativo com pop-ups invasivos.                         |
| Spyware      | Espiona atividades do usuário.                             | Monitoramento de navegação e teclas digitadas.            |
| Rootkit      | Se oculta no sistema para manter acesso privilegiado.      | Rootkit de kernel impede antivírus.                       |
| Botnet       | Rede de dispositivos infectados e controlados remotamente. | Usado em ataques DDoS massivos.                           |
| Cryptojacker | Usa a CPU da vítima para minerar criptomoedas.             | Script escondido em site ou e-mail HTML.                  |
| SQLi         | Injeta código SQL em formulários.                          | `OR 1=1 --` para burlar login.                            |
| XSS          | Injeta scripts maliciosos em páginas web.                  | Comentário HTML com JS de roubo de cookie.                |

---

## 4. Vulnerabilidades e sua Gestão

### 4.1. Definição

Falhas que podem ser exploradas para comprometer os pilares da SI.

**Exemplos:**

* Software desatualizado;
* Configurações inseguras;
* Privilégios excessivos.

### 4.2. Tipos

| Tipo            | Definição                                                                     |
| --------------- | ----------------------------------------------------------------------------- |
| Zero-day        | Ainda não conhecida publicamente nem pelo fabricante.                         |
| CVE             | Registro formal de vulnerabilidade publicado publicamente.                    |
| Misconfiguração | Falhas de configuração, como permissões abertas ou autenticação desabilitada. |

### 4.3. Ciclo de Vida

1. **Identificação** (scanner: Nessus, OpenVAS);
2. **Avaliação** (classifica por CVSS);
3. **Correção** (patch, mitigacão);
4. **Validação** (teste de eficiência);
5. **Monitoramento** (SIEM, auditoria, logs).

---

## 5. Ferramentas e Tecnologias

| Tecnologia           | Função principal                                                                 |
| -------------------- | -------------------------------------------------------------------------------- |
| Firewall             | Bloqueio e liberação de tráfego por regras.                                      |
| WAF                  | Proteção de aplicações web contra XSS, SQLi, etc.                                |
| IDS                  | Detecta ataques, mas não bloqueia.                                               |
| IPS                  | Detecta e bloqueia automaticamente.                                              |
| EDR                  | Detecta, analisa e responde ameaças em endpoints.                                |
| SIEM                 | Centraliza logs e eventos, correlaciona incidentes.                              |
| VPN                  | Cria túnel criptografado para conexão remota segura.                             |
| Failover             | Redireciona para recurso de backup automaticamente em caso de falha.             |
| Alta disponibilidade | Conjunto de técnicas que garantem operação mesmo com falhas parciais do sistema. |

---

## 6. Controles de Segurança

| Tipo       | Objetivo                              | Exemplos                                             |
| ---------- | ------------------------------------- | ---------------------------------------------------- |
| Preventivo | Impedir que ocorra um incidente.      | Políticas, firewall, autenticação multifator.        |
| Detectivo  | Identificar atividades suspeitas.     | IDS, SIEM, monitoramento de logs.                    |
| Corretivo  | Restaurar operação após um incidente. | Backup, failover, plano de recuperação de desastres. |

**Categorias:**

* **Físicos:** câmeras, acesso com crachá;
* **Lógicos:** criptografia, senhas fortes;
* **Administrativos:** políticas, treinamentos, normas.

---

## 7. Backup, Recuperação e Continuidade

| Conceito | Função                                                             |
| -------- | ------------------------------------------------------------------ |
| Backup   | Cópia periódica de dados. Pode ser local, em nuvem, SAN ou NAS.    |
| Restore  | Restauração dos dados após falha.                                  |
| SAN      | Rede de armazenamento dedicada e de alta performance.              |
| NAS      | Armazenamento conectado à rede, compartilhado em ambientes comuns. |
| PCN      | Plano para manter o funcionamento mínimo durante falhas.           |
| DRP      | Ações para recuperação total após desastre.                        |

---

## 8. Normas ISO Relacionadas

| Norma     | Finalidade                                           |
| --------- | ---------------------------------------------------- |
| ISO 27001 | Requisitos para SGSI.                                |
| ISO 27002 | Diretrizes para controles de segurança.              |
| ISO 27005 | Diretrizes para gestão de riscos.                    |
| ISO 27017 | Segurança em computação em nuvem.                    |
| ISO 27701 | Gestão da privacidade e dados pessoais (LGPD, GDPR). |

**Nota:** A ISO 27001 é a principal para certificações, enquanto a ISO 27005 trata de riscos e a 27017 aborda nuvem, cada vez mais cobradas em provas de concursos.
