# Informe de Auditoría de Red Wi-Fi Insegura

## Introducción

En esta práctica se realizó un análisis básico de tráfico web utilizando las herramientas de desarrollador de Google Chrome.

El objetivo fue observar qué información puede visualizarse cuando un sitio utiliza HTTP y analizar los riesgos de utilizar este protocolo en una red Wi-Fi pública.

También se analiza cómo una VPN puede mejorar la seguridad mediante el cifrado y la creación de un túnel seguro para el tráfico.

---

## Sitio analizado

El sitio utilizado para la práctica fue:

http://neverssl.com/

Durante el análisis, la captura realizada desde la pestaña Network de Chrome mostró una solicitud al siguiente host:

`clearwonderfulshinyverse.neverssl.com`

La URL observada comenzaba con:

`http://clearwonderfulshinyverse.neverssl.com/online/`

Por lo tanto, la comunicación observada utilizó HTTP.

---

## Evidencia observada

Desde las herramientas de desarrollador del navegador se ingresó a:

**Network → Headers**

En la solicitud analizada se observaron los siguientes datos:

- Request URL: `http://clearwonderfulshinyverse.neverssl.com/online/`
- Request Method: `GET`
- Status Code: `200 OK`
- Remote Address: `34.223.124.45:80`
- Host: `clearwonderfulshinyverse.neverssl.com`
- Referer: `http://neverssl.com/`
- User-Agent
- Accept-Encoding
- Accept-Language
- Connection

El puerto observado fue el **80**, utilizado habitualmente para tráfico HTTP.

---

## 1. ¿Qué protocolo utiliza el sitio?

El sitio analizado utiliza **HTTP**.

Esto puede observarse porque la URL comienza con `http://` y la conexión observada utiliza el puerto 80.

HTTP no proporciona por sí mismo el cifrado de transporte que ofrece HTTPS mediante TLS.

---

## 2. ¿Qué información puede observarse durante la solicitud?

Durante la práctica fue posible observar diferentes datos relacionados con la solicitud HTTP.

Entre ellos:

1. El **Host** al que se realiza la solicitud.
2. La **URL** solicitada.
3. El método HTTP utilizado, en este caso **GET**.
4. Los **Headers** o encabezados.
5. Información del **User-Agent** del navegador.

Esto demuestra que una conexión HTTP puede exponer información de la comunicación que no está protegida mediante TLS.

---

## 3. ¿Qué riesgos existen al navegar mediante HTTP desde una red Wi-Fi pública?

Utilizar HTTP en una red Wi-Fi pública presenta riesgos porque la comunicación entre el navegador y el sitio no cuenta con la protección de HTTPS/TLS.

Un atacante que consiguiera interceptar tráfico de red podría intentar observar información transmitida sin cifrar.

Dependiendo del sitio y de los datos enviados, esto podría exponer URLs, encabezados, contenido enviado o recibido y otra información sensible transmitida mediante HTTP.

Además, una conexión HTTP no proporciona las mismas garantías de integridad y autenticación que HTTPS, por lo que existe mayor riesgo de manipulación del tráfico.

Por esta razón, no se deberían ingresar contraseñas, datos bancarios ni información personal sensible en sitios que utilicen únicamente HTTP.

---

## 4. ¿Cómo cambiaría este escenario utilizando una VPN?

Una **VPN (Virtual Private Network)** crea un **túnel cifrado** entre el dispositivo del usuario y el servidor VPN.

El tráfico es sometido a **cifrado** y **encapsulamiento** dentro de ese túnel antes de atravesar la red local.

Esto resulta especialmente útil en una red Wi-Fi pública porque dificulta que otras personas conectadas a esa red puedan inspeccionar directamente el contenido del tráfico entre el dispositivo y el servidor VPN.

La VPN aporta:

- **Cifrado** del tráfico entre el dispositivo y el servidor VPN.
- **Encapsulamiento** de los datos.
- Creación de un **túnel seguro**.
- Mayor protección frente a observadores de la red Wi-Fi local.
- Mayor privacidad frente a la red local.

Sin embargo, una VPN no reemplaza a HTTPS. Lo recomendable es utilizar **HTTPS y, cuando corresponda, una VPN confiable**.

---

## 5. Mis 3 Reglas de Oro para utilizar redes Wi-Fi públicas

### Regla de Oro 1: Utilizar HTTPS

Antes de introducir información sensible, verificar que el sitio utilice HTTPS. Evitar ingresar contraseñas, información bancaria o datos personales en páginas que funcionen únicamente mediante HTTP.

### Regla de Oro 2: Utilizar una VPN confiable

Cuando sea necesario utilizar una red Wi-Fi pública, una VPN puede crear un túnel cifrado que protege el tráfico entre el dispositivo y el servidor VPN.

### Regla de Oro 3: Evitar operaciones sensibles

En redes públicas, evitar realizar operaciones bancarias, compras o acceder a información especialmente sensible. Cuando sea posible, utilizar una conexión propia, como los datos móviles.

---

## Conclusión

La práctica permitió comprobar la diferencia de seguridad existente entre HTTP y HTTPS.

Al analizar NeverSSL se pudieron observar datos de la solicitud como la URL, el método GET, el host, el User-Agent y otros encabezados.

Esto demuestra la importancia de utilizar HTTPS y adoptar medidas adicionales de seguridad cuando se utilizan redes Wi-Fi públicas.

Una VPN puede mejorar la protección mediante cifrado, encapsulamiento y un túnel seguro, aunque no reemplaza la necesidad de utilizar HTTPS.
