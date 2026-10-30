# Base de datos IP → PC / sede (UTM 64046)

## Archivos
- `ip_a_pc.csv` — inventario plano IP/hostname/sede estimada
- `utm_inventario.sqlite` — tablas `ip_host`, `sedes_faz`, `faz_conectividad`
- `faz_conectividad_logger.csv` — logger semanal de conectividad sedes → FortiAnalyzer

## Cómo se construye
Se cruzan hostnames e IPs de:
1. Top bandwidth users (Reporte Uso Dominios WEB)
2. Usuarios más activos y más bloqueados
3. Sesiones anómalas (Top 500: radios/streaming)

El prefijo del hostname (`ADM-`, `PBL-`, `COM-`, `LIB-`, `LOM-`, `POL-`, `AGC-`, etc.) estima la sede y el código de dispositivo FAZ (`IMS_*`).

## Logger de conectividad FAZ
Cada corte semanal registra:
- `faz_connection_failed` (crítico)
- `cm_connectivity_inactive` (Central Management)
- shutdown/reboot de dispositivos
- cambios de interfaz
- lista de 38 dispositivos presentes en el Appendix A del Admin Report

Si una sede deja de reportar, el conteo de dispositivos o el evento FAZ connection failed lo reflejan. Ampliar el espectro: no solo tráfico web, también salud del canal de logs.
