## 🛡️ Lab 01: Configuração Inicial e Hardening de Roteador
**Tópico da Certificação:** 1.0 Network Fundamentals & 5.0 Security Fundamentals

### 🎯 Objetivo do Laboratório
Configurar um roteador Cisco do zero, aplicando práticas de segurança de acesso (Hardening). O foco foi garantir acesso remoto criptografado (SSH), proteger o acesso físico (Console) e criar um banco de dados local para rastreabilidade, desativando protocolos sem segurança como o Telnet.

### 🛠️ Tecnologias e Configurações Aplicadas
* **Equipamento Utilizado:** Roteador 2911.
* **Criptografia:** Geração de chaves RSA (1024 bits) para suporte ao SSH.
* **Autenticação Local:** Criação de usuários com privilégios específicos (`username / secret`) atrelados ao comando `login local`.
* **Proteção Física e Remota:** Senhas blindadas (`enable secret`), bloqueio de Telnet (`transport input ssh`) e timeout de inatividade (`exec-timeout`).
* **Avisos Legais:** Configuração de Banner MOTD.

### 📝 Principais Comandos Executados
```bash
# Configuração de Domínio e Criptografia
ip domain-name provedordeinternet.com
crypto key generate rsa

# Banco de Dados Local e Senha Global
username admin privilege 15 secret [SENHA_OCULTA]
username jhonata privilege 1 secret [SENHA_OCULTA]
enable secret [SENHA_OCULTA]

# Hardening das Linhas VTY (SSH) e Console
line vty 0 4
 transport input ssh
 logging synchronous
 login local
 exec-timeout 2 0

line console 0
 login local
 logging synchronous
 exec-timeout 2 0
