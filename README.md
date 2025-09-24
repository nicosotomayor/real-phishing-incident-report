# real-phishing-incident-report

## 📌 Contexto
El **23 de septiembre de 2025**, recibí en mi bandeja de entrada personal un correo con el asunto:

> **“¡Has sido elegido para tu Taladro Makita GRATIS!”**

El mensaje provenía de un dominio fraudulento (`maxeduc.com`) que suplantaba a Carrefour. Este es un ejemplo típico de **phishing masivo dirigido a usuarios finales**, donde los atacantes buscan que la víctima haga clic en un enlace malicioso disfrazado:contentReference[oaicite:0]{index=0}.

---

## 📨 Evidencia del Correo
- **Remitente fraudulento:** `hr@maxeduc.com`  
- **Dominio suplantado:** Carrefour Regalos  
- **Técnicas utilizadas:**
  - Uso de *SafeLinks* para ofuscar la URL real.  
  - Ingeniería social mediante un asunto atractivo para inducir al clic.  

---

## 🔎 Análisis del Enlace (Sandbox – ANY.RUN)
- **Resultado:** Actividad maliciosa confirmada:contentReference[oaicite:1]{index=1}  
- **Indicadores de Compromiso (IoCs):**

| Tipo   | Valor |
|--------|-------|
| **MD5**     | 8CD7A169656FA1C34981E89A90C0B79C |
| **SHA256**  | 216786186F382129D46519D59E274273AAFB8EC8131D931ED270D75FE19460F6 |

- **Comportamiento detectado:**
  - Redirección a sitio de phishing.  
  - Modificación de claves de registro en Windows.  
  - Persistencia mediante ejecución automática (`Run` en el registro).  
  - Procesos maliciosos asociados a `msedge.exe`.  

---

## 📂 Análisis del Archivo Adjunto
- Archivo: `nicoelsoto.pdf`  
- **Veredicto:** No se detectaron amenazas:contentReference[oaicite:2]{index=2}.  
- **Observación:** Aunque el PDF era benigno, fue utilizado como vector de confianza para incentivar la apertura del correo.

---

## ⚠️ Riesgos Asociados
- **Robo de credenciales** mediante formularios falsos.  
- **Descarga de malware secundario** aprovechando navegadores.  
- **Persistencia en el sistema** por modificaciones en el registro.  

---

## 🛠️ Recomendaciones
1. **Bloqueo de IoCs** en firewall, EDR y SIEM.  
2. **Concientización del usuario** para identificar correos fraudulentos.  
3. **Hardening de endpoints**: deshabilitar ejecución automática y reforzar políticas de seguridad.  
4. **Gestión de incidentes** siguiendo **NIST 800-61**, documentando el caso para playbooks de phishing.  

---

## ✅ Conclusión
Este caso real demuestra cómo un simple correo recibido por un usuario puede ser la puerta de entrada a un compromiso mayor.  
La combinación de **sandboxing (ANY.RUN), análisis forense y buenas prácticas de respuesta** permitió **detectar y neutralizar la amenaza antes de que produjera un impacto real**.  

📌 **Lección aprendida:** La **ciberseguridad comienza en el usuario final**. Capacitación continua y monitoreo proactivo son claves para prevenir incidentes.

---
## 📂 Evidencias incluidas

En la carpeta [`Evidencias/`](./Evidencias) se encuentran los siguientes archivos:

- [`AnalisisLink.pdf`](./Evidencias/AnalisisLink.pdf) → Informe PDF del análisis desde el enlace de Any.Run.  
- [`AnalisisPDFadjunto.pdf`](./Evidencias/AnalisisPDFadjunto.pdf) → Informe PDF del análisis del archivo adjunto malicioso.  
- [`Archivo.eml`](./Evidencias/Archivo.eml) → Correo electrónico original recibido en formato **.eml**.  
- [`Imagen.jpg`](./Evidencias/Imagen.jpg) → Captura de pantalla del correo recibido.  
## 👨‍💻 Autor
**Nicolás Sotomayor**  
- SOC Analyst Jr. | Blue Team | Cybersecurity Enthusiast  
- [LinkedIn](https://www.linkedin.com/in/nicolas-sotomayor-071b67238/)  
