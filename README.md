# Projeto_CAR
Arquivos do projeto Carrinho Bluetooth e também do Segue Faixa

# DICA 01: 
## Para usar o módulo bluetooth HC-05 no Arduino UNO R3 com biblioteca <SoftwareSerial.h>

🧩 1️⃣ Confirme se o módulo está em modo AT completo
O HC‑05 trabalha em dois modos AT diferentes, dependendo de como ele entra em modo de configuração:

Tipo de modo AT	Como entra	Baud típico	Limitações
Modo AT “completo”	Pino KEY (ou EN) em HIGH antes de energizar	38 400 bps	Permite mudar nome, senha, UART, etc.
Modo AT “reduzido”	Pino KEY ativado após ligado (ou só com botão)	9 600 bps	Só aceita poucos comandos (como AT, AT+VERSION)
➡ Você precisa usar o modo AT completo, onde o LED pisca bem devagar (1x a cada 2 s), e a comunicação está em 38 400 bps.

Se o LED continua piscando rápido, o nome não é realmente salvo.

🧩 2️⃣ Desemparelhe o módulo do telefone
Após mudar o nome, o celular pode continuar mostrando o nome antigo por causa do cache Bluetooth.

No smartphone:

Vá em Configurações → Bluetooth
Encontre o dispositivo HC-05
Escolha “Esquecer” ou “Desemparelhar”
Desligue e ligue o Bluetooth do celular
Faça uma nova busca
Agora o novo nome deve aparecer como CARRINHO_01 (ou o que você definiu).

### Veja exemplo do teste PARA MUDAR NOME DO DISPOSITIVO BLUETOOTH VIA COMANDOS AT: 
![Muda_Nome_BT](https://github.com/igarashimassaki/Projeto_CAR/blob/main/teste_ComandoAT_BTSerial_(RX%3D10_TX%3D11).png)
