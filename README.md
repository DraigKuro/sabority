# Sabority

Sistema de gestión para restaurantes y hostelería que permite a los clientes hacer pedidos directamente desde la mesa, sin necesidad de intervención de un camarero.

El proyecto está dividido en varias partes independientes, cada una en su propio repositorio:

| Repositorio | Descripción | Stack |
|---|---|---|
| [`sabority-api`](https://github.com/DraigKuro/sabority-api) | Backend que centraliza la lógica de negocio: mesas, pedidos, menú y comunicación entre el panel de administración y la app de cliente. | TypeScript · Node.js · Express · MongoDB |
| [`sabority-android`](https://github.com/DraigKuro/sabority-android) | App nativa para que el cliente haga su pedido desde la mesa: consulta el menú, añade productos y envía el pedido directamente a cocina/barra. | Kotlin |
| [`sabority-admin-web`](https://github.com/DraigKuro/sabority-admin-web) | Panel de administración web para el personal del restaurante: gestión de mesas, pedidos en curso y menú. | TypeScript · Node.js · Express |
| [`sabority-web-legacy`](https://github.com/DraigKuro/sabority-web-legacy) | Primera versión del proyecto. Antes de existir la app Android, los clientes pedían desde la mesa a través de un cliente web. Se conserva como referencia de la evolución del proyecto. | TypeScript · Node.js · Express |

## Cómo funciona

1. El cliente se sienta en la mesa y, desde la app Android (`sabority-android`), consulta el menú y hace su pedido sin esperar a un camarero.
2. El pedido llega a la `sabority-api`, que lo registra y lo distribuye.
3. El personal del restaurante gestiona los pedidos, mesas y el menú desde el panel de administración (`sabority-admin-web`).

## Evolución del proyecto

La primera versión de Sabority (`sabority-web-legacy`) resolvía el pedido desde la mesa también mediante un cliente web. Esa parte evolucionó hacia una app Android nativa (`sabority-android`), pensada para dar una mejor experiencia al cliente en el momento de pedir, mientras que la gestión por parte del restaurante se mantuvo y creció como aplicación web (`sabority-admin-web`).

## Stack general

- **Backend:** TypeScript, Node.js, Express, MongoDB
- **Cliente de pedidos:** Kotlin (Android)
- **Panel de administración:** TypeScript, Node.js, Express
