# Projeto: Controle de LED e Leitura de Luminosidade com ESP32 via MQTT e Azure

## Descrição

Este projeto utiliza um ESP32 para controlar o LED onboard, além de ler o valor de luminosidade de um sensor e publicar o valor em um tópico MQTT. A comunicação é feita via Wi-Fi e o status do LED, bem como os dados de luminosidade, são enviados para um broker MQTT, possibilitando a integração com a plataforma FIWARE.

## Autor(es)

- **Fábio Henrique Cabrini** - Autor original
- **Lucas Demetrius Augusto** - Revisão e melhorias para leitura de luminosidade
- **Fábio Henrique Cabrini** - Revisões adicionais e ajustes para funcionamento no FIWARE Descomplicado

## Resumo

O programa permite ligar e desligar o LED onboard do ESP32, além de publicar o estado atual do LED e o valor da luminosidade em tópicos específicos do broker MQTT, que é integrado ao FIWARE Descomplicado.

## Funcionalidades

- Conexão com a rede Wi-Fi e broker MQTT.
- Controle do LED onboard via comandos MQTT.
- Publicação do estado do LED em um tópico MQTT.
- Leitura de luminosidade e publicação do valor em um tópico MQTT.

## Requisitos

- **Placa ESP32**
- **Sensor de luminosidade**
- **Broker MQTT (endereço IP: 191.232.165.99)**
- **Rede Wi-Fi**
- **Microsoft Azure** (opcional, dependendo do cenário de integração)
- **Postman** (para teste de requisições MQTT via API)

## Instalação

1. **Clone este repositório:**

   ```bash
   https://github.com/fernmoraes/SmartLamp.git
   ```

2. **Configure o ambiente:**
   - Abra o código no Arduino IDE ou na sua IDE preferida.
   - Instale as bibliotecas necessárias: `WiFi.h` e `PubSubClient.h`.
   - Ajuste as configurações de rede e MQTT no código (SSID, senha, IP do broker, etc.).

3. **Realize a conexão:**
   - Conecte o ESP32 ao seu computador e faça o upload do código.
   - Certifique-se de que o ESP32 se conecta corretamente ao Wi-Fi e ao broker MQTT.

## Configuração do Hardware

Conecte os pinos do sensor de luminosidade ao ESP32 conforme o diagrama abaixo:

- **VCC do sensor → 3.3V do ESP32**
- **GND do sensor → GND do ESP32**
- **OUT do sensor → Pino 34 do ESP32**

## Uso

1. **Controle do LED:**
   - Envie comandos MQTT para o tópico `/TEF/lampEmbrace02/cmd` para ligar (`lampEmbrace02@on|`) ou desligar (`lampEmbrace02@off|`) o LED onboard do ESP32.

2. **Leitura de luminosidade:**
   - O valor da luminosidade será publicado automaticamente no tópico `/TEF/lampEmbrace02/attrs/l`.

3. **Monitoramento:**
   - Utilize o Postman ou outro cliente MQTT para monitorar os tópicos e testar o envio e recebimento de mensagens.

## Revisões

- **Rev1 (26-08-2023):** Código portado para o ESP32 e adição da leitura de luminosidade.
- **Rev2 (28-08-2023):** Ajustes para compatibilidade com FIWARE Descomplicado.
- **Rev3 (01-11-2023):** Refinamento do código e melhorias no funcionamento com FIWARE Descomplicado.

## Alunos:

Fernando Navajas RM555080;  Henrique Botti RM556187;  José Guilherme Sipaúba; Costa RM557274; André Queiroz RM554503
