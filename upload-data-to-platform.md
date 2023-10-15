
## Carregar informações para a plataforma

Todos os dispositivos que estão conectados à plataforma devem enviar obrigatoriamente os seguintes dados para o link apresentado abaixo no formato JSON:

```bash
  POST https://hub.wiot.pt/sensor?id_sensor=A1B2C3&key=A1b2C3d4
```

Por exemplo, no caso de se tratar de um dispositivo que recolha dados sobre energia (sistema trifásico), o código JSON deve seguir as seguintes normas:

```bash
  {
    "latitude": "31.123456",
    "longitude": "-8.23324234",
    "device": "A1B2C3",
    "time": "2023-05-15 15:30",
    "data": {
      "volt_1": 230,
      "volt_2": 235,
      "volt_3": 234,
      "amp_1": 2,
      "amp_2": 3,
      "amp_3": 23,
      ...
    }
  }
```

- Brevemente estarão disponíveis as formatações JSON para outro tipo de dispositivos.
- Caso se trate de um dispositivo com GPS, quando as coordenadas são enviadas elas sobrepõem-se às previamente configuradas quando se cria um dispositivo.
- Estes sistema apenas é serve para dispositivos tipo Arduino/ESP.

## 🕗 Periocidade
Todos os dados devem ser enviados com intervalos de 15 minutos.
