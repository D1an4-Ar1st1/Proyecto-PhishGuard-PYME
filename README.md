# PhishGuard PYME – Prototipo funcional TRL 5

Plataforma web de **capacitación, simulación controlada de phishing y monitoreo** para PYMES.
Proyecto de grado – Ingeniería de Sistemas, UNAD (ECBTI).

> Todos los datos son ficticios. Las simulaciones no capturan contraseñas ni datos reales.

## Acceso rápido
- **URL de pruebas:** https://claude.ai/artifact/LCHRWsnGtpz91UXjGxwqhY
- **Ejecución local:** abrir `prototipo/index.html` en un navegador moderno (sin instalación).

## Cuentas de demostración
| Rol | Usuario | Contraseña |
|---|---|---|
| Administrador | admin | Admin2026* |
| Supervisor | supervisor | Super2026* |
| Participante | ana / luis / marta | Ana2026* / Luis2026* / Marta2026* |

## Estructura
```
prototipo/   Aplicación (HTML5 + CSS3 + JavaScript, API simulada sobre localStorage)
tests/       Pruebas de extremo a extremo (Playwright + Chromium) – 29 casos
evidencias/  Capturas, video demostrativo y resultados_pruebas.json
docs/        Documento maestro del proyecto
```

## Pruebas
```bash
npm install
npx playwright install chromium
npm test            # APP_URL opcional para probar una URL publicada
```
Resultado de la última ejecución: **29/29 casos aprobados** (ver `evidencias/resultados_pruebas.json`).

## Arquitectura (frontend)
Vistas por rol → controlador de eventos/enrutador → estado y lógica de negocio → API simulada asíncrona → `localStorage`.
La API simulada replica el contrato de los servicios REST previstos (Django) para la versión de producción.

## Alcance y limitaciones (TRL 5)
Cobertura: 11 de 13 requerimientos funcionales completos y 2 parciales. Autenticación y datos simulados en el navegador
(contraseñas de demostración sin cifrado). Pendientes: servidor (Django/PostgreSQL), hash de contraseñas, MFA,
descarga de reportes, validación con usuarios (SUS) y piloto con PYMES reales.
