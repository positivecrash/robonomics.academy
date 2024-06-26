---
title: "Robonomics School 2024 / Manual de reubicación de Chipre: Hogar Inteligente"
lastUpdate: 
description: "Manual de reubicación de Chipre: Hogar Inteligente"
metaOptions: [Aprender, "Robonomics School 2024 / Manual de reubicación de Chipre: Hogar Inteligente"]
defaultName: "Robonomics School 2024 / Cyprus Relocant Manual: Smart Home"
---

<LessonImages imageClasses="mb"  src='school-2024-cyprus-relocant-manual/Setup_SmartHome-Academy.jpg' alt="Cyprus Relocant Manual Cover" />

Cambiar de país de residencia siempre trae no solo nuevas oportunidades, sino también desafíos. Sucedió que en mi caso, el nuevo país fue Chipre, donde vine a construir una empresa. Durante los últimos 10 años antes de mudarme, viví en una gran ciudad, donde me acostumbré a ciertos beneficios en forma de calefacción central de la ciudad, suministro de agua caliente y electricidad barata. En Chipre, cada casa y cada apartamento son mucho más autónomos en términos de soporte de vida, pero las preocupaciones sobre mantener una vida cómoda recaen en el propietario. Tome el agua caliente, por ejemplo. En los meses fríos, tienes que encender la caldera tú mismo para calentarla. El apartamento también necesita ser calentado por ti mismo. En invierno encendemos/apagamos la manta térmica y la caldera, y en verano el aire acondicionado y el repelente de mosquitos. Esto requiere no solo tiempo y energía, sino también dinero.

Mi primer invierno en Chipre resultó en facturas de electricidad astronómicas. Esto fue un golpe serio para mi presupuesto. Una posible solución: cambiar tus hábitos y adaptarte a las nuevas condiciones. Pero después de mudarte, ya tendrás suficientes preocupaciones. Como ingeniero, comencé a buscar soluciones que me ayudaran a controlar los costos y hacer mi vida más cómoda, y quiero compartir mi experiencia contigo.

## Elección de Hardware

Lo primero con lo que quiero empezar es eligiendo un ecosistema. Los sistemas cableados se eliminan de inmediato, ya que requieren grandes presupuestos y una intervención seria en la infraestructura del apartamento/casa. De los dispositivos inalámbricos, hay una gran cantidad de dispositivos bajo las marcas Sonoff y Tyua, pero todos funcionan a través de Internet, lo que no siempre funciona de manera confiable en la isla. Sin mencionar el problema de la privacidad y seguridad de tus datos personales en los servidores de otras compañías. Recomiendo construir tu hogar inteligente con [Home Assistant](https://www.home-assistant.io) como servidor principal. Pros: puede funcionar sin acceso a Internet externo; es posible llevarlo contigo al mudarte y desplegarlo en un nuevo lugar sin perder la configuración; admite una gran cantidad de dispositivos, incluidos televisores inteligentes, aspiradoras y mucho más.

Los protocolos más populares para la conexión inalámbrica de dispositivos son Wi-Fi, Zigbee, Bluetooth. En un apartamento, los tres tipos de conexiones pueden encontrarse a la vez, pero en cuanto a los dispositivos que convierten cosas comunes en cosas inteligentes, es más conveniente trabajar con el protocolo Zigbee. En este caso, no necesitamos preocuparnos por sus direcciones y área de cobertura, además pueden funcionar con baterías. Los dispositivos Wi-Fi requieren una conexión constante a la energía y dependen de la fuerza de la señal Wi-Fi. Incluso en un pequeño apartamento, donde hay un par de paredes entre el enrutador y tu dormitorio, a veces tienes que instalar un extensor de Wi-Fi. En el caso de Zigbee, los propios dispositivos actúan como repetidores.

Volviendo a Chipre, mi mínimo requerido de dispositivos resultó ser el siguiente:

## Computadora - Servidor doméstico

La tarea definitiva para el servidor es servir a un hogar inteligente controlado por Home Assistant. La forma más fácil es tomar el [Home Assistant Green](https://www.home-assistant.io/green/) ya preconfigurado. Costo [€70 sin impuestos](https://thepihut.com/products/home-assistant-green).

<LessonImages src="school-2024-cyprus-relocant-manual/home-assistant-green.png" alt="Home Assistant green"/>

La opción es un poco más avanzada, pero incluso puedes tener control sobre el sistema operativo, esto es encontrar/comprar una [Raspberry Pi](https://www.raspberrypi.com). Costo [€90 sin impuestos](https://https://thepihut.com/products/raspberry-pi-5-starter-kit). La página de [Instalación](https://www.home-assistant.io/installation/) tiene muchas opciones para todos los gustos.

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/raspberry-pi.png" alt="Raspberry Pi"/>

Como Coordinador Zigbee tomamos el [Sonoff Zigbee Dongle P o E](https://sonoff.tech/product/gateway-and-sensors/sonoff-zigbee-3-0-usb-dongle-plus-p/), que prácticamente siempre están disponibles en la isla. Costo aproximado [€35](https://www.amazon.de/-/en/dp/B09KXTCMSC/). También puedes elegir un stick de [esta lista](https://www.zigbee2mqtt.io/guide/adapters/).

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/sonoff-zigbee-stick.png" alt="Sonoff Zigbee USB Stick"/>

Recomiendo encarecidamente asignar una dirección IP local estática para tu servidor doméstico. Si no es posible acceder a la configuración del enrutador, entonces puedes instalar adicionalmente un segundo enrutador (yo tengo [MikroTik](https://mikrotik.com/product/hap_ax2), aproximadamente [€80](https://www.mstronics.com/c/337_1345_485/networking-devices-routers.html?filter_id=154)), y configurar Internet en él. Y en general, es mejor asignar una IP estática a todos los dispositivos inteligentes Wi-Fi. A menudo es importante para que las integraciones de Home Assistant funcionen correctamente.

## Interruptor de caldera

La caldera consume 3-3.5 kWh y un interruptor inteligente regular no funcionará. Al elegir, asegúrese de prestar atención a la corriente permitida; debe ser al menos de 16A, y de preferencia 20A. Es difícil encontrar rápidamente un interruptor Zigbee en la isla misma, lo pedí desde [China](https://vi.aliexpress.com/item/1005006833309900.html), costó alrededor de €20.

<robo-academy-grid :columns="2" textAlign="center">
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-dimension.png" alt="Boiler Switch"/>
    </robo-academy-grid-element>
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-wiring.png" alt="Boiler Switch Wiring"/>
    </robo-academy-grid-element/>
</robo-academy-grid>

La primera y más importante automatización es apagar el botón N minutos después de cualquier activación. Lo configuramos y ya no pensamos si olvidaste apagar el botón o si ha estado funcionando durante el tercer día. Un ejemplo de automatización para Home Assistant, necesitas reemplazarlo con tu `device_id` y `entity_id`:

<LessonCodeWrapper language="yaml" noCopyIcon>
    alias: Boiler turn off after 30 min
    description: ""
    trigger:
    - platform: device
        type: turned_on
        device_id: a7ee4b26ec5b9e36d959f7b4b8490c42
        entity_id: 61230c7b5528330e3b60ee38c5fe1f12
        domain: switch
        for:
        hours: 0
        minutes: 30
        seconds: 0
    condition: []
    action:
    - type: turn_off
        device_id: a7ee4b26ec5b9e36d959f7b4b8490c42
        entity_id: 61230c7b5528330e3b60ee38c5fe1f12
        domain: switch
    mode: single
</LessonCodeWrapper>

Puedes cambiar el tiempo a lo largo del año. Por ejemplo, en febrero necesito calentar el agua durante una hora, y en abril 30 minutos son suficientes. Algo útil es agregar el envío de una notificación a tu teléfono cuando el agua esté caliente.

<robo-academy-note type="note" title="Homework">
  Realice una automatización que apague la caldera después de X minutos específicos. Para establecer el tiempo como variable, consulte <a href="https://www.home-assistant.io/integrations/input_number/">esta integración</a>
</robo-academy-note>

## Controles remotos IR para aires acondicionados y TV

Los controles remotos vienen con conexión Wi-Fi (requieren alimentación constante) y conexión Zigbee (funcionan con batería).

La opción de Wi-Fi que probé fue del fabricante [Broadlink](https://www.ibroadlink.com/productinfo/762674.html), comprado en [Amazon](https://www.amazon.de/-/en/dp/B07ZSG9Y67/), alrededor de €30. Para la configuración inicial, deberás instalar su aplicación en tu teléfono y crear una cuenta, pero después de eso el control remoto IR funcionará en la red local, la conexión a HA se realiza utilizando la [integración](https://www.home-assistant.io/integrations/broadlink/). Para personalizar aún más el control remoto para que se adapte a tus necesidades, te recomiendo que mires el repositorio [SmartIR](https://github.com/smartHomeHub/SmartIR) - esta es una gran biblioteca de comandos listos para diferentes aires acondicionados y TVs.

<robo-academy-note type="note" title="Consejo">
  Si no encuentras tu modelo específico de A/C, prueba con otros modelos del mismo fabricante. Probablemente los comandos sean los mismos y podrás conectar tu A/C.
</robo-academy-note>

<LessonImages src="school-2024-cyprus-relocant-manual/broadlink-ir.png" alt="Broadlink IR Remote Control"/>

Ejemplo de configuración para Broadlink IR Remote:

<LessonCodeWrapper language="yaml" noCopyIcon>
    climate:
    - platform: smartir
        name: Living Room AC
        unique_id: living_room_ac
        device_code: 1390
        controller_data: remote.living_room_ir_remote_control
        temperature_sensor: sensor.0xa4c138b6ad623598_temperature
        humidity_sensor: sensor.0xa4c138b6ad623598_humidity 
</LessonCodeWrapper>

Los controles remotos que funcionan con Zigbee no requieren una conexión constante a la energía, sino que funcionan con baterías. Por un lado, esto es una ventaja, porque puedes colocar el dispositivo en cualquier lugar conveniente de la habitación. Por otro lado, las baterías deberán cambiarse según sea necesario. El proceso de configuración para estos controles remotos también puede diferir de Broadlink. Si no puedes usar la biblioteca SmartIR, el control remoto deberá ser entrenado para cada comando por separado y guardado en la configuración de Home Assistant.

Los controles remotos programables son muy fáciles de instalar y configurar; no requieren montaje en la pared ni conexión a un bus de aire acondicionado. Sin embargo, hay una ligera limitación debido a la falta de retroalimentación entre dispositivos. No podemos verificar que el aire acondicionado se haya encendido y esté ejecutando exactamente el comando que enviamos. Sin embargo, lo hacemos rápidamente y sin dañar el apartamento. Para dar un poco más de información al control remoto, puedes instalar cualquier sensor de temperatura y humedad Zigbee, por ejemplo [este](https://vi.aliexpress.com/item/1005005595631552.html) por €10, y vincular las lecturas al control remoto. De esta manera tenemos una retroalimentación simple, y el número de escenarios interesantes aumenta.

## Medidor de Energía

Existen medidores semi-invasivos para el consumo de electricidad, como el que se muestra en la imagen a continuación:

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/energy-meter.png" alt="Energy Meter"/>

Deben ser alimentados aplicando L y N a la entrada. Por otro lado, un anillo de inducción está conectado al medidor, que colgamos en una fase o línea de consumo para la medición. La mayoría de las casas y apartamentos tienen 3 fases, lo que significa que necesitas instalar 3 de estos módulos. Lo compré en [Amazon](https://www.amazon.de/gp/product/B0C37DJXVD/) por €60, uno para cada fase. Las casas más antiguas pueden tener solo una fase.

## Conclusión

Para mí, un hogar inteligente no es un lujo, sino una necesidad. Es un lugar donde quiero relajarme y pasar tiempo con mi familia, sin desperdiciar energía resolviendo problemas cotidianos. ¡El costo del kit anterior en mi caso fue de aproximadamente €500 y un par de tardes. ¡El resultado es invaluable!