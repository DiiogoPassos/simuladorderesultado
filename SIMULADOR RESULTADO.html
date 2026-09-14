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
  header.topbar h1{
    margin:0; font-size:17px; font-weight:600; letter-spacing:-0.01em;
  }
  header.topbar p{
    margin:2px 0 0; font-size:12.5px; color:var(--text-dim);
  }

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
    font-size:11.5px; font-weight:600; text-transform:none;
    color:var(--text-dim); margin:0 0 8px; letter-spacing:.01em;
  }
  .row{
    display:flex; align-items:center; justify-content:space-between;
    padding:9px 0; border-top:1px solid var(--border);
    gap:12px;
  }
  .row:first-of-type{border-top:none;}
  .row label{font-size:14.5px; color:var(--text); flex:1 1 auto;}
  .row .sub{display:block;font-size:11.5px;color:var(--text-dim);font-weight:400;margin-top:1px;}

  .row input[type=text], .row input[type=number]{
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
  .row input[type=text]{text-align:left;width:150px;}
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
  .hero .block{}
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

  select.seg{
    background:var(--surface-2);border:1px solid var(--border);color:var(--text);
    border-radius:7px;padding:7px 9px;font-size:14.5px;font-family:inherit;width:128px;
  }
</style>
</head>
<body>

<header class="topbar">
  <h1 id="pageTitle">Simulador de Resultado</h1>
  <p id="pageSub">Guarapari · Vitoria Motors</p>
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
      <h2>Dados do veículo novo</h2>
      <div class="row"><label>Cliente</label><input type="text" id="m_cliente" value="" placeholder="Nome"></div>
      <div class="row"><label>PPS (preço de tabela)</label><input type="number" id="m_pps" value="150000"></div>
      <div class="row"><label>Desconto VD<span class="sub">reduz o PPS</span></label><input type="number" id="m_descVD" value="0" step="0.1">%</div>
    </div>

    <div class="card">
      <h2>Custo e margem</h2>
      <div class="row"><label>Custo VN − markup</label><input type="number" id="m_custo" value="125000"></div>
      <div class="row"><label>Margem pretendida</label><input type="number" id="m_margemPret" value="6.5" step="0.1">%</div>
      <div class="row"><label>Valor a receber</label><input type="number" id="m_valorReceber" value="150000"></div>
      <div class="row"><label>Bônus</label><input type="number" id="m_bonus" value="0"></div>
      <div class="row"><label>Incidência</label><input type="number" id="m_incid" value="0"></div>
      <div class="row"><label>Deduções</label><input type="number" id="m_deducoes" value="0"></div>
    </div>

    <div class="card">
      <h2>Resultado da margem</h2>
      <div class="result-line"><span class="k">Valor de venda mínimo</span><span class="v" id="m_vendaMin">—</span></div>
      <div class="result-line"><span class="k">Imposto (12%)</span><span class="v" id="m_imposto">—</span></div>
      <div class="result-line"><span class="k">Custo + imposto</span><span class="v" id="m_custoImp">—</span></div>
      <div class="result-line"><span class="k">LB após deduções</span><span class="v" id="m_lbDeduzido">—</span></div>
      <div class="result-line"><span class="k">Margem após deduções</span><span class="v" id="m_margemDeduzida">—</span></div>
    </div>

    <div class="card">
      <h2>Veículo usado na troca</h2>
      <div class="row"><label>Modelo</label><input type="text" id="m_usadoModelo" value=""></div>
      <div class="row"><label>FIPE</label><input type="number" id="m_fipe" value="0"></div>
      <div class="row"><label>Valor aprovado</label><input type="number" id="m_aprovado" value="0"></div>
      <div class="row"><label>Débito</label><input type="number" id="m_debito" value="0"></div>
      <div class="row"><label>Cautelar</label><input type="number" id="m_cautelar" value="0"></div>
      <div class="row"><label>Emplacamento</label><input type="number" id="m_emplac" value="0"></div>
      <div class="row"><label>Acessórios</label><input type="number" id="m_acess" value="0"></div>
      <div class="row"><label>Filme</label><input type="number" id="m_filme" value="0"></div>
    </div>

    <div class="card">
      <h2>Resultado do usado</h2>
      <div class="result-line"><span class="k">% FIPE (aprovado/FIPE)</span><span class="v" id="m_pctFipe">—</span></div>
      <div class="result-line"><span class="k">Troco (soma dos itens)</span><span class="v" id="m_troco">—</span></div>
      <div class="result-line"><span class="k">Valor final do usado</span><span class="v" id="m_valorFinalUsado">—</span></div>
      <div class="result-line"><span class="k">Volta</span><span class="v" id="m_volta">—</span></div>
      <div class="result-line"><span class="k">Volta pagando FIPE</span><span class="v" id="m_voltaFipe">—</span></div>
    </div>

    <div class="card">
      <h2>Financiamento tx 0%</h2>
      <div class="row"><label>Entrada</label><input type="number" id="m_entrada" value="0"></div>
      <div class="row"><label>Complemento real</label><input type="number" id="m_compReal" value="0"></div>
    </div>

    <div class="card">
      <h2>Resultado do financiamento</h2>
      <div class="result-line"><span class="k">Complemento mínimo</span><span class="v" id="m_compMin">—</span></div>
      <div class="result-line"><span class="k">Valor financiado</span><span class="v" id="m_valorFinanc">—</span></div>
      <div class="result-line"><span class="k">Valorização do usado</span><span class="v" id="m_valorizacao">—</span></div>
      <div class="result-line"><span class="k">% FIPE financiamento</span><span class="v" id="m_pctFipeFin">—</span></div>
    </div>

    <div class="card">
      <h2>Composição da proposta</h2>
      <div class="result-line"><span class="k">NF (valor a receber)</span><span class="v" id="c_nf">—</span></div>
      <div class="result-line"><span class="k">VU (valor final usado)</span><span class="v" id="c_vu">—</span></div>
      <div class="result-line"><span class="k">Financiamento</span><span class="v" id="c_fin">—</span></div>
      <div class="result-line"><span class="k">Bônus</span><span class="v" id="c_bonus">—</span></div>
      <div class="result-line"><span class="k">Troco</span><span class="v" id="c_troco">—</span></div>
      <div class="result-line"><span class="k">Incidência</span><span class="v" id="c_incid">—</span></div>
      <div class="result-line" style="border-top:1px solid var(--border);margin-top:2px;padding-top:10px;">
        <span class="k" style="font-weight:600;">Soma da composição</span><span class="v accent" id="c_soma">—</span>
      </div>
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
      <h2>Dados da venda</h2>
      <div class="row"><label>Loja</label><input type="text" id="v_loja" value="Guarapari"></div>
      <div class="row"><label>Vendedor</label><input type="text" id="v_vendedor" value=""></div>
      <div class="row"><label>Cliente</label><input type="text" id="v_cliente" value=""></div>
      <div class="row"><label>Modalidade</label><input type="text" id="v_modalidade" value=""></div>
      <div class="row"><label>Veículo</label><input type="text" id="v_veiculo" value=""></div>
      <div class="row"><label>Ano/modelo</label><input type="text" id="v_anoModelo" value=""></div>
    </div>

    <div class="card">
      <h2>Preço e política</h2>
      <div class="row"><label>Preço sugerido (site)</label><input type="number" id="v_preco" value="174990"></div>
      <div class="row"><label>% política do mês</label><input type="number" id="v_pctPolitica" value="15.5" step="0.1">%</div>
      <div class="row"><label>Desconto adicional (VM)</label><input type="number" id="v_descAdic" value="0" step="0.1">%</div>
      <div class="row"><label>Acessórios cortesia</label><input type="number" id="v_acessCortesia" value="0"></div>
      <div class="row"><label>F&amp;I cortesia</label><input type="number" id="v_fiCortesia" value="0"></div>
      <div class="row"><label>% margem base</label><input type="number" id="v_pctMargem" value="6" step="0.1">%</div>
    </div>

    <div class="card">
      <h2>Resultado</h2>
      <div class="result-line"><span class="k">Valor política do mês (NF)</span><span class="v" id="v_valorPolitica">—</span></div>
      <div class="result-line"><span class="k">Valor final a receber</span><span class="v" id="v_valorFinal">—</span></div>
      <div class="result-line"><span class="k">% margem efetiva</span><span class="v" id="v_margemEfetiva">—</span></div>
    </div>

    <div class="card">
      <h2>Troca (usado)</h2>
      <div class="row"><label>VU (valor do usado)</label><input type="number" id="v_vu" value="0"></div>
      <div class="row"><label>Trade in (extra)</label><input type="number" id="v_tradeIn" value="0"></div>
    </div>

    <div class="card">
      <h2>Resultado da troca</h2>
      <div class="result-line"><span class="k">Total (VU + trade in)</span><span class="v" id="v_totalTroca">—</span></div>
      <div class="result-line"><span class="k">Volta</span><span class="v" id="v_voltaTroca">—</span></div>
    </div>

  </section>

  <!-- ================= EMPLACAMENTO ================= -->
  <section id="view-emplac" class="view">

    <div class="hero">
      <div class="block">
        <div class="lbl">Total c/ alienação</div>
        <div class="val" id="e_totalAlienEstoque">R$ 0</div>
      </div>
      <div class="divider"></div>
      <div class="block">
        <div class="lbl">Total sem alienação</div>
        <div class="val" id="e_totalSemAlienEstoque">R$ 0</div>
      </div>
    </div>

    <div class="card">
      <h2>Venda estoque</h2>
      <div class="row"><label>Valor do veículo</label><input type="number" id="e_valorEstoque" value="152500"></div>
      <div class="row"><label>Mês de faturamento</label>
        <select class="seg" id="e_mesEstoque">
          <option value="1">Janeiro</option><option value="2">Fevereiro</option><option value="3">Março</option>
          <option value="4">Abril</option><option value="5">Maio</option><option value="6">Junho</option>
          <option value="7">Julho</option><option value="8">Agosto</option><option value="9" selected>Setembro</option>
          <option value="10">Outubro</option><option value="11">Novembro</option><option value="12">Dezembro</option>
        </select>
      </div>
      <div class="row"><label>Emplacamento alienado</label><input type="number" id="e_alienEstoque" value="1578.53"></div>
      <div class="row"><label>Emplacamento sem alienação</label><input type="number" id="e_semAlienEstoque" value="1435.32"></div>
    </div>

    <div class="card">
      <h2>Resultado — venda estoque</h2>
      <div class="result-line"><span class="k">IPVA (1% a.a.)</span><span class="v" id="e_ipvaEstoque">—</span></div>
      <div class="result-line"><span class="k">Total alienado</span><span class="v" id="e_totalAlienEstoque2">—</span></div>
      <div class="result-line"><span class="k">Total sem alienação</span><span class="v" id="e_totalSemAlienEstoque2">—</span></div>
    </div>

    <div class="card">
      <h2>Venda direta</h2>
      <div class="row"><label>Valor do veículo</label><input type="number" id="e_valorDireta" value="114990"></div>
      <div class="row"><label>Mês de faturamento</label>
        <select class="seg" id="e_mesDireta">
          <option value="1">Janeiro</option><option value="2">Fevereiro</option><option value="3">Março</option>
          <option value="4">Abril</option><option value="5">Maio</option><option value="6">Junho</option>
          <option value="7">Julho</option><option value="8">Agosto</option><option value="9" selected>Setembro</option>
          <option value="10">Outubro</option><option value="11">Novembro</option><option value="12">Dezembro</option>
        </select>
      </div>
      <div class="row"><label>Emplacamento alienado</label><input type="number" id="e_alienDireta" value="1578.53"></div>
      <div class="row"><label>Emplacamento sem alienação</label><input type="number" id="e_semAlienDireta" value="1435.32"></div>
    </div>

    <div class="card">
      <h2>Resultado — venda direta</h2>
      <div class="result-line"><span class="k">IPVA (2% a.a.)</span><span class="v" id="e_ipvaDireta">—</span></div>
      <div class="result-line"><span class="k">Total alienado</span><span class="v" id="e_totalAlienDireta">—</span></div>
      <div class="result-line"><span class="k">Total sem alienação</span><span class="v" id="e_totalSemAlienDireta">—</span></div>
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
  <button class="tab" data-view="emplac">
    <svg viewBox="0 0 24 24"><rect x="3" y="9" width="18" height="7" rx="1.5"/><circle cx="7.5" cy="16.5" r="1.6"/><circle cx="16.5" cy="16.5" r="1.6"/><path d="M5 9l1.5-3.5A2 2 0 0 1 8.3 4.3h7.4a2 2 0 0 1 1.8 1.2L19 9"/></svg>
    Emplacamento
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
    const titles = {margem:['Simulador de Margem','Novo, usado e financiamento'],
                     direta:['Venda Direta','Política do mês e bancagem'],
                     emplac:['Emplacamento','Estoque e venda direta']};
    $('pageTitle').textContent = titles[btn.dataset.view][0];
    $('pageSub').textContent = titles[btn.dataset.view][1];
  });
});

// ---------- MARGEM ----------
function calcMargem(){
  const pps = num('m_pps'), descVD = num('m_descVD')/100;
  const custo = num('m_custo'), margemPret = num('m_margemPret')/100;
  const eReceber = num('m_valorReceber'), bonus = num('m_bonus'), incid = num('m_incid');
  const deducoes = num('m_deducoes');

  const vendaMin = custo/(0.88-margemPret);
  const imposto = eReceber*0.12;
  const custoImp = custo+imposto;
  const lb = eReceber+bonus-custoImp-incid;
  const margem = lb/(eReceber+bonus);

  const e11 = eReceber-deducoes;
  const h11 = e11*0.12;
  const k11 = custo+h11;
  const j11 = e11+bonus-k11-incid;
  const i11 = j11/(e11+bonus-incid);

  setVal('m_lb', brl(lb));
  $('m_lb').style.color = lb>=0?'var(--positive)':'var(--negative)';
  setVal('m_margem', pct(margem));
  $('m_margem').style.color = margem>=margemPret?'var(--positive)':'var(--negative)';

  setVal('m_vendaMin', brl(vendaMin));
  setVal('m_imposto', brl(imposto));
  setVal('m_custoImp', brl(custoImp));
  setVal('m_lbDeduzido', brl(j11), j11>=0?'pos':'neg');
  setVal('m_margemDeduzida', pct(i11));

  // usado
  const fipe = num('m_fipe'), aprovado = num('m_aprovado'), debito = num('m_debito');
  const cautelar = num('m_cautelar'), emplac = num('m_emplac'), acess = num('m_acess'), filme = num('m_filme');
  const troco = cautelar+emplac+acess+filme;
  const valorFinalUsado = aprovado-debito-troco;
  const pctFipe = fipe ? (aprovado/fipe) : 0;
  const volta = eReceber-valorFinalUsado;
  const voltaFipe = pps-fipe;

  setVal('m_pctFipe', fipe? pct(pctFipe) : '—');
  setVal('m_troco', brl(troco));
  setVal('m_valorFinalUsado', brl(valorFinalUsado));
  setVal('m_volta', brl(volta), volta>=0?'pos':'neg');
  setVal('m_voltaFipe', brl(voltaFipe));

  // financiamento
  const entrada = num('m_entrada'), compReal = num('m_compReal');
  const compMin = entrada-valorFinalUsado;
  const valorFinanc = volta-compReal;
  const valorizacao = pps-volta;
  const pctFipeFin = fipe ? (valorizacao/fipe) : 0;

  setVal('m_compMin', brl(compMin));
  setVal('m_valorFinanc', brl(valorFinanc));
  setVal('m_valorizacao', brl(valorizacao));
  setVal('m_pctFipeFin', fipe? pct(pctFipeFin) : '—');

  // composição
  const soma = e11+compReal+valorFinalUsado+valorFinanc+bonus+troco+incid;
  setVal('c_nf', brl(e11));
  setVal('c_vu', brl(valorFinalUsado));
  setVal('c_fin', brl(valorFinanc));
  setVal('c_bonus', brl(bonus));
  setVal('c_troco', brl(troco));
  setVal('c_incid', brl(incid));
  setVal('c_soma', brl(soma), 'accent');
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
  setVal('v_valorPolitica', brl(valorPolitica));
  setVal('v_valorFinal', brl(valorFinal));
  setVal('v_margemEfetiva', pct(margemEfetiva));

  const vu = num('v_vu'), tradeIn = num('v_tradeIn');
  const total = vu+tradeIn;
  const volta = valorFinal-total;
  setVal('v_totalTroca', brl(total));
  setVal('v_voltaTroca', brl(volta), volta>=0?'pos':'neg');
}

// ---------- EMPLACAMENTO ----------
function calcEmplac(){
  const vEstoque = num('e_valorEstoque'), mesEstoque = num('e_mesEstoque');
  const ipvaEstoque = ((vEstoque*0.01)/12)*((12-mesEstoque)+1);
  const alienEstoque = num('e_alienEstoque'), semAlienEstoque = num('e_semAlienEstoque');
  const totalAlienEstoque = alienEstoque+ipvaEstoque;
  const totalSemAlienEstoque = semAlienEstoque+ipvaEstoque;

  setVal('e_totalAlienEstoque', brl(totalAlienEstoque));
  setVal('e_totalSemAlienEstoque', brl(totalSemAlienEstoque));
  setVal('e_ipvaEstoque', brl(ipvaEstoque));
  setVal('e_totalAlienEstoque2', brl(totalAlienEstoque));
  setVal('e_totalSemAlienEstoque2', brl(totalSemAlienEstoque));

  const vDireta = num('e_valorDireta'), mesDireta = num('e_mesDireta');
  const ipvaDireta = ((vDireta*0.02)/12)*((12-mesDireta)+1);
  const alienDireta = num('e_alienDireta'), semAlienDireta = num('e_semAlienDireta');
  const totalAlienDireta = alienDireta+ipvaDireta;
  const totalSemAlienDireta = semAlienDireta+ipvaDireta;

  setVal('e_ipvaDireta', brl(ipvaDireta));
  setVal('e_totalAlienDireta', brl(totalAlienDireta));
  setVal('e_totalSemAlienDireta', brl(totalSemAlienDireta));
}

function calcAll(){ calcMargem(); calcDireta(); calcEmplac(); }

document.querySelectorAll('main input, main select').forEach(el=>{
  el.addEventListener('input', calcAll);
  el.addEventListener('change', calcAll);
});

calcAll();
</script>
</body>
</html>
