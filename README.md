# tydom2mqtt
Link between a Delta Dore's Tydom Hub and and a MQTT broker, unofficial of course.


Credit : 
 - WiwiWillou/tydom2mqtt who created the mqtt interface.
 - https://github.com/cth35/tydom_python who reverse tydom


configuration : 
```
sensor: 
  - platform: Tydom2MQTT
    tydomMAC: "" # MAC address of your tydom
    tydomIP: ""  # IP address of your tydom
    tydomPassword: "" #Tydom password
    mqttIP: ""        # MQTT broker
    mqttPort: 1883
```
AND 
```
mqtt:
  broker: 172.18.1.18
  discovery: true
  discovery_prefix: homeassistant

```

The plugin is :
 - HACS compatible ( easy installation, easy update ) 
 - all configurations are stored in hass 
 - auto install depedencies
 
 
 TODO : 
  - handle errors


BONUS : 
Mosquitto installation ( mqtt broker) : 
```
    mosquitto:
        container_name: mqtt
        volumes:
            - '/home/docker/mqtt/config:/mqtt/config:ro'
            - '/home/docker/mqtt/log:/mqtt/log'
            - '/home/docker/mqtt/data/:/mqtt/data/'
        ports:
            - '1883:1883'
        image: toke/mosquitto
        networks:
          static-network:
            ipv4_address:  172.18.1.18
```
