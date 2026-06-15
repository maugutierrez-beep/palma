# GVC Capital · Plataforma de Inversión en Palma de Aceite

## Qué es esto
Plataforma web de evaluación de inversiones en palma de aceite para la Zona Norte de Colombia (Valledupar, Cesar). Creada por Mauricio Gutiérrez para GVC Capital.

La aplicación COMPLETA vive en un solo archivo: **`index.html`**. Es una app React (cargada vía CDN con Babel en el navegador), autocontenida, sin dependencias de build. Eso la hace trivial de desplegar: GitHub Pages sirve el `index.html` directamente.

## Cómo está publicada
- Repositorio: `maugutierrez-beep/palma`
- Hosting: GitHub Pages (rama `main`, raíz `/`)
- URL en vivo: https://maugutierrez-beep.github.io/palma/
- Clave de acceso de la app: `gvc2026` (está dentro del index.html, constante CLAVE)

## Cómo publicar un cambio (IMPORTANTE)
Cada vez que edites `index.html`, publica con:
```
git add index.html
git commit -m "Descripción del cambio"
git push origin main
```
GitHub Pages republica solo en 1-2 minutos. NO se requiere build ni GitHub Actions: el index.html es estático y autocontenido.

## Estructura del proyecto
- `index.html` — LA APLICACIÓN COMPLETA. Aquí se hacen todos los cambios.
- `/build-version/` — versión opcional con Vite/build (NO es la que está publicada; ignorar salvo que se migre a build).
- `CLAUDE.md` — este archivo.

## Qué hace la plataforma (módulos)
1. **Inicio** — resumen del negocio de la palma en Colombia por zona, con datos Fedepalma.
2. **Evaluar finca** — evaluador de compra de finca: el usuario mete sus costos reales (precio tierra, mano de obra, riego, insumos), elige sembrar vs. comprar en producción, y ve TIR/VPN con deuda Finagro, impuesto de renta e inflación. Veredicto con semáforo.
3. **Extractora** (modo avanzado) — planta de beneficio, margen de maquila + spread de terceros.
4. **Mi empresa** — consolida varias fincas (núcleos) + extractora; EBITDA y valoración.
5. **Capital y salida** (modo avanzado) — valoración EV, dilución, control accionario.
6. **Mis proyectos** — guardar y comparar escenarios (localStorage).
7. **Glosario** — términos de palma explicados.

Modos: **simple** (didáctico) y **avanzado** (todos los parámetros). Selector de zona (Norte/Oriental/Central/Suroccidental) y de año de precio (2022-2026).

## Datos clave (anclados en Fedepalma/Cenipalma)
- Precio CPO referencia FEP/IPML: 2026 = COP 4.539.376/t (dato real). Años 2022-2025 son aproximaciones; AFINAR con Anuario Estadístico Fedepalma.
- Costos ICPA 2024: guineensis COP 478.501/t RFF, OxG COP 461.629/t RFF.
- Tasas de extracción y rendimientos por zona en la constante ZONAS dentro del index.html.

## Pendientes / mejoras futuras sugeridas
- Verificar precios CPO históricos exactos (2022-2025) con el Anuario Estadístico de Fedepalma.
- Verificar costos finos por zona rubro por rubro con el estudio ICPA completo.
- Reemplazar el recuadro "GVC" por el logo real de GVC Capital.
- Pulir la exportación a PDF para que salga como informe presentable a inversionistas.
- La clave de acceso es protección ligera (está en el cliente); si se requiere seguridad real, migrar a autenticación con backend.
