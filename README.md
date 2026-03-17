<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>README — NQ Command Center</title>
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
body { background: #0d0d0d; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; color: #e8e4dc; padding: 2rem; line-height: 1.7; }
.wrap { max-width: 860px; margin: 0 auto; }
h1 { font-size: 22px; font-weight: 500; color: #e8e4dc; margin-bottom: 0.5rem; }
h2 { font-size: 16px; font-weight: 500; color: #5DCAA5; margin: 2rem 0 0.75rem; padding-bottom: 6px; border-bottom: 0.5px solid #1e1e1e; text-transform: uppercase; letter-spacing: 0.05em; }
h3 { font-size: 14px; font-weight: 500; color: #FAC775; margin: 1.2rem 0 0.5rem; }
p { font-size: 14px; color: #aaa; margin-bottom: 0.75rem; }
a { color: #5DCAA5; text-decoration: none; }
a:hover { text-decoration: underline; }
.subtitle { font-size: 13px; color: #555; margin-bottom: 2rem; padding-bottom: 1.5rem; border-bottom: 0.5px solid #1e1e1e; }
table { width: 100%; border-collapse: collapse; margin: 0.75rem 0 1rem; font-size: 13px; }
th { background: #1a1a1a; color: #5DCAA5; font-weight: 500; padding: 8px 12px; text-align: left; border: 0.5px solid #2a2a2a; font-size: 11px; text-transform: uppercase; letter-spacing: 0.04em; }
td { padding: 7px 12px; border: 0.5px solid #1e1e1e; color: #c8c4bc; vertical-align: top; }
tr:hover td { background: #141414; }
code { background: #1a1a1a; border: 0.5px solid #2a2a2a; border-radius: 4px; padding: 2px 6px; font-family: 'SF Mono', 'Fira Code', monospace; font-size: 12px; color: #FAC775; }
pre { background: #111; border: 0.5px solid #2a2a2a; border-radius: 8px; padding: 1rem; margin: 0.75rem 0; overflow-x: auto; }
pre code { background: none; border: none; padding: 0; color: #5DCAA5; font-size: 13px; }
.badge { display: inline-block; font-size: 11px; padding: 2px 8px; border-radius: 20px; font-weight: 500; margin-right: 4px; }
.red { background: #2a1010; color: #f09595; }
.green { background: #081a12; color: #5DCAA5; }
.amber { background: #251a06; color: #FAC775; }
.gray { background: #1a1a1a; color: #888; }
.note { background: #1a1a0a; border: 0.5px solid #3a3010; border-radius: 8px; padding: 0.75rem 1rem; margin: 0.75rem 0; font-size: 13px; color: #FAC775; }
.note strong { color: #FAC775; }
.step-list { list-style: none; padding: 0; margin: 0.5rem 0 1rem; }
.step-list li { display: flex; gap: 10px; padding: 6px 0; border-bottom: 0.5px solid #1a1a1a; font-size: 13px; color: #c8c4bc; }
.step-list li:last-child { border-bottom: none; }
.step-num { width: 22px; height: 22px; border-radius: 50%; background: #1a2a1a; color: #5DCAA5; display: flex; align-items: center; justify-content: center; font-size: 11px; font-weight: 500; flex-shrink: 0; margin-top: 1px; }
.step-num-r { background: #2a1010; color: #f09595; }
.section { margin-bottom: 2rem; }
.files-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 10px; margin: 0.75rem 0; }
.file-card { background: #141414; border: 0.5px solid #2a2a2a; border-radius: 10px; padding: 0.75rem 1rem; }
.file-name { font-size: 12px; font-family: 'SF Mono', monospace; color: #FAC775; margin-bottom: 4px; }
.file-desc { font-size: 12px; color: #555; }
hr { border: none; border-top: 0.5px solid #1e1e1e; margin: 2rem 0; }
.footer { text-align: center; font-size: 11px; color: #333; padding: 2rem 0 0.5rem; }
ul { padding-left: 1.2rem; margin: 0.5rem 0 1rem; }
ul li { font-size: 13px; color: #aaa; margin-bottom: 4px; }
strong { color: #e8e4dc; font-weight: 500; }
</style>
</head>
<body>
<div class="wrap">

<h1>NQ Command Center — Silver Bullet Dashboard</h1>
<p class="subtitle">Panel de trading para operar el <strong>NQ (Nasdaq E-mini Futures)</strong> usando la estrategia <strong>ICT Silver Bullet</strong> con análisis de Market Maker y niveles institucionales.</p>

<div class="section">
<h2>Archivos incluidos</h2>
<div class="files-grid">
  <div class="file-card"><div class="file-name">nq_dashboard_dark_v4.html</div><div class="file-desc">Dashboard versión oscura — recomendada</div></div>
  <div class="file-card"><div class="file-name">nq_dashboard_v2.html</div><div class="file-desc">Dashboard versión blanca</div></div>
  <div class="file-card"><div class="file-name">SilverBulletV5.cs</div><div class="file-desc">Bot NinjaScript para NinjaTrader 8</div></div>
  <div class="file-card"><div class="file-name">README.html</div><div class="file-desc">Este archivo de documentación</div></div>
</div>
</div>

<div class="section">
<h2>Cómo abrir el dashboard</h2>
<p>El dashboard usa el widget de TradingView para mostrar la gráfica del NQ en vivo. <strong>No funciona abriendo el archivo directamente</strong> — necesita correr en un servidor local.</p>

<h3>Opción A — VS Code + Live Server (recomendada)</h3>
<ol class="step-list">
  <li><span class="step-num">1</span>Descarga <strong>VS Code</strong> en <a href="https://code.visualstudio.com" target="_blank">code.visualstudio.com</a></li>
  <li><span class="step-num">2</span>Instala la extensión <strong>Live Server</strong> desde el panel de Extensions</li>
  <li><span class="step-num">3</span>Abre la carpeta del proyecto en VS Code</li>
  <li><span class="step-num">4</span>Click derecho sobre el HTML → <strong>Open with Live Server</strong></li>
  <li><span class="step-num">5</span>Se abre en <code>http://localhost:5500</code> — el chart carga automáticamente</li>
</ol>

<h3>Opción B — Python</h3>
<p>Abre una terminal en la carpeta del proyecto y ejecuta:</p>
<pre><code>python -m http.server 8080</code></pre>
<p>Luego abre: <code>http://localhost:8080/nq_dashboard_dark_v4.html</code></p>

<h3>Opción C — GitHub Pages (acceso desde cualquier dispositivo)</h3>
<ol class="step-list">
  <li><span class="step-num">1</span>Crea una cuenta en <a href="https://github.com" target="_blank">github.com</a></li>
  <li><span class="step-num">2</span>Crea un repositorio nuevo llamado <code>nq-dashboard</code></li>
  <li><span class="step-num">3</span>Sube todos los archivos al repositorio</li>
  <li><span class="step-num">4</span>Ve a <strong>Settings → Pages → Branch: main → Save</strong></li>
  <li><span class="step-num">5</span>Tu dashboard estará en <code>https://tuusuario.github.io/nq-dashboard</code></li>
</ol>
</div>

<div class="section">
<h2>Cómo usar el dashboard</h2>

<h3>Datos a ingresar cada día antes de las 9:30am NY</h3>
<table>
  <tr><th>Campo</th><th>Descripción</th><th>Dónde verlo</th></tr>
  <tr><td>High del día</td><td>Máximo del día actual</td><td>TradingView</td></tr>
  <tr><td>Low del día</td><td>Mínimo del día actual</td><td>TradingView</td></tr>
  <tr><td>Precio actual</td><td>Precio del NQ en ese momento</td><td>TradingView / NT8</td></tr>
  <tr><td>VWAP del día</td><td>VWAP institucional intradía</td><td>TradingView — indicador VWAP</td></tr>
  <tr><td>PWH</td><td>Previous Week High</td><td>TradingView — timeframe semanal</td></tr>
  <tr><td>PWL</td><td>Previous Week Low</td><td>TradingView — timeframe semanal</td></tr>
  <tr><td>High semana actual</td><td>Máximo de la semana en curso</td><td>TradingView</td></tr>
  <tr><td>Low semana actual</td><td>Mínimo de la semana en curso</td><td>TradingView</td></tr>
  <tr><td>Asian High / Low</td><td>Rango sesión asiática 8pm–2am</td><td>TradingView — marcar manualmente</td></tr>
  <tr><td>London High / Low</td><td>Rango sesión londinense 2am–8am</td><td>TradingView — marcar manualmente</td></tr>
</table>

<h3>Horarios de sesión (hora NY)</h3>
<table>
  <tr><th>Sesión</th><th>Horario NY</th><th>Importancia</th></tr>
  <tr><td>Asian</td><td>8:00 PM – 2:00 AM</td><td>Forma el rango de liquidez nocturno</td></tr>
  <tr><td>London</td><td>2:00 AM – 8:00 AM</td><td>Primer movimiento institucional del día</td></tr>
  <tr><td>NY Open</td><td>9:30 AM – 10:00 AM</td><td>Apertura — dirección inicial del día</td></tr>
  <tr><td><strong>Silver Bullet</strong></td><td><strong>10:00 AM – 11:00 AM</strong></td><td><strong>Ventana principal de entrada</strong></td></tr>
  <tr><td>NY Afternoon</td><td>1:30 PM – 4:00 PM</td><td>Segunda ventana Silver Bullet (2–3pm)</td></tr>
</table>

<h3>Niveles de Market Maker</h3>
<table>
  <tr><th>Nivel</th><th>Descripción</th><th>Acción del MM</th></tr>
  <tr><td><span class="badge red">Buyside Liq.</span></td><td>High del rango — stops de vendedores</td><td>MM venden desde aquí</td></tr>
  <tr><td><span class="badge red">Premium 75%</span></td><td>Zona cara del rango</td><td>Institucionales abren shorts</td></tr>
  <tr><td><span class="badge amber">OTE 79%</span></td><td>Optimal Trade Entry bajista</td><td>Entrada óptima short</td></tr>
  <tr><td><span class="badge gray">Equilibrium 50%</span></td><td>Punto medio — MM neutrales</td><td>Zona de decisión / targets parciales</td></tr>
  <tr><td><span class="badge amber">OTE 61.8%</span></td><td>Optimal Trade Entry alcista</td><td>Entrada óptima long</td></tr>
  <tr><td><span class="badge green">Discount 25%</span></td><td>Zona barata del rango</td><td>Institucionales abren longs</td></tr>
  <tr><td><span class="badge green">Sellside Liq.</span></td><td>Low del rango — stops de compradores</td><td>MM compran desde aquí</td></tr>
</table>
</div>

<div class="section">
<h2>Workflow del Silver Bullet</h2>

<h3>Setup SHORT — Bias bajista (mayor probabilidad)</h3>
<ol class="step-list">
  <li><span class="step-num step-num-r">1</span>Precio en zona <strong>Premium</strong> o sube a barrer Buyside Liquidity</li>
  <li><span class="step-num step-num-r">2</span>Sweep del BSL en ventana 10–11am · mecha larga arriba, cierre bajo el nivel en 1-3m</li>
  <li><span class="step-num step-num-r">3</span>CHoCH bajista en 1m o 3m — rompe un low previo (trigger de entrada)</li>
  <li><span class="step-num step-num-r">4</span>Entrada short en FVG / IFVG bajista post-CHoCH · stop sobre el high del sweep</li>
  <li><span class="step-num step-num-r">5</span>Target 1: Equilibrium · Target 2: SSL / Low · RR mínimo 1:2</li>
</ol>

<h3>Setup LONG — Contra tendencia</h3>
<ol class="step-list">
  <li><span class="step-num">1</span>Precio en zona <strong>Discount</strong> o baja a barrer Sellside Liquidity</li>
  <li><span class="step-num">2</span>Sweep del SSL en ventana 10–11am · mecha larga abajo, cierre sobre el nivel en 1-3m</li>
  <li><span class="step-num">3</span>CHoCH alcista en 1m o 3m — rompe un high previo (trigger de entrada)</li>
  <li><span class="step-num">4</span>Entrada long en FVG / IFVG bullish post-CHoCH · stop bajo el low del sweep</li>
  <li><span class="step-num">5</span>Target 1: Equilibrium · Target 2: BSL / High · RR mínimo 1:2</li>
</ol>
</div>

<div class="section">
<h2>Bot NinjaTrader — SilverBulletV5.cs</h2>

<h3>Instalación en NT8</h3>
<ol class="step-list">
  <li><span class="step-num">1</span>Abre NinjaTrader 8</li>
  <li><span class="step-num">2</span>Ve a <strong>New → NinjaScript Editor</strong></li>
  <li><span class="step-num">3</span>File → New → Strategy</li>
  <li><span class="step-num">4</span>Pega el contenido de <code>SilverBulletV5.cs</code> y borra el código por defecto</li>
  <li><span class="step-num">5</span>Presiona <strong>F5</strong> para compilar — si no hay errores en rojo está listo</li>
</ol>

<h3>Parámetros configurables</h3>
<table>
  <tr><th>Parámetro</th><th>Default</th><th>Descripción</th></tr>
  <tr><td><code>StopTicks</code></td><td>20</td><td>Stop loss en ticks (20 ticks = $100 en NQ)</td></tr>
  <tr><td><code>TargetTicks</code></td><td>40</td><td>Profit target en ticks (40 ticks = $200 en NQ)</td></tr>
  <tr><td><code>MaxFVGAge</code></td><td>20</td><td>Antigüedad máxima del FVG en barras</td></tr>
</table>

<h3>Correr backtest en NT8</h3>
<ol class="step-list">
  <li><span class="step-num">1</span>Ve a <strong>New → Strategy Analyzer</strong></li>
  <li><span class="step-num">2</span>Strategy: <code>SilverBulletV5</code> · Instrumento: <code>NQ 06-25</code></li>
  <li><span class="step-num">3</span>Timeframe: <strong>1 Minute</strong> · Fecha inicio: mínimo 6 meses atrás</li>
  <li><span class="step-num">4</span>Capital inicial: $25,000 · Commission: $4.50 por lado</li>
  <li><span class="step-num">5</span>Click en <strong>Run</strong> y revisa Performance, Trades y Equity</li>
</ol>

<div class="note"><strong>Métricas objetivo:</strong> Profit Factor mayor a 1.5 · Win Rate sobre 45% · Max Drawdown menor al 15% del capital</div>

<h3>Conectar Tradovate a NT8</h3>
<ol class="step-list">
  <li><span class="step-num">1</span>Descarga el plugin en <a href="https://tradovate.com/ninjatrader" target="_blank">tradovate.com/ninjatrader</a></li>
  <li><span class="step-num">2</span>Cierra NT8 completamente antes de instalar</li>
  <li><span class="step-num">3</span>Ejecuta el instalador y sigue el wizard</li>
  <li><span class="step-num">4</span>En NT8 ve a <strong>Connections → Configure → Add → Tradovate</strong></li>
  <li><span class="step-num">5</span>Ingresa tus credenciales → punto verde = conectado</li>
</ol>
</div>

<div class="section">
<h2>Calendario de noticias de alto impacto</h2>
<table>
  <tr><th>Evento</th><th>Frecuencia / Hora NY</th><th>Impacto</th></tr>
  <tr><td>FOMC Decision + Powell</td><td>8x al año · Miércoles 2:00 PM</td><td><span class="badge red">Crítico — no operar</span></td></tr>
  <tr><td>NFP (Non-Farm Payrolls)</td><td>1er viernes del mes · 8:30 AM</td><td><span class="badge red">Crítico — no operar</span></td></tr>
  <tr><td>CPI (Inflación)</td><td>Mensual · Miércoles 8:30 AM</td><td><span class="badge red">Alto impacto</span></td></tr>
  <tr><td>Jobless Claims</td><td>Todos los jueves · 8:30 AM</td><td><span class="badge amber">Alto impacto</span></td></tr>
  <tr><td>GDP</td><td>Trimestral · 8:30 AM</td><td><span class="badge amber">Alto impacto</span></td></tr>
  <tr><td>Fed Speakers / Powell</td><td>Variable</td><td><span class="badge amber">Medio-alto</span></td></tr>
  <tr><td>PPI / PCE</td><td>Mensual · 8:30 AM</td><td><span class="badge amber">Medio impacto</span></td></tr>
</table>
<div class="note"><strong>Regla:</strong> No operar 15 minutos antes ni 15 minutos después de cualquier dato de alto impacto. Revisar <a href="https://forexfactory.com/calendar" target="_blank">forexfactory.com/calendar</a> cada mañana antes de la sesión.</div>
</div>

<div class="section">
<h2>Recursos</h2>
<ul>
  <li><a href="https://forexfactory.com/calendar" target="_blank">ForexFactory Calendar</a> — Calendario económico filtrado por USD High Impact</li>
  <li><a href="https://tradingview.com/chart/?symbol=CME_MINI:NQ1!" target="_blank">TradingView — NQ Futures</a> — Chart en tiempo real</li>
  <li><a href="https://barchart.com/futures/quotes/NQH26" target="_blank">Barchart NQ</a> — Precio con 15min delay, gratis</li>
  <li><a href="https://ninjatrader.com/support" target="_blank">NinjaTrader Docs</a> — Documentación oficial NT8</li>
  <li><a href="https://tradovate.com" target="_blank">Tradovate</a> — Broker para futuros NQ</li>
</ul>
</div>

<hr>
<div class="note">
  <strong>Aviso importante:</strong> Este dashboard es una herramienta de análisis — no ejecuta órdenes automáticamente desde el browser. El bot SilverBulletV5.cs opera en NinjaTrader 8. Siempre prueba en modo simulación antes de operar con capital real. El trading de futuros involucra riesgo significativo de pérdida.
</div>

<div class="footer">NQ Command Center · Silver Bullet Dashboard · Desarrollado con Claude (Anthropic) · Estrategia basada en ICT — Inner Circle Trader</div>

</div>
</body>
</html>
