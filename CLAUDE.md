# ARISTOMAS® — Briefing permanente para Claude
*Actualizado: Mayo 2026 · Leer completo antes de cualquier acción*

---

## 1. QUÉ ES ARISTOMAS

Plataforma de entrenamiento en virtudes. 21 días · una virtud · 9 min/día. Fundamento: Aristóteles + Tomás de Aquino. No es autoayuda, no es meditación, no es productividad. Es práctica filosófica estructurada.

**Frase central:** "El carácter no se aprende. Se practica."
**Tagline:** "Sigue transformándote · Capa a capa. Lo que entrenas, se queda."
**Mercado:** 500M hispanohablantes, núcleo LATAM.

**Virtudes (12 en total):** Solo Paciencia tiene ciclo completo. El resto: próximamente.
**Ciclos en producción (guionizados):** Paciencia, Laboriosidad, Orden (al menos 3 confirmados).

---

## 2. ARCHIVOS DEL PROYECTO

| Archivo | Descripción |
|---------|-------------|
| `index.html` | Web principal (GitHub Pages) |
| `aristomas-logo.html` | SVG del logo (AT geométrico dorado) |
| `aristomas-impulsores.html` | Página oculta para colaboradores/inversores |
| `ciclos/paciencia.html` | Ciclo completo Paciencia (autónomo) |
| `ciclos/[otras virtudes].html` | Mismo patrón para cada virtud |
| `NOTAS INTERNAS.md` | Decisiones estratégicas pendientes |
| `CLAUDE.md` | Este archivo — briefing permanente |
| `Aristomas_Modelo_Financiero.xlsx` | Modelo P&L con churn (openpyxl) |
| `Aristomas_OnePager_Inversor_Dark.docx` | One-pager inversor (fondo oscuro) |
| `Aristomas_OnePager_Inversor_Light.docx` | One-pager inversor (fondo claro) |

**GitHub:** https://github.com/QV69/Aristomas1 → https://qv69.github.io/Aristomas1

---

## 3. ARQUITECTURA WEB

- Un solo HTML por página, CSS+JS embebidos, sin frameworks, sin servidor
- Desplegado en GitHub Pages (rama `main`)
- Para publicar: `git add [archivos] && git commit -m "..." && git push origin main`

**Design tokens:**
```css
--bg: #08080F; --surface: #10101A; --card: #16161F;
--gold: #C8A45A; --gold-dim: rgba(200,164,90,0.18); --gold-glow: rgba(200,164,90,0.08);
--text: #EDE8DF; --muted: #6B6B7E; --radius: 16px;
```
**Fuentes:** Playfair Display (titulares) + Inter (cuerpo)
**Animaciones:** `.reveal` → IntersectionObserver → clase `.visible`

### Estructura index.html (secciones en orden):
1. Nav fijo glass blur
2. Hero — "El carácter no se aprende. Se practica."
3. Concept strip 4 columnas: 01 Elige virtud / 02 Transfórmate (9min/día) / 03 Masterclass con el Mánager / 04 Elige una nueva y avanza
4. Sección "El Método" — fases con mockup app a la derecha:
   - 📖 Contemplación (días 1–7)
   - 💪 Acción (días 8–14)
   - ★ Masterclass de Cierre (días 20–21) — dorado, especial
   - ∞ Consolidación: "Sigue transformándote" / "Cuando estés listo, elige la siguiente virtud. Capa a capa. Lo que entrenas, se queda."
5. Virtudes (12 cards, solo Paciencia clickable)
6. Para quién / diferenciadores
7. CTA final + footer
8. Etiqueta "— Ejemplo de uso —" encima del mockup app

### Masterclass (texto canónico en toda la web):
> "Al completar el ciclo, desbloqueas la masterclass del Mánager de la Virtud: 20–25 minutos de repaso integrador, perspectivas sobre la consolidación y una ronda de Q&A."

### Consolidación (texto canónico):
> H3: "Sigue transformándote"
> P: "Cuando estés listo, elige la siguiente virtud. Capa a capa. Lo que entrenas, se queda."

---

## 4. ESTRUCTURA SOCIETARIA

| Entidad | Nombre | Rol |
|---------|--------|-----|
| ATM1 | Aristomas S.L. | Empresa operativa (producto, ingresos) |
| ATM45 | ImpulsAristomas | SPV que posee 45% de ATM1 · vehículo inversor |

**Cap table ATM45 (objetivo ronda 1):**
- Inversores cash: ~33% (pool de ~99.000€ a valoración 300.000€)
- VirtuManagers: 7% (7 × 1%, vesting por hitos)
- Influencers: 5% (5 × 1%, vesting por hitos)
- Anchor investor: 7,5% (22.500€, entrada pre-constitución)
- Fundador: resto

**Orden de constitución:**
1. Acuerdo verbal con anchor
2. Constituir ATM45
3. Constituir ATM1
4. Formalizar con préstamo participativo convertible
5. Closing ronda 1: septiembre 2026

**Ley Startups 2023:** IS 15% primeros 4 años + deducción IRPF 50% para inversores.

**Pendiente:** Consulta abogado estructura Dubai Free Zone (agosto 2026, coste estimado 2.000–3.000€).

---

## 5. NÚMEROS FINANCIEROS (CANÓNICOS)

**Precios:**
- 9,99€/ciclo · 12,99€/mes · 99,99€/año · 69,99€ pionero

**ARPU:** 83€/usuario/año (99,99€ ÷ 1,21 IVA = 82,6€ ≈ 83€ neto)
**Churn anual:** 25% (usuarios_fin = round(prev × 0,75) + nuevos_captados)
**LTV:** 83€ × 4 años = 332€

**Proyección Optimista revisado (escenario canónico):**

| Año | Nuevos | Usuarios fin | Ingresos | Costes | Resultado | Acum |
|-----|--------|--------------|----------|--------|-----------|------|
| 1 | 700 | 700 | 58.100€ | 132.000€ | -73.900€ | -73.900€ |
| 2 | 800 | 1.325 | 109.975€ | 129.000€ | -19.025€ | -92.925€ |
| 3 | 1.100 | 2.094 | 173.802€ | 155.000€ | +18.802€ | -74.123€ |
| 4 | 1.500 | 3.071 | 254.893€ | 175.000€ | +79.893€ | +5.770€ |
| 5 | 1.850 | 4.153 | 344.699€ | 185.000€ | +159.699€ | +165.469€ |

**Costes Año 1 (~120.000€ presupuesto):**
- Plataforma/tech: 25.000€
- Marketing/publi: 25.000€
- Producción contenido: 18.000€
- VirtuManagers (fees producción): variable
- Fundador: sin salario hasta beneficios

**CAC estimado (paid media LATAM):**
- Optimista: 14€ · Realista: 60€ · Conservador: 350€
- CAC máximo sostenible (ratio 3:1 LTV): 110€
- 25.000€ marketing Año 1 ÷ 60€ CAC = ~416 usuarios vía paid. Resto: influencers + orgánico.

---

## 6. EQUIPO / COLABORADORES

### VirtuManagers (7 perfiles, 1% equity c/u):
- Director Filosófico (reunión pendiente)
- Otros 5+1 perfiles definidos, pendientes de contactar
- Vesting: por hitos (firma · entrega · lanzamiento · año 1)

### Influencers (5 perfiles, 1% equity c/u):
- Perfiles definidos por el fundador (acceso personal directo)
- Pendientes de contactar (fundador consulta perfil a perfil)

### Acceso lifetime (2 cuentas de por vida):
- VirtuManagers + Influencers + Inversores ≥1.000€

---

## 7. TIMELINE

| Fecha | Hito |
|-------|------|
| Julio 2026 | Beta gratuita · 30–40 usuarios |
| Agosto 2026 | Beta de pago · 30 usuarios pioneros |
| Septiembre 2026 | Lanzamiento beta · 3 virtudes · Closing ronda 1 |
| Feb–Mar 2027 | Lanzamiento completo · 12 virtudes |

---

## 8. EMBAJADORES / PROGRAMA DE REFERIDOS

Mecanismo favorito para inversores que traigan a otros:
- **Warrants** (opción a comprar X% adicional de ATM45 al mismo precio, ejercitable en próxima ronda). Coste cero ahora.
- **Pro-rata preferente**: derecho (no obligación) a mantener % en futura ronda comprando nuevas participaciones emitidas.
- Descartado: comisión en cash (sin margen) y bonus 1% equity directo (demasiado dilutivo).

**Concepto clave dilución:** Los nuevos inversores NO compran % de los actuales. ATM45 emite participaciones nuevas (ampliación de capital). El pastel crece y los % anteriores se reducen proporcionalmente. La pro-rata protege al anchor.

---

## 9. MARKETING — EMBUDO DE CONVERSIÓN

```
IMPRESIONES → (CTR 1-2%) → VISITAS → (conv 5-10%) → LEADS → (activación 40%) → PRUEBA → (conv 20%) → PAGO
```

Visitas necesarias por usuario pagante: 333 (optimista) · 2.500 (realista) · 50.000 (conservador)

Canales prioritarios: Instagram/Meta Ads LATAM + Influencers equity + Orgánico/SEO (largo plazo)

---

## 10. PROTOCOLO DE SESIÓN

Al inicio de cada sesión con este proyecto:
1. Leer este archivo (CLAUDE.md)
2. Leer NOTAS INTERNAS.md si hay trabajo estratégico pendiente
3. No inventar números — todos los financieros están en la sección 5
4. Antes de editar web: verificar texto canónico en secciones 3

Al final de sesión importante: actualizar CLAUDE.md con decisiones nuevas.

---

*CLAUDE.md · Aristomas · v2.0 · Mayo 2026*
