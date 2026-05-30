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
