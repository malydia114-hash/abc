[index.html.html](https://github.com/user-attachments/files/35467036/index.html.html)
# abc<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="theme-color" content="#1B3A5C">
<title>蜂窩性組織炎 衛教App</title>
<style>
:root{
  --navy:#1B3A5C;
  --navy-dark:#122940;
  --gold:#C9A96E;
  --text:#2D4A6A;
  --muted:#8FA4B8;
  --bg:#F5F7FA;
  --white:#FFFFFF;
  --green:#2E7D32;
  --red:#C00000;
}
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
body{
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI","Microsoft JhengHei",sans-serif;
  background:var(--bg);color:var(--text);line-height:1.6;
  padding-bottom:80px;
}
/* ===== Header ===== */
.header{
  background:linear-gradient(135deg,var(--navy),#2D5A8A);
  color:#fff;padding:20px 16px 16px;position:sticky;top:0;z-index:100;
  box-shadow:0 2px 12px rgba(27,58,92,.3);
}
.header h1{font-size:20px;font-weight:700;letter-spacing:1px;}
.header p{font-size:12px;opacity:.85;margin-top:2px;letter-spacing:2px;}
.gold-line{width:48px;height:3px;background:var(--gold);margin-top:8px;border-radius:2px;}

/* ===== Tabs ===== */
.tabs{
  display:flex;background:var(--white);position:sticky;top:76px;z-index:99;
  box-shadow:0 2px 8px rgba(0,0,0,.06);overflow-x:auto;
  -webkit-overflow-scrolling:touch;scrollbar-width:none;
}
.tabs::-webkit-scrollbar{display:none;}
.tab{
  flex:1;min-width:72px;padding:12px 8px;text-align:center;font-size:13px;
  font-weight:600;color:var(--muted);border-bottom:3px solid transparent;
  cursor:pointer;transition:.2s;white-space:nowrap;
}
.tab.active{color:var(--navy);border-bottom-color:var(--gold);background:#F8FAFC;}

/* ===== Content ===== */
.content{padding:16px;display:none;animation:fadeIn .3s ease;}
.content.active{display:block;}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px);}to{opacity:1;transform:translateY(0);}}

.card{
  background:var(--white);border-radius:14px;padding:20px 18px;
  margin-bottom:14px;box-shadow:0 2px 10px rgba(27,58,92,.07);
  border-left:4px solid var(--gold);
}
.card h2{
  font-size:17px;color:var(--navy);font-weight:700;margin-bottom:12px;
  display:flex;align-items:center;gap:8px;
}
.card h2 .icon{
  width:28px;height:28px;background:var(--navy);color:#fff;border-radius:8px;
  display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;
}
.item{
  display:flex;gap:10px;padding:9px 0;font-size:15px;
  border-bottom:1px solid #EEF2F6;
}
.item:last-child{border-bottom:none;}
.item .dot{
  width:6px;height:6px;background:var(--gold);border-radius:50%;
  margin-top:9px;flex-shrink:0;
}
.item.warn{color:var(--red);font-weight:600;}
.item.warn .dot{background:var(--red);}
.item.key{color:var(--navy);font-weight:600;}

/* ===== Quiz ===== */
.q-card{
  background:var(--white);border-radius:14px;padding:18px 16px;
  margin-bottom:14px;box-shadow:0 2px 10px rgba(27,58,92,.07);
}
.q-num{
  display:inline-block;background:var(--navy);color:#fff;font-size:12px;
  font-weight:700;padding:3px 10px;border-radius:20px;margin-bottom:8px;
}
.q-text{font-size:15.5px;font-weight:700;color:var(--navy);margin-bottom:12px;line-height:1.5;}
.opt{
  display:flex;align-items:flex-start;gap:10px;padding:11px 13px;
  background:#F8FAFC;border:2px solid #E3E9F0;border-radius:10px;
  margin-bottom:8px;font-size:14.5px;cursor:pointer;transition:.2s;
}
.opt:active{transform:scale(.98);}
.opt .letter{
  width:24px;height:24px;background:var(--navy);color:#fff;border-radius:50%;
  display:flex;align-items:center;justify-content:center;font-size:12px;
  font-weight:700;flex-shrink:0;margin-top:1px;
}
.opt.correct{background:#E8F5E9;border-color:var(--green);}
.opt.correct .letter{background:var(--green);}
.opt.wrong{background:#FFEBEE;border-color:var(--red);}
.opt.wrong .letter{background:var(--red);}
.opt.disabled{pointer-events:none;opacity:.75;}
.result-msg{
  display:none;margin-top:8px;padding:10px 13px;border-radius:8px;
  font-size:14px;font-weight:600;
}
.result-msg.show{display:block;}
.result-msg.ok{background:#E8F5E9;color:var(--green);}
.result-msg.ng{background:#FFEBEE;color:var(--red);}

/* ===== Score ===== */
.score-card{
  background:linear-gradient(135deg,var(--navy),#2D5A8A);color:#fff;
  border-radius:14px;padding:22px 18px;text-align:center;
  box-shadow:0 4px 16px rgba(27,58,92,.3);
}
.score-card h2{color:#fff;font-size:18px;margin-bottom:6px;}
.score-num{font-size:48px;font-weight:800;color:var(--gold);line-height:1.2;}
.score-num span{font-size:20px;opacity:.7;}
.score-label{font-size:13px;opacity:.85;margin-top:4px;}
.btn{
  display:inline-block;background:var(--gold);color:var(--navy-dark);
  font-size:15px;font-weight:700;padding:12px 32px;border:none;
  border-radius:30px;cursor:pointer;margin-top:16px;transition:.2s;
}
.btn:active{transform:scale(.95);}
.answer-box{
  background:#FFFDF5;border:2px solid var(--gold);border-radius:12px;
  padding:14px 16px;text-align:center;margin-top:14px;
  font-size:15px;font-weight:700;color:var(--navy);
}

/* ===== Footer ===== */
.footer{
  text-align:center;padding:20px 16px;font-size:12px;color:var(--muted);
  line-height:1.8;
}
</style>
</head>
<body>

<div class="header">
  <h1>蜂窩性組織炎 衛教</h1>
  <p>CELLULITIS HEALTH EDUCATION</p>
  <div class="gold-line"></div>
</div>

<div class="tabs">
  <div class="tab active" onclick="go(0)">簡介</div>
  <div class="tab" onclick="go(1)">症狀</div>
  <div class="tab" onclick="go(2)">治療</div>
  <div class="tab" onclick="go(3)">照護</div>
  <div class="tab" onclick="go(4)">預防</div>
  <div class="tab" onclick="go(5)">警訊</div>
  <div class="tab" onclick="go(6)">測驗</div>
</div>

<!-- 0 簡介 -->
<div class="content active">
  <div class="card">
    <h2><span class="icon">ℹ</span>什麼是蜂窩性組織炎？</h2>
    <div class="item"><span class="dot"></span>細菌進入<b>皮膚深層</b>所造成的感染</div>
    <div class="item"><span class="dot"></span>常見於<b>小腿或足部</b>，也可能發生於身體其他部位</div>
    <div class="item warn"><span class="dot"></span>若未及時治療，感染可能<b>擴散或進入血液</b></div>
  </div>
  <div class="card">
    <h2><span class="icon">⚠</span>好發族群</h2>
    <div class="item"><span class="dot"></span>糖尿病患者</div>
    <div class="item"><span class="dot"></span>下肢水腫或循環不良者</div>
    <div class="item"><span class="dot"></span>有足癬、濕疹或皮膚龜裂者</div>
    <div class="item"><span class="dot"></span>皮膚有傷口者</div>
  </div>
</div>

<!-- 1 症狀 -->
<div class="content">
  <div class="card">
    <h2><span class="icon">🔥</span>典型症狀</h2>
    <div class="item key"><span class="dot"></span>局部皮膚<b>紅、腫、熱、痛</b>及觸壓疼痛</div>
    <div class="item"><span class="dot"></span>皮膚<b>緊繃</b>、表面像<b>橘皮</b>，可能出現水泡</div>
    <div class="item warn"><span class="dot"></span>可能合併<b>發燒、畏寒</b>或全身不適</div>
  </div>
  <div class="card">
    <h2><span class="icon">🔍</span>自我觀察</h2>
    <div class="item"><span class="dot"></span>可在<b>紅腫邊緣做記號</b>並記錄時間</div>
    <div class="item"><span class="dot"></span>觀察範圍是否<b>擴大</b></div>
    <div class="item"><span class="dot"></span>記錄疼痛程度變化</div>
  </div>
</div>

<!-- 2 治療 -->
<div class="content">
  <div class="card">
    <h2><span class="icon">💊</span>治療原則</h2>
    <div class="item"><span class="dot"></span>依醫囑使用<b>口服或靜脈抗生素</b></div>
    <div class="item key"><span class="dot"></span>即使症狀改善，仍須<b>完成全部療程</b>（不可自行停藥）</div>
    <div class="item"><span class="dot"></span>治療最初 <b>48 小時</b>，紅腫可能暫時加重</div>
    <div class="item warn"><span class="dot"></span>抗生素 <b>2～3 天後</b>仍未改善，請<b>回診評估</b></div>
  </div>
</div>

<!-- 3 照護 -->
<div class="content">
  <div class="card">
    <h2><span class="icon">🏠</span>居家照護 6 要點</h2>
    <div class="item key"><span class="dot"></span>休息時將<b>患肢抬高於心臟</b>，減輕腫脹</div>
    <div class="item"><span class="dot"></span>保持傷口<b>清潔乾燥</b>，依醫護人員指示換藥</div>
    <div class="item warn"><span class="dot"></span><b>勿抓、擠、按摩</b>患部或自行刺破水泡</div>
    <div class="item warn"><span class="dot"></span><b>勿自行塗抹</b>草藥、偏方或不明藥物</div>
    <div class="item"><span class="dot"></span>補充適量水分，適度活動鄰近關節，避免僵硬</div>
    <div class="item"><span class="dot"></span>在紅腫邊緣<b>做記號</b>並記錄時間，觀察是否擴大</div>
  </div>
</div>

<!-- 4 預防 -->
<div class="content">
  <div class="card">
    <h2><span class="icon">🛡</span>預防再次感染</h2>
    <div class="item"><span class="dot"></span>保持皮膚清潔並適度使用<b>保濕乳液</b></div>
    <div class="item key"><span class="dot"></span>傷口應立即<b>清潔、消毒並適當覆蓋</b></div>
    <div class="item"><span class="dot"></span>積極治療<b>足癬、濕疹</b>及皮膚龜裂</div>
    <div class="item warn"><span class="dot"></span><b>避免赤腳</b>，穿著合適的鞋襪以預防受傷</div>
    <div class="item key"><span class="dot"></span>糖尿病等慢性病患者：控制病情並<b>每日檢查皮膚</b></div>
  </div>
</div>

<!-- 5 警訊 -->
<div class="content">
  <div class="card" style="border-left-color:var(--red);">
    <h2><span class="icon" style="background:var(--red)">🚨</span>立即就醫警訊</h2>
    <div class="item warn"><span class="dot"></span>紅腫範圍<b>快速擴大</b>或疼痛明顯加劇</div>
    <div class="item warn"><span class="dot"></span>感染位於<b>眼睛周圍或臉部</b></div>
    <div class="item warn"><span class="dot"></span><b>高燒、畏寒</b>、呼吸急促或心跳加快</div>
    <div class="item warn"><span class="dot"></span>頭暈、<b>意識混亂</b>、冒冷汗或昏厥</div>
    <div class="item warn"><span class="dot"></span>皮膚出現<b>紫黑色斑塊、壞死</b>或水泡快速增加</div>
    <div class="item warn"><span class="dot"></span>傷口出現<b>大量或有惡臭</b>的分泌物</div>
  </div>
  <div class="card" style="border-left-color:var(--navy);background:#F8FAFC;">
    <h2><span class="icon">📌</span>提醒</h2>
    <div class="item"><span class="dot"></span>實際用藥、換藥及活動方式，請依<b>醫師或護理師指示</b></div>
  </div>
</div>

<!-- 6 測驗 -->
<div class="content">
  <div class="score-card">
    <h2>課後測驗</h2>
    <div class="score-num" id="score">0<span> / 5</span></div>
    <div class="score-label">答對題數</div>
    <button class="btn" onclick="resetQuiz()">重新測驗</button>
  </div>

  <div style="height:14px"></div>

  <div class="q-card" id="q1">
    <span class="q-num">第 1 題</span>
    <div class="q-text">下列何者關於蜂窩性組織炎的定義敘述正確？</div>
    <div class="opt" onclick="ans(1,0,this)"><span class="letter">A</span>由病毒感染引起，常見於手部</div>
    <div class="opt" onclick="ans(1,1,this)"><span class="letter">B</span>細菌進入皮膚深層所造成的感染，常見於小腿或足部</div>
    <div class="opt" onclick="ans(1,2,this)"><span class="letter">C</span>為過敏反應，表現為皮疹與搔癢</div>
    <div class="opt" onclick="ans(1,3,this)"><span class="letter">D</span>為真菌感染，主要發生於趾之間</div>
    <div class="result-msg" id="r1"></div>
  </div>

  <div class="q-card" id="q2">
    <span class="q-num">第 2 題</span>
    <div class="q-text">下列哪項為蜂窩性組織炎的常見症狀？</div>
    <div class="opt" onclick="ans(2,0,this)"><span class="letter">A</span>皮膚出現白色鳞屑、搔癢</div>
    <div class="opt" onclick="ans(2,1,this)"><span class="letter">B</span>局部皮膚紅、腫、熱、痛及觸壓疼痛</div>
    <div class="opt" onclick="ans(2,2,this)"><span class="letter">C</span>像麻風一樣的神經損害</div>
    <div class="opt" onclick="ans(2,3,this)"><span class="letter">D</span>關節腫脹但無紅腫</div>
    <div class="result-msg" id="r2"></div>
  </div>

  <div class="q-card" id="q3">
    <span class="q-num">第 3 題</span>
    <div class="q-text">服用抗生素治療蜂窩性組織炎時，下列何者是正確原則？</div>
    <div class="opt" onclick="ans(3,0,this)"><span class="letter">A</span>症狀改善後可自行停藥</div>
    <div class="opt" onclick="ans(3,1,this)"><span class="letter">B</span>若無改善，可增加自行服用的劑量</div>
    <div class="opt" onclick="ans(3,2,this)"><span class="letter">C</span>必須完成全部療程，即使症狀已好轉</div>
    <div class="opt" onclick="ans(3,3,this)"><span class="letter">D</span>只需服用 2 天即可停藥</div>
    <div class="result-msg" id="r3"></div>
  </div>

  <div class="q-card" id="q4">
    <span class="q-num">第 4 題</span>
    <div class="q-text">下列何者為錯誤的居家照護做法？</div>
    <div class="opt" onclick="ans(4,0,this)"><span class="letter">A</span>休息時將患肢抬高於心臟</div>
    <div class="opt" onclick="ans(4,1,this)"><span class="letter">B</span>保持傷口清潔乾燥，依指示換藥</div>
    <div class="opt" onclick="ans(4,2,this)"><span class="letter">C</span>可在紅腫邊緣做記號觀察擴大情形</div>
    <div class="opt" onclick="ans(4,3,this)"><span class="letter">D</span>自行塗抹草藥試圖加速癒合</div>
    <div class="result-msg" id="r4"></div>
  </div>

  <div class="q-card" id="q5">
    <span class="q-num">第 5 題</span>
    <div class="q-text">以下何種情況需要立即就醫？</div>
    <div class="opt" onclick="ans(5,0,this)"><span class="letter">A</span>紅腫範圍慢慢擴大，但無其他症狀</div>
    <div class="opt" onclick="ans(5,1,this)"><span class="letter">B</span>足癒合後略有色素沉澱</div>
    <div class="opt" onclick="ans(5,2,this)"><span class="letter">C</span>皮膚出現紫黑色斑塊、壞死或水泡快速增加</div>
    <div class="opt" onclick="ans(5,3,this)"><span class="letter">D</span>輕微的觸痛消失</div>
    <div class="result-msg" id="r5"></div>
  </div>

  <div class="answer-box">參考答案：1-B　2-B　3-C　4-D　5-C</div>
</div>

<div class="footer">
  衛生福利部臺中醫院　外科<br>
  資料來源：台中醫院衛教資訊<br>
  實際用藥、換藥及活動方式，請依醫師或護理師指示
</div>

<script>
var answers={1:1,2:1,3:2,4:3,5:2};
var done={};
var score=0;

function go(i){
  document.querySelectorAll('.tab').forEach(function(t,k){t.classList.toggle('active',k===i);});
  document.querySelectorAll('.content').forEach(function(c,k){c.classList.toggle('active',k===i);});
  window.scrollTo({top:0,behavior:'smooth'});
}

function ans(q,choice,el){
  if(done[q])return;
  done[q]=true;
  var card=document.getElementById('q'+q);
  var opts=card.querySelectorAll('.opt');
  opts.forEach(function(o){o.classList.add('disabled');});
  var correct=answers[q];
  opts[correct].classList.add('correct');
  var msg=document.getElementById('r'+q);
  if(choice===correct){
    score++;
    msg.textContent='答對了！';
    msg.className='result-msg show ok';
  }else{
    el.classList.add('wrong');
    msg.textContent='答錯了，正確答案是 '+'ABCD'[correct];
    msg.className='result-msg show ng';
  }
  document.getElementById('score').innerHTML=score+'<span> / 5</span>';
}

function resetQuiz(){
  done={};score=0;
  document.getElementById('score').innerHTML='0<span> / 5</span>';
  for(var i=1;i<=5;i++){
    var card=document.getElementById('q'+i);
    card.querySelectorAll('.opt').forEach(function(o){
      o.className='opt';
    });
    var m=document.getElementById('r'+i);
    m.className='result-msg';
    m.textContent='';
  }
}
</script>
</body>
</html>
