# User Stories - Sistema de Reclutamiento de Talento LTI

## User Story 1: Creación de Ofertas de Empleo

**Como** reclutador de RRHH, 
**quiero** crear ofertas de empleo con título, descripción, requisitos, salario y ubicación, 
**para** poder publicar puestos vacantes y atraer candidatos cualificados.

**Criterios de Aceptación:**
- El formulario debe incluir campos: título (obligatorio), descripción (obligatorio), requisitos (obligatorio), salario (opcional), ubicación (obligatorio)
- La oferta puede guardarse como borrador antes de publicar
- Validación de campos obligatorios antes de guardar
- El reclutador puede editar la oferta en cualquier estado excepto "cerrada"

**Verificación INVEST:**
- **I (Independent):** No depende de otras funcionalidades, puede desarrollarse de forma aislada
- **N (Negotiable):** Los campos específicos y validaciones pueden ajustarse según feedback del equipo
- **V (Valuable):** Esencial para el negocio - sin ofertas no hay proceso de reclutamiento
- **E (Estimable):** Claridad en requisitos permite estimación precisa (2-3 días)
- **S (Small):** Alcance limitado a CRUD básico de ofertas
- **T (Testeable):** Criterios claros de validación de campos y estados

---

## User Story 2: Registro y Perfil de Candidato

**Como** candidato, 
**quiero** registrarme en el sistema completando mi perfil con información personal, experiencia laboral y educación, 
**para** poder postularme a ofertas de empleo y ser considerado por las empresas.

**Criterios de Aceptación:**
- Formulario de registro con: nombre, email, teléfono, experiencia laboral, educación
- Validación de formato de email (RFC 5322)
- El perfil debe estar 100% completo para poder postularse
- Autenticación 2FA obligatoria para proteger la cuenta
- El candidato puede actualizar su perfil en cualquier momento

**Verificación INVEST:**
- **I (Independent):** Funcionalidad autónoma de gestión de usuarios
- **N (Negotiable):** Campos específicos del perfil pueden ajustarse según necesidades
- **V (Valuable):** Fundamental para el candidato - sin perfil no puede participar
- **E (Estimable):** Requisitos claros permiten estimación (2-3 días)
- **S (Small):** CRUD de perfil de usuario con validaciones estándar
- **T (Testeable):** Validaciones de formulario y reglas de completitud verificables

---

## User Story 3: Postulación a Ofertas

**Como** candidato, 
**quiero** postularme a ofertas de empleo cargando mi CV y carta de presentación, 
**para** ser considerado por los reclutadores y avanzar en el proceso de selección.

**Criterios de Aceptación:**
- El candidato puede cargar CV (PDF/Word, máx 10MB) y carta de presentación (opcional)
- Escaneo antivirus de todos los documentos cargados
- No se permiten postulaciones duplicadas a la misma oferta
- Solo se puede postular a ofertas en estado "activa"
- Confirmación inmediata de recepción de la postulación

**Verificación INVEST:**
- **I (Independent):** Depende mínimamente de US1 y US2, pero lógica de postulación es autónoma
- **N (Negotiable):** Formatos de archivo, límites de tamaño y campos opcionales negociables
- **V (Valuable):** Core del sistema - es la acción principal del candidato
- **E (Estimable):** Integración con carga de archivos y antivirus (3-4 días)
- **S (Small):** Flujo específico de postulación con validaciones claras
- **T (Testeable):** Validaciones de archivo, duplicados y estados verificables

---

## User Story 4: Pipeline Visual de Candidatos

**Como** reclutador, 
**quiero** visualizar todos los candidatos en un pipeline tipo Kanban con estados (recibido, en revisión, prueba técnica, entrevista, oferta, contratado, rechazado), 
**para** tener un seguimiento claro y organizado del estado de cada candidatura.

**Criterios de Aceptación:**
- Visualización Kanban con columnas para cada estado del pipeline
- Los candidatos avanzan de estado cuando: el reclutador valida el paso a la siguiente fase, o el candidato supera automáticamente una fase (ej: completa prueba técnica en tiempo)
- El reclutador puede rechazar candidatos en cualquier etapa, moviéndolos a "Rechazado"
- Contador de candidatos en cada estado
- Filtros por oferta de empleo
- Los cambios de estado se registran con timestamp y usuario

**Verificación INVEST:**
- **I (Independent):** Interfaz visual con lógica de transiciones de estados que puede desarrollarse de forma modular
- **N (Negotiable):** Estados específicos, reglas de transición automática y diseño visual pueden ajustarse
- **V (Valuable):** Herramienta principal de trabajo del reclutador
- **E (Estimable):** Componente UI con lógica de validación y transiciones automáticas (3-4 días)
- **S (Small):** Alcance limitado a visualización y reglas de transición básicas
- **T (Testeable):** Transiciones de estado por validación y superación automática verificables

---

## User Story 5: Asignación de Pruebas Técnicas

**Como** reclutador, 
**quiero** asignar pruebas técnicas a candidatos en etapa de "en revisión", 
**para** evaluar sus habilidades técnicas antes de avanzar a entrevista.

**Criterios de Aceptación:**
- El reclutador puede seleccionar una prueba de una biblioteca o crear una nueva
- El candidato recibe notificación con enlace a la prueba
- La prueba tiene un límite de tiempo configurable por la empresa
- El sistema registra automáticamente cuando el candidato completa la prueba
- El reclutador puede ver los resultados de la prueba en el perfil del candidato

**Verificación INVEST:**
- **I (Independent):** Funcionalidad autónoma de gestión de pruebas
- **N (Negotiable):** Tipos de pruebas, límites de tiempo y formatos de resultados negociables
- **V (Valuable):** Permite filtrar candidatos por habilidades técnicas
- **E (Estimable):** Sistema de asignación y tracking de pruebas (3-4 días)
- **S (Small):** Alcance limitado a asignación y registro de resultados
- **T (Testeable):** Flujo de asignación, notificaciones y registro verificables

---

## User Story 6: Programación de Entrevistas

**Como** reclutador, 
**quiero** programar entrevistas con candidatos que pasaron las pruebas técnicas, 
**para** evaluar sus soft skills y cultural fit antes de hacer una oferta.

**Criterios de Aceptación:**
- El reclutador puede seleccionar fecha y hora de la entrevista
- Integración con calendario externo (Google Calendar/Outlook)
- El candidato recibe notificación con detalles de la entrevista
- El reclutador puede registrar feedback post-entrevista (máx 2000 caracteres)
- La entrevista no puede programarse en el pasado

**Verificación INVEST:**
- **I (Independent):** Funcionalidad de calendario independiente
- **N (Negotiable):** Integraciones específicas y formato de feedback negociables
- **V (Valuable):** Etapa crítica del proceso de selección
- **E (Estimable):** Integración con calendarios externos (3-4 días)
- **S (Small):** Programación básica con integración de calendario
- **T (Testeable):** Validaciones de fecha, notificaciones y feedback verificables

---

## User Story 7: Búsqueda y Filtrado de Candidatos

**Como** reclutador, 
**quiero** buscar y filtrar candidatos por habilidades, experiencia, ubicación y educación, 
**para** encontrar rápidamente candidatos que cumplan con los requisitos del puesto.

**Criterios de Aceptación:**
- Buscador con filtros: habilidades (tags), experiencia (años), ubicación (ciudad/país), educación (nivel/título)
- Búsqueda por texto libre en CV y descripción
- Resultados ordenados por relevancia
- Posibilidad de guardar filtros para uso futuro
- Exportación de resultados a CSV

**Verificación INVEST:**
- **I (Independent):** Funcionalidad de búsqueda independiente
- **N (Negotiable):** Filtros específicos y algoritmo de relevancia negociables
- **V (Valuable):** Ahorra tiempo significativo en el proceso de selección
- **E (Estimable):** Sistema de búsqueda con filtros (2-3 días)
- **S (Small):** Búsqueda y filtrado con criterios predefinidos
- **T (Testeable):** Resultados de búsqueda por cada filtro verificables

---

## User Story 8: Publicación Multi-canal de Ofertas

**Como** reclutador, 
**quiero** publicar ofertas de empleo en múltiples canales (LinkedIn, Twitter, Facebook, portales de empleo) desde el sistema, 
**para** maximizar la visibilidad de las vacantes y atraer más candidatos.

**Criterios de Aceptación:**
- El reclutador puede seleccionar los canales donde publicar la oferta
- Publicación simultánea en múltiples canales
- Seguimiento del estado de publicación en cada canal
- Si falla la publicación en un canal, se notifica al reclutador
- La oferta se despublica automáticamente al cerrarse

**Verificación INVEST:**
- **I (Independent):** Integraciones con APIs externas independientes
- **N (Negotiable):** Canales específicos y formato de publicación negociables
- **V (Valuable):** Aumenta significativamente el alcance de las ofertas
- **E (Estimable):** Integraciones con APIs de redes sociales (4-5 días)
- **S (Small):** Publicación básica con tracking de estado
- **T (Testeable):** Publicación y tracking en cada canal verificables

---

## User Story 9: Notificaciones Automáticas

**Como** candidato, 
**quiero** recibir notificaciones automáticas sobre cambios en el estado de mi candidatura, 
**para** estar informado en tiempo real sobre mi progreso en el proceso de selección.

**Criterios de Aceptación:**
- Notificaciones por email en cada cambio de estado del pipeline
- Notificaciones push en la aplicación móvil (opcional)
- Las notificaciones incluyen: nuevo estado, fecha del cambio, instrucciones siguientes
- El candidato puede configurar preferencias de notificación
- Historial de notificaciones disponible en el perfil

**Verificación INVEST:**
- **I (Independent):** Sistema de notificaciones independiente
- **N (Negotiable):** Canales de notificación y contenido negociables
- **V (Valuable):** Mejora significativamente la experiencia del candidato
- **E (Estimable):** Sistema de notificaciones por email (2-3 días)
- **S (Small):** Envío de emails basado en eventos del pipeline
- **T (Testeable):** Recepción de notificaciones en cada cambio verificable

---

## User Story 10: Reportes y Analytics de Reclutamiento

**Como** reclutador, 
**quiero** ver reportes con métricas de tiempo de contratación, calidad de candidatos y fuentes de reclutamiento, 
**para** tomar decisiones basadas en datos y optimizar el proceso de selección.

**Criterios de Aceptación:**
- Dashboard con métricas clave: tiempo promedio de contratación, tasa de conversión por etapa, fuentes de reclutamiento más efectivas
- Filtros por periodo de tiempo y oferta de empleo
- Gráficos visuales (bar charts, line charts, pie charts)
- Exportación de reportes a PDF y CSV
- Comparación con periodos anteriores

**Verificación INVEST:**
- **I (Independent):** Sistema de analytics independiente del flujo principal
- **N (Negotiable):** Métricas específicas y visualizaciones negociables
- **V (Valuable):** Permite optimización continua del proceso
- **E (Estimable):** Dashboard con queries y visualizaciones (4-5 días)
- **S (Small):** Reportes predefinidos con filtros básicos
- **T (Testeable):** Exactitud de métricas y generación de reportes verificable

---

## Resumen de Priorización

| User Story | Prioridad | Estimación (días) | Dependencias |
|------------|-----------|-------------------|--------------|
| US1: Creación de Ofertas | Alta | 2-3 | Ninguna |
| US2: Registro de Candidato | Alta | 2-3 | Ninguna |
| US3: Postulación a Ofertas | Alta | 3-4 | US1, US2 |
| US4: Pipeline Visual | Alta | 3-4 | US3 |
| US5: Pruebas Técnicas | Media | 3-4 | US4 |
| US6: Programación de Entrevistas | Media | 3-4 | US4, US5 |
| US7: Búsqueda y Filtrado | Alta | 2-3 | US2 |
| US8: Publicación Multi-canal | Media | 4-5 | US1 |
| US9: Notificaciones Automáticas | Media | 2-3 | US4 |
| US10: Reportes y Analytics | Baja | 4-5 | US4, US6 |

---

## Requisitos Técnicos

### Arquitectura General

**Backend:**
- API RESTful o GraphQL para comunicación cliente-servidor
- Arquitectura modular por dominios (ofertas, candidatos, pipeline, pruebas, entrevistas)
- Sistema de autenticación y autorización basado en roles (RBAC)
- Middleware para validación de datos, sanitización de inputs y manejo de errores
- Sistema de logging estructurado para auditoría y debugging

**Frontend:**
- Framework SPA (React/Vue/Angular) para interfaz interactiva
- Componentes reutilizables para formularios, tablas y visualizaciones
- State management para manejo de estado global
- Responsive design para soporte multi-dispositivo
- Sistema de routing para navegación SPA

**Base de Datos:**
- Base de datos relacional (PostgreSQL/MySQL) para datos estructurados
- Tablas principales: usuarios, empresas, ofertas, candidaturas, pruebas, entrevistas, notificaciones
- Índices optimizados para búsquedas frecuentes (email, estado de candidatura, habilidades)
- Relaciones con integridad referencial
- Migraciones versionadas para gestión de schema

---

### Requisitos por User Story

#### US1 - Creación de Ofertas de Empleo
- **Backend:** CRUD API para ofertas con validación de campos
- **Frontend:** Formulario dinámico con validación en tiempo real
- **Base de datos:** Tabla `ofertas` con campos: id, titulo, descripcion, requisitos, salario, ubicacion, estado, empresa_id
- **Validaciones:** Sanitización de HTML en descripción, validación de formato de salario

#### US2 - Registro y Perfil de Candidato
- **Autenticación:** Sistema de autenticación con JWT y 2FA (TOTP/SMS)
- **Backend:** CRUD API para usuarios con validación de email (RFC 5322)
- **Frontend:** Formulario de registro multi-paso con validación progresiva
- **Base de datos:** Tabla `usuarios` con campos: id, email, password_hash, nombre, telefono, rol, mfa_enabled, mfa_secret
- **Seguridad:** Hash de contraseñas (bcrypt/argon2), encriptación de datos sensibles

#### US3 - Postulación a Ofertas
- **Almacenamiento de archivos:** Servicio de almacenamiento (AWS S3/Cloud Storage) para CVs y cartas
- **Antivirus:** Integración con servicio de escaneo antivirus (ClamAV/Cloud-based)
- **Backend:** API para carga de archivos con validación de formato (PDF/Word) y tamaño (máx 10MB)
- **Base de datos:** Tabla `candidaturas` con campos: id, usuario_id, oferta_id, fecha_postulacion, estado, cv_url, carta_url
- **Validaciones:** Verificación de duplicados, estado de oferta activa

#### US4 - Pipeline Visual de Candidatos
- **Frontend:** Componente Kanban con drag-and-drop (React DnD/similar)
- **Backend:** API para transiciones de estado con lógica de validación
- **Tiempo real:** WebSocket (Socket.io/SignalR) para actualizaciones en vivo del pipeline
- **Base de datos:** Tabla `candidaturas` con campo `estado` y tabla `auditoria_candidaturas` para tracking de cambios
- **Lógica de negocio:** Reglas de transición automática (ej: completar prueba → avanzar estado)
- **Auditoría:** Registro de todos los cambios con timestamp y usuario_id

#### US5 - Asignación de Pruebas Técnicas
- **Backend:** Sistema de gestión de pruebas con biblioteca de tests
- **Timer:** Sistema de límites de tiempo configurables por empresa
- **Frontend:** Interfaz para crear/seleccionar pruebas y ver resultados
- **Base de datos:** Tablas: `pruebas` (id, titulo, tipo, contenido, tiempo_limite), `asignaciones_pruebas` (id, prueba_id, candidatura_id, fecha_asignacion, fecha_completacion, resultado)
- **Notificaciones:** Sistema de eventos para notificar al candidato

#### US6 - Programación de Entrevistas
- **Integraciones:** APIs de Google Calendar (Calendar API) y Microsoft Outlook (Graph API)
- **Backend:** Servicio de sincronización con calendarios externos
- **Frontend:** Date picker con validación de fechas (no pasado, máx 6 meses futuro)
- **Base de datos:** Tabla `entrevistas` con campos: id, candidatura_id, fecha, hora, feedback, calendario_externo_id
- **Validaciones:** Conflicto de horarios, disponibilidad del reclutador

#### US7 - Búsqueda y Filtrado de Candidatos
- **Motor de búsqueda:** Elasticsearch o full-text search en PostgreSQL para búsqueda por texto libre
- **Backend:** API de búsqueda con filtros compuestos y paginación
- **Frontend:** Componente de búsqueda con filtros dinámicos y guardado de filtros
- **Base de datos:** Índices optimizados en campos: habilidades, experiencia, ubicacion, educacion
- **Exportación:** Servicio de generación de CSV
- **Tags:** Sistema de etiquetas para habilidades

#### US8 - Publicación Multi-canal de Ofertas
- **Integraciones:** APIs de LinkedIn (Share API), Twitter (X API), Facebook (Graph API), portales de empleo
- **Backend:** Sistema de colas (RabbitMQ/Redis) para publicaciones asíncronas
- **Frontend:** Interfaz para seleccionar canales y ver estado de publicación
- **Base de datos:** Tabla `publicaciones` con campos: id, oferta_id, canal, estado, fecha_publicacion, error_message
- **Retry:** Mecanismo de reintentos automáticos para publicaciones fallidas
- **Webhooks:** Recepción de confirmaciones de plataformas externas

#### US9 - Notificaciones Automáticas
- **Email:** Servicio de envío de emails (SendGrid/Mailgun/AWS SES) con templates
- **Push:** Servicio de notificaciones push (Firebase Cloud Messaging/OneSignal) - opcional
- **Backend:** Sistema de eventos/trigger para detectar cambios de estado en pipeline
- **Colas:** Sistema de colas para envío asíncrono de notificaciones
- **Base de datos:** Tabla `notificaciones` con campos: id, usuario_id, tipo, contenido, fecha_envio, estado, preferencias
- **Plantillas:** Sistema de templates de email personalizados por estado

#### US10 - Reportes y Analytics
- **Dashboard:** Framework de visualización (Chart.js/D3.js/Recharts)
- **Backend:** API de analytics con queries agregadas y filtros temporales
- **Base de datos:** Vistas materializadas o queries optimizadas para métricas
- **Exportación:** Servicios de generación de PDF (Puppeteer/jsPDF) y CSV
- **Caching:** Sistema de cache (Redis) para métricas frecuentes
- **Métricas:** Cálculo de KPIs: tiempo promedio contratación, tasa conversión, fuentes efectivas

---

### Requisitos Transversales

**Seguridad:**
- HTTPS/TLS 1.3 para todas las comunicaciones
- CORS configurado para dominios autorizados
- Rate limiting para prevenir abuso
- Sanitización de inputs para prevenir XSS/SQL injection
- Headers de seguridad (CSP, X-Frame-Options, etc.)
- Cumplimiento RGPD: consentimiento explícito, derecho al olvido, portabilidad de datos

**Performance:**
- CDN para assets estáticos
- Compresión de respuestas (gzip/brotli)
- Optimización de imágenes y archivos
- Lazy loading de componentes
- Paginación en listados grandes
- Cache de respuestas frecuentes

**Escalabilidad:**
- Arquitectura stateless para horizontal scaling
- Balanceador de carga (Nginx/HAProxy/ALB)
- Base de datos con replicación read-only para consultas
- Sistema de colas para tareas asíncronas
- Microservicios opcionales para componentes independientes

**Monitoring y Logging:**
- Sistema de logging centralizado (ELK stack/Grafana Loki)
- Monitoring de aplicación (APM: New Relic/DataDog)
- Alertas automáticas para errores críticos
- Health checks para servicios
- Métricas de performance y uso

**DevOps:**
- CI/CD pipeline (GitHub Actions/GitLab CI)
- Contenedorización (Docker)
- Orquestación (Kubernetes/Docker Compose)
- Gestión de configuración (Environment variables/Secrets manager)
- Blue-green deployments para actualizaciones sin downtime

**Testing:**
- Unit tests para lógica de negocio
- Integration tests para APIs
- E2E tests para flujos críticos
- Tests de carga para componentes críticos
- Tests de seguridad automatizados

---

## Análisis de Problemas Comunes y Mejoras Propuestas

### Problema 1: Barrera de Entrada Alta para Candidatos (US2)

**Descripción:**
El requisito de que el perfil esté 100% completo antes de poder postularse crea una barrera significativa. Los candidatos deben invertir tiempo considerable completando información detallada antes de saber si hay ofertas relevantes para ellos.

**Impacto:**
- Alta tasa de abandono durante el registro
- Pérdida de candidatos cualificados que no quieren completar formularios largos
- Experiencia de usuario frustrante

**Mejoras Propuestas:**
- **Registro progresivo:** Permitir postulación con perfil básico (nombre, email, CV) y completar el resto después
- **Importación de LinkedIn:** Permitir importar perfil automáticamente desde LinkedIn para reducir fricción
- **Perfil por etapas:** Indicar porcentaje de completitud y permitir postulación con perfil mínimo (ej: 60%)
- **Campos opcionales estratégicos:** Marcar campos como "recomendados" en lugar de obligatorios

---

### Problema 2: Falta de Feedback Estructurado en Pruebas Técnicas (US5)

**Descripción:**
El sistema asigna pruebas técnicas y registra resultados, pero no proporciona feedback detallado al candidato sobre qué acertó/erró ni áreas de mejora.

**Impacto:**
- Los candidatos no aprenden de sus errores
- Experiencia negativa que puede dañar el employer branding
- Los reclutadores no tienen justificación clara para rechazos basados en pruebas

**Mejoras Propuestas:**
- **Feedback automático:** Generar reporte detallado con aciertos/errores por categoría de habilidad
- **Recomendaciones de mejora:** Sugerir recursos o cursos basados en áreas débiles
- **Comparación con otros:** Mostrar percentil de desempeño vs otros candidatos (anonimizado)
- **Reintentos limitados:** Permitir repetir prueba después de X días con nuevas preguntas

---

### Problema 3: Ausencia de Colaboración entre Reclutadores (US4)

**Descripción:**
El pipeline visual permite seguimiento individual pero no hay sistema de comentarios, etiquetas o asignación de candidatos entre múltiples reclutadores del mismo equipo.

**Impacto:**
- Dificultad para coordinar decisiones en equipo
- Pérdida de contexto cuando múltiples reclutadores revisan al mismo candidato
- No hay historial de opiniones colaborativas

**Mejoras Propuestas:**
- **Comentarios en candidatos:** Sistema de comentarios @mención entre reclutadores en cada candidatura
- **Etiquetas personalizadas:** Permitir etiquetar candidatos (ej: "prioridad alta", "referencia interna", "backup")
- **Asignación de propietario:** Designar reclutador responsable de cada candidatura
- **Vista de equipo:** Panel colaborativo para ver candidatos asignados a cada reclutador
- **Voting system:** Sistema de votación para decisiones de avance/rechazo en equipo

---

### Problema 4: Limitaciones en Formatos y Tamaño de Archivos (US3)

**Descripción:**
El sistema solo acepta PDF/Word con límite de 10MB, lo que excluye candidatos con CVs en otros formatos o con portfolios multimedia (diseñadores, desarrolladores con GitHub, etc.).

**Impacto:**
- Candidatos creativos/tecnológicos no pueden mostrar su trabajo completo
- Rechazo automático de postulaciones válidas por formato
- Pérdida de talento especializado

**Mejoras Propuestas:**
- **Soporte multi-formato:** Aceptar también: imágenes (JPG/PNG para portfolios), enlaces a GitHub/Behance/Dribbble, videos (YouTube/Vimeo)
- **Límite flexible:** Aumentar límite a 25MB o usar compresión automática
- **Vista previa:** Generar preview de CVs y portfolios directamente en el sistema
- **Parser inteligente:** Extraer información automáticamente de CVs en diferentes formatos
- **Enlaces externos:** Permitir adjuntar enlaces a portfolios online en lugar de solo archivos

---

### Problema 5: Falta de Sistema de Videoconferencia Integrado (US6)

**Descripción:**
La programación de entrevistas se integra con calendarios externos pero no incluye plataforma de videoconferencia, obligando a usar herramientas externas (Zoom, Teams, Meet) manualmente.

**Impacto:**
- Fricción adicional para coordinar enlaces de videollamada
- Riesgo de errores en la coordinación de enlaces
- Experiencia menos profesional y fluida
- No hay grabación automática de entrevistas para revisión posterior

**Mejoras Propuestas:**
- **Integración nativa de video:** Integrar API de Zoom/Teams/Meet para generar enlaces automáticamente
- **Sala de espera:** Virtual waiting room para candidatos antes de la entrevista
- **Grabación automática:** Opción de grabar entrevistas con consentimiento para revisión posterior
- **Evaluación en vivo:** Formulario de feedback accesible durante la videollamada
- **Transcripción automática:** Generar transcripción de la entrevista para búsqueda posterior
- **Calendario unificado:** Mostrar disponibilidad de todos los entrevistadores en una sola vista

---

## Resumen de Prioridad de Mejoras

| Mejora | Prioridad | Complejidad | Impacto en UX | User Story Relacionada |
|--------|-----------|-------------|---------------|------------------------|
| Registro progresivo | Alta | Media | Muy alto | US2 |
| Feedback en pruebas técnicas | Alta | Media | Alto | US5 |
| Colaboración entre reclutadores | Media | Alta | Alto | US4 |
| Soporte multi-formato archivos | Media | Baja | Medio | US3 |
| Videoconferencia integrada | Alta | Alta | Muy alto | US6 |
