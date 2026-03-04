# 04. Creación de Puntos de Control (Snapshots) y Pruebas

## 1. Creación de Snapshots
Para asegurar la integridad del entorno antes de realizar despliegues complejos, se han creado puntos de control (Snapshots) de ambas máquinas en VirtualBox.

**Procedimiento realizado:**
1. Apagado controlado de las máquinas virtuales (`sudo poweroff`).
2. En el panel de VirtualBox, acceso a la sección de **Instantáneas** (Snapshots).
3. Creación de la instantánea con el nombre: `Base - Docker y Herramientas instaladas`.

## 2. Pruebas de Restauración (Rollback)
En caso de fallo crítico en el sistema o corrupción de datos durante el proyecto, el procedimiento de recuperación comprobado es el siguiente:
1. Apagar la máquina virtual afectada de forma forzada o mediante línea de comandos.
2. Desde el administrador de Snapshots de VirtualBox, seleccionar el punto de control funcional más reciente.
3. Hacer clic en **Restaurar** (Restore).
4. *(Opcional)* Desmarcar la casilla de "Crear una instantánea del estado actual de la máquina" si el estado actual es irrecuperable y no aporta valor conservarlo.
5. Iniciar la máquina virtual. El sistema y la red arrancarán exactamente en el estado documentado en el snapshot.
