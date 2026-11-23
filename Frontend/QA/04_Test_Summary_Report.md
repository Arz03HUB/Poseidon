# Informe de ejecución de QA — Poseidon

Fecha: 2026-11-15 (America/La_Paz).

## Resultado

- Backend: 47 pruebas automáticas aprobadas; 0 fallidas, canceladas u omitidas. Duración: 5388 ms.
- Frontend: compilación de producción aprobada con `npm run build`.
- Catálogo manual: TC-NFR-009 aprobado mediante ejecución directa de la suite. Los otros 160 casos permanecen sin ejecutar de forma completa.
- No se establece aceptación de la versión con estos resultados: falta ejecutar el catálogo manual y validar MySQL.

## Evidencia

- [Salida del backend](ejecucion_backend_2026-11-15.log).
- [Salida de compilación](compilacion_frontend_2026-11-15.log).
- [Hoja de ejecución de los 161 casos](05_Test_Execution_2026-11-15.csv).

La hoja original y el documento Word no se modificaron. La compilación es una comprobación adicional y no sustituye pruebas visuales.

## Funciones ejercitadas automáticamente

La suite contiene pruebas de componente y pruebas de integración que arrancan servidores reales del backend y realizan peticiones HTTP. Las integraciones usan memoria, carpetas temporales y servicios externos desactivados o simulados según cada prueba.

| Área | Comprobaciones incluidas en la suite |
|---|---|
| Autenticación y permisos | Credenciales incorrectas, peticiones sin sesión, permisos y cambios inmediatos, usuario desactivado |
| Administración | Registro, validaciones, aprobación y auditoría sin credenciales |
| Parcelas | Registro, perímetros, coordenadas, superficie, terreno e historial |
| Rotaciones | Tres estrategias, prioridades, clima, ladera y presión de plagas |
| Asistencia | Asignación, revisión técnica, visitas, CSV y validaciones locales |
| Monitoreo | Agregados, privacidad de grupos pequeños, escenarios, adopción y NDVI |
| Alertas | Detección de helada y sequía, preferencias, teléfono y alerta de prueba |
| Comercio | Oferta sostenible, filtros, privacidad, solicitudes y pausa de ofertas |
| Incidencias | Fotos, detección de tipo de imagen y efecto de plagas en la rotación |
| Respaldos | Creación, restauración y conservación de las tablas incluidas |

Estas comprobaciones aportan evidencia parcial para varios casos manuales, pero no equivalen a ejecutar sus pasos completos en el navegador.

## Pendientes y limitaciones

- No hay herramienta de navegador disponible ni Playwright/Puppeteer instalado en el proyecto. No se verificaron interacciones visuales, Session Storage, responsive, accesibilidad, service worker ni rendimiento en 3G.
- No se comprobó persistencia con MySQL; las integraciones ejecutadas fuerzan modo memoria.
- No se verificaron dispositivos GPS, permisos del navegador, entrega real de Web Push/SMS ni Google Drive real.
- Los casos de alertas y respaldos que cambian configuración, reloj o datos deben ejecutarse en un ambiente de QA preparado.
- Los 160 casos pendientes mantienen el estado `No ejecutado`; no se atribuye aprobación por similitud con una prueba automática.
