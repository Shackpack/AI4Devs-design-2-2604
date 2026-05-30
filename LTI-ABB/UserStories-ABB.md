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

---

## Estimación del Backlog de Producto
*(Prompt: Estima por cada item en el backlog: Impacto en el usuario y valor del negocio. Urgencia basada en tendencias del mercado y feedback de usuarios. Complejidad y esfuerzo estimado de implementación. Riesgos y dependencias entre tareas.)*

| User Story | Impacto en Usuario | Valor de Negocio | Urgencia | Complejidad | Esfuerzo (días) | Riesgos | Dependencias |
|------------|-------------------|------------------|----------|-------------|-----------------|---------|--------------|
| **US1: Creación de Ofertas** | Alta - Permite a reclutadores publicar vacantes | Crítico - Sin ofertas no hay proceso | Alta - Funcionalidad core | Baja - CRUD básico | 2-3 | Bajo - Validaciones estándar | Ninguna |
| **US2: Registro de Candidato** | Alta - Permite a candidatos participar | Crítico - Sin candidatos no hay proceso | Alta - Funcionalidad core | Media - 2FA, validaciones | 2-3 | Medio - Seguridad, RGPD | Ninguna |
| **US3: Postulación a Ofertas** | Muy Alta - Acción principal del candidato | Crítico - Core del sistema | Alta - Funcionalidad core | Media - Carga archivos, antivirus | 3-4 | Medio - Integración antivirus, S3 | US1, US2 |
| **US4: Pipeline Visual** | Muy Alta - Herramienta principal reclutador | Alto - Mejora eficiencia 50% | Alta - Diferenciador clave | Media - Kanban, WebSockets | 3-4 | Medio - Tiempo real, auditoría | US3 |
| **US5: Pruebas Técnicas** | Alta - Filtrado de habilidades técnicas | Alto - Mejora calidad contrataciones | Media - Valor añadido | Media - Timer, biblioteca tests | 3-4 | Medio - Límites tiempo, notificaciones | US4 |
| **US6: Programación de Entrevistas** | Alta - Etapa crítica selección | Alto - Necesario para contratación | Media - Estandar del mercado | Alta - Integraciones calendarios | 3-4 | Alto - APIs externas, conflictos | US4, US5 |
| **US7: Búsqueda y Filtrado** | Muy Alta - Ahorra tiempo significativo | Alto - Eficiencia operativa | Alta - Expectativa básica | Media - Elasticsearch, filtros | 2-3 | Bajo - Motor búsqueda estándar | US2 |
| **US8: Publicación Multi-canal** | Media - Amplía alcance ofertas | Medio - Reduce costos publicación | Baja - Nice-to-have | Alta - Múltiples APIs, colas | 4-5 | Alto - APIs externas, webhooks | US1 |
| **US9: Notificaciones Automáticas** | Alta - Mejora experiencia candidato | Medio - Employer branding | Media - Expectativa usuario | Baja - Email service, colas | 2-3 | Bajo - Servicio email estándar | US4 |
| **US10: Reportes y Analytics** | Media - Toma de decisiones | Medio - Optimización continua | Baja - Valor estratégico | Alta - Dashboard, queries | 4-5 | Medio - Métricas complejas | US4, US6 |

### Leyenda de Evaluación

**Impacto en Usuario:**
- **Muy Alta:** Funcionalidad esencial sin la cual el sistema no es usable
- **Alta:** Funcionalidad importante que mejora significativamente la experiencia
- **Media:** Funcionalidad útil pero no crítica
- **Baja:** Funcionalidad complementaria

**Valor de Negocio:**
- **Crítico:** Necesario para el modelo de negocio
- **Alto:** Impacto directo en KPIs principales (tiempo contratación, calidad)
- **Medio:** Mejora operativa o branding
- **Bajo:** Valor estratégico a largo plazo

**Urgencia:**
- **Alta:** Requerimiento de mercado, expectativa básica del usuario
- **Media:** Diferenciador competitivo
- **Baja:** Nice-to-have, puede diferirse

**Complejidad:**
- **Baja:** Tecnología estándar, sin integraciones complejas
- **Media:** Algunas integraciones o lógica de negocio moderada
- **Alta:** Múltiples integraciones externas, lógica compleja

**Riesgos:**
- **Bajo:** Tecnología probada, dependencias estables
- **Medio:** Integraciones con servicios externos, requisitos regulatorios
- **Alto:** APIs de terceros no controladas, coordinación compleja

### Recomendación de Roadmap por Fases

**Fase 1 - MVP (Sprint 1-2):**
- US1: Creación de Ofertas
- US2: Registro de Candidato
- US3: Postulación a Ofertas
- US7: Búsqueda y Filtrado

**Fase 2 - Core del Sistema (Sprint 3-4):**
- US4: Pipeline Visual
- US9: Notificaciones Automáticas

**Fase 3 - Evaluación (Sprint 5-6):**
- US5: Pruebas Técnicas
- US6: Programación de Entrevistas

**Fase 4 - Escalabilidad (Sprint 7-8):**
- US8: Publicación Multi-canal
- US10: Reportes y Analytics

---

## Desglose Técnico del Backlog de Desarrollo
*(Prompt: Actúa como un Tech Lead senior. A partir de las 10 User Stories del Sistema de Reclutamiento LTI, genera un backlog de tareas técnicas desglosando cada User Story en subtareas específicas de desarrollo. Para cada User Story, incluye: Tareas de Backend (endpoints, modelos, lógica de negocio), Tareas de Frontend (componentes, pantallas, validaciones), Tareas de Base de Datos (tablas, índices, migraciones), Tareas de Integración (APIs externas, servicios), Tareas de Testing (unit tests, integration tests). Prioriza las tareas siguiendo el roadmap por fases.)*

### FASE 1 - MVP (Sprint 1-2)

#### US1: Creación de Ofertas de Empleo
├── Backend: [16 horas]
│   ├── POST /api/ofertas - Crear oferta (4h)
│   ├── GET /api/ofertas - Listar ofertas (2h)
│   ├── GET /api/ofertas/:id - Obtener oferta (2h)
│   ├── PUT /api/ofertas/:id - Actualizar oferta (4h)
│   ├── DELETE /api/ofertas/:id - Desactivar oferta (2h)
│   └── Validación de campos y sanitización HTML (2h)
├── Frontend: [12 horas]
│   ├── Formulario de creación de oferta (4h)
│   ├── Lista de ofertas con filtros (3h)
│   ├── Vista detalle de oferta (2h)
│   ├── Modal de edición de oferta (2h)
│   └── Validaciones en tiempo real (1h)
├── Database: [6 horas]
│   ├── Crear tabla ofertas (2h)
│   ├── Crear índices en estado, empresa_id (2h)
│   ├── Migration script (1h)
│   └── Seed data para testing (1h)
├── Integrations: [0 horas]
│   └── Sin integraciones externas
└── Testing: [8 horas]
    ├── Unit tests de endpoints (3h)
    ├── Integration tests de CRUD (3h)
    └── E2E tests de flujo creación (2h)

**Total US1: 42 horas**

---

#### US2: Registro y Perfil de Candidato
├── Backend: [20 horas]
│   ├── POST /api/auth/register - Registro usuario (4h)
│   ├── POST /api/auth/login - Login con JWT (3h)
│   ├── POST /api/auth/2fa/setup - Configurar 2FA (4h)
│   ├── POST /api/auth/2fa/verify - Verificar 2FA (3h)
│   ├── GET /api/usuarios/perfil - Obtener perfil (2h)
│   ├── PUT /api/usuarios/perfil - Actualizar perfil (3h)
│   └── Middleware de autenticación JWT (1h)
├── Frontend: [16 horas]
│   ├── Formulario de registro multi-paso (5h)
│   ├── Pantalla de login (3h)
│   ├── Configuración 2FA (QR code) (4h)
│   ├── Formulario de edición de perfil (3h)
│   └── Indicador de completitud de perfil (1h)
├── Database: [8 horas]
│   ├── Crear tabla usuarios (3h)
│   ├── Crear tabla perfiles (2h)
│   ├── Índices en email, rol (2h)
│   └── Migration script (1h)
├── Integrations: [4 horas]
│   ├── Integración servicio 2FA (TOTP) (3h)
│   └── Servicio de envío SMS 2FA (1h)
└── Testing: [10 horas]
    ├── Unit tests de auth (4h)
    ├── Integration tests de 2FA (3h)
    └── E2E tests de registro (3h)

**Total US2: 58 horas**

---

#### US3: Postulación a Ofertas
├── Backend: [18 horas]
│   ├── POST /api/candidaturas - Crear candidatura (4h)
│   ├── GET /api/candidaturas - Listar candidaturas (2h)
│   ├── POST /api/candidaturas/upload - Cargar CV (4h)
│   ├── Integración antivirus ClamAV (3h)
│   ├── Validación de duplicados (2h)
│   └── Verificación estado oferta activa (1h)
├── Frontend: [14 horas]
│   ├── Formulario de postulación (4h)
│   ├── Componente de carga de archivos (3h)
│   ├── Vista previa de CV (2h)
│   ├── Lista de candidaturas del usuario (3h)
│   └── Pantalla de confirmación (2h)
├── Database: [8 horas]
│   ├── Crear tabla candidaturas (3h)
│   ├── Crear tabla documentos (2h)
│   ├── Índices en usuario_id, oferta_id (2h)
│   └── Migration script (1h)
├── Integrations: [8 horas]
│   ├── Integración AWS S3/Cloud Storage (4h)
│   ├── Integración servicio antivirus (3h)
│   └── Configuración CDN para archivos (1h)
└── Testing: [10 horas]
    ├── Unit tests de carga archivos (3h)
    ├── Integration tests antivirus (3h)
    └── E2E tests de postulación (4h)

**Total US3: 58 horas**

---

#### US7: Búsqueda y Filtrado de Candidatos
├── Backend: [16 horas]
│   ├── GET /api/candidaturas/buscar - Búsqueda avanzada (5h)
│   ├── POST /api/candidaturas/filtros - Guardar filtros (3h)
│   ├── GET /api/candidaturas/filtros - Listar filtros guardados (2h)
│   ├── GET /api/candidaturas/exportar - Exportar CSV (3h)
│   └── Implementación Elasticsearch o full-text search (3h)
├── Frontend: [14 horas]
│   ├── Componente de búsqueda con filtros (5h)
│   ├── Panel de filtros dinámicos (3h)
│   ├── Lista de resultados con paginación (3h)
│   ├── Sistema de guardado de filtros (2h)
│   └── Botón de exportación CSV (1h)
├── Database: [10 horas]
│   ├── Configurar Elasticsearch (4h)
│   ├── Crear índices en habilidades, experiencia (3h)
│   ├── Optimizar queries de búsqueda (2h)
│   └── Migration script (1h)
├── Integrations: [4 horas]
│   ├── Configuración Elasticsearch (3h)
│   └── Servicio de generación CSV (1h)
└── Testing: [8 horas]
    ├── Unit tests de búsqueda (3h)
    ├── Integration tests de filtros (3h)
    └── E2E tests de exportación (2h)

**Total US7: 52 horas**

---

### FASE 2 - Core del Sistema (Sprint 3-4)

#### US4: Pipeline Visual de Candidatos
├── Backend: [20 horas]
│   ├── GET /api/pipeline - Obtener pipeline (3h)
│   ├── PUT /api/candidaturas/:id/estado - Cambiar estado (5h)
│   ├── POST /api/candidaturas/:id/rechazar - Rechazar candidato (3h)
│   ├── GET /api/candidaturas/auditoria - Historial de cambios (3h)
│   ├── Lógica de transición automática (4h)
│   └── WebSocket para actualizaciones en tiempo real (2h)
├── Frontend: [18 horas]
│   ├── Componente Kanban con drag-and-drop (6h)
│   ├── Columnas por estado del pipeline (3h)
│   ├── Tarjetas de candidatos (3h)
│   ├── Filtros por oferta de empleo (2h)
│   ├── Contadores por estado (2h)
│   └── Modal de rechazo con feedback (2h)
├── Database: [10 horas]
│   ├── Crear tabla auditoria_candidaturas (3h)
│   ├── Triggers para logging de cambios (3h)
│   ├── Índices en estado, fecha_cambio (3h)
│   └── Migration script (1h)
├── Integrations: [6 horas]
│   ├── Configuración Socket.io/SignalR (4h)
│   └── Manejo de conexiones WebSocket (2h)
└── Testing: [12 horas]
    ├── Unit tests de transiciones (4h)
    ├── Integration tests de WebSocket (3h)
    └── E2E tests de pipeline (5h)

**Total US4: 66 horas**

---

#### US9: Notificaciones Automáticas
├── Backend: [14 horas]
│   ├── POST /api/notificaciones/enviar - Enviar notificación (3h)
│   ├── GET /api/notificaciones - Listar notificaciones (2h)
│   ├── PUT /api/notificaciones/preferencias - Configurar preferencias (3h)
│   ├── Sistema de eventos para cambios de estado (4h)
│   └── Cola de envío asíncrono (2h)
├── Frontend: [10 horas]
│   ├── Centro de notificaciones (3h)
│   ├── Panel de configuración de preferencias (3h)
│   ├── Badges de notificaciones no leídas (2h)
│   └── Historial de notificaciones (2h)
├── Database: [6 horas]
│   ├── Crear tabla notificaciones (2h)
│   ├── Crear tabla preferencias_notificaciones (2h)
│   └── Migration script (2h)
├── Integrations: [8 horas]
│   ├── Integración SendGrid/Mailgun (4h)
│   ├── Sistema de templates de email (3h)
│   └── Configuración Firebase FCM (opcional) (1h)
└── Testing: [8 horas]
    ├── Unit tests de envío de emails (3h)
    ├── Integration tests de colas (3h)
    └── E2E tests de notificaciones (2h)

**Total US9: 46 horas**

---

### FASE 3 - Evaluación (Sprint 5-6)

#### US5: Asignación de Pruebas Técnicas
├── Backend: [18 horas]
│   ├── POST /api/pruebas - Crear prueba (4h)
│   ├── GET /api/pruebas - Listar biblioteca de pruebas (2h)
│   ├── POST /api/pruebas/asignar - Asignar a candidato (4h)
│   ├── GET /api/pruebas/:id/completar - Completar prueba (3h)
│   ├── Sistema de timer configurable (3h)
│   └── Cálculo automático de resultados (2h)
├── Frontend: [16 horas]
│   ├── Formulario de creación de pruebas (4h)
│   ├── Biblioteca de pruebas (3h)
│   ├── Interfaz de toma de prueba para candidato (5h)
│   ├── Vista de resultados para reclutador (3h)
│   └── Timer visual con countdown (1h)
├── Database: [10 horas]
│   ├── Crear tabla pruebas (3h)
│   ├── Crear tabla asignaciones_pruebas (3h)
│   ├── Índices en prueba_id, candidatura_id (3h)
│   └── Migration script (1h)
├── Integrations: [4 horas]
│   ├── Sistema de eventos para notificaciones (2h)
│   └── Servicio de evaluación automática (2h)
└── Testing: [10 horas]
    ├── Unit tests de lógica de pruebas (4h)
    ├── Integration tests de timer (3h)
    └── E2E tests de flujo de prueba (3h)

**Total US5: 58 horas**

---

#### US6: Programación de Entrevistas
├── Backend: [20 horas]
│   ├── POST /api/entrevistas - Programar entrevista (5h)
│   ├── GET /api/entrevistas - Listar entrevistas (2h)
│   ├── PUT /api/entrevistas/:id/feedback - Registrar feedback (4h)
│   ├── Integración Google Calendar API (4h)
│   ├── Integración Microsoft Graph API (4h)
│   └── Validación de conflictos de horarios (1h)
├── Frontend: [16 horas]
│   ├── Calendario con disponibilidad (5h)
│   ├── Formulario de programación (3h)
│   ├── Integración con calendarios externos (3h)
│   ├── Formulario de feedback post-entrevista (3h)
│   └── Vista de agenda de entrevistas (2h)
├── Database: [8 horas]
│   ├── Crear tabla entrevistas (3h)
│   ├── Crear tabla sincronizaciones_calendario (3h)
│   └── Migration script (2h)
├── Integrations: [12 horas]
│   ├── Google Calendar API setup (4h)
│   ├── Microsoft Graph API setup (4h)
│   ├── Sincronización bidireccional (3h)
│   └── Manejo de tokens OAuth (1h)
└── Testing: [12 horas]
    ├── Unit tests de programación (4h)
    ├── Integration tests de calendarios (4h)
    └── E2E tests de flujo de entrevista (4h)

**Total US6: 68 horas**

---

### FASE 4 - Escalabilidad (Sprint 7-8)

#### US8: Publicación Multi-canal de Ofertas
├── Backend: [24 horas]
│   ├── POST /api/publicaciones - Publicar oferta (5h)
│   ├── GET /api/publicaciones - Listar publicaciones (2h)
│   ├── PUT /api/publicaciones/:id - Reintentar publicación (3h)
│   ├── Integración LinkedIn Share API (5h)
│   ├── Integración Twitter/X API (4h)
│   ├── Integración Facebook Graph API (4h)
│   └── Sistema de colas para publicaciones asíncronas (1h)
├── Frontend: [14 horas]
│   ├── Selector de canales de publicación (4h)
│   ├── Vista de estado de publicaciones (3h)
│   ├── Panel de configuración de APIs (3h)
│   ├── Historial de publicaciones (2h)
│   └── Indicadores de éxito/error (2h)
├── Database: [8 horas]
│   ├── Crear tabla publicaciones (3h)
│   ├── Crear tabla configuraciones_canales (3h)
│   └── Migration script (2h)
├── Integrations: [20 horas]
│   ├── LinkedIn API OAuth y setup (5h)
│   ├── Twitter/X API OAuth y setup (5h)
│   ├── Facebook API OAuth y setup (5h)
│   ├── Sistema de webhooks para confirmaciones (3h)
│   └── Mecanismo de reintentos automáticos (2h)
└── Testing: [14 horas]
    ├── Unit tests de APIs de redes sociales (5h)
    ├── Integration tests de colas (4h)
    └── E2E tests de publicación multi-canal (5h)

**Total US8: 80 horas**

---

#### US10: Reportes y Analytics
├── Backend: [22 horas]
│   ├── GET /api/analytics/metricas - Obtener KPIs (5h)
│   ├── GET /api/analytics/tiempo-contratación - Tiempo promedio (3h)
│   ├── GET /api/analytics/conversion - Tasa conversión (3h)
│   ├── GET /api/analytics/fuentes - Fuentes efectivas (3h)
│   ├── POST /api/analytics/exportar-pdf - Generar PDF (4h)
│   ├── POST /api/analytics/exportar-csv - Generar CSV (2h)
│   └── Vistas materializadas para métricas (2h)
├── Frontend: [18 horas]
│   ├── Dashboard principal con KPIs (5h)
│   ├── Gráficos de tiempo de contratación (3h)
│   ├── Gráficos de conversión por etapa (3h)
│   ├── Gráficos de fuentes de reclutamiento (3h)
│   ├── Filtros por periodo y oferta (2h)
│   └── Componentes de exportación (2h)
├── Database: [12 horas]
│   ├── Crear vistas materializadas (4h)
│   ├── Optimizar queries agregadas (4h)
│   ├── Configurar Redis para cache (3h)
│   └── Migration script (1h)
├── Integrations: [8 horas]
│   ├── Integración Chart.js/D3.js (3h)
│   ├── Servicio de generación PDF (Puppeteer) (3h)
│   └── Configuración Redis cache (2h)
└── Testing: [12 horas]
    ├── Unit tests de cálculo de métricas (4h)
    ├── Integration tests de cache (3h)
    └── E2E tests de dashboard (5h)

**Total US10: 72 horas**

---

## Resumen de Esfuerzo Total por Fase

| Fase | User Stories | Horas Totales | Días (8h/día) | Sprint (2 semanas) |
|------|--------------|---------------|---------------|-------------------|
| **Fase 1 - MVP** | US1, US2, US3, US7 | 210 horas | 26 días | 2-3 sprints |
| **Fase 2 - Core** | US4, US9 | 112 horas | 14 días | 1-2 sprints |
| **Fase 3 - Evaluación** | US5, US6 | 126 horas | 16 días | 2 sprints |
| **Fase 4 - Escalabilidad** | US8, US10 | 152 horas | 19 días | 2-3 sprints |
| **TOTAL** | 10 US | 600 horas | 75 días | 7-10 sprints |

### Notas de Estimación

- **Horas por desarrollador:** Considerando 1 desarrollador full-stack trabajando 8 horas/día
- **Buffer de contingencia:** Se recomienda agregar 20% adicional por imprevistos
- **Equipo recomendado:** 2-3 desarrolladores para completar en 4-5 meses
- **Tiempo total estimado:** 75 días + 20% buffer = 90 días (aprox. 4.5 meses con equipo de 2-3 devs)
