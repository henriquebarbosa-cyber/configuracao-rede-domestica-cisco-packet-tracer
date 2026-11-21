# Configuração de Rede Doméstica no Cisco Packet Tracer

## 1. Sobre o projeto

Este projeto apresenta a montagem e configuração de uma rede doméstica utilizando o **Cisco Packet Tracer**, simulador de redes desenvolvido pela Cisco.

O objetivo é conectar dispositivos de uma residência por meio de conexões cabeadas e sem fio, configurando modem, roteador wireless, servidor DHCP e segurança da rede Wi-Fi.

O projeto também demonstra testes de conectividade entre os dispositivos e acesso a um servidor externo simulado.

## 2. Objetivos

- Realizar conexões utilizando cabos coaxiais e Ethernet.
- Conectar o Cable Modem ao Home Wireless Router.
- Configurar computadores para obter endereços IP automaticamente via DHCP.
- Acessar a interface gráfica do roteador.
- Alterar as credenciais administrativas padrão.
- Configurar a rede wireless com segurança WPA2.
- Conectar um laptop à rede Wi-Fi.
- Verificar a conectividade dos computadores com a Internet simulada.

## 3. Equipamentos utilizados

| Equipamento | Função |
|---|---|
| Cable Splitter | Dividir o sinal do cabo coaxial |
| Cable Modem | Fornecer conexão de rede ao roteador |
| Home Wireless Router | Gerenciar a rede doméstica cabeada e sem fio |
| TV | Receber o sinal de televisão |
| Office PC | Computador conectado por cabo |
| Bedroom PC | Computador conectado por cabo |
| Laptop | Dispositivo conectado via Wi-Fi |

**Software:** Cisco Packet Tracer.

---

# 4. Desenvolvimento do projeto

## ETAPA 1 — Conexão do cabo de televisão

Nesta etapa, foi realizada a conexão entre o divisor de cabo (Cable Splitter), o Cable Modem e a televisão.

### Procedimentos

1. Acesse **Network Components** e clique em **Connections** (ícone de raio).
2. Selecione o cabo coaxial, identificado pelo ícone azul em formato de zigue-zague.
3. Clique no Cable Splitter e selecione a porta `Coaxial1`.
4. Clique no Cable Modem e selecione a porta `Port 0`.
5. Repita o procedimento utilizando a porta `Coaxial2` do Cable Splitter e a porta `Port 0` da TV.
6. Clique na TV e altere o campo **Status** para **ON**.

Com as conexões realizadas corretamente, a televisão deverá exibir uma imagem representando um programa de TV.

### Evidências

![Conexão do cabo coaxial](images/01-conexao-tv.PNG)

*Figura 1 — Conexão entre o divisor de cabo e os dispositivos.*

![TV funcionando](images/01.1-tv-funcionando.PNG)

*Figura 2 — Televisão funcionando após a conexão.*

---

## ETAPA 2 — Conexão do modem e do roteador wireless

Nesta etapa, foi realizada a conexão entre o Cable Modem, o Home Wireless Router e os computadores da residência.

### Procedimentos

1. Acesse **Connections** e selecione o cabo **Copper Straight-Through**, identificado por uma linha preta sólida.
2. Conecte a porta `Port 1` do Cable Modem à porta `Internet` do Home Wireless Router.
3. Selecione o Office PC e conecte a porta `FastEthernet0` ao roteador, utilizando a porta `GigabitEthernet 1`.
4. Repita o procedimento para o Bedroom PC, utilizando a porta `FastEthernet0` do computador e a porta `GigabitEthernet 2` do roteador.

### Evidências

![Conexão do modem e roteador](images/02-cabo-modem-home-wireless.PNG)

*Figura 3 — Conexão entre Cable Modem e Home Wireless Router.*

![Conexão do PC do quarto](images/02.1-pc-quarto.PNG)

*Figura 4 — Conexão cabeada do computador do quarto.*

---

## ETAPA 3 — Configuração do roteador e do DHCP

Nesta etapa, foi realizada a configuração inicial do roteador wireless, incluindo o acesso à interface administrativa, a configuração do DHCP e a alteração das credenciais de administração.

### 3.1. Acessando a interface do roteador

1. Clique no **Office PC**.
2. Acesse a guia **Desktop**.
3. Abra **IP Configuration**.
4. Selecione a opção **DHCP**.
5. Aguarde a obtenção automática das configurações de rede.

O computador deverá receber um endereço IPv4 iniciado por `192`.

Caso a configuração demore, utilize a opção **Fast Forward Time**, localizada abaixo da topologia de rede.

6. Anote o endereço do **Default Gateway**, que corresponde ao endereço IP do Home Wireless Router.
7. Feche a janela IP Configuration.
8. Abra o aplicativo **Web Browser**.
9. Digite o endereço IP do gateway padrão no campo URL e clique em **Go**.
10. Na tela de autenticação, utilize as credenciais padrão do laboratório:

- Usuário: `admin`
- Senha: `admin`

Após a autenticação, será exibida a interface gráfica de configuração do roteador.

### Evidência

![Configuração DHCP](images/03-configuracao-dhcp.PNG)

*Figura 5 — Configuração automática de IP por DHCP.*

![Acesso ao roteador](images/03.1-acesso-roteador.PNG)

*Figura 6 — Acesso à interface administrativa do roteador.*

### 3.2. Configurando o limite de usuários DHCP

O objetivo é limitar a quantidade de dispositivos que poderão receber endereços IP automaticamente.

1. Na interface do roteador, permaneça na guia **Setup**.
2. Localize a seção **Network Setup**.
3. Encontre o campo **Maximum Number of Users**.
4. Altere o valor para `10`.
5. Role a página até o final.
6. Clique em **Save Settings**.

Essa configuração limita a quantidade de endereços disponibilizados pelo servidor DHCP para os dispositivos conectados à rede.

### Evidência

![Limite de usuários](images/03.2-limite-usuarios.PNG)

*Figura 7 — Configuração do limite máximo de 10 usuários.*

### 3.3. Alterando a senha administrativa

Por segurança, é importante substituir as credenciais padrão do roteador.

1. Acesse a guia **Administration**.
2. Localize os campos de senha administrativa.
3. Defina uma nova senha.
4. Confirme a nova senha.
5. Clique em **Save Settings**.

**Atenção:** a senha utilizada durante o laboratório não deve ser publicada no GitHub. Utilize uma senha de teste e mantenha credenciais reais sempre privadas.

### Evidência

![Configuração de senha](images/03.3-configuracao-senha.PNG)

*Figura 8 — Alteração das credenciais administrativas.*

---

## ETAPA 4 — Configuração da rede Wi-Fi e segurança WPA2

Nesta etapa, foi configurada a rede wireless e realizada a conexão do laptop.

### 4.1. Configurando a rede sem fio

No Home Wireless Router, acesse as configurações wireless e defina:

- Nome da rede (SSID): nome de sua preferência.
- Modo de segurança: WPA2.
- Tipo de criptografia: conforme disponibilizado pelo roteador.
- Senha da rede: defina uma senha segura para o laboratório.

Salve as configurações utilizando **Save Settings**.

### Evidência

![Configuração Wi-Fi](images/04-configuracao-wifi.PNG)

*Figura 9 — Configuração da rede sem fio.*

### 4.2. Configurando a segurança WPA2

1. Acesse as configurações de segurança wireless.
2. Selecione o protocolo WPA2-PSK, caso disponível.
3. Defina a chave pré-compartilhada (Pre-Shared Key).
4. Salve as alterações.

O WPA2 protege a comunicação entre os dispositivos conectados à rede sem fio, exigindo uma senha para autenticação.

### Evidência

![Configuração WPA2](images/04.1-configuracao-wpa2.PNG)

*Figura 10 — Configuração de segurança WPA2.*

### 4.3. Conectando o laptop à rede Wi-Fi

1. Clique no **Laptop** localizado na sala de estar.
2. Acesse a guia **Desktop**.
3. Abra o aplicativo **PC Wireless**.
4. Entre na guia **Connect**.
5. Aguarde a identificação das redes wireless disponíveis.
6. Selecione o SSID configurado anteriormente.
7. Clique em **Connect**.
8. Digite a senha configurada no campo **Pre-shared Key**.
9. Clique novamente em **Connect**.
10. Acesse a guia **Link Information**.

A conexão será realizada corretamente quando aparecer a mensagem:

`You have successfully connected to the access point`

Clique em **More Information** para visualizar os detalhes da conexão.

Caso o endereço IP não comece com `192`, utilize **Fast Forward Time** para acelerar a simulação.

### Evidências

![Configuração Wi-Fi](images/04-configuracao-wifi.PNG)

*Figura 11 — Seleção da rede wireless.*

![Conexão Wi-Fi estabelecida](images/04.2-conexao-wifi-sucesso.PNG)

*Figura 12 — Laptop conectado com sucesso ao ponto de acesso.*

### 4.4. Testando o acesso à Internet simulada

1. Feche o aplicativo **PC Wireless**.
2. Abra o **Web Browser**.
3. Acesse o endereço:

`skillsforall.srv`

4. Aguarde o carregamento da página.
5. Utilize **Fast Forward Time** caso necessário.

O carregamento da página demonstra que o laptop possui conectividade com o servidor externo simulado no Packet Tracer.

---

## ETAPA 5 — Configuração do Bedroom PC e testes finais

Nesta etapa, foi realizada a configuração do segundo computador da residência e a verificação da conectividade.

### 5.1. Configurando o Bedroom PC

1. Clique no **Bedroom PC**.
2. Acesse a guia **Desktop**.
3. Abra **IP Configuration**.
4. Selecione **DHCP**.
5. Aguarde a atribuição automática do endereço IP.

Verifique se o endereço IPv4 recebido começa com `192`.

### Evidência

![Bedroom PC configurado](images/05.1-pc-quarto.PNG)

*Figura 13 — Configuração DHCP do computador do quarto.*

### 5.2. Testando a conectividade

1. Feche a janela **IP Configuration**.
2. Abra o aplicativo **Web Browser**.
3. Digite o endereço:

`skillsforall.srv`

4. Aguarde o carregamento da página.
5. Utilize **Fast Forward Time** caso necessário.

O acesso ao servidor confirma a conectividade do Bedroom PC com a rede simulada.

### Evidência

![Office PC funcionando](images/05-office-pc-ok.PNG)

*Figura 14 — Teste de conectividade do Office PC.*

---

# 5. Resultados obtidos

Ao finalizar as configurações, a rede doméstica apresentou os seguintes resultados esperados:

- Conexão do Cable Splitter com o Cable Modem e a TV.
- Funcionamento da televisão após a conexão coaxial.
- Comunicação entre o Cable Modem e o Home Wireless Router.
- Conexão cabeada dos computadores ao roteador.
- Configuração automática de endereços IP por DHCP.
- Limitação do DHCP para até 10 usuários.
- Alteração das credenciais administrativas do roteador.
- Configuração da rede wireless com segurança WPA2.
- Conexão do laptop à rede Wi-Fi.
- Testes de acesso ao servidor `skillsforall.srv`.

# 6. Conclusão

A realização deste projeto permitiu colocar em prática conceitos fundamentais de redes de computadores, utilizando o Cisco Packet Tracer como ambiente de simulação.

Foram desenvolvidas atividades envolvendo cabeamento coaxial, conexões Ethernet, configuração de roteadores, endereçamento IPv4, DHCP, segurança wireless e testes de conectividade.

O laboratório demonstrou como diferentes dispositivos podem ser integrados em uma rede doméstica, permitindo comunicação entre equipamentos cabeados e sem fio.

**Projeto concluído com sucesso!**

---

## 7. Tecnologias e conceitos utilizados

- Cisco Packet Tracer
- Redes de computadores
- LAN (Local Area Network)
- WLAN (Wireless Local Area Network)
- IPv4
- DHCP
- Cable Modem
- Home Wireless Router
- Ethernet
- Cabo coaxial
- Wi-Fi
- WPA2-PSK
- Conectividade de rede

## 8. Arquivo do projeto

O arquivo original do Cisco Packet Tracer poderá ser disponibilizado na pasta `projeto/`, permitindo que outros usuários abram a topologia e reproduzam as configurações.

**Formato:** `.pkt`

