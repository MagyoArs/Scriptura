# Redes de Computadores

## 1. Conceito e Importância

Rede de computadores é o **conjunto de dispositivos interligados** que compartilham recursos (arquivos, impressoras, internet, etc.). Seu objetivo é **permitir a comunicação e a troca de dados** entre sistemas, otimizando processos e facilitando a conectividade.

**Exemplos de uso:** redes locais em empresas, internet residencial, redes sem fio públicas.

---

## 2. Tipos de Redes

| Tipo | Abrangência                      | Exemplo                                   |
| ---- | -------------------------------- | ----------------------------------------- |
| PAN  | Pessoal (até alguns metros)      | Bluetooth entre celular e smartwatch      |
| LAN  | Local (mesma residência/empresa) | Rede cabeada de um escritório             |
| MAN  | Metropolitana (cidade ou campus) | Rede da prefeitura ou de uma universidade |
| WAN  | Ampla (regiões, países)          | Internet (interligação de redes globais)  |

---

## 3. Arquiteturas de Rede

### 3.1. Modelo OSI (ISO)

Divisão em 7 camadas para padronizar a comunicação de redes.

| Camada (de cima p/ baixo) | Função Principal                         | Exemplo                        |
| ------------------------- | ---------------------------------------- | ------------------------------ |
| 7. Aplicação              | Interface com o usuário                  | HTTP, FTP, SMTP                |
| 6. Apresentação           | Codificação, criptografia                | SSL, ASCII, JPEG               |
| 5. Sessão                 | Gerencia sessões (início, controle, fim) | RPC, NetBIOS                   |
| 4. Transporte             | Controle de fluxo e erros                | TCP, UDP                       |
| 3. Rede                   | Roteamento e endereçamento               | IP, ICMP                       |
| 2. Enlace                 | Comunicação entre nós na mesma rede      | Ethernet, MAC                  |
| 1. Física                 | Transmissão de bits (meio físico)        | Cabos, sinais elétricos, Wi-Fi |

### 3.2. Modelo TCP/IP

Modelo prático de 4 camadas usado na internet.

| Camada TCP/IP | Correspondente OSI              | Protocolos                 |
| ------------- | ------------------------------- | -------------------------- |
| Aplicação     | Aplicação, Apresentação, Sessão | HTTP, SMTP, FTP, DNS, DHCP |
| Transporte    | Transporte                      | TCP, UDP                   |
| Internet      | Rede                            | IP, ICMP, ARP              |
| Acesso à Rede | Enlace + Física                 | Ethernet, Wi-Fi            |

---

## 4. Equipamentos de Rede

| Dispositivo  | Função Principal                                             | Camada (Modelo OSI) |
| ------------ | ------------------------------------------------------------ | ------------------- |
| Hub          | Repassa sinal para todas as portas (sem inteligência)        | Camada 1 (Física)   |
| Switch       | Encaminha dados com base no MAC (com inteligência local)     | Camada 2 (Enlace)   |
| Roteador     | Interliga redes distintas e define rotas com base no IP      | Camada 3 (Rede)     |
| Modem        | Converte sinais digitais ↔ analógicos para acesso à internet | Camada 1 (Física)   |
| Access Point | Distribui sinal Wi-Fi (rede sem fio)                         | Camada 2            |
| Firewall     | Controla o tráfego com base em regras                        | Camadas 3 e 4       |

---

## 5. Endereçamento IP

### 5.1. IPv4

Endereço de 32 bits dividido em 4 octetos (ex: 192.168.0.1)

| Classe | Intervalo                   | Uso                              |
| ------ | --------------------------- | -------------------------------- |
| A      | 1.0.0.0 a 126.255.255.255   | Grandes redes (empresas globais) |
| B      | 128.0.0.0 a 191.255.255.255 | Redes médias (universidades)     |
| C      | 192.0.0.0 a 223.255.255.255 | Pequenas redes                   |

* IPs **privados** (não roteáveis na internet):

  * A: 10.0.0.0/8
  * B: 172.16.0.0 – 172.31.255.255
  * C: 192.168.0.0/16

### 5.2. IPv6

Endereço de 128 bits (ex: `2001:0db8:85a3::8a2e:0370:7334`). Suporta número muito maior de dispositivos.

**Vantagens:**

* Não requer NAT.
* Segurança embutida (IPsec).
* Mais eficiente para roteamento.

---

## 6. Protocolos Importantes

| Protocolo | Função                                | Porta Padrão      |
| --------- | ------------------------------------- | ----------------- |
| HTTP      | Transferência de páginas web          | 80                |
| HTTPS     | HTTP com criptografia TLS/SSL         | 443               |
| FTP       | Transferência de arquivos             | 21                |
| SMTP      | Envio de e-mails                      | 25                |
| DNS       | Resolve nomes para IPs                | 53                |
| DHCP      | Atribuição automática de IPs          | 67/68             |
| SSH       | Acesso remoto seguro                  | 22                |
| Telnet    | Acesso remoto sem criptografia        | 23                |
| SNMP      | Gerenciamento de dispositivos de rede | 161               |
| ICMP      | Diagnóstico e testes de conectividade | - (não usa porta) |

---

## 7. Endereçamento MAC e ARP

* **MAC Address:** identificador físico de 48 bits da placa de rede (ex: `00:1A:2B:3C:4D:5E`)
* **ARP (Address Resolution Protocol):** resolve IPs em endereços MAC na rede local.

---

## 8. Comutação e Roteamento

| Conceito   | Definição                                                    |
| ---------- | ------------------------------------------------------------ |
| Comutação  | Movimento de dados dentro da mesma rede local (usando MAC)   |
| Roteamento | Encaminhamento de pacotes entre redes diferentes (usando IP) |

---

## 9. Segurança em Redes

| Risco        | Medida de Proteção                       |
| ------------ | ---------------------------------------- |
| Sniffing     | Criptografia (TLS, VPN)                  |
| ARP Spoofing | Detecção de MAC duplicado, DHCP snooping |
| MITM         | TLS, certificados, firewall              |
| Ataques DDoS | Firewalls, IDS/IPS, filtrar tráfego      |

---

## 10. Sub-redes e Máscara de Sub-rede

Máscara define qual parte do IP é **rede** e qual é **host**.

**Exemplo:**
IP: 192.168.1.10
Máscara: 255.255.255.0 → 192.168.1 é a rede; 10 é o host

**CIDR:** notação compacta

* `/24` equivale a `255.255.255.0`
* `/16` equivale a `255.255.0.0`

---

## 11. Comandos de Diagnóstico

| Comando    | Finalidade                             |
| ---------- | -------------------------------------- |
| ping       | Testa conectividade entre hosts        |
| traceroute | Exibe o caminho percorrido por pacotes |
| nslookup   | Consulta registros DNS                 |
| ipconfig   | Exibe configurações IP no Windows      |
| ifconfig   | Exibe configurações IP no Linux/macOS  |
| netstat    | Exibe conexões ativas e portas abertas |

