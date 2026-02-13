---
name: btk-automation
description: Script de automatización con colores :D
license: MIT
compatibility: Bash
user-invocable: true
---

# BTK (Bash ToolKit)

Esta skill permite integrar el script `btk.sh` en tus proyectos para mejorar la salida visual de logs y mensajes en terminal.

---

## Notas

Antes de usar BTK, asegúrate de:

1. Tener instalado `tput` (incluido en la mayoría de sistemas Unix/Linux).
2. Importar el script en tus scripts de Bash:
  ```bash
   source /ruta/a/btk.sh
  ```

---

## ¿Qué es?

BTK es un **Bash ToolKit** (versión 2.1) que proporciona un sistema avanzado de logging con colores y estilos para scripts de Bash. Está diseñado para facilitar la depuración y mejorar la experiencia visual en terminales.

---

## Propósito

- **Logging con colores:** Mensajes de error, éxito, advertencia, info y debug con estilos personalizables.
- **Detección de modo:** Ajusta automáticamente los colores según el modo claro (`light`) u oscuro (`dark`).
- **Portabilidad:** Usa `tput` para garantizar compatibilidad entre terminales.

---

## Dependencias

- `tput` (herramienta estándar en Unix/Linux)
- `bash` (versión 4.0 o superior)

---

## Funcionalidades


| Funcionalidad       | Descripción                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------ |
| Colored Logging     | Funciones para imprimir logs con colores: `log_error`, `log_success`, `log_warning`, `log_info`, `log_debug` |
| Mode Detection      | Detecta y ajusta el esquema de colores según la variable `MODE` (light/dark)                                 |
| Customizable Styles | Permite personalizar colores y estilos mediante variables de entorno                                         |


---

## Habilidades

1. **Logging Avanzado**
  - Imprime mensajes con colores y estilos predefinidos.
  - Ejemplo:
    ```bash
    log_info "Iniciando proceso..."
    log_success "Proceso completado con éxito"
    ```
2. **Detección de Modo**
  - Cambia automáticamente entre esquemas de colores claros/oscuros.
  - Ejemplo:
    ```bash
    export MODE=dark  # Cambia a modo oscuro
    ```
3. **Utilidades de Formato**
  - Funciones auxiliares para negrita, subrayado, etc.

---

## Uso Típico

### 1. Importar BTK

```bash
source btk.sh
```

### 2. Usar funciones de log

```bash
log_info "Iniciando proceso..."
log_success "Proceso completado con éxito"
```

### 3. Cambiar modo de colores

```bash
export MODE=dark  # Cambia a modo oscuro
```

---

## Ejemplo Completo

```bash
#!/bin/bash
source btk.sh

log_info "Script iniciado"
if [ $? -eq 0 ]; then
    log_success "Operación exitosa"
else
    log_error "Error en la operación"
fi
```
