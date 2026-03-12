<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MTG Commander Sim</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700;900&display=swap');
  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --theme-a: #c084fc; --theme-b: #818cf8; --theme-c: #7c3aed; --theme-d: #4f46e5;
    --theme-bg1: #1a0a2e; --theme-bg2: #07070f;
    --theme-glow1: rgba(124,58,237,0.27); --theme-glow2: rgba(124,58,237,0.6);
  }

  body {
    min-height: 100vh;
    background: radial-gradient(ellipse at 20% 10%, var(--theme-bg1) 0%, var(--theme-bg2) 60%, #0d0a14 100%);
    color: #e2e8f0; font-family: Georgia, serif; padding: 24px 20px;
    transition: background 1s ease;
  }
  ::-webkit-scrollbar { width: 5px; }
  ::-webkit-scrollbar-thumb { background: var(--theme-c); border-radius: 3px; }
  @keyframes glow { 0%,100%{box-shadow:0 0 18px var(--theme-glow1)} 50%{box-shadow:0 0 36px var(--theme-glow2)} }
  @keyframes shake { 0%,100%{transform:translateX(0)} 20%{transform:translateX(-6px)} 40%{transform:translateX(6px)} 60%{transform:translateX(-4px)} 80%{transform:translateX(4px)} }
  .shake { animation: shake 0.4s ease; }

.header { text-align: center; margin-bottom: 24px; }
.eyebrow { font-size: 10px; letter-spacing: 5px; color: var(--theme-c); font-family: 'Cinzel',serif; margin-bottom: 6px; transition: color 0.8s; }
h1 { font-family: 'Cinzel',serif; font-weight: 900; font-size: 30px; background: linear-gradient(135deg, var(--theme-a), var(--theme-b), var(--theme-a)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
.subtitle { color: #475569; font-size: 12px; margin-top: 5px; font-style: italic; }

.deck-section { max-width: 820px; margin: 0 auto 28px auto; }
.deck-section-header { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 8px; gap: 16px; }
.deck-section-title { font-family: 'Cinzel',serif; font-size: 12px; color: #818cf8; letter-spacing: 2px; white-space: nowrap; }
.deck-format-hint { font-size: 10px; color: #475569; text-align: right; }
.deck-format-hint span { color: #64748b; }

/* Commander instruction banner */
.cmd-first-banner {
  display: flex; align-items: flex-start; gap: 10px; margin-bottom: 8px;
  background: rgba(124,58,237,0.12); border: 1px solid rgba(124,58,237,0.4);
  border-radius: 8px; padding: 10px 14px; font-size: 11px; color: #c4b5fd; line-height: 1.6;
}
.cmd-first-banner .banner-icon { font-size: 18px; line-height: 1; flex-shrink: 0; margin-top: 1px; }
.cmd-first-banner strong { color: #e9d5ff; font-family: 'Cinzel', serif; letter-spacing: 0.5px; font-size: 11px; }

/* Sim max badge */
.sim-max-badge {
  display: inline-flex; align-items: center; gap: 4px;
  background: rgba(124,58,237,0.18); border: 1px solid rgba(139,92,246,0.4);
  border-radius: 12px; padding: 2px 9px; font-size: 9px; color: #a78bfa;
  font-family: 'Cinzel', serif; letter-spacing: 1px; white-space: nowrap;
}

/* Scryfall progress */
#scryfallProgress {
  display: none; margin-top: 8px;
  background: rgba(0,0,0,0.4); border: 1px solid rgba(139,92,246,0.2);
  border-radius: 8px; padding: 10px 14px;
}
#scryfallProgress.active { display: block; }
.sf-status-text { font-size: 10px; color: #94a3b8; font-family: monospace; margin-bottom: 6px; }
.sf-bar-track { height: 3px; background: rgba(255,255,255,0.06); border-radius: 2px; overflow: hidden; }
.sf-bar-fill { height: 100%; background: linear-gradient(90deg, var(--theme-c), var(--theme-a)); border-radius: 2px; transition: width 0.3s ease; width: 0%; }

/* Color identity pips on commander card */
.cmd-color-pips { display: flex; gap: 5px; justify-content: center; margin-top: 8px; flex-wrap: wrap; }
.color-pip { width: 21px; height: 21px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 700; font-family: 'Cinzel', serif; border: 1.5px solid rgba(255,255,255,0.2); flex-shrink: 0; }

#deckInput {
width: 100%; height: 200px; background: rgba(0,0,0,0.55);
border: 1px solid rgba(139,92,246,0.3); border-radius: 10px;
color: #e2e8f0; font-family: monospace; font-size: 12px;
padding: 14px 16px; resize: vertical; outline: none; line-height: 1.7;
transition: border-color 0.2s; display: block;
}
#deckInput:focus { border-color: rgba(139,92,246,0.7); }
#deckInput.input-error { border-color: #f87171; }
#deckInput.input-ok { border-color: #4ade80; }
#deckInput::placeholder { color: #2d3748; }

.cmc-row {
display: flex; align-items: center; gap: 12px; margin-top: 10px;
background: rgba(0,0,0,0.3); border: 1px solid rgba(139,92,246,0.2);
border-radius: 8px; padding: 10px 14px;
}
.cmc-label { font-family: 'Cinzel',serif; font-size: 10px; color: #818cf8; letter-spacing: 1px; white-space: nowrap; }
.cmc-hint { font-size: 10px; color: #475569; flex: 1; }
#cmdCmcInput {
width: 60px; background: rgba(0,0,0,0.5); border: 1px solid rgba(139,92,246,0.4);
border-radius: 6px; color: #c084fc; font-family: 'Cinzel',serif; font-size: 14px;
font-weight: 700; text-align: center; padding: 6px 8px; outline: none;
transition: border-color 0.2s;
}
#cmdCmcInput:focus { border-color: #c084fc; }

.deck-actions { display: flex; gap: 8px; margin-top: 10px; align-items: center; }
#parseBtn {
background: linear-gradient(135deg,#4f46e5,#7c3aed); color: #fff;
border: none; border-radius: 7px; padding: 9px 22px; font-size: 11px;
font-family: 'Cinzel',serif; letter-spacing: 1px; cursor: pointer; white-space: nowrap;
}
#clearBtn {
background: rgba(255,255,255,0.05); color: #64748b;
border: 1px solid rgba(255,255,255,0.08); border-radius: 7px;
padding: 9px 16px; font-size: 11px; font-family: 'Cinzel',serif;
letter-spacing: 1px; cursor: pointer; white-space: nowrap;
}
#cardCountLive { font-size: 11px; color: #475569; font-family: monospace; padding: 0 4px; }

#validationBox { margin-top: 12px; display: none; border-radius: 8px; padding: 12px 16px; font-size: 11px; line-height: 1.9; font-family: monospace; }
#validationBox.show-error { display: block; background: rgba(248,113,113,0.07); border: 1px solid rgba(248,113,113,0.4); }
#validationBox.show-ok    { display: block; background: rgba(74,222,128,0.06); border: 1px solid rgba(74,222,128,0.35); }
.v-title { font-family: 'Cinzel',serif; font-size: 11px; letter-spacing: 1px; margin-bottom: 6px; }
.v-err { color: #f87171; }
.v-ok  { color: #4ade80; }
.v-dim { color: #94a3b8; }
.v-item { padding-left: 10px; border-left: 2px solid rgba(255,255,255,0.08); margin-bottom: 2px; }

#deckPreview { margin-top: 12px; display: none; background: rgba(0,0,0,0.35); border: 1px solid rgba(139,92,246,0.2); border-radius: 8px; padding: 12px 16px; }
.preview-title { font-family: 'Cinzel',serif; font-size: 10px; color: #475569; letter-spacing: 2px; margin-bottom: 8px; }
.preview-pills { display: flex; gap: 8px; flex-wrap: wrap; }
.pill { background: rgba(139,92,246,0.12); border: 1px solid rgba(139,92,246,0.25); border-radius: 20px; padding: 3px 10px; font-size: 10px; color: #94a3b8; }
.pill span { font-weight: 700; }

.cmd-zone { display: flex; justify-content: center; margin-bottom: 22px; }
.cmd-card { background: linear-gradient(145deg,#1e0a3c,#0a0a1a); border: 2px solid var(--theme-c); border-radius: 12px; padding: 12px 36px; text-align: center; animation: glow 3s ease-in-out infinite; transition: border-color 0.8s; }
.cmd-label { font-size: 8px; letter-spacing: 4px; color: var(--theme-c); font-family: 'Cinzel',serif; transition: color 0.8s; }
.cmd-name-display { font-family: 'Cinzel',serif; font-size: 17px; font-weight: 700; color: var(--theme-a); margin-top: 4px; transition: color 0.8s; }
.cmd-sub { color: #64748b; font-size: 10px; margin-top: 3px; }
#cmdDisplay { display: none; }

.btn-wrap { text-align: center; margin-bottom: 26px; }
#simBtn { background: linear-gradient(135deg, var(--theme-c), var(--theme-d)); color: #fff; border: none; border-radius: 8px; padding: 13px 44px; font-size: 13px; font-family: 'Cinzel',serif; letter-spacing: 2px; cursor: pointer; box-shadow: 0 0 28px var(--theme-glow1); transition: all 0.2s; }
#simBtn:disabled { background: rgba(124,58,237,0.2); box-shadow: none; cursor: not-allowed; color: #475569; }

.summary-row { display: flex; gap: 10px; flex-wrap: wrap; justify-content: center; margin-bottom: 14px; }
.stat-card { background: rgba(0,0,0,0.45); border-radius: 10px; padding: 12px 20px; text-align: center; min-width: 105px; }
.stat-val { font-size: 24px; font-weight: 700; font-family: 'Cinzel',serif; }
.stat-lbl { font-size: 9px; margin-top: 3px; letter-spacing: 1px; color: #64748b; }

/* Export button row */
.export-row { display: flex; justify-content: center; margin-bottom: 22px; }
#exportBtn {
  background: rgba(0,0,0,0.4); color: #a78bfa;
  border: 1px solid rgba(139,92,246,0.4); border-radius: 7px;
  padding: 8px 20px; font-size: 10px; font-family: 'Cinzel',serif;
  letter-spacing: 2px; cursor: pointer; display: flex; align-items: center; gap: 7px;
  transition: all 0.2s;
}
#exportBtn:hover { background: rgba(124,58,237,0.2); border-color: #7c3aed; color: #c084fc; }
#exportBtn:disabled { opacity: 0.4; cursor: not-allowed; }

/* Export snapshot card */
#exportSnapshot {
  position: fixed; left: -9999px; top: 0;
  width: 860px;
  background: radial-gradient(ellipse at 20% 10%, #1a0a2e 0%, #07070f 60%, #0d0a14 100%);
  padding: 36px 40px;
  font-family: Georgia, serif;
  color: #e2e8f0;
}
.snap-header { text-align: center; margin-bottom: 28px; border-bottom: 1px solid rgba(139,92,246,0.25); padding-bottom: 20px; }
.snap-eyebrow { font-size: 9px; letter-spacing: 5px; color: #6d28d9; font-family: 'Cinzel',serif; margin-bottom: 6px; }
.snap-title { font-family: 'Cinzel',serif; font-weight: 900; font-size: 26px; color: #c084fc; margin-bottom: 4px; }
.snap-cmd { font-family: 'Cinzel',serif; font-size: 14px; color: #818cf8; }
.snap-meta { font-size: 10px; color: #475569; margin-top: 4px; font-style: italic; }
.snap-stats { display: flex; gap: 10px; flex-wrap: wrap; justify-content: center; margin-bottom: 28px; }
.snap-stat { background: rgba(0,0,0,0.55); border-radius: 10px; padding: 14px 22px; text-align: center; min-width: 110px; }
.snap-stat-val { font-size: 26px; font-weight: 700; font-family: 'Cinzel',serif; }
.snap-stat-lbl { font-size: 9px; margin-top: 3px; letter-spacing: 1px; color: #64748b; }
.snap-section-title { font-family: 'Cinzel',serif; font-size: 10px; color: #818cf8; letter-spacing: 2px; margin-bottom: 12px; }
.snap-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 20px; }
.snap-box { background: rgba(0,0,0,0.4); border: 1px solid rgba(139,92,246,0.2); border-radius: 10px; padding: 18px; }
.snap-bar-row { margin-bottom: 7px; }
.snap-bar-header { display: flex; justify-content: space-between; font-size: 10px; color: #94a3b8; margin-bottom: 3px; }
.snap-bar-track { height: 6px; background: rgba(255,255,255,0.06); border-radius: 3px; overflow: hidden; }
.snap-bar-fill { height: 100%; border-radius: 3px; }
.snap-cmd-hist { display: flex; gap: 5px; align-items: flex-end; height: 80px; margin-top: 8px; }
.snap-cmd-bar-wrap { flex: 1; display: flex; flex-direction: column; align-items: center; gap: 3px; }
.snap-cmd-bar-count { font-size: 9px; color: #94a3b8; }
.snap-cmd-bar { width: 100%; min-height: 3px; border-radius: 3px 3px 0 0; }
.snap-cmd-bar-label { font-size: 8px; color: #475569; }
.snap-footer { text-align: center; margin-top: 20px; padding-top: 16px; border-top: 1px solid rgba(139,92,246,0.15); font-size: 9px; color: #374151; letter-spacing: 2px; font-family: 'Cinzel',serif; }

.tabs { display: flex; gap: 4px; justify-content: center; margin-bottom: 20px; }
.tab-btn { background: rgba(255,255,255,0.04); color: #64748b; border: 1px solid rgba(255,255,255,0.08); border-radius: 6px; padding: 7px 22px; font-size: 10px; font-family: 'Cinzel',serif; letter-spacing: 2px; cursor: pointer; }
.tab-btn.active { background: linear-gradient(135deg,#7c3aed,#4f46e5); color: #fff; border-color: #7c3aed; }

.panel { max-width: 820px; margin: 0 auto; display: none; }
.panel.active { display: block; }
.grid2 { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; }
.box { background: rgba(0,0,0,0.4); border: 1px solid rgba(139,92,246,0.2); border-radius: 10px; padding: 20px; }
.box-title { font-family: 'Cinzel',serif; font-size: 11px; color: #818cf8; letter-spacing: 2px; margin-bottom: 14px; }
.span2 { grid-column: 1 / -1; }

.bar-row { margin-bottom: 8px; }
.bar-header { display: flex; justify-content: space-between; font-size: 11px; color: #94a3b8; margin-bottom: 3px; }
.bar-track { height: 6px; background: rgba(255,255,255,0.06); border-radius: 3px; overflow: hidden; }
.bar-fill { height: 100%; border-radius: 3px; }

.turn-row { display: flex; align-items: center; gap: 8px; margin-bottom: 6px; }
.turn-label { color: #475569; font-size: 10px; width: 24px; flex-shrink: 0; }
.turn-bars { flex: 1; display: flex; gap: 3px; height: 11px; }
.turn-bar { border-radius: 2px; min-width: 2px; }
.turn-nums { font-size: 9px; color: #475569; width: 95px; flex-shrink: 0; text-align: right; }

.cmd-dist { display: flex; gap: 6px; align-items: flex-end; height: 100px; }
.cmd-bar-wrap { flex: 1; display: flex; flex-direction: column; align-items: center; gap: 3px; }
.cmd-bar-count { font-size: 10px; color: #94a3b8; }
.cmd-bar { width: 100%; min-height: 3px; border-radius: 3px 3px 0 0; }
.cmd-bar-label { font-size: 9px; color: #475569; }

.chart-wrap { display: flex; align-items: flex-end; gap: 4px; height: 70px; }
.chart-col { flex: 1; display: flex; flex-direction: column; align-items: center; gap: 3px; }
.chart-bar { width: 100%; border-radius: 3px 3px 0 0; min-height: 2px; opacity: 0.85; }
.chart-label { font-size: 8px; color: #475569; }
.chart-footer { display: flex; justify-content: space-between; margin-top: 8px; font-size: 9px; color: #475569; }

#runsPanel { max-width: 900px; margin: 0 auto; display: none; }
#runsPanel.active { display: block; }
.run-selector-label { font-family: 'Cinzel',serif; font-size: 10px; color: #475569; letter-spacing: 2px; margin-bottom: 8px; }
.run-grid { display: flex; gap: 3px; flex-wrap: wrap; margin-bottom: 8px; }
.run-btn { background: rgba(255,255,255,0.04); color: #374151; border: 1px solid rgba(255,255,255,0.06); border-radius: 4px; width: 30px; height: 26px; font-size: 9px; cursor: pointer; font-family: monospace; }
.run-btn.has-cmd { color: #a78bfa; border-color: rgba(139,92,246,0.3); }
.run-btn.selected { background: linear-gradient(135deg,#7c3aed,#4f46e5); color: #fff; border-color: #7c3aed; }
.run-legend { font-size: 9px; color: #475569; margin-bottom: 14px; }

.run-summary { display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 14px; }

/* Opening hand display */
.opening-hand-section { margin-bottom: 18px; }
.opening-hand-title { font-family: 'Cinzel',serif; font-size: 10px; color: #475569; letter-spacing: 2px; margin-bottom: 10px; }
.hand-cards { display: flex; gap: 8px; flex-wrap: wrap; }
.hand-card {
  background: rgba(0,0,0,0.5); border-radius: 8px; padding: 9px 13px;
  font-size: 11px; font-family: monospace; line-height: 1.4;
  min-width: 110px; max-width: 180px;
  display: flex; flex-direction: column; gap: 3px;
}
.hand-card-name { color: #e2e8f0; font-weight: 600; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.hand-card-type { font-size: 9px; letter-spacing: 0.5px; text-transform: uppercase; }
.hand-card-cmc  { font-size: 9px; color: #475569; }
.run-stat { background: rgba(0,0,0,0.4); border-radius: 8px; padding: 9px 16px; text-align: center; }
.run-stat-val { font-size: 20px; font-weight: 700; font-family: 'Cinzel',serif; }
.run-stat-lbl { font-size: 9px; color: #475569; margin-top: 2px; }

.turn-log { background: rgba(0,0,0,0.5); border: 1px solid rgba(139,92,246,0.12); border-radius: 8px; padding: 11px 14px; margin-bottom: 7px; font-family: monospace; font-size: 11px; line-height: 1.75; color: #94a3b8; }
.turn-log.has-cmd { border-color: rgba(192,132,252,0.35); }
.turn-head { color: #a78bfa; font-weight: 700; font-size: 12px; margin-bottom: 5px; font-family: 'Cinzel',serif; }
.turn-meta { color: #374151; font-weight: 400; margin-left: 10px; font-size: 10px; }
.action { padding-left: 10px; border-left: 2px solid rgba(139,92,246,0.2); margin-bottom: 2px; }
.a-land { color: #4ade80; }
.a-cmd  { color: #c084fc; }
.a-cast { color: #a78bfa; }
.a-draw { color: #60a5fa; }
.a-token { color: #fbbf24; }

#results { display: none; }
</style>
</head>
<body>

<div class="header">
  <div class="eyebrow">&#9760; MTG COMMANDER SIM &#9760;</div>
  <h1 id="mainTitle">MTG Commander Sim</h1>
  <div class="subtitle" id="mainSubtitle">Paste your 100-card decklist below to begin</div>
</div>

<div class="deck-section">
  <div class="deck-section-header">
    <div class="deck-section-title">DECKLIST INPUT</div>
    <div class="deck-format-hint">Format: <span>1 Card Name</span> per line &middot; Accepts MTGO, Moxfield &amp; Archidekt</div>
  </div>

  <div class="cmd-first-banner">
    <div class="banner-icon">&#9760;</div>
    <div>
      <strong>LINE 1 = YOUR COMMANDER.</strong> Place your commander on the very first line of the list.
      The sim reads line 1 as the Command Zone — everything else goes on lines 2&ndash;100.
      <span style="color:#7c6a94;display:block;margin-top:2px;">Example: &nbsp;<code style="color:#c4b5fd;">1 The Scarab God</code>&nbsp; on line 1, then your 99 cards below.</span>
    </div>
  </div>

  <textarea id="deckInput" placeholder="1 The Scarab God          ← YOUR COMMANDER (line 1)
1 Sol Ring
1 Arcane Signet
1 Cyclonic Rift
22 Swamp
3 Island
...
(100 cards total including commander)"></textarea>

  <div class="cmc-row" id="cmcRow">
    <div class="cmc-label">COMMANDER CMC</div>
    <div class="cmc-hint" id="cmcHint">Will auto-detect via Scryfall after loading decklist &middot; Override manually if needed</div>
    <input type="number" id="cmdCmcInput" min="0" max="20" value="5" placeholder="5" />
  </div>

  <div class="cmc-row" style="margin-top:6px;">
    <div class="cmc-label">SIMULATIONS</div>
    <div class="cmc-hint" style="flex:1;">Number of games to simulate &middot; More = slower but more accurate &middot; Recommended: 100–500</div>
    <div class="sim-max-badge">&#9660; MAX 1,000</div>
    <input type="number" id="simCountInput" min="10" max="1000" value="100" placeholder="100" style="width:72px;background:rgba(0,0,0,0.5);border:1px solid rgba(139,92,246,0.4);border-radius:6px;color:#c084fc;font-family:'Cinzel',serif;font-size:14px;font-weight:700;text-align:center;padding:6px 8px;outline:none;transition:border-color 0.2s;" onfocus="this.style.borderColor='#c084fc'" onblur="this.style.borderColor='rgba(139,92,246,0.4)'" />
  </div>

  <div id="scryfallProgress">
    <div class="sf-status-text" id="sfStatusText">Looking up cards via Scryfall…</div>
    <div class="sf-bar-track"><div class="sf-bar-fill" id="sfBarFill"></div></div>
  </div>

  <div class="deck-actions">
    <button id="parseBtn" onclick="parseDeck()">&#10022; LOAD DECKLIST</button>
    <button id="clearBtn" onclick="clearDeck()">&#10005; CLEAR</button>
    <div id="cardCountLive"></div>
  </div>
  <div id="validationBox"></div>
  <div id="deckPreview"></div>
</div>

<div id="cmdDisplay">
  <div class="cmd-zone">
    <div class="cmd-card">
      <div class="cmd-label">COMMAND ZONE</div>
      <div class="cmd-name-display" id="cmdNameText">-</div>
      <div class="cmd-sub" id="cmdSubText">Commander &middot; Draws T1 &middot; +2 per recast</div>
      <div class="cmd-color-pips" id="cmdColorPips"></div>
    </div>
  </div>
</div>

<div class="btn-wrap">
  <button id="simBtn" onclick="runSims()" disabled>&#9654; SIMULATE GAMES</button>
</div>

<div id="results">
  <div class="summary-row" id="summaryRow"></div>

  <!-- Export button -->
  <div class="export-row">
    <button id="exportBtn" onclick="exportSummaryImage()">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/>
        <polyline points="7 10 12 15 17 10"/>
        <line x1="12" y1="15" x2="12" y2="3"/>
      </svg>
      EXPORT SUMMARY IMAGE
    </button>
  </div>

  <div class="tabs">
    <button class="tab-btn active" onclick="switchTab('stats')">STATS</button>
    <button class="tab-btn" onclick="switchTab('charts')">CHARTS</button>
    <button class="tab-btn" onclick="switchTab('runs')">RUNS</button>
  </div>
  <div class="panel active" id="statsPanel"></div>
  <div class="panel" id="chartsPanel"></div>
  <div id="runsPanel"></div>
</div>

<!-- Hidden export snapshot element -->
<div id="exportSnapshot"></div>

<script>
var BASIC_LAND_NAMES = [
  "plains","island","swamp","mountain","forest","wastes",
  "snow-covered plains","snow-covered island","snow-covered swamp",
  "snow-covered mountain","snow-covered forest"
];

// ─── COMMANDER COLOR THEME ENGINE ────────────────────────────────────────────
// Maps color identity arrays to visual theme palettes
var COLOR_THEMES = {
  // Mono
  "W": {bg1:"#1a1814",bg2:"#0c0c0a",a:"#f5f0dc",b:"#c8c4a8",c:"#9c9880",d:"#706c58",g1:"rgba(200,196,168,0.2)",g2:"rgba(200,196,168,0.5)"},
  "U": {bg1:"#081828",bg2:"#040d18",a:"#93c5fd",b:"#60a5fa",c:"#3b82f6",d:"#1d4ed8",g1:"rgba(59,130,246,0.25)",g2:"rgba(59,130,246,0.55)"},
  "B": {bg1:"#1a0a2e",bg2:"#07070f",a:"#c084fc",b:"#a855f7",c:"#7c3aed",d:"#5b21b6",g1:"rgba(124,58,237,0.27)",g2:"rgba(124,58,237,0.6)"},
  "R": {bg1:"#200a08",bg2:"#0f0404",a:"#fca5a5",b:"#f87171",c:"#ef4444",d:"#b91c1c",g1:"rgba(239,68,68,0.25)",g2:"rgba(239,68,68,0.55)"},
  "G": {bg1:"#071a0a",bg2:"#030d05",a:"#86efac",b:"#4ade80",c:"#22c55e",d:"#15803d",g1:"rgba(34,197,94,0.25)",g2:"rgba(34,197,94,0.55)"},
  // Multi — blend to closest feel
  "UB":{bg1:"#0a0820",bg2:"#050412",a:"#c084fc",b:"#818cf8",c:"#6d28d9",d:"#4338ca",g1:"rgba(109,40,217,0.27)",g2:"rgba(109,40,217,0.6)"},
  "WU":{bg1:"#0c1422",bg2:"#060a14",a:"#93c5fd",b:"#e0e8f8",c:"#3b82f6",d:"#1d4ed8",g1:"rgba(59,130,246,0.22)",g2:"rgba(59,130,246,0.5)"},
  "WB":{bg1:"#140a1c",bg2:"#0a060f",a:"#e2c4f8",b:"#b48ad4",c:"#8b5cf6",d:"#5b21b6",g1:"rgba(139,92,246,0.25)",g2:"rgba(139,92,246,0.55)"},
  "BR":{bg1:"#1a0808",bg2:"#0d0404",a:"#f87171",b:"#c084fc",c:"#9b1c1c",d:"#7c3aed",g1:"rgba(185,28,28,0.25)",g2:"rgba(124,58,237,0.5)"},
  "BG":{bg1:"#0a1410",bg2:"#050a07",a:"#86efac",b:"#c084fc",c:"#16a34a",d:"#6d28d9",g1:"rgba(22,163,74,0.22)",g2:"rgba(109,40,217,0.5)"},
  "RG":{bg1:"#140e04",bg2:"#0a0702",a:"#fbbf24",b:"#86efac",c:"#d97706",d:"#15803d",g1:"rgba(217,119,6,0.25)",g2:"rgba(21,128,61,0.5)"},
  "RW":{bg1:"#1a0e06",bg2:"#0d0703",a:"#fca5a5",b:"#fde68a",c:"#ef4444",d:"#d97706",g1:"rgba(239,68,68,0.22)",g2:"rgba(217,119,6,0.5)"},
  "GW":{bg1:"#0c1408",bg2:"#060a04",a:"#86efac",b:"#fde68a",c:"#16a34a",d:"#ca8a04",g1:"rgba(22,163,74,0.22)",g2:"rgba(202,138,4,0.5)"},
  "GU":{bg1:"#061814",bg2:"#030d0a",a:"#86efac",b:"#60a5fa",c:"#22c55e",d:"#3b82f6",g1:"rgba(34,197,94,0.2)",g2:"rgba(59,130,246,0.5)"},
  "UR":{bg1:"#0a0818",bg2:"#060410",a:"#c084fc",b:"#f87171",c:"#6d28d9",d:"#b91c1c",g1:"rgba(109,40,217,0.22)",g2:"rgba(185,28,28,0.5)"},
  // Default (colorless or undetected)
  "":  {bg1:"#1a0a2e",bg2:"#07070f",a:"#c084fc",b:"#818cf8",c:"#7c3aed",d:"#4f46e5",g1:"rgba(124,58,237,0.27)",g2:"rgba(124,58,237,0.6)"}
};

var COLOR_PIP_STYLES = {
  W:{bg:"#e5e4d0",fg:"#1e293b",border:"#c8c4a8"},
  U:{bg:"#1d4ed8",fg:"#fff",border:"#60a5fa"},
  B:{bg:"#2d1b4e",fg:"#e2d9f3",border:"#7c3aed"},
  R:{bg:"#991b1b",fg:"#fff",border:"#f87171"},
  G:{bg:"#14532d",fg:"#fff",border:"#4ade80"},
  C:{bg:"#1e293b",fg:"#94a3b8",border:"#475569"}
};

function applyColorTheme(colorIdentity) {
  // Build key from sorted color identity, fall back to pairs/singles/default
  var sorted = (colorIdentity || []).slice().sort().join('');
  var theme = COLOR_THEMES[sorted] || COLOR_THEMES[''];
  var root = document.documentElement;
  root.style.setProperty('--theme-a', theme.a);
  root.style.setProperty('--theme-b', theme.b);
  root.style.setProperty('--theme-c', theme.c);
  root.style.setProperty('--theme-d', theme.d);
  root.style.setProperty('--theme-bg1', theme.bg1);
  root.style.setProperty('--theme-bg2', theme.bg2);
  root.style.setProperty('--theme-glow1', theme.g1);
  root.style.setProperty('--theme-glow2', theme.g2);
  // Update body background
  document.body.style.background = 'radial-gradient(ellipse at 20% 10%, ' + theme.bg1 + ' 0%, ' + theme.bg2 + ' 60%, #0d0a14 100%)';
}

function renderColorPips(colorIdentity) {
  var container = document.getElementById('cmdColorPips');
  if (!container) return;
  if (!colorIdentity || colorIdentity.length === 0) { container.innerHTML = ''; return; }
  container.innerHTML = colorIdentity.map(function(c) {
    var s = COLOR_PIP_STYLES[c] || COLOR_PIP_STYLES['C'];
    return '<div class="color-pip" style="background:' + s.bg + ';color:' + s.fg + ';border-color:' + s.border + ';">' + c + '</div>';
  }).join('');
}

// ─── CARD DATABASE + SCRYFALL BATCH LOOKUP ───────────────────────────────────
// Global card DB: cardName.toLowerCase() → {type, cmc, isManaRock, rockBonus, tokenCount}
var CARD_DB = {};

var ROCK_MAP = {
  "sol ring":{cmc:1,bonus:2},"mana crypt":{cmc:0,bonus:2},"mox diamond":{cmc:0,bonus:1},
  "chrome mox":{cmc:0,bonus:1},"lotus petal":{cmc:0,bonus:1},"mana vault":{cmc:1,bonus:2},
  "grim monolith":{cmc:2,bonus:2},"basalt monolith":{cmc:3,bonus:3},"gilded lotus":{cmc:5,bonus:3},
  "thran dynamo":{cmc:4,bonus:3},"worn powerstone":{cmc:3,bonus:2},"everflowing chalice":{cmc:2,bonus:1},
  "mind stone":{cmc:2,bonus:1},"thought vessel":{cmc:2,bonus:1},"coalition relic":{cmc:3,bonus:1},
  "chromatic lantern":{cmc:3,bonus:1},"darksteel ingot":{cmc:3,bonus:1},
  "commanders sphere":{cmc:3,bonus:1},"commander's sphere":{cmc:3,bonus:1},
  "arcane signet":{cmc:2,bonus:1},"fellwar stone":{cmc:2,bonus:1},"coldsteel heart":{cmc:2,bonus:1},
  "cryptolith fragment":{cmc:3,bonus:1},"midnight clock":{cmc:3,bonus:1},
  "heraldic banner":{cmc:3,bonus:1},"prismatic lens":{cmc:2,bonus:1},"star compass":{cmc:2,bonus:1}
};

// Parse token count from Scryfall oracle text
// Catches: "create a", "create two 2/2", "create X", "create three 1/1" etc.
function parseTokensFromOracle(oracle) {
  if (!oracle) return 0;
  var numWords = {a:1,an:1,one:1,two:2,three:3,four:4,five:5,six:6,seven:7,eight:8,nine:9,ten:10,thirteen:13};
  var best = 0;
  // Match "create <qty> ... token" patterns
  var re = /create\s+([a-z]+|\d+|x)\s[^.!?]*?tokens?/gi;
  var m;
  while ((m = re.exec(oracle)) !== null) {
    var raw = m[1].toLowerCase();
    var n = parseInt(raw, 10);
    if (isNaN(n)) n = numWords[raw] || 1;
    if (n > best) best = n;
  }
  return best;
}

// Map Scryfall type_line → simulation card type
// Key fix: "Legendary Planeswalker — Vraska" is a planeswalker;
// "Legendary Creature — Human Pirate" is a creature even if named Vraska.
function scryfallTypeLine(type_line) {
  if (!type_line) return 'creature';
  var t = type_line.toLowerCase();
  if (t.includes('land'))         return 'land';
  if (t.includes('planeswalker')) return 'planeswalker';
  if (t.includes('artifact'))     return 'artifact';
  if (t.includes('enchantment'))  return 'enchantment';
  if (t.includes('instant'))      return 'instant';
  if (t.includes('sorcery'))      return 'sorcery';
  if (t.includes('creature'))     return 'creature';
  return 'creature';
}

// Check if a card is a mana rock given its name + type
function detectManaRock(name, type_line, oracle) {
  var n = name.toLowerCase();
  // Explicit ROCK_MAP entries
  var keys = Object.keys(ROCK_MAP);
  for (var ri = 0; ri < keys.length; ri++) {
    if (n.indexOf(keys[ri]) !== -1) return {yes:true, bonus:ROCK_MAP[keys[ri]].bonus, cmc:ROCK_MAP[keys[ri]].cmc};
  }
  // Pattern-based artifact mana rocks
  if ((type_line||'').toLowerCase().includes('artifact') &&
      (n.indexOf('signet')!==-1||n.indexOf('talisman')!==-1||n.indexOf('locket')!==-1||
       n.indexOf('keyrune')!==-1||n.indexOf('cluestone')!==-1||n.indexOf('obelisk')!==-1||
       n.indexOf('medallion')!==-1||n.indexOf('banner')!==-1)) {
    return {yes:true, bonus:1, cmc:2};
  }
  // Oracle-based: "add {" suggests mana production
  if ((type_line||'').toLowerCase().includes('artifact') && oracle && /\badd \{/.test(oracle)) {
    return {yes:true, bonus:1, cmc:2};
  }
  return {yes:false};
}

// Batch-fetch up to 75 cards per request from Scryfall /cards/collection
async function batchScryfallLookup(names, onProgress) {
  var results = {};
  var chunks = [];
  for (var i = 0; i < names.length; i += 75) chunks.push(names.slice(i, i+75));
  var done = 0;
  for (var ci = 0; ci < chunks.length; ci++) {
    var identifiers = chunks[ci].map(function(n){ return {name:n}; });
    try {
      var resp = await fetch('https://api.scryfall.com/cards/collection', {
        method: 'POST',
        headers: {'Content-Type':'application/json'},
        body: JSON.stringify({identifiers: identifiers})
      });
      var json = await resp.json();
      if (json && json.data) {
        json.data.forEach(function(card) {
          var key = card.name.toLowerCase();
          // For double-faced cards (DFCs), get type_line and oracle from front face
          var type_line = card.type_line || (card.card_faces ? card.card_faces[0].type_line : '');
          var oracle = card.oracle_text || (card.card_faces ? card.card_faces.map(function(f){return f.oracle_text||'';}).join('\n') : '');
          var cmc = card.cmc !== undefined ? Math.round(card.cmc) : 3;
          var simType = scryfallTypeLine(type_line);
          var tokenCount = parseTokensFromOracle(oracle);
          var rock = detectManaRock(card.name, type_line, oracle);
          if (rock.yes && simType === 'artifact') {
            if (rock.cmc !== undefined) cmc = rock.cmc;
          }
          results[key] = {
            type: simType, cmc: cmc,
            isManaRock: rock.yes && simType === 'artifact',
            rockBonus: rock.bonus || 1,
            tokenCount: tokenCount,
            color_identity: card.color_identity || []
          };
        });
      }
    } catch(e) { /* network error — handled by fallback */ }
    done += chunks[ci].length;
    if (onProgress) onProgress(done, names.length);
    // Respect Scryfall rate limit (~10 req/s)
    if (ci < chunks.length - 1) await new Promise(function(r){ setTimeout(r, 110); });
  }
  return results;
}

// Local fallback when Scryfall is unreachable
function inferCardFallback(name) {
  var n = name.toLowerCase().trim();
  if (BASIC_LAND_NAMES.indexOf(n) !== -1) return {type:'land', cmc:0, isBasic:true, isManaRock:false, tokenCount:0};
  var keys = Object.keys(ROCK_MAP);
  for (var ri = 0; ri < keys.length; ri++) {
    if (n.indexOf(keys[ri]) !== -1) {
      var r = ROCK_MAP[keys[ri]];
      return {type:'artifact', cmc:r.cmc, rockBonus:r.bonus, isManaRock:true, tokenCount:0};
    }
  }
  if (n.indexOf('signet')!==-1||n.indexOf('talisman')!==-1||n.indexOf('locket')!==-1||
      n.indexOf('keyrune')!==-1||n.indexOf('cluestone')!==-1||n.indexOf('obelisk')!==-1)
    return {type:'artifact', cmc:2, rockBonus:1, isManaRock:true, tokenCount:0};
  var landWords = ['abbey','barrens','bay','bog','catacomb','cavern','citadel','clearing','coast','confluence','crag','crossing','delta','depths','expanse','falls','fen','field','flats','fortress','fountain','garden','gate','glade','grove','grotto','harbor','haven','highland','hollow','keep','lake','lair','lowland','manor','marsh','mire','monastery','moor','nexus','outpost','overlook','peak','pool','port','prairie','reach','refuge','ruins','river','road','sanctum','sanctuary','scrub','sea','shore','shrine','sink','spring','steppe','strand','stronghold','summit','tarn','temple','thicket','tomb','tower','trail','tundra','vale','vault','vista','wilds','wood'];
  for (var li = 0; li < landWords.length; li++) {
    if (n.indexOf(landWords[li]) !== -1) return {type:'land', cmc:0, isBasic:false, isManaRock:false, tokenCount:0};
  }
  if (/\b(drowned|fetid|hallowed|breeding|overgrown|stomping|watery|godless|glacial|sulfur|woodland|hinterland|clifftop|isolated|sunpetal|rootbound|dragonskull|steam|blood|sacred foundry)\b/.test(n))
    return {type:'land', cmc:0, isBasic:false, isManaRock:false, tokenCount:0};
  return {type:'creature', cmc:3, isManaRock:false, tokenCount:0};
}

function resolveCard(name) {
  var key = name.toLowerCase().trim();
  if (CARD_DB[key]) {
    var d = CARD_DB[key];
    return { name:name, type:d.type, cmc:d.cmc, isManaRock:d.isManaRock, rockBonus:d.rockBonus||1, tokenCount:d.tokenCount||0 };
  }
  return Object.assign({name:name}, inferCardFallback(name));
}

var PARSED_DECK = [];
var COMMANDER = null;

function parseDeck() {
  var raw = document.getElementById('deckInput').value.trim();
  var inp = document.getElementById('deckInput');
  inp.classList.remove('input-error','input-ok');
  if (!raw) { displayErrors(['Decklist is empty. Paste your list above.']); inp.classList.add('input-error'); shakeEl(inp); return; }

  var lines = raw.split('\n');
  var cards = [];
  var parseErrs = [];
  for (var i = 0; i < lines.length; i++) {
    var line = lines[i].trim();
    if (!line) continue;
    if (/^(\/\/|##|--)/.test(line)) continue;
    if (line.charAt(0) === '#') continue;
    var m = line.match(/^(\d+)[xX]?\s+(.+?)(\s+\([A-Z0-9a-z]+\)\s*\d*)?(\s*\*[FE]\*)?$/);
    if (m) {
      var qty = parseInt(m[1], 10);
      var name = m[2].trim();
      for (var q = 0; q < qty; q++) cards.push(name);
    } else {
      var bare = line.replace(/\s*\([A-Z0-9a-z]+\)\s*\d*\s*(\*[FE]\*)?$/, '').trim();
      if (bare && !/^\d+$/.test(bare)) cards.push(bare);
      else parseErrs.push('Could not parse line ' + (i+1) + ': "' + line + '"');
    }
  }
  if (parseErrs.length) { displayErrors(parseErrs); inp.classList.add('input-error'); shakeEl(inp); return; }

  var errors = [];
  var total = cards.length;
  var nameCount = {};
  for (var ci = 0; ci < cards.length; ci++) { var key = cards[ci].toLowerCase(); nameCount[key] = (nameCount[key]||0)+1; }
  var dupes = [];
  var nkeys = Object.keys(nameCount);
  for (var ki = 0; ki < nkeys.length; ki++) {
    if (BASIC_LAND_NAMES.indexOf(nkeys[ki]) !== -1) continue;
    if (nameCount[nkeys[ki]] > 1) {
      var dname = '';
      for (var ci2 = 0; ci2 < cards.length; ci2++) { if (cards[ci2].toLowerCase() === nkeys[ki]) { dname = cards[ci2]; break; } }
      dupes.push(dname + ' (x' + nameCount[nkeys[ki]] + ')');
    }
  }
  if (dupes.length) errors.push('Duplicate non-basic cards: ' + dupes.join(', '));
  if (total < 100) errors.push('Too few cards: ' + total + ' total (need exactly 100, including commander).');
  if (total > 100) errors.push('Too many cards: ' + total + ' total (need exactly 100, including commander).');
  if (errors.length) { displayErrors(errors, total); inp.classList.add('input-error'); shakeEl(inp); return; }

  var cmdName = cards[0];
  document.getElementById('parseBtn').disabled = true;
  document.getElementById('cmcHint').innerHTML = '<span style="color:#fbbf24">&#9679; Fetching all card data from Scryfall…</span>';

  // Get unique names for batch lookup
  var seen = {}, uniqueNames = [];
  for (var ui = 0; ui < cards.length; ui++) {
    var uk = cards[ui].toLowerCase();
    if (!seen[uk]) { seen[uk] = true; uniqueNames.push(cards[ui]); }
  }

  // Show progress bar
  var sfProg = document.getElementById('scryfallProgress');
  sfProg.classList.add('active');
  document.getElementById('sfStatusText').textContent = 'Fetching ' + uniqueNames.length + ' unique cards from Scryfall…';
  document.getElementById('sfBarFill').style.width = '0%';

  batchScryfallLookup(uniqueNames, function(done, tot) {
    document.getElementById('sfBarFill').style.width = Math.round((done/tot)*100) + '%';
    document.getElementById('sfStatusText').textContent = 'Scryfall: ' + done + ' / ' + tot + ' cards verified…';
  }).then(function(dbResults) {
    Object.assign(CARD_DB, dbResults);
    sfProg.classList.remove('active');
    document.getElementById('parseBtn').disabled = false;

    // Commander data
    var cmdKey = cmdName.toLowerCase();
    var cmdData = CARD_DB[cmdKey];
    var cmcVal = cmdData ? cmdData.cmc : parseInt(document.getElementById('cmdCmcInput').value, 10);
    if (isNaN(cmcVal) || cmcVal < 0) cmcVal = 5;
    document.getElementById('cmdCmcInput').value = cmcVal;
    var colorIdentity = cmdData ? (cmdData.color_identity || []) : [];

    if (cmdData) {
      document.getElementById('cmcHint').innerHTML = '<span style="color:#4ade80">&#10003; CMC <strong>' + cmcVal + '</strong> auto-detected &middot; ' + Object.keys(CARD_DB).length + ' cards verified via Scryfall</span>';
    } else {
      document.getElementById('cmcHint').innerHTML = '<span style="color:#fbbf24">&#9888; Commander not found on Scryfall &mdash; CMC set to ' + cmcVal + ' &middot; Adjust if needed</span>';
    }
    finishLoadDeck(cards, cmdName, cmcVal, total, colorIdentity);
  }).catch(function() {
    sfProg.classList.remove('active');
    document.getElementById('parseBtn').disabled = false;
    var cmcFallback = parseInt(document.getElementById('cmdCmcInput').value, 10);
    if (isNaN(cmcFallback) || cmcFallback < 0) cmcFallback = 5;
    document.getElementById('cmcHint').innerHTML = '<span style="color:#f87171">&#9888; Scryfall unreachable &mdash; using local inference &middot; CMC set to ' + cmcFallback + '</span>';
    finishLoadDeck(cards, cmdName, cmcFallback, total, []);
  });
}

function finishLoadDeck(cards, cmdName, cmcVal, total, colorIdentity) {
  var inp = document.getElementById('deckInput');
  COMMANDER = { name:cmdName, type:'creature', cmc:cmcVal, isCommander:true };
  PARSED_DECK = [];
  for (var di = 1; di < cards.length; di++) PARSED_DECK.push(resolveCard(cards[di]));
  inp.classList.add('input-ok');

  var typeCounts = {};
  for (var pi = 0; pi < PARSED_DECK.length; pi++) { var t = PARSED_DECK[pi].type; typeCounts[t] = (typeCounts[t]||0)+1; }
  displaySuccess(cmdName, cmcVal, total, typeCounts, colorIdentity);

  document.getElementById('cmdNameText').textContent = cmdName;
  document.getElementById('cmdSubText').textContent = 'CMC ' + cmcVal + ' \u00b7 +2 mana tax per recast';
  document.getElementById('cmdDisplay').style.display = 'block';
  document.getElementById('mainTitle').textContent = cmdName;
  document.getElementById('mainSubtitle').textContent = 'Commander Deck \u00b7 99 Cards \u00b7 Monte Carlo Simulation';

  // Apply commander color theme + render pips
  applyColorTheme(colorIdentity);
  renderColorPips(colorIdentity);

  document.getElementById('simBtn').disabled = false;
  var sc = parseInt(document.getElementById('simCountInput').value, 10);
  document.getElementById('simBtn').textContent = '\u25B6 SIMULATE ' + ((!isNaN(sc)&&sc>=10&&sc<=1000)?sc:100) + ' GAMES';
  document.getElementById('results').style.display = 'none';
}

function displayErrors(errs, total) {
  var vb = document.getElementById('validationBox');
  vb.className = 'show-error';
  var html = '<div class="v-title v-err">&#10007; DECKLIST ERRORS</div>';
  if (total !== undefined) html += '<div class="v-item v-dim">Cards counted: ' + total + ' / 100</div>';
  for (var i = 0; i < errs.length; i++) html += '<div class="v-item v-err">&rsaquo; ' + errs[i] + '</div>';
  vb.innerHTML = html;
  document.getElementById('deckPreview').style.display = 'none';
  document.getElementById('cmdDisplay').style.display = 'none';
  document.getElementById('simBtn').disabled = true;
}

function displaySuccess(cmdName, cmc, total, typeCounts, colorIdentity) {
  var vb = document.getElementById('validationBox');
  vb.className = 'show-ok';
  var ciStr = (colorIdentity && colorIdentity.length) ? '{' + colorIdentity.join('') + '}' : '{C}';
  vb.innerHTML = '<div class="v-title v-ok">&#10003; VALID &mdash; ' + total + ' cards loaded &middot; Scryfall-verified</div>'
    + '<div class="v-item v-ok">&rsaquo; Commander: ' + cmdName + ' &mdash; CMC ' + cmc + ' ' + ciStr + '</div>'
    + '<div class="v-item v-dim">&rsaquo; 99-card library ready for simulation</div>';
  var order = ['creature','land','artifact','instant','sorcery','enchantment','planeswalker'];
  var colors = {creature:'#a78bfa',land:'#4ade80',artifact:'#94a3b8',instant:'#60a5fa',sorcery:'#c084fc',enchantment:'#86efac',planeswalker:'#f87171'};
  var pills = '';
  for (var oi = 0; oi < order.length; oi++) {
    var ot = order[oi];
    if (typeCounts[ot]) pills += '<div class="pill"><span style="color:' + colors[ot] + '">' + typeCounts[ot] + '</span> ' + ot + 's</div>';
  }
  var prev = document.getElementById('deckPreview');
  prev.style.display = 'block';
  prev.innerHTML = '<div class="preview-title">DECK BREAKDOWN — Scryfall-verified (99 cards, excl. commander)</div><div class="preview-pills">' + pills + '</div>';
}

function clearDeck() {
  var inp = document.getElementById('deckInput');
  inp.value = ''; inp.className = '';
  document.getElementById('validationBox').className = '';
  document.getElementById('validationBox').innerHTML = '';
  document.getElementById('deckPreview').style.display = 'none';
  document.getElementById('cmdDisplay').style.display = 'none';
  document.getElementById('simBtn').disabled = true;
  document.getElementById('results').style.display = 'none';
  document.getElementById('cardCountLive').innerHTML = '';
  document.getElementById('mainTitle').textContent = 'MTG Commander Sim';
  document.getElementById('mainSubtitle').textContent = 'Paste your 100-card decklist below to begin';
  document.getElementById('cmcHint').innerHTML = 'Will auto-detect via Scryfall after loading decklist &middot; Override manually if needed';
  document.getElementById('cmdCmcInput').disabled = false;
  document.getElementById('cmdColorPips').innerHTML = '';
  document.getElementById('scryfallProgress').classList.remove('active');
  applyColorTheme([]); // reset to default purple
  PARSED_DECK = []; COMMANDER = null; CARD_DB = {};
}

function shakeEl(el) {
  el.classList.add('shake');
  setTimeout(function(){ el.classList.remove('shake'); }, 500);
}

document.addEventListener('DOMContentLoaded', function() {
  document.getElementById('deckInput').addEventListener('input', function() {
    var raw = this.value.trim();
    if (!raw) { document.getElementById('cardCountLive').innerHTML = ''; return; }
    var lines = raw.split('\n');
    var total = 0;
    for (var i = 0; i < lines.length; i++) {
      var l = lines[i].trim();
      if (!l || /^(\/\/|##|--)/.test(l) || l.charAt(0) === '#') continue;
      var m = l.match(/^(\d+)[xX]?\s+/);
      total += m ? parseInt(m[1], 10) : 1;
    }
    var col = total === 100 ? '#4ade80' : (total > 100 ? '#f87171' : '#fbbf24');
    document.getElementById('cardCountLive').innerHTML = '<span style="color:' + col + '">' + total + '</span> / 100';
  });
  document.getElementById('simCountInput').addEventListener('input', function() {
    if (parseInt(this.value, 10) > 1000) this.value = 1000;
    var btn = document.getElementById('simBtn');
    if (btn.disabled) return;
    var v = parseInt(this.value, 10);
    var n = (!isNaN(v) && v >= 10 && v <= 1000) ? v : 100;
    btn.textContent = '\u25B6 SIMULATE ' + n + ' GAMES';
  });
});

// ─── SIMULATION ───────────────────────────────────────────────────────────────

function shuffle(arr) {
  var a = arr.map(function(c, i) { return Object.assign({}, c, {uid: i + '-' + Math.random()}); });
  for (var i = a.length - 1; i > 0; i--) {
    var j = Math.floor(Math.random() * (i + 1));
    var t = a[i]; a[i] = a[j]; a[j] = t;
  }
  return a;
}

function isKeepable(hand) {
  var l = hand.filter(function(c) { return c.type === 'land'; }).length;
  return l >= 2 && l <= 5;
}

function simulateGame() {
  var lib = shuffle(PARSED_DECK);
  var hand = lib.splice(0, 7);
  var mulls = 0;
  if (!isKeepable(hand)) {
    mulls++;
    lib = shuffle(lib.concat(hand));
    hand = lib.splice(0, 7);
  }
  while (!isKeepable(hand) && mulls < 4) {
    mulls++;
    lib = shuffle(lib.concat(hand));
    hand = lib.splice(0, 7 - mulls + 1);
  }

  // Count basic land types in opening hand
  var openingBasics = {Plains:0, Island:0, Swamp:0, Mountain:0, Forest:0, Wastes:0, total:0};
  for (var hb = 0; hb < hand.length; hb++) {
    var hn = hand[hb].name.toLowerCase();
    if (hn === "plains" || hn === "snow-covered plains")        { openingBasics.Plains++;  openingBasics.total++; }
    else if (hn === "island" || hn === "snow-covered island")   { openingBasics.Island++;  openingBasics.total++; }
    else if (hn === "swamp" || hn === "snow-covered swamp")     { openingBasics.Swamp++;   openingBasics.total++; }
    else if (hn === "mountain" || hn === "snow-covered mountain"){ openingBasics.Mountain++; openingBasics.total++; }
    else if (hn === "forest" || hn === "snow-covered forest")   { openingBasics.Forest++;  openingBasics.total++; }
    else if (hn === "wastes")                                    { openingBasics.Wastes++;  openingBasics.total++; }
  }

  var openingHand = hand.slice(); // snapshot of kept opening hand

  var board = [], gy = [], tokens = 0;
  var handArr = hand.slice(), libArr = lib.slice();
  var cmdCasts = 0, cmdOut = false, cmdTurn = null;
  var logs = [];
  var cmdCmc = COMMANDER.cmc;
  var cantrips = ["Brainstorm","Sign in Blood","Ponder","Preordain","Night's Whisper"];

  // Check if a doubler (Parallel Lives, Doubling Season, Anointed Procession) is on board
  function getTokenMultiplier() {
    var mult = 1;
    for (var bi = 0; bi < board.length; bi++) {
      var bn = board[bi].name.toLowerCase();
      if (bn.indexOf("parallel lives") !== -1 || bn.indexOf("doubling season") !== -1 || bn.indexOf("anointed procession") !== -1) mult *= 2;
    }
    return mult;
  }

  for (var turn = 1; turn <= 10; turn++) {
    var actions = [];
    var dr = libArr.shift();
    if (dr) { handArr.push(dr); actions.push({type:"draw", text:"Drew: " + dr.name}); }
    var landCt = board.filter(function(c) { return c.type === 'land'; }).length;
    var rockMana = board.filter(function(c) { return c.type === 'artifact' && c.isManaRock; }).reduce(function(s, r) { return s + (r.rockBonus || 1); }, 0);
    var mana = landCt + rockMana;
    var landIdx = -1;
    for (var k = 0; k < handArr.length; k++) { if (handArr[k].type === 'land') { landIdx = k; break; } }
    if (landIdx !== -1) {
      var ld = handArr.splice(landIdx, 1)[0];
      board.push(ld); mana++;
      actions.push({type:"land", text:"Played: " + ld.name});
    }
    var rocks = handArr.filter(function(c) { return c.type === 'artifact' && c.isManaRock && c.cmc <= mana; });
    rocks.sort(function(a, b) { return a.cmc - b.cmc; });
    for (var ri = 0; ri < rocks.length; ri++) {
      var rk = rocks[ri];
      if (rk.cmc <= mana) { mana -= rk.cmc; mana += (rk.rockBonus || 1); handArr = handArr.filter(function(c) { return c.uid !== rk.uid; }); board.push(rk); actions.push({type:"cast", text:"Cast: " + rk.name + " (mana rock)"}); }
    }
    if (!cmdOut) {
      var cmdCost = cmdCmc + (cmdCasts * 2);
      if (mana >= cmdCost) { mana -= cmdCost; cmdOut = true; cmdCasts++; cmdTurn = turn; board.push(Object.assign({}, COMMANDER, {uid:'cmd-' + cmdCasts})); actions.push({type:"cmd", text:"Cast COMMANDER: " + COMMANDER.name + " (cost " + cmdCost + ")"}); }
    }
    var castable = handArr.filter(function(c) { return c.type !== 'land' && !c.isManaRock && c.cmc <= mana; });
    castable.sort(function(a, b) { return a.cmc - b.cmc; });
    var spent = 0;
    for (var si = 0; si < castable.length; si++) {
      var sp = castable[si];
      if (spent + sp.cmc > mana) continue;
      spent += sp.cmc;
      handArr = handArr.filter(function(c) { return c.uid !== sp.uid; });
      if (["creature","artifact","enchantment","planeswalker"].indexOf(sp.type) !== -1) {
        board.push(sp);
        actions.push({type:"cast", text:"Cast: " + sp.name + " (" + sp.type + ")"});
        // Accurate token creation with doubler support
        var tc = sp.tokenCount || 0;
        if (tc > 0) {
          var actualTokens = tc * getTokenMultiplier();
          tokens += actualTokens;
          actions.push({type:"token", text:"  \u2736 " + actualTokens + " token" + (actualTokens !== 1 ? "s" : "") + " created by " + sp.name});
        }
      } else {
        gy.push(sp);
        actions.push({type:"cast", text:"Cast: " + sp.name + " (" + sp.type + ")"});
        if (cantrips.indexOf(sp.name) !== -1) { var d2 = libArr.shift(); if (d2) { handArr.push(d2); actions.push({type:"draw", text:"  Drew: " + d2.name}); } }
      }
    }
    var crCount = board.filter(function(c) { return c.type === 'creature'; }).length;
    var lc = board.filter(function(c) { return c.type === 'land'; }).length;
    logs.push({ turn: turn, actions: actions, mana: mana, handSize: handArr.length, creatureCount: crCount, tokenCount: tokens, landCount: lc, commanderOut: cmdOut, boardState: crCount + " creatures, " + tokens + " tokens, " + lc + " lands" });
  }
  return { mulligans: mulls, openingBasics: openingBasics, openingHand: openingHand, logs: logs, finalHand: handArr, finalBoard: board, finalGY: gy, cmdTurn: cmdTurn, finalTokens: tokens };
}

// ─── OPENING HAND BASICS ANALYSIS ────────────────────────────────────────────

function buildOpeningBasicsData() {
  var SIM_COUNT = ALL_RESULTS.length;
  var types = ["Plains","Island","Swamp","Mountain","Forest","Wastes"];
  var colorHex = {Plains:"#f9f7e8",Island:"#60a5fa",Swamp:"#c084fc",Mountain:"#f87171",Forest:"#4ade80",Wastes:"#94a3b8"};
  var pipBg   = {Plains:"#e5e4d0",Island:"#1d4ed8",Swamp:"#4c1d95",Mountain:"#991b1b",Forest:"#14532d",Wastes:"#1e293b"};
  var pipFg   = {Plains:"#1e293b",Island:"#fff",Swamp:"#fff",Mountain:"#fff",Forest:"#fff",Wastes:"#fff"};
  var colorLetter = {Plains:"W",Island:"U",Swamp:"B",Mountain:"R",Forest:"G",Wastes:"C"};

  // Count how many basics of each type exist in deck
  var deckCounts = {Plains:0,Island:0,Swamp:0,Mountain:0,Forest:0,Wastes:0};
  for (var di = 0; di < PARSED_DECK.length; di++) {
    var dn = PARSED_DECK[di].name.toLowerCase();
    if (dn === "plains" || dn === "snow-covered plains") deckCounts.Plains++;
    else if (dn === "island" || dn === "snow-covered island") deckCounts.Island++;
    else if (dn === "swamp" || dn === "snow-covered swamp") deckCounts.Swamp++;
    else if (dn === "mountain" || dn === "snow-covered mountain") deckCounts.Mountain++;
    else if (dn === "forest" || dn === "snow-covered forest") deckCounts.Forest++;
    else if (dn === "wastes") deckCounts.Wastes++;
  }

  // Sum across all simulations
  var totals = {Plains:0,Island:0,Swamp:0,Mountain:0,Forest:0,Wastes:0,total:0};
  var atLeastOne = {Plains:0,Island:0,Swamp:0,Mountain:0,Forest:0,Wastes:0}; // games where >=1 of this type opened
  for (var ri = 0; ri < ALL_RESULTS.length; ri++) {
    var ob = ALL_RESULTS[ri].openingBasics;
    for (var ti = 0; ti < types.length; ti++) {
      totals[types[ti]] += ob[types[ti]];
      if (ob[types[ti]] > 0) atLeastOne[types[ti]]++;
    }
    totals.total += ob.total;
  }

  var result = [];
  for (var oi = 0; oi < types.length; oi++) {
    var tp = types[oi];
    if (deckCounts[tp] === 0) continue; // skip colors not in deck
    result.push({
      type: tp,
      letter: colorLetter[tp],
      hex: colorHex[tp],
      pipBg: pipBg[tp],
      pipFg: pipFg[tp],
      deckCount: deckCounts[tp],
      avgPerHand: totals[tp] / SIM_COUNT,
      openedAtLeastOnce: atLeastOne[tp],
      pctAtLeastOne: (atLeastOne[tp] / SIM_COUNT) * 100
    });
  }
  return result;
}

// ─── AGGREGATION ──────────────────────────────────────────────────────────────

var ALL_RESULTS = [];
var SELECTED_RUN = 0;
var LAST_AGGREGATED = {};

function runSims() {
  if (!PARSED_DECK.length || !COMMANDER) return;
  var btn = document.getElementById('simBtn');
  var simCountRaw = parseInt(document.getElementById('simCountInput').value, 10);
  var SIM_COUNT = (!isNaN(simCountRaw) && simCountRaw >= 10 && simCountRaw <= 1000) ? simCountRaw : 100;
  btn.disabled = true; btn.textContent = 'SIMULATING ' + SIM_COUNT + ' GAMES...';
  setTimeout(function() {
    ALL_RESULTS = [];
    for (var i = 0; i < SIM_COUNT; i++) ALL_RESULTS.push(simulateGame());
    var avgM = ALL_RESULTS.reduce(function(s, r) { return s + r.mulligans; }, 0) / SIM_COUNT;
    var ct = ALL_RESULTS.map(function(r) { return r.cmdTurn; }).filter(function(t) { return t !== null; });
    var avgC = ct.length ? ct.reduce(function(a, b) { return a + b; }, 0) / ct.length : null;
    var cRate = (ct.length / SIM_COUNT) * 100;
    var tAvg = [];
    for (var ti = 0; ti < 10; ti++) {
      var td = ALL_RESULTS.map(function(r) { return r.logs[ti]; }).filter(Boolean);
      tAvg.push({ turn: ti+1, avgCreatures: td.reduce(function(s,l){return s+l.creatureCount;},0)/td.length, avgTokens: td.reduce(function(s,l){return s+l.tokenCount;},0)/td.length, avgLands: td.reduce(function(s,l){return s+l.landCount;},0)/td.length, avgHandSize: td.reduce(function(s,l){return s+l.handSize;},0)/td.length });
    }
    var mDist = [0,1,2,3,4].map(function(m) { return { count: m, games: ALL_RESULTS.filter(function(r) { return r.mulligans === m; }).length }; });
    var cDist = [];
    for (var t = 1; t <= 10; t++) cDist.push({ turn: t, count: ALL_RESULTS.filter(function(r) { return r.cmdTurn === t; }).length });
    // Opening hand basics analysis (uses ALL_RESULTS, so call after sims)
    var colorData = buildOpeningBasicsData();
    LAST_AGGREGATED = { avgM: avgM, cRate: cRate, avgC: avgC, tAvg: tAvg, mDist: mDist, cDist: cDist, colorData: colorData, simCount: SIM_COUNT };
    renderSummary(avgM, cRate, avgC, tAvg);
    renderStats(mDist, tAvg, cDist, cRate, colorData);
    renderCharts(tAvg);
    renderRuns();
    document.getElementById('results').style.display = 'block';
    btn.disabled = false;
    btn.textContent = '\u21ba RE-SIMULATE ' + SIM_COUNT + ' GAMES';
    switchTab('stats');
  }, 50);
}

function renderSummary(avgM, cRate, avgC, tAvg) {
  // Mulligan color: green=good(low), red=bad(high). Scale 0=green, >=1.5=red
  var mullColor = avgM <= 0.3 ? '#4ade80' : avgM <= 0.7 ? '#a3e635' : avgM <= 1.1 ? '#fbbf24' : avgM <= 1.5 ? '#fb923c' : '#f87171';
  var stats = [
    {label:"Avg Mulligans",     value: avgM.toFixed(2),                    color: mullColor},
    {label:"Cmd Cast Rate",     value: cRate.toFixed(0) + "%",             color:"#c084fc"},
    {label:"Avg Cmd Turn",      value: avgC ? avgC.toFixed(1) : "N/A",     color:"#a78bfa"},
    {label:"Avg T10 Creatures", value: tAvg[9].avgCreatures.toFixed(1),    color:"#818cf8"},
    {label:"Avg T10 Tokens",    value: tAvg[9].avgTokens.toFixed(1),       color:"#fbbf24"},
    {label:"Avg T10 Lands",     value: tAvg[9].avgLands.toFixed(1),        color:"#4ade80"}
  ];
  var h = '';
  for (var i = 0; i < stats.length; i++) {
    var s = stats[i];
    h += '<div class="stat-card" style="border:1px solid ' + s.color + '33"><div class="stat-val" style="color:' + s.color + '">' + s.value + '</div><div class="stat-lbl">' + s.label.toUpperCase() + '</div></div>';
  }
  document.getElementById('summaryRow').innerHTML = h;
}

function renderStats(mDist, tAvg, cDist, cRate, colorData) {
  var SIM_COUNT = LAST_AGGREGATED.simCount || 100;
  // Mulligan color: inverted — 0=green(good), increasing=worse(red)
  var mc = ["#4ade80","#a3e635","#fbbf24","#f87171","#ef4444"];
  var mh = '<div class="box-title">MULLIGAN DISTRIBUTION</div><div style="font-size:9px;color:#475569;margin-bottom:10px">Green = good opening hand &nbsp;&middot;&nbsp; Red = many mulligans</div>';
  for (var mi = 0; mi < mDist.length; mi++) {
    var m = mDist[mi]; var lbl = m.count === 0 ? "No mulligan" : m.count + " mulligan" + (m.count > 1 ? "s" : ""); var pct = Math.min(100, (m.games / SIM_COUNT) * 100);
    mh += '<div class="bar-row"><div class="bar-header"><span>' + lbl + '</span><span style="color:' + mc[m.count] + '">' + m.games + '</span></div><div class="bar-track"><div class="bar-fill" style="width:' + pct + '%;background:' + mc[m.count] + '"></div></div></div>';
  }
  var bh = '<div class="box-title">AVG BOARD BY TURN</div>';
  for (var ti = 0; ti < tAvg.length; ti++) {
    var t = tAvg[ti]; var lp = Math.min(55,(t.avgLands/10)*55); var cp = Math.min(30,(t.avgCreatures/6)*30); var tp = Math.min(15,(t.avgTokens/4)*15);
    bh += '<div class="turn-row"><div class="turn-label">T'+t.turn+'</div><div class="turn-bars"><div class="turn-bar" style="background:#4ade80;width:'+lp+'%"></div><div class="turn-bar" style="background:#818cf8;width:'+cp+'%"></div><div class="turn-bar" style="background:#fbbf24;width:'+tp+'%"></div></div><div class="turn-nums"><span style="color:#4ade80">'+t.avgLands.toFixed(1)+'L </span><span style="color:#818cf8">'+t.avgCreatures.toFixed(1)+'C </span><span style="color:#fbbf24">'+t.avgTokens.toFixed(1)+'T</span></div></div>';
  }
  bh += '<div style="margin-top:10px;display:flex;gap:12px;font-size:9px"><span style="color:#4ade80">&#9632; Lands</span><span style="color:#818cf8">&#9632; Creatures</span><span style="color:#fbbf24">&#9632; Tokens</span></div>';
  var maxC = Math.max.apply(null, cDist.map(function(d){return d.count;})); maxC = Math.max(maxC,1);
  var notCast = ALL_RESULTS.filter(function(r){return !r.cmdTurn;}).length;
  var ch = '<div class="box-title">COMMANDER CAST TURN &nbsp;<span style="color:#475569;font-size:9px;font-weight:400">'+cRate.toFixed(0)+'% within 10 turns (CMC '+COMMANDER.cmc+')</span></div><div class="cmd-dist">';
  for (var ci = 0; ci < cDist.length; ci++) {
    var d = cDist[ci]; var ht = Math.max(3,(d.count/maxC)*70);
    ch += '<div class="cmd-bar-wrap"><div class="cmd-bar-count">'+d.count+'</div><div class="cmd-bar" style="height:'+ht+'px;background:linear-gradient(180deg,#c084fc,#7c3aed)"></div><div class="cmd-bar-label">T'+d.turn+'</div></div>';
  }
  var nh = Math.max(3,(notCast/SIM_COUNT)*70);
  ch += '<div class="cmd-bar-wrap"><div class="cmd-bar-count" style="color:#f87171">'+notCast+'</div><div class="cmd-bar" style="height:'+nh+'px;background:linear-gradient(180deg,#f87171,#dc2626)"></div><div class="cmd-bar-label">None</div></div></div>';
  var maxL = Math.max.apply(null,tAvg.map(function(t){return t.avgLands;})); maxL = Math.max(maxL,1);
  var lh = '<div class="box-title">AVG LANDS PER TURN</div>';
  for (var li = 0; li < tAvg.length; li++) {
    var lt = tAvg[li]; var pct2 = Math.min(100,(lt.avgLands/maxL)*100);
    lh += '<div class="bar-row"><div class="bar-header"><span style="color:#94a3b8">Turn '+lt.turn+'</span><span style="color:#4ade80">'+lt.avgLands.toFixed(2)+'</span></div><div class="bar-track"><div class="bar-fill" style="width:'+pct2+'%;background:linear-gradient(90deg,#166534,#4ade80)"></div></div></div>';
  }
  lh += '<div style="margin-top:10px;font-size:9px;color:#475569">Average lands on battlefield across ' + SIM_COUNT + ' games</div>';

  // Opening hand basic lands panel
  var maxAvg = colorData.length ? Math.max.apply(null, colorData.map(function(c){ return c.avgPerHand; })) : 1;
  maxAvg = Math.max(maxAvg, 0.01);
  var clh = '<div class="box-title">BASIC LANDS IN OPENING HAND</div>';
  clh += '<div style="font-size:9px;color:#475569;margin-bottom:14px">Avg # of each basic type in kept opening hand across ' + SIM_COUNT + ' games &middot; % = games where &#8805;1 drawn</div>';
  if (colorData.length === 0) {
    clh += '<div style="color:#475569;font-size:11px;padding:10px 0;">No basic lands detected in this deck.</div>';
  } else {
    // Big pip row
    clh += '<div style="display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin-bottom:18px;">';
    for (var cdi = 0; cdi < colorData.length; cdi++) {
      var cd = colorData[cdi];
      clh += '<div style="text-align:center;background:rgba(0,0,0,0.45);border:1px solid '+cd.hex+'44;border-radius:10px;padding:12px 16px;min-width:82px;">';
      clh += '<div style="width:30px;height:30px;border-radius:50%;background:'+cd.pipBg+';margin:0 auto 6px auto;border:2px solid '+cd.hex+';display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:700;color:'+cd.pipFg+';font-family:Cinzel,serif;">'+cd.letter+'</div>';
      clh += '<div style="font-size:20px;font-weight:700;font-family:Cinzel,serif;color:'+cd.hex+'">'+cd.avgPerHand.toFixed(2)+'</div>';
      clh += '<div style="font-size:8px;color:#475569;margin-top:2px;letter-spacing:1px;">'+cd.type.toUpperCase()+'</div>';
      clh += '<div style="font-size:9px;color:#64748b;">'+cd.pctAtLeastOne.toFixed(0)+'% drew one</div>';
      clh += '<div style="font-size:8px;color:#374151;">'+cd.deckCount+' in deck</div>';
      clh += '</div>';
    }
    clh += '</div>';
    // Bar chart
    for (var cbi = 0; cbi < colorData.length; cbi++) {
      var cb = colorData[cbi];
      var bp = Math.min(100, (cb.avgPerHand / maxAvg) * 100);
      var pipHtml = '<span style="display:inline-block;width:11px;height:11px;border-radius:50%;background:'+cb.pipBg+';border:1px solid '+cb.hex+';vertical-align:middle;margin-right:6px;"></span>';
      clh += '<div class="bar-row"><div class="bar-header">'+pipHtml+'<span style="color:'+cb.hex+'">'+cb.type+'</span><div style="display:flex;gap:10px;"><span style="color:'+cb.hex+'">avg '+cb.avgPerHand.toFixed(2)+'/hand</span><span style="color:#475569">'+cb.pctAtLeastOne.toFixed(0)+'% drew &#8805;1</span><span style="color:#374151">'+cb.deckCount+' in deck</span></div></div><div class="bar-track"><div class="bar-fill" style="width:'+bp+'%;background:'+cb.hex+'88"></div></div></div>';
    }
  }

  document.getElementById('statsPanel').innerHTML = '<div class="grid2"><div class="box">'+mh+'</div><div class="box">'+bh+'</div><div class="box span2">'+ch+'</div><div class="box span2">'+lh+'</div><div class="box span2">'+clh+'</div></div>';
}

function renderCharts(tAvg) {
  var charts = [{key:"avgCreatures",color:"#818cf8",label:"AVG CREATURES ON BOARD"},{key:"avgTokens",color:"#fbbf24",label:"AVG TOKENS ON BOARD"},{key:"avgLands",color:"#4ade80",label:"AVG LANDS ON BOARD"},{key:"avgHandSize",color:"#60a5fa",label:"AVG HAND SIZE"}];
  var h = '<div class="grid2">';
  for (var ci = 0; ci < charts.length; ci++) {
    var chart = charts[ci]; var vals = tAvg.map(function(t){return t[chart.key];}); var mx = Math.max.apply(null,vals); mx = Math.max(mx,1); var bars = '';
    for (var bi = 0; bi < tAvg.length; bi++) { var t = tAvg[bi]; var ht = Math.max(2,(t[chart.key]/mx)*52); bars += '<div class="chart-col"><div class="chart-bar" style="height:'+ht+'px;background:'+chart.color+'"></div><div class="chart-label">T'+t.turn+'</div></div>'; }
    h += '<div class="box"><div class="box-title">'+chart.label+'</div><div class="chart-wrap">'+bars+'</div><div class="chart-footer"><span>Min: '+Math.min.apply(null,vals).toFixed(1)+'</span><span>Max: '+Math.max.apply(null,vals).toFixed(1)+'</span><span>T10: '+vals[9].toFixed(1)+'</span></div></div>';
  }
  h += '</div>';
  document.getElementById('chartsPanel').innerHTML = h;
}

function renderRuns() {
  var SIM_COUNT = ALL_RESULTS.length;
  var h = '<div class="run-selector-label">SELECT RUN (1\u2013' + SIM_COUNT + ')</div><div class="run-grid">';
  for (var i = 0; i < SIM_COUNT; i++) {
    var r = ALL_RESULTS[i]; var cls = 'run-btn'+(r.cmdTurn?' has-cmd':'')+(i===SELECTED_RUN?' selected':'');
    h += '<button class="'+cls+'" onclick="selectRun('+i+')">'+(i+1)+'</button>';
  }
  h += '</div><div class="run-legend"><span style="color:#a78bfa">&#9632;</span> Commander cast &nbsp;<span style="color:#374151">&#9632;</span> Not cast</div><div id="runDetail"></div>';
  document.getElementById('runsPanel').innerHTML = h;
  renderRunDetail(SELECTED_RUN);
}

function selectRun(idx) { SELECTED_RUN = idx; renderRuns(); }

function renderRunDetail(idx) {
  var run = ALL_RESULTS[idx];
  var sc = {Mulligans:"#f87171","Cmd Turn":"#c084fc","Opening Hand":"#60a5fa",Board:"#818cf8",Tokens:"#fbbf24",Graveyard:"#94a3b8"};
  var stats = [
    {label:"Mulligans",     value: run.mulligans},
    {label:"Cmd Turn",      value: run.cmdTurn || "\u2014"},
    {label:"Opening Hand",  value: run.openingHand ? run.openingHand.length : "\u2014"},
    {label:"Board",         value: run.finalBoard.length},
    {label:"Tokens",        value: run.finalTokens},
    {label:"Graveyard",     value: run.finalGY.length}
  ];
  var h = '<div class="run-summary">';
  for (var si = 0; si < stats.length; si++) {
    var s = stats[si]; var c = sc[s.label] || "#94a3b8";
    h += '<div class="run-stat" style="border:1px solid '+c+'33"><div class="run-stat-val" style="color:'+c+'">'+s.value+'</div><div class="run-stat-lbl">'+s.label.toUpperCase()+'</div></div>';
  }
  h += '</div>';

  // Opening hand card display
  var typeColors = {land:"#4ade80",creature:"#a78bfa",artifact:"#94a3b8",instant:"#60a5fa",sorcery:"#c084fc",enchantment:"#86efac",planeswalker:"#f87171"};
  var typeBorders = {land:"rgba(74,222,128,0.3)",creature:"rgba(167,139,250,0.3)",artifact:"rgba(148,163,184,0.3)",instant:"rgba(96,165,250,0.3)",sorcery:"rgba(192,132,252,0.3)",enchantment:"rgba(134,239,172,0.3)",planeswalker:"rgba(248,113,113,0.3)"};

  if (run.openingHand && run.openingHand.length > 0) {
    var mulLabel = run.mulligans === 0 ? "No mulligan" : run.mulligans + " mulligan" + (run.mulligans > 1 ? "s" : "");
    h += '<div class="opening-hand-section">';
    h += '<div class="opening-hand-title">OPENING HAND &nbsp;&middot;&nbsp; ' + run.openingHand.length + ' CARDS &nbsp;&middot;&nbsp; <span style="color:#64748b">' + mulLabel.toUpperCase() + '</span></div>';
    h += '<div class="hand-cards">';

    // Sort: lands first, then by CMC
    var sorted = run.openingHand.slice().sort(function(a, b) {
      var aLand = a.type === 'land' ? 0 : 1;
      var bLand = b.type === 'land' ? 0 : 1;
      if (aLand !== bLand) return aLand - bLand;
      return (a.cmc || 0) - (b.cmc || 0);
    });

    for (var hi = 0; hi < sorted.length; hi++) {
      var card = sorted[hi];
      var tc = typeColors[card.type] || "#94a3b8";
      var tb = typeBorders[card.type] || "rgba(255,255,255,0.1)";
      var cmcStr = card.type === 'land' ? 'Land' : 'CMC ' + (card.cmc !== undefined ? card.cmc : '?');
      h += '<div class="hand-card" style="border:1px solid ' + tb + '">';
      h += '<div class="hand-card-name" title="' + card.name + '">' + card.name + '</div>';
      h += '<div class="hand-card-type" style="color:' + tc + '">' + (card.type || 'unknown') + '</div>';
      h += '<div class="hand-card-cmc">' + cmcStr + '</div>';
      h += '</div>';
    }
    h += '</div></div>';
  }

  // Turn logs
  for (var li = 0; li < run.logs.length; li++) {
    var log = run.logs[li]; var cls = 'turn-log'+(log.commanderOut?' has-cmd':'');
    h += '<div class="'+cls+'"><div class="turn-head">'+(log.commanderOut?'<span style="color:#c084fc">&#9733; </span>':'')+'Turn '+log.turn+'<span class="turn-meta">mana:'+log.mana+' &middot; hand:'+log.handSize+' &middot; '+log.boardState+'</span></div>';
    for (var ai = 0; ai < log.actions.length; ai++) {
      var a = log.actions[ai];
      var ac = a.type==='land'?'a-land':a.type==='cmd'?'a-cmd':a.type==='token'?'a-token':a.type==='cast'?'a-cast':'a-draw';
      h += '<div class="action '+ac+'">&rsaquo; '+a.text+'</div>';
    }
    h += '</div>';
  }
  document.getElementById('runDetail').innerHTML = h;
}

function switchTab(name) {
  document.querySelectorAll('.tab-btn').forEach(function(b){b.classList.remove('active');});
  document.querySelectorAll('.panel').forEach(function(p){p.classList.remove('active');});
  document.getElementById('runsPanel').classList.remove('active');
  if (name==='runs') { document.getElementById('runsPanel').classList.add('active'); }
  else { document.getElementById(name+'Panel').classList.add('active'); }
  document.querySelectorAll('.tab-btn').forEach(function(b){ if(b.textContent.toLowerCase()===name) b.classList.add('active'); });
}

// ─── EXPORT SUMMARY IMAGE ─────────────────────────────────────────────────────

function exportSummaryImage() {
  var btn = document.getElementById('exportBtn');
  if (!ALL_RESULTS.length || !COMMANDER) return;
  btn.disabled = true;
  btn.innerHTML = '<svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg> GENERATING...';

  var d = LAST_AGGREGATED;
  var SIM_COUNT = d.simCount || 100;
  var cmdName = COMMANDER.name;
  var today = new Date().toLocaleDateString('en-US', {year:'numeric',month:'short',day:'numeric'});

  // Build mulligan bars HTML
  var mulColors = ["#4ade80","#a3e635","#fbbf24","#f87171","#ef4444"];
  var mullHTML = '';
  for (var mi = 0; mi < d.mDist.length; mi++) {
    var m = d.mDist[mi];
    var lbl = m.count === 0 ? "No mulligan" : m.count + " mulligan" + (m.count > 1 ? "s" : "");
    var pct = Math.min(100, (m.games / SIM_COUNT) * 100);
    mullHTML += '<div class="snap-bar-row"><div class="snap-bar-header"><span>' + lbl + '</span><span style="color:' + mulColors[m.count] + '">' + m.games + ' games</span></div><div class="snap-bar-track"><div class="snap-bar-fill" style="width:' + pct + '%;background:' + mulColors[m.count] + '"></div></div></div>';
  }

  // Build commander histogram HTML
  var maxC = Math.max.apply(null, d.cDist.map(function(x){return x.count;})); maxC = Math.max(maxC, 1);
  var notCast = ALL_RESULTS.filter(function(r){return !r.cmdTurn;}).length;
  var histHTML = '<div class="snap-cmd-hist">';
  for (var ci = 0; ci < d.cDist.length; ci++) {
    var cd = d.cDist[ci]; var ht = Math.max(4, (cd.count / maxC) * 62);
    histHTML += '<div class="snap-cmd-bar-wrap"><div class="snap-cmd-bar-count">' + cd.count + '</div><div class="snap-cmd-bar" style="height:' + ht + 'px;background:linear-gradient(180deg,#c084fc,#7c3aed)"></div><div class="snap-cmd-bar-label">T' + cd.turn + '</div></div>';
  }
  var nh = Math.max(4, (notCast / SIM_COUNT) * 62);
  histHTML += '<div class="snap-cmd-bar-wrap"><div class="snap-cmd-bar-count" style="color:#f87171">' + notCast + '</div><div class="snap-cmd-bar" style="height:' + nh + 'px;background:linear-gradient(180deg,#f87171,#dc2626)"></div><div class="snap-cmd-bar-label">None</div></div></div>';

  // Build lands per turn HTML
  var maxL = Math.max.apply(null, d.tAvg.map(function(t){return t.avgLands;})); maxL = Math.max(maxL, 1);
  var landsHTML = '';
  for (var li = 0; li < d.tAvg.length; li++) {
    var lt = d.tAvg[li]; var lp = Math.min(100, (lt.avgLands / maxL) * 100);
    landsHTML += '<div class="snap-bar-row"><div class="snap-bar-header"><span style="color:#94a3b8">Turn ' + lt.turn + '</span><span style="color:#4ade80">' + lt.avgLands.toFixed(2) + '</span></div><div class="snap-bar-track"><div class="snap-bar-fill" style="width:' + lp + '%;background:linear-gradient(90deg,#166534,#4ade80)"></div></div></div>';
  }

  var summaryStats = [
    {label:"AVG MULLIGANS",     value: d.avgM.toFixed(2),                      color:"#f87171"},
    {label:"CMD CAST RATE",     value: d.cRate.toFixed(0) + "%",               color:"#c084fc"},
    {label:"AVG CMD TURN",      value: d.avgC ? d.avgC.toFixed(1) : "N/A",     color:"#a78bfa"},
    {label:"T10 CREATURES",     value: d.tAvg[9].avgCreatures.toFixed(1),      color:"#818cf8"},
    {label:"T10 TOKENS",        value: d.tAvg[9].avgTokens.toFixed(1),         color:"#fbbf24"},
    {label:"T10 LANDS",         value: d.tAvg[9].avgLands.toFixed(1),          color:"#4ade80"}
  ];
  var statsHTML = '';
  for (var si = 0; si < summaryStats.length; si++) {
    var ss = summaryStats[si];
    statsHTML += '<div class="snap-stat" style="border:1px solid ' + ss.color + '44"><div class="snap-stat-val" style="color:' + ss.color + '">' + ss.value + '</div><div class="snap-stat-lbl">' + ss.label + '</div></div>';
  }

  var snap = document.getElementById('exportSnapshot');
  snap.innerHTML =
    '<div class="snap-header">' +
      '<div class="snap-eyebrow">&#9760; MTG COMMANDER SIM &#9760;</div>' +
      '<div class="snap-title">' + cmdName + '</div>' +
      '<div class="snap-cmd">Commander &middot; CMC ' + COMMANDER.cmc + ' &middot; ' + SIM_COUNT + '-Game Monte Carlo</div>' +
      '<div class="snap-meta">Simulated ' + today + '</div>' +
    '</div>' +
    '<div class="snap-stats">' + statsHTML + '</div>' +
    '<div class="snap-grid">' +
      '<div class="snap-box"><div class="snap-section-title">MULLIGAN DISTRIBUTION</div>' + mullHTML + '</div>' +
      '<div class="snap-box"><div class="snap-section-title">COMMANDER CAST TURN (' + d.cRate.toFixed(0) + '% rate)</div>' + histHTML + '</div>' +
      '<div class="snap-box" style="grid-column:1/-1"><div class="snap-section-title">AVG LANDS PER TURN</div>' + landsHTML + '</div>' +
    '</div>' +
    '<div class="snap-footer">MTG COMMANDER SIM &middot; ' + SIM_COUNT + '-GAME MONTE CARLO SIMULATION</div>';

  // Position off-screen but renderable
  snap.style.left = '-9999px';
  snap.style.top = '0px';

  setTimeout(function() {
    html2canvas(snap, {
      backgroundColor: '#07070f',
      scale: 2,
      useCORS: true,
      logging: false
    }).then(function(canvas) {
      var link = document.createElement('a');
      var safeName = cmdName.replace(/[^a-zA-Z0-9_\- ]/g, '').replace(/\s+/g, '_');
      link.download = 'MTGCommanderSim_' + safeName + '.png';
      link.href = canvas.toDataURL('image/png');
      link.click();
      btn.disabled = false;
      btn.innerHTML = '<svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg> EXPORT SUMMARY IMAGE';
    }).catch(function(err) {
      console.error('Export failed:', err);
      btn.disabled = false;
      btn.innerHTML = '&#10007; EXPORT FAILED — TRY AGAIN';
    });
  }, 100);
}
</script>
</body>
</html>
