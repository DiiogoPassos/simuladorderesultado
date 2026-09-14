<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover, maximum-scale=1">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Simulador">
<title>Simulador de Resultado</title>
<style>
  :root{
    --bg:#12151b;
    --surface:#1b2028;
    --surface-2:#242a34;
    --border:#313846;
    --text:#edeff3;
    --text-dim:#8891a1;
    --accent:#d8a54a;
    --accent-dim:#8a6a2e;
    --positive:#4fae7c;
    --negative:#e2685c;
    --radius:10px;
    --safe-bottom: env(safe-area-inset-bottom, 0px);
    --safe-top: env(safe-area-inset-top, 0px);
  }
  *{box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
  html,body{
    margin:0;padding:0;height:100%;
    background:var(--bg);color:var(--text);
    font-family:-apple-system,BlinkMacSystemFont,"SF Pro Text",system-ui,sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  body{display:flex;flex-direction:column;height:100dvh;overflow:hidden;}
  ::selection{background:var(--accent-dim);}

  header.topbar{
    flex:0 0 auto;
    padding:calc(10px + var(--safe-top)) 18px 12px;
    background:var(--bg);
    border-bottom:1px solid var(--border);
  }
  header.topbar h1{margin:0; font-size:17px; font-weight:600; letter-spacing:-0.01em;}
  header.topbar p{margin:2px 0 0; font-size:12.5px; color:var(--text-dim);}

  main{
    flex:1 1 auto; overflow-y:auto; -webkit-overflow-scrolling:touch;
    padding:14px 14px 6px;
  }
  .view{display:none;}
  .view.active{display:block;animation:fade .18s ease;}
  @keyframes fade{from{opacity:0;transform:translateY(4px)}to{opacity:1;transform:none}}

  .card{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    padding:14px 14px 6px;
    margin-bottom:12px;
  }
  .card h2{
    font-size:11.5px; font-weight:600; color:var(--text-dim); margin:0 0 8px; letter-spacing:.01em;
  }
  .row{
    display:flex; align-items:center; justify-content:space-between;
    padding:9px 0; border-top:1px solid var(--border);
    gap:12px;
  }
  .row:first-of-type{border-top:none;}
  .row label{font-size:14.5px; color:var(--text); flex:1 1 auto;}
  .row .sub{display:block;font-size:11.5px;color:var(--text-dim);font-weight:400;margin-top:1px;}

  .row input[type=number]{
    background:var(--surface-2);
    border:1px solid var(--border);
    color:var(--text);
    border-radius:7px;
    padding:7px 9px;
    font-size:15px;
    width:128px;
    text-align:right;
    font-variant-numeric:tabular-nums;
    font-family:inherit;
  }
  .row input:focus{outline:none;border-color:var(--accent);}
  .row input::-webkit-inner-spin-button{-webkit-appearance:none;}

  .result-line{
    display:flex;justify-content:space-between;align-items:baseline;
    padding:8px 0;border-top:1px solid var(--border);
  }
  .result-line:first-of-type{border-top:none;}
  .result-line span.k{font-size:13.5px;color:var(--text-dim);}
  .result-line span.v{font-size:15.5px;font-variant-numeric:tabular-nums;font-weight:600;}
  .v.pos{color:var(--positive);}
  .v.neg{color:var(--negative);}
  .v.accent{color:var(--accent);}

  .hero{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    padding:16px;margin-bottom:12px;
    display:flex;justify-content:space-between;align-items:center;
  }
  .hero .block .lbl{font-size:11.5px;color:var(--text-dim);margin-bottom:2px;}
  .hero .block .val{font-size:22px;font-weight:700;font-variant-numeric:tabular-nums;letter-spacing:-0.01em;}
  .hero .divider{width:1px;align-self:stretch;background:var(--border);margin:0 16px;}

  nav.tabbar{
    flex:0 0 auto;
    display:flex;
    background:var(--surface);
    border-top:1px solid var(--border);
    padding:6px 4px calc(6px + var(--safe-bottom));
  }
  nav.tabbar button{
    flex:1 1 0; background:none; border:none; color:var(--text-dim);
    display:flex; flex-direction:column; align-items:center; gap:3px;
    padding:6px 2px; font-family:inherit; font-size:10.5px;
    border-radius:8px;
  }
  nav.tabbar button svg{width:22px;height:22px;stroke:var(--text-dim);fill:none;stroke-width:1.6;}
  nav.tabbar button.active{color:var(--accent);}
  nav.tabbar button.active svg{stroke:var(--accent);}
</style>
</head>
<body>

<header class="topbar">
  <h1 id="pageTitle">Simulador de Margem</h1>
  <p id="pageSub">Preço público, custo e imposto</p>
</header>

<main>

  <!-- ================= MARGEM ================= -->
  <section id="view-margem" class="view active">

    <div class="hero">
      <div class="block">
        <div class="lbl">Lucro bruto (LB)</div>
        <div class="val" id="m_lb">R$ 0</div>
      </div>
      <div class="divider"></div>
      <div class="block">
        <div class="lbl">Margem alcançada</div>
        <div class="val" id="m_margem">0,0%</div>
      </div>
    </div>

    <div class="card">
      <h2>Dados</h2>
      <div class="row"><label>Preço público sugerido</label><input type="number" id="m_precoPublico" value="199990"></div>
      <div class="row"><label>Valor a receber</label><input type="number" id="m_valorReceber" value="145000"></div>
      <div class="row"><label>Bônus</label><input type="number" id="m_bonus" value="46000"></div>
      <div class="row"><label>Incidência</label><input type="number" id="m_incid" value="0"></div>
      <div class="row"><label>Deduções</label><input type="number" id="m_deducoes" value="0"></div>
    </div>

    <div class="card">
      <h2>Resultado</h2>
      <div class="result-line"><span class="k">Custo sem imposto</span><span class="v" id="m_custoSemImposto">—</span></div>
      <div class="result-line"><span class="k">Markup</span><span class="v" id="m_markup">—</span></div>
      <div class="result-line"><span class="k">Imposto (12%)</span><span class="v" id="m_imposto">—</span></div>
      <div class="result-line"><span class="k">Custo + imposto</span><span class="v" id="m_custoImp">—</span></div>
      <div class="result-line"><span class="k">LB após deduções</span><span class="v" id="m_lbDeduzido">—</span></div>
      <div class="result-line"><span class="k">Margem após deduções</span><span class="v" id="m_margemDeduzida">—</span></div>
    </div>

  </section>

  <!-- ================= VENDA DIRETA ================= -->
  <section id="view-direta" class="view">

    <div class="hero">
      <div class="block">
        <div class="lbl">Lucro bruto</div>
        <div class="val" id="v_lb">R$ 0</div>
      </div>
      <div class="divider"></div>
      <div class="block">
        <div class="lbl">Bancagem</div>
        <div class="val" id="v_bancagem">R$ 0</div>
      </div>
    </div>

    <div class="card">
      <h2>Preço e política</h2>
      <div class="row"><label>Preço sugerido (site)</label><input type="number" id="v_preco" value="277990"></div>
      <div class="row"><label>% política do mês</label><input type="number" id="v_pctPolitica" value="16.7" step="0.1">%</div>
      <div class="row"><label>Desconto adicional (VM)</label><input type="number" id="v_descAdic" value="2" step="0.1">%</div>
      <div class="row"><label>Acessórios cortesia (−)</label><input type="number" id="v_acessCortesia" value="0"></div>
      <div class="row"><label>F&amp;I cortesia (−)</label><input type="number" id="v_fiCortesia" value="0"></div>
      <div class="row"><label>% margem base</label><input type="number" id="v_pctMargem" value="7" step="0.1">%</div>
    </div>

    <div class="card">
      <h2>Resultado</h2>
      <div class="result-line"><span class="k">Valor política do mês (NF)</span><span class="v" id="v_valorPolitica">—</span></div>
      <div class="result-line"><span class="k">Valor final a receber</span><span class="v" id="v_valorFinal">—</span></div>
      <div class="result-line"><span class="k">% margem efetiva</span><span class="v" id="v_margemEfetiva">—</span></div>
      <div class="result-line"><span class="k">Bancagem</span><span class="v" id="v_bancagem2">—</span></div>
    </div>

  </section>

</main>

<nav class="tabbar">
  <button class="tab active" data-view="margem">
    <svg viewBox="0 0 24 24"><path d="M3 12l2-2 4 4 8-9 4 4"/><path d="M3 19h18"/></svg>
    Margem
  </button>
  <button class="tab" data-view="direta">
    <svg viewBox="0 0 24 24"><rect x="3" y="7" width="18" height="12" rx="1.5"/><path d="M8 7V5a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/></svg>
    Venda direta
  </button>
</nav>

<script>
const $ = id => document.getElementById(id);
const num = id => { const v = parseFloat($(id).value.replace(',','.')); return isNaN(v) ? 0 : v; };
const brl = n => (isFinite(n)?n:0).toLocaleString('pt-BR',{style:'currency',currency:'BRL',maximumFractionDigits:0});
const pct = n => (isFinite(n)?n*100:0).toLocaleString('pt-BR',{minimumFractionDigits:1,maximumFractionDigits:1}) + '%';
const setVal = (id, txt, cls) => { const el = $(id); el.textContent = txt; el.className = 'v' + (cls ? ' '+cls : ''); };

// ---------- TABS ----------
document.querySelectorAll('nav.tabbar .tab').forEach(btn=>{
  btn.addEventListener('click', ()=>{
    document.querySelectorAll('nav.tabbar .tab').forEach(b=>b.classList.remove('active'));
    document.querySelectorAll('main .view').forEach(v=>v.classList.remove('active'));
    btn.classList.add('active');
    $('view-'+btn.dataset.view).classList.add('active');
    const titles = {margem:['Simulador de Margem','Preço público, custo e imposto'],
                     direta:['Venda Direta','Política do mês e bancagem']};
    $('pageTitle').textContent = titles[btn.dataset.view][0];
    $('pageSub').textContent = titles[btn.dataset.view][1];
  });
});

// ---------- MARGEM ----------
// Fórmulas da planilha:
// D3 (custo sem imposto) = C3-(C3*7.7%)
// E3 (markup)            = D3-(D3*13%)
// I3 (imposto)           = F3*12%
// L3 (custo+imp)         = E3+I3   <- agora usa o MARKUP, não mais o custo sem imposto
// K3 (LB)                = F3+G3-L3-H3
// J3 (margem %)          = K3/(F3+G3)
function calcMargem(){
  const precoPublico = num('m_precoPublico');
  const eReceber = num('m_valorReceber'), bonus = num('m_bonus'), incid = num('m_incid');
  const deducoes = num('m_deducoes');

  const custoSemImposto = precoPublico - precoPublico*0.077;
  const markup = custoSemImposto - custoSemImposto*0.13;

  const imposto = eReceber*0.12;
  const custoImp = markup+imposto;
  const lb = eReceber+bonus-custoImp-incid;
  const margem = lb/(eReceber+bonus);

  // após deduções (mesma lógica, aplicada sobre o valor a receber)
  const eDeduzido = eReceber-deducoes;
  const impostoDeduzido = eDeduzido*0.12;
  const custoImpDeduzido = markup+impostoDeduzido;
  const lbDeduzido = eDeduzido+bonus-custoImpDeduzido-incid;
  const margemDeduzida = lbDeduzido/(eDeduzido+bonus-incid);

  setVal('m_lb', brl(lb));
  $('m_lb').style.color = lb>=0?'var(--positive)':'var(--negative)';
  setVal('m_margem', pct(margem));

  setVal('m_custoSemImposto', brl(custoSemImposto));
  setVal('m_markup', brl(markup));
  setVal('m_imposto', brl(imposto));
  setVal('m_custoImp', brl(custoImp));
  setVal('m_lbDeduzido', brl(lbDeduzido), lbDeduzido>=0?'pos':'neg');
  setVal('m_margemDeduzida', pct(margemDeduzida));
}

// ---------- VENDA DIRETA ----------
function calcDireta(){
  const preco = num('v_preco'), pctPolitica = num('v_pctPolitica')/100;
  const descAdic = num('v_descAdic')/100, acessC = num('v_acessCortesia'), fiC = num('v_fiCortesia');
  const pctMargem = num('v_pctMargem')/100;

  const valorPolitica = preco - preco*pctPolitica;
  const valorFinal = valorPolitica - valorPolitica*descAdic;
  const margemEfetiva = pctMargem - descAdic;
  const lb = valorPolitica*margemEfetiva - acessC - fiC;
  const bancagem = valorPolitica - valorFinal;

  setVal('v_lb', brl(lb)); $('v_lb').style.color = lb>=0?'var(--positive)':'var(--negative)';
  setVal('v_bancagem', brl(bancagem));
  setVal('v_bancagem2', brl(bancagem));
  setVal('v_valorPolitica', brl(valorPolitica));
  setVal('v_valorFinal', brl(valorFinal));
  setVal('v_margemEfetiva', pct(margemEfetiva));
}

function calcAll(){ calcMargem(); calcDireta(); }

document.querySelectorAll('main input').forEach(el=>{
  el.addEventListener('input', calcAll);
  el.addEventListener('change', calcAll);
});

calcAll();
</script>
</body>
</html>
