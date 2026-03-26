<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CYL AI Hub</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --bg:#0a0a0f;--bg2:#12121a;--bg3:#1a1a26;--bg4:#20202e;
  --border:rgba(255,255,255,0.07);--border2:rgba(255,255,255,0.13);
  --text:#e8e6f0;--text2:#8b8aa0;--text3:#5a5970;
  --accent:#7c6ee8;--accent-glow:rgba(124,110,232,0.15);
  --teal:#1fbf8f;--teal-dim:rgba(31,191,143,0.12);
  --amber:#f0a030;--amber-dim:rgba(240,160,48,0.12);
  --coral:#e05a3a;--coral-dim:rgba(224,90,58,0.12);
  --blue:#4a9fe8;--blue-dim:rgba(74,159,232,0.12);
  --radius:12px;--radius-sm:8px;
}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Noto Sans KR',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow:hidden}
body::before{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(124,110,232,0.025) 1px,transparent 1px),linear-gradient(90deg,rgba(124,110,232,0.025) 1px,transparent 1px);background-size:48px 48px;pointer-events:none;z-index:0}
.app{position:relative;z-index:1;display:flex;height:100vh;overflow:hidden}

/* SIDEBAR */
.sidebar{width:242px;flex-shrink:0;background:var(--bg2);border-right:1px solid var(--border);display:flex;flex-direction:column;overflow-y:auto}
.sidebar::-webkit-scrollbar{width:3px}.sidebar::-webkit-scrollbar-thumb{background:var(--border);border-radius:2px}
.logo{padding:20px 16px 16px;border-bottom:1px solid var(--border);flex-shrink:0}
.logo-mark{display:flex;align-items:center;gap:10px;margin-bottom:3px}
.logo-icon{width:30px;height:30px;background:linear-gradient(135deg,var(--accent),var(--teal));border-radius:7px;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:white;font-family:'DM Mono',monospace;letter-spacing:-0.5px}
.logo-text{font-size:14px;font-weight:700;letter-spacing:.04em}
.logo-sub{font-size:10px;color:var(--text3);letter-spacing:.07em;padding-left:40px;font-family:'DM Mono',monospace}
.sidebar-label{padding:14px 14px 6px;font-size:9.5px;font-weight:700;letter-spacing:.12em;color:var(--text3);text-transform:uppercase;font-family:'DM Mono',monospace}
.nav-btn{display:flex;align-items:center;gap:9px;padding:9px 10px;margin:1px 6px;border-radius:var(--radius-sm);cursor:pointer;transition:all .15s;border:1px solid transparent;background:none;width:calc(100% - 12px);text-align:left;color:var(--text2);font-family:'Noto Sans KR',sans-serif}
.nav-btn:hover{background:rgba(255,255,255,.04);color:var(--text)}
.nav-btn.active{background:var(--accent-glow);color:var(--text);border-color:rgba(124,110,232,.25)}
.nav-icon{width:26px;height:26px;border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:13px;flex-shrink:0}
.nav-name{font-size:12.5px;font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.nav-role{font-size:10px;color:var(--text3);margin-top:1px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.sidebar-footer{margin-top:auto;padding:14px;border-top:1px solid var(--border);flex-shrink:0}
.status-pill{display:flex;align-items:center;gap:6px;font-size:10.5px;color:var(--text3);font-family:'DM Mono',monospace}
.status-dot{width:6px;height:6px;border-radius:50%;background:var(--teal);box-shadow:0 0 5px var(--teal);animation:pulse 2s infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}

/* MAIN */
.main{flex:1;display:flex;flex-direction:column;overflow:hidden;min-width:0}
.topbar{display:flex;align-items:center;justify-content:space-between;padding:14px 20px;border-bottom:1px solid var(--border);background:rgba(10,10,15,.9);backdrop-filter:blur(12px);flex-shrink:0}
.th-left{display:flex;align-items:center;gap:10px}
.th-icon{width:34px;height:34px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:17px}
.th-title{font-size:14px;font-weight:600}
.th-desc{font-size:11px;color:var(--text3);margin-top:1px}
.version-badge{font-family:'DM Mono',monospace;font-size:10px;color:var(--text3);background:var(--bg3);border:1px solid var(--border);border-radius:4px;padding:3px 8px}

/* PANELS */
.content{flex:1;overflow:hidden;display:flex;flex-direction:column}
.wf-panel{flex:1;overflow-y:auto;padding:24px}
.wf-panel::-webkit-scrollbar{width:4px}.wf-panel::-webkit-scrollbar-thumb{background:var(--border2);border-radius:2px}
.wf-head{margin-bottom:22px}
.wf-head h2{font-size:19px;font-weight:600;margin-bottom:5px}
.wf-head p{font-size:13px;color:var(--text2);line-height:1.6}
.info-card{background:var(--accent-glow);border:1px solid rgba(124,110,232,.2);border-radius:var(--radius-sm);padding:11px 14px;margin-bottom:16px;font-size:12.5px;color:var(--text2);line-height:1.6}
.info-card strong{color:var(--accent)}

/* FORMS */
.fg{display:flex;flex-direction:column;gap:5px;margin-bottom:14px}
.fg2{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.fl{font-size:11.5px;font-weight:500;color:var(--text2)}
.fl span{color:var(--coral)}
.fi,.fs,.ft{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius-sm);color:var(--text);font-family:'Noto Sans KR',sans-serif;font-size:13.5px;padding:9px 12px;transition:border-color .15s;outline:none;width:100%}
.fi:focus,.fs:focus,.ft:focus{border-color:var(--accent)}
.ft{resize:vertical;min-height:88px;line-height:1.55}
.fs{cursor:pointer;appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='6' viewBox='0 0 10 6'%3E%3Cpath d='M1 1l4 4 4-4' stroke='%235a5970' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 12px center;padding-right:32px}
.fs option{background:var(--bg2)}
.tags-row{display:flex;flex-wrap:wrap;gap:6px;margin-top:4px}
.tag{padding:4px 10px;border-radius:12px;font-size:11.5px;cursor:pointer;border:1px solid var(--border);color:var(--text2);font-family:'Noto Sans KR',sans-serif;transition:all .15s;background:var(--bg2)}
.tag:hover{border-color:var(--accent);color:var(--accent);background:var(--accent-glow)}
.tag.sel{border-color:var(--accent);color:var(--accent);background:var(--accent-glow)}
.divider{display:flex;align-items:center;gap:10px;margin:18px 0 14px;font-size:11px;color:var(--text3);font-family:'DM Mono',monospace}
.divider::before,.divider::after{content:'';flex:1;height:1px;background:var(--border)}
.btn-run{display:inline-flex;align-items:center;gap:7px;padding:10px 22px;border-radius:var(--radius-sm);background:var(--accent);color:white;border:none;cursor:pointer;font-size:13.5px;font-weight:500;font-family:'Noto Sans KR',sans-serif;transition:all .15s;margin-top:4px}
.btn-run:hover{background:#9080f0;transform:translateY(-1px)}
.btn-run:disabled{opacity:.5;cursor:not-allowed;transform:none}

/* RESULT */
.result-box{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);margin-top:20px;overflow:hidden;animation:fadeUp .25s ease}
.result-hd{display:flex;align-items:center;justify-content:space-between;padding:11px 16px;border-bottom:1px solid var(--border);background:var(--bg3)}
.result-lbl{font-size:11.5px;font-weight:500;color:var(--text2);font-family:'DM Mono',monospace}
.result-acts{display:flex;gap:5px}
.act-btn{padding:4px 10px;border-radius:5px;font-size:11px;border:1px solid var(--border2);background:transparent;color:var(--text2);cursor:pointer;font-family:'Noto Sans KR',sans-serif;transition:all .15s}
.act-btn:hover{background:var(--bg4);color:var(--text)}
.result-body{padding:16px;font-size:13.5px;line-height:1.75;color:var(--text);white-space:pre-wrap;word-break:break-word}

/* CHAT */
.chat-wrap{flex:1;display:flex;flex-direction:column;overflow:hidden}
.quick-bar{display:flex;gap:6px;padding:10px 20px;border-bottom:1px solid var(--border);overflow-x:auto;flex-shrink:0}
.quick-bar::-webkit-scrollbar{height:0}
.qbtn{flex-shrink:0;padding:6px 12px;border-radius:16px;font-size:11.5px;font-weight:500;border:1px solid var(--border);background:var(--bg2);color:var(--text2);cursor:pointer;transition:all .15s;white-space:nowrap;font-family:'Noto Sans KR',sans-serif}
.qbtn:hover{border-color:var(--border2);color:var(--text);background:var(--bg3)}
.chat-area{flex:1;overflow-y:auto;padding:20px;display:flex;flex-direction:column;gap:13px}
.chat-area::-webkit-scrollbar{width:4px}.chat-area::-webkit-scrollbar-thumb{background:var(--border2);border-radius:2px}
.welcome{display:flex;flex-direction:column;align-items:center;justify-content:center;flex:1;text-align:center;padding:32px}
.w-icon{width:54px;height:54px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:24px;margin:0 auto 16px}
.welcome h3{font-size:18px;font-weight:600;margin-bottom:6px}
.welcome p{font-size:13px;color:var(--text2);line-height:1.6;max-width:350px}
.sug-grid{display:grid;grid-template-columns:1fr 1fr;gap:7px;margin-top:18px;width:100%;max-width:450px}
.sug-card{padding:10px 13px;border:1px solid var(--border);border-radius:var(--radius-sm);background:var(--bg2);cursor:pointer;text-align:left;transition:all .15s;font-size:12px;color:var(--text2);line-height:1.4;font-family:'Noto Sans KR',sans-serif}
.sug-card:hover{border-color:var(--accent);background:var(--accent-glow);color:var(--text)}
.msg{display:flex;gap:10px;animation:fadeUp .2s ease}
@keyframes fadeUp{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:translateY(0)}}
.msg.user{flex-direction:row-reverse}
.m-av{width:30px;height:30px;border-radius:7px;flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:13px;margin-top:2px}
.msg.user .m-av{background:var(--bg3);border:1px solid var(--border2);font-size:10px;font-weight:700;color:var(--text2);font-family:'DM Mono',monospace}
.m-bub{max-width:70%;padding:11px 14px;border-radius:var(--radius);font-size:13.5px;line-height:1.65}
.msg.user .m-bub{background:var(--bg3);border:1px solid var(--border);border-radius:var(--radius) 4px var(--radius) var(--radius)}
.msg.ai .m-bub{background:var(--bg2);border:1px solid var(--border);border-radius:4px var(--radius) var(--radius) var(--radius)}
.m-time{font-size:10px;color:var(--text3);margin-top:3px;font-family:'DM Mono',monospace}
.msg.user .m-time{text-align:right}
.dots{display:flex;gap:4px;padding:3px 0}
.dots span{width:6px;height:6px;border-radius:50%;background:var(--text3);animation:bonce 1.2s infinite}
.dots span:nth-child(2){animation-delay:.2s}.dots span:nth-child(3){animation-delay:.4s}
@keyframes bonce{0%,60%,100%{transform:translateY(0);opacity:.4}30%{transform:translateY(-4px);opacity:1}}
.input-area{padding:13px 20px 17px;border-top:1px solid var(--border);flex-shrink:0}
.input-box{display:flex;align-items:flex-end;gap:8px;background:var(--bg2);border:1px solid var(--border);border-radius:13px;padding:9px 9px 9px 14px;transition:border-color .15s}
.input-box:focus-within{border-color:var(--accent)}
textarea{flex:1;background:none;border:none;outline:none;color:var(--text);font-size:13.5px;font-family:'Noto Sans KR',sans-serif;resize:none;max-height:110px;line-height:1.5;padding:2px 0}
textarea::placeholder{color:var(--text3)}
.send-btn{width:32px;height:32px;border-radius:7px;background:var(--accent);border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .15s;flex-shrink:0}
.send-btn:hover{background:#9080f0;transform:scale(1.05)}
.send-btn:disabled{background:var(--bg3);cursor:not-allowed;transform:none;opacity:.5}
.send-btn svg{width:13px;height:13px;fill:white}
.input-hint{font-size:10.5px;color:var(--text3);margin-top:6px;text-align:center;font-family:'DM Mono',monospace}
.hidden{display:none!important}
.m-bub strong{font-weight:600}
</style>
</head>
<body>
<div class="app">

<!-- SIDEBAR -->
<aside class="sidebar">
  <div class="logo">
    <div class="logo-mark"><div class="logo-icon">CYL</div><div class="logo-text">AI 운영 허브</div></div>
    <div class="logo-sub">CYL GLOBAL · MARKETING</div>
  </div>

  <div class="sidebar-label">AI 워크플로우</div>
  <button class="nav-btn" id="nb-script" onclick="show('script')">
    <div class="nav-icon" style="background:var(--teal-dim)">💬</div>
    <div><div class="nav-name">다국어 상담 스크립트</div><div class="nav-role">태국·베트남·러시아·인도네시아</div></div>
  </button>
  <button class="nav-btn" id="nb-adcopy" onclick="show('adcopy')">
    <div class="nav-icon" style="background:var(--amber-dim)">📣</div>
    <div><div class="nav-name">광고 카피·콘텐츠 기획</div><div class="nav-role">메타 광고·SNS 포스팅</div></div>
  </button>
  <button class="nav-btn" id="nb-report" onclick="show('report')">
    <div class="nav-icon" style="background:var(--blue-dim)">📈</div>
    <div><div class="nav-name">주간 성과 보고서</div><div class="nav-role">자동 생성·KPI 요약</div></div>
  </button>
  <button class="nav-btn" id="nb-task" onclick="show('task')">
    <div class="nav-icon" style="background:var(--coral-dim)">📋</div>
    <div><div class="nav-name">업무지시서 자동 생성</div><div class="nav-role">팀간 표준 양식</div></div>
  </button>

  <div class="sidebar-label" style="margin-top:6px">팀 AI 어시스턴트</div>
  <button class="nav-btn active" id="nb-chat1" onclick="show('chat');setAgent('overseas')">
    <div class="nav-icon" style="background:var(--teal-dim)">🌏</div>
    <div><div class="nav-name">해외사업부 AI</div><div class="nav-role">1·2·3팀 통합 어시스턴트</div></div>
  </button>
  <button class="nav-btn" id="nb-chat2" onclick="show('chat');setAgent('marketing')">
    <div class="nav-icon" style="background:var(--amber-dim)">📊</div>
    <div><div class="nav-name">마케팅팀 AI</div><div class="nav-role">ROAS·광고 성과 분석</div></div>
  </button>
  <button class="nav-btn" id="nb-chat3" onclick="show('chat');setAgent('media')">
    <div class="nav-icon" style="background:var(--coral-dim)">🎨</div>
    <div><div class="nav-name">미디어팀 AI</div><div class="nav-role">디자인·촬영 기획</div></div>
  </button>
  <button class="nav-btn" id="nb-chat4" onclick="show('chat');setAgent('executive')">
    <div class="nav-icon" style="background:rgba(180,80,200,.15)">👔</div>
    <div><div class="nav-name">경영진 AI</div><div class="nav-role">전략·보고·의사결정</div></div>
  </button>
  <button class="nav-btn" id="nb-chat5" onclick="show('chat');setAgent('concierge')">
    <div class="nav-icon" style="background:var(--blue-dim)">🚗</div>
    <div><div class="nav-name">컨시어지 AI</div><div class="nav-role">픽업·이동 관리</div></div>
  </button>

  <div class="sidebar-footer">
    <div class="status-pill"><div class="status-dot"></div><span id="status-txt">서버 연결 확인 중...</span></div>
  </div>
</aside>

<!-- MAIN -->
<main class="main">
  <div class="topbar">
    <div class="th-left">
      <div class="th-icon" id="th-icon" style="background:var(--teal-dim)">💬</div>
      <div><div class="th-title" id="th-title">다국어 상담 스크립트 생성</div><div class="th-desc" id="th-desc">병원·시술·국가를 선택하면 현지어 상담 문구를 즉시 생성합니다</div></div>
    </div>
    <div class="version-badge">v2.0 · Vercel</div>
  </div>

  <div class="content">

    <!-- ── SCRIPT PANEL ── -->
    <div class="wf-panel" id="p-script">
      <div class="wf-head"><h2>💬 다국어 상담 스크립트 생성</h2><p>병원·시술·국가를 선택하면 현지 언어로 된 완성형 상담 문구를 즉시 만들어 드립니다.</p></div>
      <div class="info-card"><strong>사용법:</strong> 병원과 시술을 고르고, 원하는 언어를 선택한 뒤 생성 버튼을 누르세요. 추가 요청사항을 입력할수록 더 정확한 스크립트가 생성됩니다.</div>
      <div class="fg2">
        <div class="fg"><label class="fl">병원 선택<span>*</span></label>
          <select class="fs" id="s-hosp"><option value="">선택하세요</option>
            <optgroup label="해외1팀"><option>더프라이드 성형외과</option><option>로그 성형외과</option><option>무드온 성형외과</option></optgroup>
            <optgroup label="해외2팀"><option>리스토리 성형외과</option><option>신상 성형외과</option><option>아이루미 성형외과</option><option>노트 성형외과</option></optgroup>
            <optgroup label="해외3팀"><option>유니 성형외과</option><option>바이브 성형외과</option></optgroup>
          </select>
        </div>
        <div class="fg"><label class="fl">시술 종류<span>*</span></label>
          <select class="fs" id="s-proc"><option value="">선택하세요</option>
            <option>눈 수술 (쌍꺼풀)</option><option>코 수술 (융비술)</option><option>윤곽 수술</option><option>지방흡입</option><option>가슴 수술</option><option>리프팅</option><option>피부 시술</option><option>복합 수술 상담</option>
          </select>
        </div>
      </div>
      <div class="fg"><label class="fl">국가·언어<span>*</span> (복수 선택 가능)</label>
        <div class="tags-row" id="tg-lang">
          <div class="tag" onclick="tg(this)">🇹🇭 태국어</div><div class="tag" onclick="tg(this)">🇻🇳 베트남어</div>
          <div class="tag" onclick="tg(this)">🇷🇺 러시아어</div><div class="tag" onclick="tg(this)">🇮🇩 인도네시아어</div>
          <div class="tag" onclick="tg(this)">🇺🇸 영어</div><div class="tag" onclick="tg(this)">🇨🇳 중국어</div><div class="tag" onclick="tg(this)">🇯🇵 일본어</div>
        </div>
      </div>
      <div class="fg"><label class="fl">스크립트 유형</label>
        <div class="tags-row" id="tg-stype">
          <div class="tag sel" onclick="tg(this)">📩 인스타 DM 답변</div><div class="tag" onclick="tg(this)">💬 카카오톡 상담</div>
          <div class="tag" onclick="tg(this)">📧 이메일 답변</div><div class="tag" onclick="tg(this)">📞 전화 통화 가이드</div><div class="tag" onclick="tg(this)">💰 견적 안내</div>
        </div>
      </div>
      <div class="fg"><label class="fl">고객 상황 / 추가 요청</label>
        <textarea class="ft" id="s-ctx" placeholder="예: 가격이 궁금하다고 했어요. 내원 유도하는 방향으로 써주세요."></textarea>
      </div>
      <button class="btn-run" id="br-script" onclick="run('script')">⚡ 스크립트 생성하기</button>
      <div id="rs-script" class="hidden">
        <div class="result-box">
          <div class="result-hd"><div class="result-lbl" id="rs-script-lbl">생성된 상담 스크립트</div>
            <div class="result-acts"><button class="act-btn" onclick="cp('rs-script-body')">📋 복사</button><button class="act-btn" onclick="close_r('rs-script')">✕</button></div>
          </div>
          <div class="result-body" id="rs-script-body"></div>
        </div>
      </div>
    </div>

    <!-- ── ADCOPY PANEL ── -->
    <div class="wf-panel hidden" id="p-adcopy">
      <div class="wf-head"><h2>📣 광고 카피·콘텐츠 기획</h2><p>메타 광고 A/B 카피, SNS 포스팅, 틱톡 스크립트를 즉시 기획합니다.</p></div>
      <div class="fg2">
        <div class="fg"><label class="fl">콘텐츠 유형<span>*</span></label>
          <select class="fs" id="a-type"><option>메타 광고 카피 (A/B 2안)</option><option>인스타그램 피드 포스팅</option><option>인스타그램 스토리</option><option>틱톡 영상 스크립트</option><option>페이스북 광고 카피</option><option>SNS 해시태그 세트</option></select>
        </div>
        <div class="fg"><label class="fl">병원<span>*</span></label>
          <select class="fs" id="a-hosp"><option>더프라이드</option><option>로그</option><option>무드온</option><option>리스토리</option><option>신상</option><option>아이루미</option><option>노트</option><option>유니</option><option>바이브</option></select>
        </div>
      </div>
      <div class="fg2">
        <div class="fg"><label class="fl">타겟 국가</label>
          <select class="fs" id="a-country"><option>태국</option><option>베트남</option><option>러시아</option><option>인도네시아</option><option>영어권</option><option>중화권</option></select>
        </div>
        <div class="fg"><label class="fl">타겟</label>
          <select class="fs" id="a-target"><option>여성 20-30대</option><option>여성 30-40대</option><option>여성 전체</option><option>전체</option></select>
        </div>
      </div>
      <div class="fg"><label class="fl">시술</label>
        <div class="tags-row" id="tg-aproc">
          <div class="tag sel" onclick="tg(this)">눈 수술</div><div class="tag" onclick="tg(this)">코 수술</div><div class="tag" onclick="tg(this)">윤곽</div>
          <div class="tag" onclick="tg(this)">지방흡입</div><div class="tag" onclick="tg(this)">리프팅</div><div class="tag" onclick="tg(this)">피부</div><div class="tag" onclick="tg(this)">복합 패키지</div>
        </div>
      </div>
      <div class="fg"><label class="fl">캠페인 목표</label>
        <div class="tags-row" id="tg-agoal">
          <div class="tag sel" onclick="tg(this)">상담 문의 유도</div><div class="tag" onclick="tg(this)">인지도 확산</div><div class="tag" onclick="tg(this)">내원 예약 유도</div><div class="tag" onclick="tg(this)">이벤트 안내</div>
        </div>
      </div>
      <div class="fg"><label class="fl">톤앤매너 / 특이사항</label>
        <textarea class="ft" id="a-tone" placeholder="예: 신뢰감 있고 고급스럽게, '자연스러운 결과' 강조해주세요."></textarea>
      </div>
      <button class="btn-run" id="br-adcopy" onclick="run('adcopy')">⚡ 카피 생성하기</button>
      <div id="rs-adcopy" class="hidden">
        <div class="result-box">
          <div class="result-hd"><div class="result-lbl">생성된 광고 카피</div>
            <div class="result-acts"><button class="act-btn" onclick="cp('rs-adcopy-body')">📋 복사</button><button class="act-btn" onclick="close_r('rs-adcopy')">✕</button></div>
          </div>
          <div class="result-body" id="rs-adcopy-body"></div>
        </div>
      </div>
    </div>

    <!-- ── REPORT PANEL ── -->
    <div class="wf-panel hidden" id="p-report">
      <div class="wf-head"><h2>📈 주간 성과 보고서 자동 생성</h2><p>수치를 입력하면 대표님 보고용 완성 보고서가 즉시 작성됩니다.</p></div>
      <div class="fg2">
        <div class="fg"><label class="fl">보고 주차</label><input class="fi" id="r-week" placeholder="예: 2026년 3월 4주차"></div>
        <div class="fg"><label class="fl">작성자</label><input class="fi" id="r-author" placeholder="팀장 이름"></div>
      </div>
      <div class="divider">팀별 상담 실적</div>
      <div class="fg2">
        <div class="fg"><label class="fl">해외1팀 상담 건수</label><input class="fi" id="r-t1c" placeholder="예: 42건"></div>
        <div class="fg"><label class="fl">해외1팀 내원 전환</label><input class="fi" id="r-t1v" placeholder="예: 8명"></div>
      </div>
      <div class="fg2">
        <div class="fg"><label class="fl">해외2팀 상담 건수</label><input class="fi" id="r-t2c" placeholder="예: 38건"></div>
        <div class="fg"><label class="fl">해외2팀 내원 전환</label><input class="fi" id="r-t2v" placeholder="예: 6명"></div>
      </div>
      <div class="fg2">
        <div class="fg"><label class="fl">해외3팀 상담 건수</label><input class="fi" id="r-t3c" placeholder="예: 25건"></div>
        <div class="fg"><label class="fl">해외3팀 내원 전환</label><input class="fi" id="r-t3v" placeholder="예: 4명"></div>
      </div>
      <div class="divider">광고 성과</div>
      <div class="fg2">
        <div class="fg"><label class="fl">총 광고 집행액</label><input class="fi" id="r-spend" placeholder="예: 1,200만원"></div>
        <div class="fg"><label class="fl">전체 ROAS</label><input class="fi" id="r-roas" placeholder="예: 3.2"></div>
      </div>
      <div class="fg2">
        <div class="fg"><label class="fl">최고 성과 병원</label><input class="fi" id="r-toph" placeholder="예: 더프라이드 (ROAS 4.8)"></div>
        <div class="fg"><label class="fl">주요 성과 국가</label><input class="fi" id="r-topc" placeholder="예: 태국 (상담 28건)"></div>
      </div>
      <div class="divider">이슈 & 다음 주 계획</div>
      <div class="fg"><label class="fl">이번 주 주요 이슈</label>
        <textarea class="ft" id="r-issues" placeholder="예: 러시아 에이전시 계약 갱신 지연, 태국 광고 소재 교체 필요"></textarea>
      </div>
      <div class="fg"><label class="fl">다음 주 핵심 계획</label>
        <textarea class="ft" id="r-plan" placeholder="예: 방콕 상담회 준비(4/15), 더프라이드 신규 광고 소재 3종 제작"></textarea>
      </div>
      <button class="btn-run" id="br-report" onclick="run('report')">⚡ 보고서 생성하기</button>
      <div id="rs-report" class="hidden">
        <div class="result-box">
          <div class="result-hd"><div class="result-lbl">생성된 주간 성과 보고서</div>
            <div class="result-acts"><button class="act-btn" onclick="cp('rs-report-body')">📋 복사</button><button class="act-btn" onclick="close_r('rs-report')">✕</button></div>
          </div>
          <div class="result-body" id="rs-report-body"></div>
        </div>
      </div>
    </div>

    <!-- ── TASK PANEL ── -->
    <div class="wf-panel hidden" id="p-task">
      <div class="wf-head"><h2>📋 업무지시서 자동 생성</h2><p>간단히 입력하면 팀간 표준 양식의 완성된 업무지시서가 만들어집니다.</p></div>
      <div class="fg2">
        <div class="fg"><label class="fl">요청 팀<span>*</span></label>
          <select class="fs" id="t-from"><option>해외사업부 1팀</option><option>해외사업부 2팀</option><option>해외사업부 3팀</option><option>경영진</option></select>
        </div>
        <div class="fg"><label class="fl">수신 팀<span>*</span></label>
          <select class="fs" id="t-to"><option>마케팅팀 (김민규)</option><option>미디어팀 (질)</option><option>미디어팀 (띠띠)</option><option>미디어팀 (주정이)</option><option>미디어팀 전체</option><option>컨시어지팀</option></select>
        </div>
      </div>
      <div class="fg2">
        <div class="fg"><label class="fl">담당 병원</label>
          <select class="fs" id="t-hosp"><option>더프라이드</option><option>로그</option><option>무드온</option><option>리스토리</option><option>신상</option><option>아이루미</option><option>노트</option><option>유니</option><option>바이브</option></select>
        </div>
        <div class="fg"><label class="fl">마감 기한<span>*</span></label>
          <input class="fi" id="t-ddl" placeholder="예: 2026.04.10 (목) 오전 10시">
        </div>
      </div>
      <div class="fg"><label class="fl">업무 분류</label>
        <div class="tags-row" id="tg-ttype">
          <div class="tag sel" onclick="tg(this)">📊 광고 집행</div><div class="tag" onclick="tg(this)">🎨 포스팅 디자인</div>
          <div class="tag" onclick="tg(this)">🖼 광고 디자인</div><div class="tag" onclick="tg(this)">🎬 영상 촬영</div><div class="tag" onclick="tg(this)">🚗 픽업/이동</div>
        </div>
      </div>
      <div class="fg"><label class="fl">업무 내용<span>*</span></label>
        <textarea class="ft" id="t-content" placeholder="예: 더프라이드 태국 눈수술 메타 광고 새 소재 3개 필요. 여성 25-35세 타겟, A/B 테스트 용도."></textarea>
      </div>
      <div class="fg"><label class="fl">완료 기준</label>
        <textarea class="ft" id="t-done" placeholder="예: 광고 카피 2안 이상 / 이미지 1080x1080 / 팀장 검토 후 광고 매니저 업로드 완료" style="min-height:68px"></textarea>
      </div>
      <button class="btn-run" id="br-task" onclick="run('task')">⚡ 업무지시서 생성하기</button>
      <div id="rs-task" class="hidden">
        <div class="result-box">
          <div class="result-hd"><div class="result-lbl">생성된 업무지시서</div>
            <div class="result-acts"><button class="act-btn" onclick="cp('rs-task-body')">📋 복사</button><button class="act-btn" onclick="close_r('rs-task')">✕</button></div>
          </div>
          <div class="result-body" id="rs-task-body"></div>
        </div>
      </div>
    </div>

    <!-- ── CHAT PANEL ── -->
    <div class="chat-wrap hidden" id="p-chat">
      <div class="quick-bar" id="qbar"></div>
      <div class="chat-area" id="chat-area">
        <div class="welcome" id="welcome">
          <div class="w-icon" id="w-icon" style="background:var(--teal-dim)">🌏</div>
          <h3 id="w-title">해외사업부 AI</h3>
          <p id="w-desc">팀별 전용 AI와 자유롭게 대화하세요.</p>
          <div class="sug-grid" id="sug-grid"></div>
        </div>
      </div>
      <div class="input-area">
        <div class="input-box">
          <textarea id="msg-inp" rows="1" placeholder="메시지를 입력하세요..." onkeydown="hk(event)" oninput="ar(this)"></textarea>
          <button class="send-btn" id="send-btn" onclick="sendMsg()">
            <svg viewBox="0 0 24 24"><path d="M2 21L23 12 2 3v7l15 2-15 2z"/></svg>
          </button>
        </div>
        <div class="input-hint">Enter 전송 · Shift+Enter 줄바꿈</div>
      </div>
    </div>

  </div>
</main>
</div>

<script>
// ── API CALL (via /api/chat proxy) ──
async function callAPI(system, userMsg, history=[]) {
  const messages = [...history, { role:'user', content:userMsg }];
  const res = await fetch('/api/chat', {
    method:'POST',
    headers:{'Content-Type':'application/json'},
    body: JSON.stringify({ system, messages, max_tokens:1500 })
  });
  const data = await res.json();
  if (!res.ok) throw new Error(data.error || 'API 오류');
  return data.text;
}

// ── SERVER HEALTH CHECK ──
async function checkServer() {
  try {
    const res = await fetch('/api/chat', { method:'POST', headers:{'Content-Type':'application/json'}, body:JSON.stringify({messages:[{role:'user',content:'ping'}],max_tokens:5}) });
    const d = await res.json();
    if (d.text || d.error?.includes('API 키')) {
      document.getElementById('status-txt').textContent = 'API 연결됨';
      document.querySelector('.status-dot').style.background = 'var(--teal)';
    }
  } catch(e) {
    document.getElementById('status-txt').textContent = '서버 연결 안됨';
    document.querySelector('.status-dot').style.background = 'var(--coral)';
  }
}
checkServer();

// ── NAV ──
const PANEL_INFO = {
  script:  {icon:'💬',title:'다국어 상담 스크립트 생성',desc:'병원·시술·국가를 선택하면 현지어 상담 문구를 즉시 생성합니다',color:'var(--teal-dim)'},
  adcopy:  {icon:'📣',title:'광고 카피·콘텐츠 기획',desc:'메타 광고·SNS 포스팅 카피를 AI가 즉시 기획합니다',color:'var(--amber-dim)'},
  report:  {icon:'📈',title:'주간 성과 보고서 자동 생성',desc:'수치 입력만 하면 대표님 보고용 보고서가 완성됩니다',color:'var(--blue-dim)'},
  task:    {icon:'📋',title:'업무지시서 자동 생성',desc:'팀간 표준 양식 업무지시서를 즉시 생성합니다',color:'var(--coral-dim)'},
  chat:    {icon:'🌏',title:'팀별 AI 어시스턴트',desc:'각 팀 전용 AI와 자유롭게 대화하세요',color:'var(--teal-dim)'},
};

function show(id) {
  ['script','adcopy','report','task','chat'].forEach(p => document.getElementById(`p-${p}`)?.classList.add('hidden'));
  document.getElementById(`p-${id}`)?.classList.remove('hidden');
  document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
  document.getElementById(`nb-${id}`)?.classList.add('active');
  const m = PANEL_INFO[id] || PANEL_INFO.script;
  document.getElementById('th-icon').textContent = m.icon;
  document.getElementById('th-icon').style.background = m.color;
  document.getElementById('th-title').textContent = m.title;
  document.getElementById('th-desc').textContent = m.desc;
}

// ── TAG TOGGLE ──
function tg(el) { el.classList.toggle('sel'); }
function getTags(id) {
  return Array.from(document.querySelectorAll(`#${id} .tag.sel`)).map(t => t.textContent.trim().replace(/^[^\w가-힣]+/,''));
}

// ── COPY ──
async function cp(id) {
  try { await navigator.clipboard.writeText(document.getElementById(id)?.textContent||''); toast('복사됐습니다!'); }
  catch(e) { toast('직접 선택 후 복사하세요'); }
}
function close_r(id) { document.getElementById(id)?.classList.add('hidden'); }

function toast(msg) {
  const t = document.createElement('div');
  t.style.cssText='position:fixed;bottom:24px;left:50%;transform:translateX(-50%);background:#2a2a3a;border:1px solid rgba(255,255,255,.15);color:#e8e6f0;padding:9px 18px;border-radius:8px;font-size:13px;z-index:9999';
  t.textContent=msg; document.body.appendChild(t); setTimeout(()=>t.remove(),2000);
}

// ── LOADING ──
const BTN_LABELS = {'br-script':'스크립트 생성하기','br-adcopy':'카피 생성하기','br-report':'보고서 생성하기','br-task':'업무지시서 생성하기'};
function setLoad(btnId, resultId, on) {
  const btn = document.getElementById(btnId);
  const res = document.getElementById(resultId);
  if (on) {
    btn.disabled = true;
    btn.innerHTML = '<span style="display:inline-flex;gap:3px"><span style="animation:bonce 1.2s infinite;display:inline-block">●</span><span style="animation:bonce 1.2s infinite .2s;display:inline-block">●</span><span style="animation:bonce 1.2s infinite .4s;display:inline-block">●</span></span>';
    res.classList.remove('hidden');
    document.getElementById(`${resultId}-body`).textContent = '생성 중...';
  } else {
    btn.disabled = false;
    btn.innerHTML = '⚡ ' + BTN_LABELS[btnId];
  }
}

// ── WORKFLOW RUNNERS ──
async function run(type) {
  if (type==='script') await runScript();
  else if (type==='adcopy') await runAdcopy();
  else if (type==='report') await runReport();
  else if (type==='task') await runTask();
}

async function runScript() {
  const hosp = document.getElementById('s-hosp').value;
  const proc = document.getElementById('s-proc').value;
  const langs = getTags('tg-lang');
  const stypes = getTags('tg-stype');
  const ctx = document.getElementById('s-ctx').value;
  if (!hosp||!proc||!langs.length) { toast('병원, 시술, 언어를 선택해 주세요'); return; }
  setLoad('br-script','rs-script',true);
  const sys = `당신은 CYL Marketing 해외사업부 다국어 상담 전문 AI입니다. 강남 최고급 성형외과의 해외 환자 유치를 위한 상담 스크립트를 작성합니다. 병원별 특성을 반영하고, 의료 내용은 정확하며 과장 없이 작성하세요. 한국어 설명 + 현지 언어 번역을 함께 제공하세요.`;
  const prompt = `병원: ${hosp}\n시술: ${proc}\n언어: ${langs.join(', ')}\n유형: ${stypes.join(', ')}\n${ctx?`추가요청: ${ctx}\n`:''}\n각 언어별로 완성된 스크립트를 작성해주세요. 앞에 한국어 간략 설명 포함.`;
  try {
    const r = await callAPI(sys, prompt);
    document.getElementById('rs-script-lbl').textContent = `${hosp} · ${proc} · ${langs.join('/')}`;
    document.getElementById('rs-script-body').textContent = r;
  } catch(e) { document.getElementById('rs-script-body').textContent = '⚠️ 오류: '+e.message; }
  finally { setLoad('br-script','rs-script',false); document.getElementById('rs-script').scrollIntoView({behavior:'smooth',block:'start'}); }
}

async function runAdcopy() {
  const type = document.getElementById('a-type').value;
  const hosp = document.getElementById('a-hosp').value;
  const country = document.getElementById('a-country').value;
  const target = document.getElementById('a-target').value;
  const procs = getTags('tg-aproc');
  const goals = getTags('tg-agoal');
  const tone = document.getElementById('a-tone').value;
  setLoad('br-adcopy','rs-adcopy',true);
  const sys = `당신은 CYL Marketing 퍼포먼스 마케팅 전문 AI입니다. 강남 성형외과의 해외 타겟 광고 카피와 SNS 콘텐츠를 전문으로 기획합니다. 메타 광고는 A안/B안 2개 이상 제공하고, 각 안의 타겟팅 포인트를 설명하세요. 의료광고 과대광고 금지를 준수하세요.`;
  const prompt = `유형: ${type}\n병원: ${hosp}\n타겟국가: ${country}\n타겟: ${target}\n시술: ${procs.join(', ')}\n목표: ${goals.join(', ')}\n${tone?`톤앤매너: ${tone}`:''}\n\n완성된 카피를 작성해주세요.`;
  try {
    const r = await callAPI(sys, prompt);
    document.getElementById('rs-adcopy-body').textContent = r;
  } catch(e) { document.getElementById('rs-adcopy-body').textContent = '⚠️ 오류: '+e.message; }
  finally { setLoad('br-adcopy','rs-adcopy',false); document.getElementById('rs-adcopy').scrollIntoView({behavior:'smooth',block:'start'}); }
}

async function runReport() {
  const week = document.getElementById('r-week').value||'이번 주';
  const author = document.getElementById('r-author').value||'담당자';
  const d = {t1c:document.getElementById('r-t1c').value, t1v:document.getElementById('r-t1v').value, t2c:document.getElementById('r-t2c').value, t2v:document.getElementById('r-t2v').value, t3c:document.getElementById('r-t3c').value, t3v:document.getElementById('r-t3v').value, spend:document.getElementById('r-spend').value, roas:document.getElementById('r-roas').value, toph:document.getElementById('r-toph').value, topc:document.getElementById('r-topc').value, issues:document.getElementById('r-issues').value, plan:document.getElementById('r-plan').value};
  setLoad('br-report','rs-report',true);
  const sys = `당신은 CYL Marketing 경영진 보고 전문 AI입니다. 주간 성과 데이터를 받아 대표님 보고용 요약 보고서를 작성합니다. Executive Summary를 먼저 작성하고, 팀별 실적·광고성과·이슈·다음주 계획 순으로 간결하게 작성하세요.`;
  const prompt = `${week} 주간 성과 보고서 작성. 작성자: ${author}\n\n[팀별 상담]\n해외1팀: 상담 ${d.t1c||'-'} / 내원 ${d.t1v||'-'}\n해외2팀: 상담 ${d.t2c||'-'} / 내원 ${d.t2v||'-'}\n해외3팀: 상담 ${d.t3c||'-'} / 내원 ${d.t3v||'-'}\n\n[광고성과]\n집행액: ${d.spend||'-'} / ROAS: ${d.roas||'-'}\n최고성과 병원: ${d.toph||'-'} / 주요 국가: ${d.topc||'-'}\n\n[이슈] ${d.issues||'없음'}\n[다음주 계획] ${d.plan||'-'}`;
  try {
    const r = await callAPI(sys, prompt);
    document.getElementById('rs-report-body').textContent = r;
  } catch(e) { document.getElementById('rs-report-body').textContent = '⚠️ 오류: '+e.message; }
  finally { setLoad('br-report','rs-report',false); document.getElementById('rs-report').scrollIntoView({behavior:'smooth',block:'start'}); }
}

async function runTask() {
  const from = document.getElementById('t-from').value;
  const to = document.getElementById('t-to').value;
  const hosp = document.getElementById('t-hosp').value;
  const ddl = document.getElementById('t-ddl').value;
  const types = getTags('tg-ttype');
  const content = document.getElementById('t-content').value;
  const done = document.getElementById('t-done').value;
  if (!content) { toast('업무 내용을 입력해 주세요'); return; }
  setLoad('br-task','rs-task',true);
  const num = 'CYL-'+Date.now().toString().slice(-6);
  const today = new Date().toLocaleDateString('ko-KR');
  const sys = `당신은 CYL Marketing 업무 관리 AI입니다. 팀간 업무지시서를 표준 양식으로 명확하고 구체적으로 작성합니다. 담당자가 바로 실행 가능한 수준으로 작성하고, 검토 승인 흐름(요청자→수신팀→팀장→최종승인)을 포함하세요.`;
  const prompt = `문서번호: ${num}\n작성일: ${today}\n요청팀: ${from}\n수신팀: ${to}\n담당병원: ${hosp}\n마감: ${ddl||'미정'}\n업무분류: ${types.join(', ')}\n\n[업무내용]\n${content}\n\n[완료기준]\n${done||'팀장 검토 후 완료'}`;
  try {
    const r = await callAPI(sys, prompt);
    document.getElementById('rs-task-body').textContent = r;
  } catch(e) { document.getElementById('rs-task-body').textContent = '⚠️ 오류: '+e.message; }
  finally { setLoad('br-task','rs-task',false); document.getElementById('rs-task').scrollIntoView({behavior:'smooth',block:'start'}); }
}

// ── CHAT ──
const AGENTS = {
  overseas:{name:'해외사업부 AI',icon:'🌏',color:'var(--teal-dim)',
    quick:['태국어 상담 DM','베트남어 포스팅','러시아 에이전시 이메일','상담회 체크리스트','인도네시아 안내문'],
    sug:['태국어로 코 수술 상담 문자 작성','더프라이드 베트남 인스타 캡션 3개','방콕 상담회 준비 체크리스트','러시아 파트너 에이전시 영어 이메일'],
    sys:`당신은 CYL Marketing 해외사업부 AI입니다. 담당병원: 더프라이드/로그/무드온/리스토리/신상/아이루미/노트/유니/바이브. 담당국가: 태국/베트남/러시아/인도네시아/영어권/중화권/일본. 다국어 상담, 콘텐츠 기획, 에이전시 관리 전문. 실무에서 바로 쓸 수 있는 완성도로 작성.`},
  marketing:{name:'마케팅팀 AI',icon:'📊',color:'var(--amber-dim)',
    quick:['메타 광고 카피 A/B','ROAS 분석','타겟 전략','주간 보고서','CPC 최적화'],
    sug:['더프라이드 태국 눈수술 메타 광고 카피 2개','주간 광고 성과 분석 방법','인도네시아 코수술 타겟 오디언스 전략','ROAS 개선 방법 알려줘'],
    sys:`당신은 CYL Marketing 퍼포먼스 마케팅 AI. 메타 광고 전문. ROAS/CPC/CTR/CPM 분석, 광고 카피, A/B 테스트, 국가별 타겟 전략 전문.`},
  media:{name:'미디어팀 AI',icon:'🎨',color:'var(--coral-dim)',
    quick:['포스팅 기획안','디자인 브리프','촬영 기획서','영상 콘셉트','해시태그 세트'],
    sug:['리스토리 베트남 인스타 피드 포스팅 3개 컨셉','아이루미 태국 광고 배너 디자인 브리프','신상 원장 인터뷰 촬영 기획서','무드온 틱톡 영상 콘셉트 3개'],
    sys:`당신은 CYL Marketing 미디어·콘텐츠 기획 AI. SNS 포스팅 기획, 광고 크리에이티브 브리프, 촬영 기획서, 영상 콘셉트 전문. 디자이너가 바로 작업 가능한 구체적 브리프 제공.`},
  executive:{name:'경영진 AI',icon:'👔',color:'rgba(180,80,200,.12)',
    quick:['주간 보고서 초안','거래처 제안서','상담회 전략','1000억 프로젝트','신규 병원 계약'],
    sug:['이번 주 해외사업부 종합 보고서','신규 성형외과 에이전시 계약 제안서','2026 8개국 사업 확장 전략','1000억 건물 인수 후 입점 운영 방안'],
    sys:`당신은 CYL Global 경영진 전용 전략 AI. 목표: 1000억 건물 인수·계약병원 입점. 경영 보고서, 거래처 제안서, 사업 전략 전문. Executive Summary 먼저, 간결하고 전략적으로.`},
  concierge:{name:'컨시어지 AI',icon:'🚗',color:'var(--blue-dim)',
    quick:['픽업 요청서','공항 픽업 안내','병원↔호텔','VIP 일정','배차 기준'],
    sug:['내일 오후 3시 인천공항 VIP 픽업 요청서','태국 환자 3명 병원→호텔 이동 안내','이번 주 컨시어지 일정표 정리','마이바흐 vs 스프린터 배차 기준'],
    sys:`당신은 CYL Marketing 컨시어지팀 AI. 황승호(마이바흐 GLS600)·김정호(벤츠 스프린터 519). 픽업 요청서, 이동 안내, VIP 일정 관리 전문. 최소 48시간 전 요청 원칙.`}
};

let curAgent = 'overseas';
let msgs = {}; Object.keys(AGENTS).forEach(k=>msgs[k]=[]);
let busy = false;

function setAgent(id) {
  curAgent = id;
  const a = AGENTS[id];
  ['nb-chat1','nb-chat2','nb-chat3','nb-chat4','nb-chat5'].forEach(b=>document.getElementById(b)?.classList.remove('active'));
  const map={overseas:'nb-chat1',marketing:'nb-chat2',media:'nb-chat3',executive:'nb-chat4',concierge:'nb-chat5'};
  document.getElementById(map[id])?.classList.add('active');
  document.getElementById('th-icon').textContent=a.icon;
  document.getElementById('th-icon').style.background=a.color;
  document.getElementById('th-title').textContent=a.name;
  document.getElementById('th-desc').textContent='팀별 전용 AI와 자유롭게 대화하세요';
  // quick bar
  document.getElementById('qbar').innerHTML=a.quick.map(q=>`<button class="qbtn" onclick="inQ('${q.replace(/'/g,"\\'")}')"> ${q}</button>`).join('');
  // welcome
  document.getElementById('w-icon').textContent=a.icon;
  document.getElementById('w-icon').style.background=a.color;
  document.getElementById('w-title').textContent=a.name;
  document.getElementById('sug-grid').innerHTML=a.sug.map(s=>`<div class="sug-card" onclick="useSug('${s.replace(/'/g,"\\'")}')"> ${s}</div>`).join('');
  renderChat();
}

function inQ(t){const i=document.getElementById('msg-inp');i.value=t;i.focus();ar(i)}
function useSug(t){document.getElementById('msg-inp').value=t;sendMsg()}

function renderChat(){
  const area=document.getElementById('chat-area');
  area.querySelectorAll('.msg').forEach(m=>m.remove());
  const welcome=document.getElementById('welcome');
  const ms=msgs[curAgent];
  if(!ms.length){welcome.style.display='flex';return}
  welcome.style.display='none';
  const a=AGENTS[curAgent];
  ms.forEach(m=>{
    const d=document.createElement('div');
    d.className='msg '+(m.role==='user'?'user':'ai');
    if(m.role==='user'){
      d.innerHTML=`<div><div class="m-bub">${esc(m.content)}</div><div class="m-time">${m.t}</div></div><div class="m-av">나</div>`;
    } else {
      d.innerHTML=`<div class="m-av" style="background:${a.color};font-size:14px">${a.icon}</div><div><div class="m-bub">${fmt(m.content)}</div><div class="m-time">${a.name} · ${m.t}</div></div>`;
    }
    area.appendChild(d);
  });
  area.scrollTop=area.scrollHeight;
}

function fmt(t){return t.replace(/\*\*(.*?)\*\*/g,'<strong>$1</strong>').replace(/\n/g,'<br>')}
function esc(t){return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/\n/g,'<br>')}
function ts(){return new Date().toLocaleTimeString('ko-KR',{hour:'2-digit',minute:'2-digit'})}

async function sendMsg(){
  const inp=document.getElementById('msg-inp');
  const txt=inp.value.trim();
  if(!txt||busy)return;
  inp.value=''; ar(inp); busy=true;
  document.getElementById('send-btn').disabled=true;
  msgs[curAgent].push({role:'user',content:txt,t:ts()});
  renderChat();
  const area=document.getElementById('chat-area');
  const a=AGENTS[curAgent];
  const ty=document.createElement('div');
  ty.className='msg ai'; ty.id='ty';
  ty.innerHTML=`<div class="m-av" style="background:${a.color};font-size:14px">${a.icon}</div><div class="m-bub"><div class="dots"><span></span><span></span><span></span></div></div>`;
  area.appendChild(ty); area.scrollTop=area.scrollHeight;
  try {
    const history=msgs[curAgent].slice(0,-1).map(m=>({role:m.role==='user'?'user':'assistant',content:m.content}));
    const r=await callAPI(a.sys,txt,history);
    document.getElementById('ty')?.remove();
    msgs[curAgent].push({role:'assistant',content:r,t:ts()});
    renderChat();
  } catch(e){
    document.getElementById('ty')?.remove();
    msgs[curAgent].push({role:'assistant',content:'⚠️ 오류: '+e.message,t:ts()});
    renderChat();
  }
  busy=false; document.getElementById('send-btn').disabled=false;
}

function hk(e){if(e.key==='Enter'&&!e.shiftKey){e.preventDefault();sendMsg()}}
function ar(el){el.style.height='auto';el.style.height=Math.min(el.scrollHeight,110)+'px'}

// INIT
show('script');
setAgent('overseas');
</script>
</body>
</html>
