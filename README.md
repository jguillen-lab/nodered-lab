# Node-RED Lab

Repositorio temático con flows y subflows para **Node-RED + Home Assistant**, organizados por subproyectos independientes.

## Subproyectos

### [`auto-ct`](https://github.com/jguillen-lab/nodered-lab/tree/main/auto-ct)

Dos automatizaciones de iluminación para **Home Assistant** con **Node-RED**:

- **Boost de brillo matutino** — detecta el primer encendido del día de cada luz (a partir de las 08:00) y la lleva automáticamente al 100% de brillo con una transición suave. Una sola vez al día por entidad, sin interferir con el comportamiento posterior.

- **Control de temperatura de color adaptativo** (`subflow`)— ajusta la tonalidad de la luz (de cálida a fría) siguiendo la elevación real del sol. Si el usuario cambia la temperatura manualmente, el sistema lo detecta, desactiva el modo automático y envía una notificación al móvil (con opción de volver a automático tras un tiempo configurable).

## Objetivo del repositorio

Agrupar en un único sitio distintos flows y subflows de Node-RED para domótica con Home Assistant, manteniendo cada proyecto en su propia carpeta con su documentación.

## Estructura

```
.
├── README.md
└── auto-ct/
    ├── boost-brillo.json
    └── subflow-auto-ct.json
```

## Requisitos

- [Node-RED](https://nodered.org/)
- [node-red-contrib-home-assistant-websocket](https://github.com/zachowj/node-red-contrib-home-assistant-websocket) ≥ 0.80
- Home Assistant con las entidades `input_boolean` e `input_number` definidas según la configuración de cada subflow
