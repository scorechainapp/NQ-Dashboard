# NQ Command Center — Silver Bullet Dashboard

Panel de trading diseñado para operar el **NQ (Nasdaq E-mini Futures)** usando la estrategia **ICT Silver Bullet** con análisis de Market Maker (MM) y niveles institucionales.

---

## Archivos incluidos

| Archivo | Descripción |
|---|---|
| `nq_dashboard_dark_v4.html` | Dashboard versión oscura (recomendada) |
| `nq_dashboard_v2.html` | Dashboard versión blanca |
| `SilverBulletV5.cs` | Bot NinjaScript para NinjaTrader 8 |

---

## Cómo abrir el dashboard

El dashboard usa el widget de TradingView para mostrar la gráfica del NQ en vivo. Por seguridad del browser, **no funciona abriendo el archivo directamente** — necesita correr en un servidor local.

### Opción A — VS Code + Live Server (recomendada)

1. Descarga **VS Code** en `code.visualstudio.com`
2. Instala la extensión **Live Server** desde el panel de Extensions
3. Abre la carpeta del proyecto en VS Code
4. Click derecho sobre el archivo HTML → **Open with Live Server**
5. Se abre automáticamente en `http://localhost:5500`

### Opción B — Python

Si tienes Python instalado, abre una terminal en la carpeta del proyecto y ejecuta:

```bash
# Python 3
python -m http.server 8080

# Python 2
python -m SimpleHTTPServer 8080
```

Luego abre en el browser: `http://localhost:8080/nq_dashboard_dark_v4.html`

### Opción C — GitHub Pages (acceso desde cualquier dispositivo)

1. Crea una cuenta en `github.com`
2. Crea un repositorio nuevo llamado `nq-dashboard`
3. Sube todos los archivos
4. Ve a **Settings → Pages → Branch: main → Save**
5. Tu dashboard estará disponible en `https://tuusuario.github.io/nq-dashboard`

---

## Cómo usar el dashboard

### 1. Reloj NY y ventana Silver Bullet
El reloj se sincroniza automáticamente con la hora de Nueva York. La barra de progreso muestra cuánto tiempo queda de la ventana Silver Bullet **(10:00 – 11:00 AM NY)**.

### 2. Gráfica NQ en vivo
El chart del `CME_MINI:NQ1!` carga desde TradingView con VWAP incluido. Usa los botones de timeframe para cambiar entre **1m, 3m, 5m, 15m, 1H y 4H**.

> **Nota:** El plan gratuito de TradingView muestra datos con 15 minutos de delay. Para tiempo real necesitas TradingView Pro (~$15/mes).

### 3. Datos del mercado
Ingresa cada día antes de la sesión NY:

| Campo | Descripción | Dónde verlo |
|---|---|---|
| High del día | Máximo del día actual | TradingView |
| Low del día | Mínimo del día actual | TradingView |
| Precio actual | Precio del NQ en ese momento | TradingView / NT8 |
| VWAP del día | VWAP institucional intradía | TradingView (indicador VWAP) |
| PWH | Previous Week High | TradingView — timeframe semanal |
| PWL | Previous Week Low | TradingView — timeframe semanal |
| High semana actual | Máximo de la semana en curso | TradingView |
| Low semana actual | Mínimo de la semana en curso | TradingView |

### 4. Rangos de sesión
Ingresa el High y Low de la sesión asiática y londinense para que el panel detecte qué liquidez ya fue barrida y calcule los próximos targets.

| Sesión | Horario NY |
|---|---|
| Asian | 8:00 PM – 2:00 AM |
| London | 2:00 AM – 8:00 AM |
| Silver Bullet NY | 10:00 AM – 11:00 AM |

### 5. Niveles de Market Maker calculados automáticamente

| Nivel | Descripción |
|---|---|
| **Buyside Liquidity (BSL)** | High del rango — stops de vendedores acumulados |
| **Premium 75%** | Zona cara — MM venden desde aquí |
| **OTE 79%** | Optimal Trade Entry bajista |
| **Equilibrium 50%** | MM neutrales — zona de decisión |
| **OTE 61.8%** | Optimal Trade Entry alcista |
| **Discount 25%** | Zona barata — MM compran desde aquí |
| **Sellside Liquidity (SSL)** | Low del rango — stops de compradores acumulados |

### 6. Workflow del Silver Bullet

**Setup SHORT (bias bajista — mayor probabilidad):**
1. Precio en zona Premium o sube a barrer BSL
2. Sweep del nivel con rechazo en ventana 10–11am
3. CHoCH bajista en 1m o 3m — trigger de entrada
4. Entrada short en FVG / IFVG bajista post-CHoCH
5. Stop sobre el high del sweep · Target: EQ → SSL

**Setup LONG (contra tendencia):**
1. Precio en zona Discount o baja a barrer SSL
2. Sweep del nivel con rechazo en ventana 10–11am
3. CHoCH alcista en 1m o 3m — trigger de entrada
4. Entrada long en FVG / IFVG bullish post-CHoCH
5. Stop bajo el low del sweep · Target: EQ → BSL

---

## Bot NinjaTrader — SilverBulletV5.cs

### Instalación en NT8
1. Abre NinjaTrader 8
2. Ve a **New → NinjaScript Editor**
3. **File → New → Strategy**
4. Pega el contenido del archivo `SilverBulletV5.cs`
5. Presiona **F5** para compilar

### Parámetros configurables

| Parámetro | Default | Descripción |
|---|---|---|
| `StopTicks` | 20 | Stop loss en ticks (20 ticks = $100 en NQ) |
| `TargetTicks` | 40 | Profit target en ticks |
| `MaxFVGAge` | 20 | Máximo de barras de antigüedad del FVG |

### Correr backtest
1. Ve a **New → Strategy Analyzer**
2. Selecciona `SilverBulletV5`
3. Instrumento: `NQ 06-25` (o contrato vigente)
4. Timeframe: **1 Minute**
5. Fecha de inicio: mínimo 6 meses atrás
6. Click en **Run**

### Conectar Tradovate a NT8
1. Descarga el plugin en `tradovate.com/ninjatrader`
2. Cierra NT8 antes de instalar
3. Ejecuta el instalador
4. En NT8 ve a **Connections → Configure → Add → Tradovate**
5. Ingresa tus credenciales y click **Connect**

---

## Calendario de noticias de alto impacto (recurrentes)

| Evento | Día/Hora NY | Impacto |
|---|---|---|
| FOMC Decision | 8x al año · Miércoles 2pm | Crítico — no operar |
| NFP (Non-Farm Payrolls) | 1er viernes del mes · 8:30am | Crítico — no operar |
| CPI (Inflación) | Mensual · Miércoles 8:30am | Alto impacto |
| Jobless Claims | Todos los jueves · 8:30am | Alto impacto |
| GDP | Trimestral · 8:30am | Alto impacto |
| Powell / Fed Speakers | Variable | Medio-alto |

> Fuente para calendario diario: `forexfactory.com` — filtrar por USD y High Impact

---

## Recursos adicionales

- **ForexFactory Calendar:** `forexfactory.com/calendar`
- **TradingView NQ Chart:** `tradingview.com/chart/?symbol=CME_MINI:NQ1!`
- **Barchart NQ (15min delay):** `barchart.com/futures/quotes/NQH26`
- **NinjaTrader Docs:** `ninjatrader.com/support`
- **Tradovate:** `tradovate.com`

---

## Notas importantes

- Este dashboard es una **herramienta de análisis** — no ejecuta órdenes automáticamente desde el browser
- El bot `SilverBulletV5.cs` opera en **NinjaTrader 8** con cuenta real o simulada
- Siempre prueba el bot en **modo simulación (Sim101)** antes de operar con capital real
- El FOMC y NFP pueden invalidar cualquier setup — revisar calendario antes de cada sesión
- RR mínimo recomendado: **1:2** — parciales en Equilibrium

---

*Desarrollado con Claude (Anthropic) · Estrategia basada en ICT — Inner Circle Trader*
