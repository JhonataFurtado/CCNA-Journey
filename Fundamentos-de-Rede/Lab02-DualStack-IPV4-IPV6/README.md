## 🌐 Lab 02: Infraestrutura Dual-Stack (IPv4 e IPv6)
**Tópico da Certificação:** 1.0 Network Fundamentals

### 🎯 Objetivo do Laboratório
Implementar uma rede que opere no **Dual-Stack**, para permitir que os dispositivos finais se comuniquem simultaneamente através dos protocolos IPv4 e IPv6. O foco foi a ativação do roteamento IPv6 no equipamento Cisco.

### 🛠️ Tecnologias e Configurações Aplicadas
* **Equipamentos Utilizados:** Roteador Cisco 2911 e Switch Cisco 2960.
* **Roteamento IPv6:** Ativação global do processamento de tráfego IPv6 (`ipv6 unicast-routing`).
* **Endereçamento L3:** Configuração de IPs nas interfaces atuando como Default Gateway para o IPV4 e IPV6.
* **Validação End-to-End:** Testes de conectividade (ICMP) bem-sucedidos em ambas as versões de IP.

### 📝 Principais Comandos Executados
```bash
# Ativação Global do IPv6
R1-DualStack(config)# ipv6 unicast-routing

# Configuração da Interface (Dual-Stack)
R1-DualStack(config)# interface gigabitEthernet 0/0
R1-DualStack(config-if)# ip address 192.168.1.1 255.255.255.0
R1-DualStack(config-if)# ipv6 address 2001:db8:acad:1::1/64
R1-DualStack(config-if)# no shutdown
```

### 📸 Validação e Testes
