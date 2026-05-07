# Guía de Remediación Urgente – Vulnerabilidades Críticas Mayo 2026

**Publicado:** 7 de mayo de 2026  
**Barcos subiendo a la superficie:** Android + Palo Alto PAN-OS

## 1. Android – CVE-2026-0073 (Componente System / adbd)
**Impacto:** Ejecución remota de código sin interacción del usuario (Wireless ADB).  
**Afecta:** Android 14, 15, 16 y 16-QPR2.

### Pasos que deben ejecutar:
1. Verificar nivel de parche:  
   `Ajustes → Acerca del teléfono → Nivel de parche de seguridad Android`  
   Debe mostrar **2026-05-01** o superior.
2. Actualizar inmediatamente vía OTA o Google Play System Update.
3. **Desactivar Depuración inalámbrica** (medida crítica):  
   - Activar Opciones de desarrollador.  
   - Desactivar **Depuración inalámbrica** y **Depuración USB**.  
   - Reiniciar dispositivo.
4. Bloquear puerto TCP 5555 en firewalls corporativos.
5. Usar solo ADB por cable cuando sea necesario.

## 2. Palo Alto Networks – CVE-2026-0300 (PAN-OS Captive Portal)
**Impacto:** Ejecución remota de código sin credenciales → root + movimiento lateral a Active Directory.

### Pasos que deben ejecutar:
1. Revisar si utilizan PAN-OS (PA-Series o VM-Series) con **Captive Portal** activo.
2. Si el Captive Portal está expuesto a internet → **cerrarlo inmediatamente** o limitarlo solo a redes internas confiables.
3. Aplicar el parche oficial de Palo Alto lo antes posible.
4. Revisar logs del firewall por:
   - Registros borrados
   - Reinicios inusuales
   - Accesos anómalos
   - Presencia de herramientas de túnel

## Acciones transversales recomendadas (para todos los sectores)
- Realizar inventario urgente de dispositivos y firewalls.
- Aplicar política Zero-Trust.
- Activar actualizaciones automáticas y Google Play Protect.
- Monitorear logs de forma activa.
- Segmentar redes (dispositivos móviles y firewalls en VLANs aisladas).

**Fuentes oficiales:**  
- Android Security Bulletin – Mayo 2026  
- Palo Alto Networks Security Advisory (CVE-2026-0300)

---

La mejor defensa es la velocidad de respuesta.  
El sector no va a poder parchear todo a tiempo. Compartir esta guía ayuda a cerrar ventanas.

**David jaimes** – Colaboración abierta.
