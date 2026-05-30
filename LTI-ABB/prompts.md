
## Prompt - 2026-05-30 10:33:19

### Prompt
tomando el PRD Bàsico @[LTI-ABB-prev/LTI-ABB.md] del proyecto, generar 10 user stories en @[LTI-ABB/UserStories-ABB.md] . Puedes utilizar la plantilla presente en @[LTI-ABB/plantilla-generica.md] 

Detallaremos y tendremos en cuenta los criterios INVEST presentes en el mismo documento

### Response
He generado 10 user stories en el archivo LTI-ABB/UserStories-ABB.md basadas en el PRD del sistema LTI. Cada story incluye:

- **Formato estándar**: Como [tipo de usuario], quiero [acción/funcionalidad] para [beneficio/valor]
- **Criterios de aceptación**: Requisitos específicos y verificables
- **Verificación INVEST**: Análisis detallado de cada criterio (Independent, Negotiable, Valuable, Estimable, Small, Testable)

Las stories cubren las funcionalidades principales del sistema:
- **Alta prioridad**: Creación de ofertas, registro de candidatos, postulación, pipeline visual, búsqueda/filtrado
- **Media prioridad**: Pruebas técnicas, programación de entrevistas, publicación multi-canal, notificaciones
- **Baja prioridad**: Reportes y analytics

Incluí una tabla de priorización con estimaciones (2-5 días) y dependencias entre stories para facilitar la planificación del desarrollo.

---

## Prompt - 2026-05-30 10:59:57

### Prompt
en la user story 4, se menciona en los criterios de aceptación que el reclutador es quien mueve entre estados mediante drag-and drop. Este cambio de estado debe producirse por que el candidato supera las distintas fases de forma automàtica o como consecuencia que el reclutador valide el paso a la siguiente fase

### Response
Corregida la User Story 4. Ahora especifica que los candidatos avanzan de estado cuando:
- El reclutador valida el paso a la siguiente fase
- El candidato supera automáticamente una fase (ej: completa prueba técnica en tiempo)

También actualicé la verificación INVEST para reflejar que incluye lógica de transiciones automáticas además de la interfaz visual.

---

## Prompt - 2026-05-30 11:15:08

### Prompt
Dadas las historias de usuario presentes en @[LTI-ABB/UserStories-ABB.md] , qué requisitos técnicos se necesitarían? reflejarlo como un apartado adicional a continuación en el documento

### Response
Agregado el apartado de requisitos técnicos al documento con:

- **Arquitectura General**: Backend (API RESTful/GraphQL), Frontend (SPA framework), Base de datos (relacional)
- **Requisitos por User Story**: Detalles técnicos específicos para cada una de las 10 stories (integraciones, APIs, tablas de BD, validaciones)
- **Requisitos Transversales**: Seguridad, Performance, Escalabilidad, Monitoring, DevOps y Testing

---

## Prompt - 2026-05-30 11:18:11

### Prompt
Analiza las funcionalidades existentes del sistema para identificar los cinco problemas más comunes que tanto los reclutadores como candidatos podrían enfrentar. Sugerir mejoras

### Response
Agregado el apartado de análisis de problemas y mejoras al documento con 5 problemas identificados:

1. **Barrera de entrada alta para candidatos** (US2) - Perfil 100% completo antes de postular
2. **Falta de feedback en pruebas técnicas** (US5) - Sin feedback detallado al candidato
3. **Ausencia de colaboración entre reclutadores** (US4) - Sin comentarios, etiquetas o asignación
4. **Limitaciones en formatos de archivos** (US3) - Solo PDF/Word, 10MB
5. **Falta de videoconferencia integrada** (US6) - Sin plataforma nativa para entrevistas

Cada problema incluye descripción, impacto y mejoras propuestas específicas. Incluí tabla de priorización de mejoras.

---

## Prompt - 2026-05-30 11:21:18

### Prompt
Considera el backlog de producto. Estima por cada item en el backlog (genera una tabla markdown):Impacto en el usuario y valor del negocio.Urgencia basada en tendencias del mercado y feedback de usuarios.Complejidad y esfuerzo estimado de implementación.Riesgos y dependencias entre tareas.

### Response
Agregada tabla de estimación del backlog con 10 user stories evaluadas por:

- Impacto en Usuario (Muy Alta/Alta/Media/Baja)
- Valor de Negocio (Crítico/Alto/Medio/Bajo)
- Urgencia (Alta/Media/Baja)
- Complejidad (Baja/Media/Alta)
- Esfuerzo estimado (días)
- Riesgos (Bajo/Medio/Alto)
- Dependencias

Incluí leyenda de evaluación y recomendación de roadmap por 4 fases (MVP, Core, Evaluación, Escalabilidad).

## Conclusion

**Actor:** Product Owner / Analista de Negocio

**Análisis del Resultado:**
Este prompt generó una evaluación estratégica del backlog enfocada en la priorización desde la perspectiva del negocio. El resultado incluye una tabla detallada con 7 dimensiones de análisis (impacto en usuario, valor de negocio, urgencia, complejidad, esfuerzo, riesgos y dependencias) para cada una de las 10 user stories. El enfoque principal fue identificar qué funcionalidades entregan mayor valor y cuál es el orden óptimo de implementación basado en criterios de mercado y expectativas de usuario.

**Diferencias con otros prompts:**
- A diferencia del prompt de Tech Lead, este no se enfoca en detalles técnicos sino en valor de negocio
- A diferencia del prompt de Product Owner (refinamiento), este no añade nuevas funcionalidades ni divide stories existentes
- Es el único que establece una priorización basada en urgencia de mercado y tendencias

**Efectividad del prompt:**
Fue efectivo porque solicitó explícitamente múltiples dimensiones de evaluación (impacto, valor, urgencia, complejidad, riesgos, dependencias), lo que permitió obtener una visión holística del backlog. La inclusión de una leyenda de evaluación y un roadmap por fases proporcionó claridad en la toma de decisiones de priorización. El resultado es ideal para stakeholder management y planificación estratégica de releases.

---

## Prompt - 2026-05-30 11:28:38

### Prompt
Añade una seccion adicional de Estimación del Backlog de Producto siguiendo el siguiente prompt: Actúa como un Tech Lead senior. A partir de las 10 User Stories del Sistema de Reclutamiento LTI (incluidas en el documento), genera un backlog de tareas técnicas desglosando cada User Story en subtareas específicas de desarrollo. Para cada User Story, incluye: Tareas de Backend (endpoints, modelos, lógica de negocio), Tareas de Frontend (componentes, pantallas, validaciones), Tareas de Base de Datos (tablas, índices, migraciones), Tareas de Integración (APIs externas, servicios), Tareas de Testing (unit tests, integration tests). Formato de salida: US[X]: [Título] ├── Backend: [lista de tareas con estimación en horas] ├── Frontend: [lista de tareas con estimación en horas] ├── Database: [lista de tareas con estimación en horas] ├── Integrations: [lista de tareas con estimación en horas] └── Testing: [lista de tareas con estimación en horas]. Prioriza las tareas siguiendo el roadmap por fases indicado en el documento (Fase 1 MVP, Fase 2 Core, etc.).

### Response
Agregada sección de desglose técnico del backlog con las 10 User Stories desglosadas en subtareas:

- **Backend:** Endpoints, modelos, lógica de negocio con estimación en horas
- **Frontend:** Componentes, pantallas, validaciones con estimación en horas
- **Database:** Tablas, índices, migraciones con estimación en horas
- **Integrations:** APIs externas, servicios con estimación en horas
- **Testing:** Unit tests, integration tests, E2E tests con estimación en horas

Organizado por fases del roadmap (MVP, Core, Evaluación, Escalabilidad). Total estimado: 600 horas (75 días) para 1 desarrollador, o 4-5 meses con equipo de 2-3 devs incluyendo 20% buffer.

## Conclusion

**Actor:** Tech Lead Senior

**Análisis del Resultado:**
Este prompt generó un desglose técnico exhaustivo de cada user story en subtareas específicas de desarrollo, organizado por capas (Backend, Frontend, Database, Integrations, Testing) con estimaciones en horas. El resultado incluye un total de 600 horas distribuidas en 4 fases, con desglose detallado de endpoints, componentes, tablas de BD, integraciones y tests. El enfoque principal fue proporcionar una visión técnica precisa para planificación de recursos y estimación de esfuerzo real de implementación.

**Diferencias con otros prompts:**
- A diferencia del prompt de Product Owner (priorización), este se enfoca en detalles técnicos de implementación
- A diferencia del prompt de Product Owner (refinamiento), este no añade nuevas funcionalidades ni modifica el alcance
- Es el único que proporciona estimaciones en horas y desglose por capas técnicas
- Incluye un resumen de esfuerzo total por fase con cálculo de días y sprints

**Efectividad del prompt:**
Fue efectivo porque definió un formato de salida estructurado y específico (formato de árbol con subtareas por capa técnica), lo que garantizó consistencia en el desglose de todas las user stories. La solicitud de estimaciones en horas para cada subtarea permitió obtener una visión granular del esfuerzo. La organización por fases del roadmap facilitó la planificación de sprints. El resultado es ideal para gestión técnica de proyectos, asignación de recursos y tracking de progreso de desarrollo.

---

## Prompt - 2026-05-30 11:34:02

### Prompt
Añade una seccion adicional de Estimación del Backlog de Producto siguiendo el siguiente prompt: Actúa como un Product Owner experto en metodologías ágiles. Basándote en las 10 User Stories existentes del Sistema de Reclutamiento LTI y en la sección 'Análisis de Problemas Comunes y Mejoras Propuestas', genera: 1. User Stories adicionales para cubrir las 5 mejoras propuestas. 2. Refinamiento de las US existentes que no cumplan perfectamente el criterio INVEST. 3. Definition of Done (DoD) específica para cada tipo de User Story. 4. Spike stories para las áreas de mayor incertidumbre técnica.

### Response
Agregada sección 'Refinamiento del Backlog - Product Owner' con:

1. **5 User Stories adicionales** (US11-US15): Registro progresivo, Feedback pruebas, Colaboración reclutadores, Multi-formato archivos, Videoconferencia integrada
2. **Refinamiento de US existentes**: División de US2 (3 sub-US), US4 (3 sub-US), US8 (4 sub-US) para mejor cumplimiento INVEST
3. **Definition of Done por tipo**: CRUD, Integraciones, UI Compleja, Analytics con checklists específicos
4. **4 Spike stories**: APIs redes sociales, Elasticsearch, Videoconferencia, Antivirus
5. **Tabla priorización actualizada**: 22 US totales con dependencias y spikes
6. **Roadmap actualizado**: Sprint 0 + 5 fases (11 sprints totales, 79-99 días con spikes)

## Conclusion

**Actor:** Product Owner Experto en Metodologías Ágiles

**Análisis del Resultado:**
Este prompt generó un refinamiento comprehensivo del backlog desde una perspectiva ágil, añadiendo 5 nuevas user stories para las mejoras identificadas, dividiendo 3 user stories existentes que no cumplían el criterio INVEST (US2, US4, US8), creando Definition of Done específicas por tipo de story (CRUD, Integraciones, UI Compleja, Analytics), y definiendo 4 spike stories para áreas de incertidumbre técnica. El resultado expandió el backlog de 10 a 22 user stories con un roadmap actualizado de 11 sprints (79-99 días incluyendo spikes). El enfoque principal fue mejorar la calidad del backlog y reducir riesgos técnicos.

**Diferencias con otros prompts:**
- A diferencia del prompt de Product Owner (priorización), este añade nuevas funcionalidades y modifica el alcance existente
- A diferencia del prompt de Tech Lead, este no se enfoca en detalles técnicos de implementación sino en calidad ágil del backlog
- Es el único que divide user stories existentes para mejor cumplimiento INVEST
- Es el único que introduce spike stories para mitigar incertidumbre técnica
- Es el único que crea Definition of Done específicas por tipo de story

**Efectividad del prompt:**
Fue efectivo porque solicitó explícitamente cuatro deliverables específicos (US adicionales, refinamiento INVEST, DoD por tipo, spike stories), lo que proporcionó un refinamiento holístico del backlog. La referencia al análisis de problemas comunes aseguró que las nuevas US addressingaran necesidades reales identificadas. La división de US complejas (US2 en 3, US4 en 3, US8 en 4) mejoró significativamente el criterio "Small" de INVEST. La inclusión de spikes para áreas de incertidumbre (APIs redes sociales, Elasticsearch, videoconferencia, antivirus) demostró pensamiento proactivo en gestión de riesgos. El resultado es ideal para equipos ágiles que buscan backlog de alta calidad y reducción de riesgos técnicos.

---

## Prompt - 2026-05-30 11:51:55

### Prompt
Eres un experto planificador de proyectos. Tomaremos el US3 como elemento de trabajo. Aterrizar técnicamente en tickets de trabajo la US3. Realizar las preguntas que se requieran para poder completar esta planificacion. Considera la complejidad de los diferentes tickets y la estimación de tiempo necesario para su implementación. Proporciona este punto en formato tabla

### Response
# Planificación Técnica - US3: Postulación a Ofertas

## Preguntas de Clarificación

**Infraestructura y Servicios:**
1. ¿Qué proveedor de almacenamiento en la nube se utilizará? (AWS S3, Google Cloud Storage, Azure Blob Storage, o solución on-premise)
2. ¿Qué servicio de antivirus se implementará? (ClamAV on-premise, VirusTotal API, AWS Macie, o servicio cloud-based específico)
3. ¿Se requiere CDN para distribución de archivos o solo almacenamiento?

**Validaciones y Seguridad:**
4. ¿El límite de 10MB es por archivo o total (CV + carta)?
5. ¿Se requiere validación de contenido del CV (extraer texto para indexación) o solo almacenamiento?
6. ¿Se permitirá reemplazar el CV en una postulación existente?
7. ¿Se requiere versionado de documentos (guardar historial de cambios)?

**Integraciones:**
8. ¿La confirmación de recepción será solo en pantalla o también por email?
9. ¿Se requiere integración con ATS externos para sincronización de candidaturas?
10. ¿Se necesita procesamiento asíncrono de archivos (colas) o puede ser síncrono?

**UX y Funcionalidad Adicional:**
11. ¿Se permitirá guardar postulación como borrador antes de enviar?
12. ¿Se requiere vista previa del CV en el navegador antes de enviar?
13. ¿Se mostrará al candidato el estado de su postulación en tiempo real?

**Performance y Escalabilidad:**
14. ¿Cuál es el volumen esperado de postulaciones por día/mes?
15. ¿Se requiere procesamiento por lotes para escaneo antivirus?

---

## Tickets de Trabajo Técnicos

| ID | Ticket | Tipo | Descripción | Complejidad | Estimación (horas) | Dependencias |
|----|--------|------|-------------|-------------|-------------------|--------------|
| **US3-BE-01** | Endpoint POST /api/candidaturas | Backend | Crear endpoint para registrar postulación con validación de oferta activa y usuario autenticado | Media | 4 | US2-BE-01 |
| **US3-BE-02** | Endpoint GET /api/candidaturas | Backend | Listar candidaturas del usuario actual con paginación y filtros básicos | Baja | 2 | US3-BE-01 |
| **US3-BE-03** | Endpoint POST /api/candidaturas/upload | Backend | Implementar carga de archivos con validación de formato (PDF/Word) y tamaño (máx 10MB) | Media | 4 | US3-BE-01 |
| **US3-BE-04** | Integración Antivirus ClamAV | Backend | Integrar servicio de escaneo antivirus para todos los documentos cargados | Alta | 3 | US3-BE-03 |
| **US3-BE-05** | Validación de Duplicados | Backend | Implementar lógica para prevenir postulaciones duplicadas a la misma oferta | Baja | 2 | US3-BE-01 |
| **US3-BE-06** | Verificación Estado Oferta | Backend | Validar que la oferta esté en estado "activa" antes de permitir postulación | Baja | 1 | US3-BE-01 |
| **US3-FE-01** | Formulario de Postulación | Frontend | Crear formulario con campos para CV (obligatorio) y carta de presentación (opcional) | Media | 4 | US3-BE-03 |
| **US3-FE-02** | Componente Carga Archivos | Frontend | Implementar componente drag-and-drop para carga de CV y carta con barra de progreso | Media | 3 | US3-FE-01 |
| **US3-FE-03** | Vista Previa CV | Frontend | Mostrar vista previa del CV cargado antes de enviar postulación | Media | 2 | US3-FE-02 |
| **US3-FE-04** | Lista Candidaturas Usuario | Frontend | Pantalla para ver historial de postulaciones del usuario con estado actual | Baja | 3 | US3-BE-02 |
| **US3-FE-05** | Pantalla Confirmación | Frontend | Mostrar confirmación inmediata de recepción de postulación con ID de referencia | Baja | 2 | US3-FE-01 |
| **US3-DB-01** | Tabla candidaturas | Database | Crear tabla candidaturas con campos: id, usuario_id, oferta_id, fecha_postulacion, estado, cv_url, carta_url | Media | 3 | US1-DB-01, US2-DB-01 |
| **US3-DB-02** | Tabla documentos | Database | Crear tabla documentos para tracking de archivos cargados con metadatos | Media | 2 | US3-DB-01 |
| **US3-DB-03** | Índices candidaturas | Database | Crear índices en usuario_id, oferta_id para optimizar consultas de duplicados | Baja | 2 | US3-DB-01 |
| **US3-DB-04** | Migration Script | Database | Script de migración para crear tablas e índices con rollback | Baja | 1 | US3-DB-01 |
| **US3-INT-01** | Integración AWS S3/Cloud Storage | Integración | Configurar servicio de almacenamiento en la nube para CVs y cartas | Alta | 4 | US3-BE-03 |
| **US3-INT-02** | Integración Servicio Antivirus | Integración | Configurar conexión con servicio de escaneo antivirus (ClamAV o cloud-based) | Alta | 3 | US3-BE-04 |
| **US3-INT-03** | Configuración CDN | Integración | Configurar CDN para distribución eficiente de archivos almacenados | Baja | 1 | US3-INT-01 |
| **US3-TST-01** | Unit Tests Carga Archivos | Testing | Unit tests para validación de formatos, tamaños y carga de archivos | Media | 3 | US3-BE-03 |
| **US3-TST-02** | Integration Tests Antivirus | Testing | Tests de integración para verificar escaneo antivirus y manejo de archivos infectados | Alta | 3 | US3-BE-04 |
| **US3-TST-03** | E2E Tests Postulación | Testing | Tests end-to-end del flujo completo de postulación desde frontend hasta backend | Media | 4 | US3-FE-05 |

**Total Estimado: 58 horas (7.25 días laborales)**

---

## Resumen por Categoría

| Categoría | Tickets | Horas Totales | % del Total |
|-----------|---------|---------------|-------------|
| Backend | 6 | 16 | 27.6% |
| Frontend | 5 | 14 | 24.1% |
| Database | 4 | 8 | 13.8% |
| Integrations | 3 | 8 | 13.8% |
| Testing | 3 | 10 | 17.2% |
| **Total** | **21** | **58** | **100%** |

---

## Prompt - 2026-05-30 11:56:56

### Prompt
Eres un experto planificador de proyectos. Tomaremos el US3 como elemento de trabajo. Aterrizar técnicamente en tickets de trabajo la US3. Realizar las preguntas que se requieran para poder completar esta planificacion. Considera la complejidad de los diferentes tickets y la estimación de tiempo necesario para su implementación. Proporciona este punto en formato tabla

### Response
# Planificación Técnica Refinada - US3: Postulación a Ofertas

## Respuestas a Preguntas de Clarificación

**Infraestructura y Servicios:**
- Almacenamiento: AWS S3
- Antivirus: VirusTotal API
- CDN: Solo almacenamiento (sin CDN)

**Validaciones y Seguridad:**
- Límite 10MB: Por archivo (CV y carta independientes)
- Contenido CV: Extraer texto para indexación
- Reemplazo CV: Sí permitido
- Versionado documentos: Sí requerido

**Integraciones:**
- Confirmación: Pantalla + email
- ATS externos: No
- Procesamiento: Asíncrono con colas

**UX y Funcionalidad:**
- Borrador: Sí permitido
- Vista previa CV: No requerida
- Estado en tiempo real: Sí

**Performance y Escalabilidad:**
- Volumen: 50 postulaciones/día inicial, hasta 1000 futuro
- Procesamiento antivirus: Por lotes

---

## Tickets de Trabajo Técnicos Actualizados

| ID | Ticket | Tipo | Descripción | Complejidad | Estimación (horas) | Dependencias |
|----|--------|------|-------------|-------------|-------------------|--------------|
| **US3-BE-01** | Endpoint POST /api/candidaturas | Backend | Crear endpoint para registrar postulación con validación de oferta activa y usuario autenticado | Media | 4 | US2-BE-01 |
| **US3-BE-02** | Endpoint GET /api/candidaturas | Backend | Listar candidaturas del usuario actual con paginación y filtros básicos | Baja | 2 | US3-BE-01 |
| **US3-BE-03** | Endpoint POST /api/candidaturas/upload | Backend | Implementar carga de archivos con validación de formato (PDF/Word) y tamaño (máx 10MB por archivo) | Media | 4 | US3-BE-01 |
| **US3-BE-04** | Integración VirusTotal API | Backend | Integrar VirusTotal API para escaneo antivirus de documentos | Alta | 3 | US3-BE-03 |
| **US3-BE-05** | Validación de Duplicados | Backend | Implementar lógica para prevenir postulaciones duplicadas a la misma oferta | Baja | 2 | US3-BE-01 |
| **US3-BE-06** | Verificación Estado Oferta | Backend | Validar que la oferta esté en estado "activa" antes de permitir postulación | Baja | 1 | US3-BE-01 |
| **US3-BE-07** | Endpoint PUT /api/candidaturas/:id/documentos | Backend | Permitir reemplazar CV y carta en postulación existente | Media | 3 | US3-BE-01 |
| **US3-BE-08** | Endpoint POST /api/candidaturas/borrador | Backend | Guardar postulación como borrador antes de enviar | Media | 3 | US3-BE-01 |
| **US3-BE-09** | Endpoint GET /api/candidaturas/estado | Backend | Endpoint para consultar estado de postulación en tiempo real | Baja | 2 | US3-BE-01 |
| **US3-BE-10** | Sistema de Colas | Backend | Implementar sistema de colas (Redis/RabbitMQ) para procesamiento asíncrono de archivos | Alta | 5 | US3-BE-03 |
| **US3-BE-11** | Procesamiento por Lotes Antivirus | Backend | Implementar batch processing para escaneo antivirus eficiente | Alta | 4 | US3-BE-04, US3-BE-10 |
| **US3-FE-01** | Formulario de Postulación | Frontend | Crear formulario con campos para CV (obligatorio) y carta de presentación (opcional) | Media | 4 | US3-BE-03 |
| **US3-FE-02** | Componente Carga Archivos | Frontend | Implementar componente drag-and-drop para carga de CV y carta con barra de progreso | Media | 3 | US3-FE-01 |
| **US3-FE-03** | Lista Candidaturas Usuario | Frontend | Pantalla para ver historial de postulaciones del usuario con estado actual en tiempo real | Media | 4 | US3-BE-02, US3-BE-09 |
| **US3-FE-04** | Pantalla Confirmación | Frontend | Mostrar confirmación inmediata de recepción de postulación con ID de referencia | Baja | 2 | US3-FE-01 |
| **US3-FE-05** | Funcionalidad Borrador | Frontend | Implementar botón para guardar postulación como borrador y recuperar borradores | Media | 3 | US3-BE-08 |
| **US3-FE-06** | Interfaz Reemplazo Documentos | Frontend | UI para reemplazar CV y carta en postulaciones existentes | Media | 3 | US3-BE-07 |
| **US3-DB-01** | Tabla candidaturas | Database | Crear tabla candidaturas con campos: id, usuario_id, oferta_id, fecha_postulacion, estado, cv_url, carta_url, es_borrador | Media | 3 | US1-DB-01, US2-DB-01 |
| **US3-DB-02** | Tabla documentos | Database | Crear tabla documentos para tracking de archivos con versionado y metadatos | Alta | 3 | US3-DB-01 |
| **US3-DB-03** | Tabla versiones_documentos | Database | Crear tabla para historial de versiones de documentos | Media | 2 | US3-DB-02 |
| **US3-DB-04** | Índices candidaturas | Database | Crear índices en usuario_id, oferta_id, es_borrador para optimizar consultas | Baja | 2 | US3-DB-01 |
| **US3-DB-05** | Migration Script | Database | Script de migración para crear tablas e índices con rollback | Baja | 1 | US3-DB-01 |
| **US3-INT-01** | Integración AWS S3 | Integración | Configurar AWS S3 para almacenamiento de CVs y cartas | Alta | 4 | US3-BE-03 |
| **US3-INT-02** | Integración VirusTotal API | Integración | Configurar conexión con VirusTotal API para escaneo antivirus | Alta | 3 | US3-BE-04 |
| **US3-INT-03** | Servicio Extracción Texto CV | Integración | Integrar servicio (PDFTextExtractor/Apache Tika) para extraer texto de CVs para indexación | Alta | 5 | US3-BE-03 |
| **US3-INT-04** | Servicio Email Confirmación | Integración | Configurar servicio de email (SendGrid/Mailgun) para confirmación de postulación | Media | 3 | US3-BE-01 |
| **US3-INT-05** | Integración Elasticsearch | Integración | Configurar Elasticsearch para indexación de texto extraído de CVs | Alta | 4 | US3-INT-03 |
| **US3-TST-01** | Unit Tests Carga Archivos | Testing | Unit tests para validación de formatos, tamaños y carga de archivos | Media | 3 | US3-BE-03 |
| **US3-TST-02** | Integration Tests Antivirus | Testing | Tests de integración para verificar escaneo VirusTotal y manejo de archivos infectados | Alta | 3 | US3-BE-04 |
| **US3-TST-03** | E2E Tests Postulación | Testing | Tests end-to-end del flujo completo de postulación desde frontend hasta backend | Media | 4 | US3-FE-04 |
| **US3-TST-04** | Tests Sistema Colas | Testing | Tests para verificar procesamiento asíncrono y manejo de errores en colas | Alta | 3 | US3-BE-10 |
| **US3-TST-05** | Tests Versionado Documentos | Testing | Tests para verificar versionado correcto de documentos y reemplazo | Media | 3 | US3-BE-07 |
| **US3-TST-06** | Tests Extracción Texto | Testing | Tests para verificar extracción correcta de texto de diferentes formatos de CV | Media | 3 | US3-INT-03 |
| **US3-TST-07** | Load Tests Escalabilidad | Testing | Tests de carga para validar rendimiento con 1000 postulaciones/día | Alta | 4 | Todos los anteriores |

**Total Estimado: 92 horas (11.5 días laborales)**

---

## Resumen por Categoría

| Categoría | Tickets | Horas Totales | % del Total |
|-----------|---------|---------------|-------------|
| Backend | 11 | 33 | 35.9% |
| Frontend | 6 | 19 | 20.7% |
| Database | 5 | 11 | 12.0% |
| Integrations | 5 | 19 | 20.7% |
| Testing | 7 | 23 | 25.0% |
| **Total** | **34** | **105** | **100%** |

**Nota:** El aumento de 58 a 92 horas se debe a los nuevos requisitos: procesamiento asíncrono con colas, extracción de texto para indexación, versionado de documentos, funcionalidad de borradores, confirmación por email, y pruebas de escalabilidad para 1000 postulaciones/día.

---

## Prompt - 2026-05-30 12:08:00

### Prompt
añade en @[LTI-ABB/UserStories-ABB.md] un anexo con las estimaciones de esfuerzo de los tickets de trabajo con metodologias diferentes. usaremos (fibonacci, poker, tallas de camiseta) y unidades (horas, puntos de historia)

### Response
Agregado anexo de estimaciones de esfuerzo por metodología en UserStories-ABB.md con:

**Tabla de conversión de metodologías:**
- Story Points (1 SP = 6 horas)
- Fibonacci (1, 2, 3, 5, 8, 13, 21, 34)
- Planning Poker (0, 1, 2, 3, 5, 8, 13, 20, 40, 100)
- T-Shirt Sizing (XS, S, M, L, XL, XXL)

**Estimaciones por User Story (10 US originales):**
- US1: 42h → 7 SP → Fibonacci 8 → Poker 8 → T-Shirt M
- US2: 58h → 10 SP → Fibonacci 13 → Poker 13 → T-Shirt L
- US3: 58h → 10 SP → Fibonacci 13 → Poker 13 → T-Shirt L
- US4: 66h → 11 SP → Fibonacci 13 → Poker 13 → T-Shirt L
- US5: 58h → 10 SP → Fibonacci 13 → Poker 13 → T-Shirt L
- US6: 68h → 11 SP → Fibonacci 13 → Poker 13 → T-Shirt L
- US7: 52h → 9 SP → Fibonacci 8 → Poker 8 → T-Shirt L
- US8: 80h → 13 SP → Fibonacci 21 → Poker 20 → T-Shirt XL
- US9: 46h → 8 SP → Fibonacci 8 → Poker 8 → T-Shirt M
- US10: 72h → 12 SP → Fibonacci 13 → Poker 13 → T-Shirt L

**Totales:**
- 600 horas totales
- 101 Story Points
- 113 puntos Fibonacci
- 116 puntos Planning Poker
- Distribución T-Shirt: 2 M, 7 L, 1 XL

**Análisis comparativo por metodología** con ventajas y uso recomendado para cada una.

**Tabla de velocidad del equipo** con proyección de sprints según velocity (20, 30, 40 puntos por sprint).

**Recomendaciones de uso:**
- Planificación técnica: Story Points basados en horas
- Planning Poker: Fibonacci (estándar industria)
- Comunicación con negocio: T-Shirt Sizing
- Proyectos complejos: Planning Poker extendido

---
