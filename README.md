<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#0a0a0a">
<title>MVBD+</title>
<style>
:root{--bg:#0a0a0a;--card:#161616;--tx:#f2f2f2;--mu:#9a9a9a;--ac:#3ddc84;--yl:#ffd60a;--bd:#2a2a2a;--gd:#f5c542;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px)}
@media(prefers-color-scheme:light){:root:not([data-theme="dark"]){--bg:#f5f5f5;--card:#fff;--tx:#111;--mu:#666;--bd:#ddd}}
:root[data-theme="light"]{--bg:#f5f5f5;--card:#fff;--tx:#111;--mu:#666;--bd:#ddd}
:root[data-theme="dark"]{--bg:#0a0a0a;--card:#161616;--tx:#f2f2f2;--mu:#9a9a9a;--bd:#2a2a2a}
*{box-sizing:border-box;margin:0}
html{scroll-padding-top:env(safe-area-inset-top,0px);height:100%}
body{background:var(--bg);color:var(--tx);font-family:system-ui,-apple-system,"Segoe UI",sans-serif;min-height:100%;overflow-x:hidden;font-size:18px}
body.lock{overflow:hidden}
.hide{display:none!important}
@keyframes up{from{opacity:0;transform:translateY(26px)}to{opacity:1;transform:none}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-14px)}}
@keyframes glow{0%,100%{filter:drop-shadow(0 0 8px #3ddc8488)}50%{filter:drop-shadow(0 0 28px #3ddc84)}}
@keyframes shine{to{background-position:200% 0}}
@keyframes pulse{0%{box-shadow:0 0 0 0 #3ddc84aa}100%{box-shadow:0 0 0 30px #3ddc8400}}
@keyframes orb{0%,100%{transform:translate(0,0) scale(1)}50%{transform:translate(40px,-50px) scale(1.25)}}
@keyframes pop{0%{transform:scale(.6)}60%{transform:scale(1.25)}100%{transform:scale(1)}}
@keyframes fade{from{opacity:0}to{opacity:1}}
@keyframes sh{0%,100%{background-position:0 0,0% 50%}50%{background-position:0 0,100% 50%}}
@keyframes bar{from{width:0}to{width:50%}}
@keyframes slideU{from{opacity:0;transform:translateY(60px)}to{opacity:1;transform:none}}
@keyframes slideD{from{opacity:0;transform:translateY(-60px)}to{opacity:1;transform:none}}

#landing{position:relative;overflow:hidden;min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:24px;background:radial-gradient(circle at 50% 30%,#1b3a2a,#0a0a0a 70%);color:#f2f2f2}
.orb{position:absolute;border-radius:50%;filter:blur(60px);opacity:.5;animation:orb 9s ease-in-out infinite;pointer-events:none}
.o1{width:260px;height:260px;background:#3ddc84;top:-60px;left:-80px}
.o2{width:300px;height:300px;background:#f5c542;bottom:-100px;right:-90px;animation-delay:-3s;opacity:.35}
.o3{width:200px;height:200px;background:#7a4dff;top:40%;right:-70px;animation-delay:-6s;opacity:.35}
#landing>*:not(.orb){position:relative;z-index:2;animation:up .9s both}
.bigLogo{width:min(85vw,380px);max-height:260px;object-fit:contain;margin-bottom:10px;border-radius:18px;animation:up .9s both,float 4s ease-in-out .9s infinite,glow 3s ease-in-out infinite!important}
#lgL svg{width:min(80vw,360px);height:auto;color:#f2f2f2;display:block;margin:0 auto 10px;animation:float 4s ease-in-out infinite,glow 3s infinite}
#landing h1{font-size:3.6rem;letter-spacing:3px;animation-delay:.2s!important}
#landing p{color:#b5b5b5;margin:10px 0 14px;font-size:1.25rem;animation-delay:.4s!important}
.chips{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-bottom:30px;animation-delay:.55s!important}
.chips span{border:1px solid #3ddc8466;background:#3ddc8414;padding:9px 18px;border-radius:24px;font-size:1.05rem}
.visit{background:linear-gradient(110deg,#3ddc84 30%,#b8ffd5 50%,#3ddc84 70%);background-size:200% 100%;color:#04200f;border:0;font-size:1.8rem;font-weight:800;padding:24px 76px;border-radius:60px;cursor:pointer;animation:up .9s .7s both,shine 2.5s linear infinite,pulse 1.8s infinite!important}
.visit:active{transform:scale(.95)}

header{position:sticky;top:env(safe-area-inset-top,0px);z-index:20;display:flex;align-items:center;gap:10px;padding:12px;background:var(--bg);background:color-mix(in srgb,var(--bg) 85%,transparent);backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);border-bottom:1px solid var(--bd)}
#logoBox{flex:none;cursor:pointer;display:flex;align-items:center;max-width:30vw;border-radius:12px}
#logoImg{height:84px;max-width:30vw;object-fit:contain;border-radius:12px;display:block}
#logoTx svg{height:80px;width:auto;max-width:30vw;color:var(--tx);display:block}
.search{flex:1;min-width:0;display:flex;align-items:center;gap:8px;background:var(--card);border:1px solid var(--bd);border-radius:34px;padding:0 18px;height:64px;font-size:1.4rem;transition:.25s}
.search:focus-within{border-color:var(--ac);box-shadow:0 0 0 3px #3ddc8433}
.search input{flex:1;min-width:0;background:none;border:0;outline:0;color:var(--tx);font-size:1.15rem}
.ib{width:64px;height:64px;flex:none;border-radius:50%;border:1px solid var(--bd);background:var(--card);color:var(--tx);font-size:2rem;line-height:1;cursor:pointer;transition:.25s}
.ib:active{border-color:var(--ac);transform:scale(.92)}

main{padding:14px 14px 24px;max-width:960px;margin:auto}
main>div{animation:fade .5s both}
.hero{height:250px;border-radius:20px;display:flex;align-items:flex-end;padding:20px;background:linear-gradient(transparent 30%,#000b),linear-gradient(135deg,#1e4d36,#0e1f2e,#3b1f5e);background-size:100% 100%,300% 300%;box-shadow:0 0 0 1px #f5c54244,0 12px 40px #0008;color:#fff;animation:up .7s backwards,sh 8s ease-in-out infinite}
.hero h2{font-size:1.9rem}.hero small{color:#ddd;font-size:1.05rem}
h3.t{text-align:center;color:#ff7a2f;letter-spacing:4px;margin:26px 0 4px;font-size:1.5rem}
.cnt{text-align:center;color:var(--ac);font-weight:700;margin-bottom:16px;font-size:1.15rem}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:14px}
.mv{aspect-ratio:2/3.1;border-radius:16px;padding:12px;display:flex;flex-direction:column;justify-content:flex-end;font-weight:700;font-size:1.1rem;position:relative;color:#fff;cursor:pointer;overflow:hidden;animation:up .6s backwards;transition:.25s}
.mv:active{transform:scale(.96)}
.mv em{font-style:normal;font-size:3.4rem;position:absolute;top:22%;left:50%;transform:translateX(-50%);opacity:.9;animation:float 4s ease-in-out infinite}
.mv span{position:absolute;top:8px;right:8px;background:#000a;border-radius:10px;padding:3px 9px;font-size:.9rem;color:var(--yl)}
.mv small{font-size:.95rem}
.rl .mv{aspect-ratio:9/16}

.box{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:24px;margin-top:10px}
.box h2{font-size:1.6rem}
.box p{color:var(--mu);line-height:1.8;margin-top:10px;font-size:1.1rem}
input.f,textarea.f{width:100%;background:var(--bg);border:1px solid var(--bd);color:var(--tx);border-radius:12px;padding:16px;margin:6px 0;font:inherit;font-size:1.15rem}
.btn{background:var(--ac);color:#04200f;border:0;border-radius:12px;padding:16px 28px;font-weight:700;font-size:1.15rem;cursor:pointer;margin-top:6px;transition:.2s}
.btn:active{transform:scale(.96)}.btn.out{background:#ff453a;color:#fff}
.av{width:100px;height:100px;border-radius:50%;background:var(--ac);color:#04200f;font-size:2.8rem;font-weight:800;display:flex;align-items:center;justify-content:center;margin:0 auto 10px;animation:pop .6s}

footer{border-top:1px solid var(--bd);padding:26px 14px 140px;text-align:center;color:var(--mu);font-size:1.05rem}
footer h4{color:var(--tx);margin-bottom:14px;font-size:1.5rem}
.soc{display:flex;justify-content:center;flex-wrap:wrap;gap:12px;margin-bottom:16px}
.soc a{color:var(--tx);text-decoration:none;border:1px solid var(--bd);background:var(--card);padding:14px 22px;border-radius:26px;transition:.25s;display:flex;flex-direction:column;align-items:center;line-height:1.4;font-size:1.15rem;font-weight:600}
.soc a small{color:var(--ac);font-size:.95rem;font-weight:400}
.soc a:active{border-color:var(--ac);transform:scale(.96)}

nav{position:fixed;left:0;right:0;bottom:0;width:100%;display:flex;justify-content:center;background:var(--card);border-top:1px solid var(--bd);border-radius:24px 24px 0 0;padding:8px 4px calc(8px + env(safe-area-inset-bottom,0px));z-index:30;box-shadow:0 -6px 30px #0007}
nav button{--c:#3ddc84;flex:1;min-width:0;max-width:200px;position:relative;background:none;border:0;color:var(--mu);display:flex;flex-direction:column;align-items:center;gap:4px;font-size:1.05rem;font-weight:600;padding:12px 2px 10px;cursor:pointer;border-radius:18px;transition:.3s}
nav button i{font-style:normal;font-size:2.3rem;line-height:1;transition:.3s}
nav button[data-go=home]{--c:#3ddc84}nav button[data-go=anime]{--c:#ff5c8a}nav button[data-go=reels]{--c:#4dabff}nav button[data-go=subs]{--c:#f5c542}nav button[data-go=saved]{--c:#ffb020}nav button[data-go=profile]{--c:#b57aff}
nav button.on{color:var(--c);font-weight:800;background:color-mix(in srgb,var(--c) 16%,transparent)}
nav button.on i{animation:pop .5s;filter:drop-shadow(0 0 8px var(--c))}
nav button.on::before{content:"";position:absolute;top:-8px;left:25%;height:4px;border-radius:4px;background:var(--c);animation:bar .4s forwards;width:50%}

.mw{position:relative;flex:none}
.menu{position:absolute;right:0;top:74px;min-width:270px;max-width:80vw;background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:8px;z-index:40;box-shadow:0 8px 30px #0006;animation:up .25s}
.menu button{display:block;width:100%;text-align:left;background:none;border:0;color:var(--tx);padding:18px 16px;font-size:1.2rem;border-radius:10px;cursor:pointer}
.menu button:active{background:var(--bg)}
.note{text-align:center;color:var(--mu);padding:40px 0;font-size:1.15rem}
.plans{display:grid;gap:14px}
.plan{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:24px;text-align:center;animation:up .6s backwards}
.plan h3{font-size:1.5rem}
.plan.pop{border-color:var(--gd);box-shadow:0 0 30px #f5c54233}
.plan b{font-size:2.2rem;color:var(--gd)}.plan small{font-size:1rem;color:var(--mu)}
.plan p{color:var(--mu);margin:8px 0 12px;font-size:1.1rem}

#aiB{position:fixed;right:16px;bottom:calc(20px + env(safe-area-inset-bottom,0px));z-index:50;width:76px;height:76px;border-radius:50%;border:0;background:linear-gradient(135deg,#3ddc84,#1fa8ff);font-size:2.3rem;cursor:pointer;animation:pulse 2s infinite,float 3s ease-in-out infinite;box-shadow:0 6px 24px #0007}
body.inapp #aiB{bottom:calc(128px + env(safe-area-inset-bottom,0px))}
#aiP{position:fixed;right:10px;left:10px;max-width:460px;margin-left:auto;bottom:calc(100px + env(safe-area-inset-bottom,0px));height:min(78vh,640px);z-index:60;background:var(--card);color:var(--tx);border:1px solid var(--ac);border-radius:20px;display:flex;flex-direction:column;overflow:hidden;box-shadow:0 10px 50px #000a;animation:up .3s}
body.inapp #aiP{bottom:calc(210px + env(safe-area-inset-bottom,0px));height:min(66vh,600px)}
#aiH{padding:18px;background:linear-gradient(135deg,#3ddc84,#1fa8ff);color:#04200f;font-weight:800;font-size:1.3rem;display:flex;justify-content:space-between;align-items:center}
#aiH button{background:#0003;border:0;color:inherit;border-radius:50%;width:44px;height:44px;font-size:1.3rem;cursor:pointer;padding:0}
#aiM{flex:1;overflow-y:auto;padding:14px;display:flex;flex-direction:column;gap:10px}
.m{max-width:88%;padding:12px 16px;border-radius:16px;line-height:1.55;font-size:1.1rem;animation:up .3s;white-space:pre-line}
.m.b{background:var(--bg);border:1px solid var(--bd);align-self:flex-start}
.m.u{background:var(--ac);color:#04200f;align-self:flex-end}
#aiQ{display:flex;gap:8px;padding:0 12px 10px;overflow-x:auto}
#aiQ button{flex:none;background:none;border:1px solid var(--ac);color:var(--ac);border-radius:18px;padding:9px 16px;font-size:1rem;cursor:pointer}
#aiF{display:flex;gap:8px;padding:12px;border-top:1px solid var(--bd)}
#aiF input{flex:1;min-width:0;background:var(--bg);border:1px solid var(--bd);color:var(--tx);border-radius:24px;padding:15px 18px;font-size:1.1rem;outline:0}
#aiF button{background:var(--ac);border:0;border-radius:50%;width:54px;height:54px;font-size:1.5rem;cursor:pointer}

#rv{position:fixed;inset:0;z-index:100;background:#000;color:#fff;overflow:hidden;touch-action:none}
#rs{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:24px}
#rs.sU{animation:slideU .35s both}#rs.sD{animation:slideD .35s both}
#rs .big{font-size:9rem;animation:float 4s ease-in-out infinite}
#rs h2{font-size:2rem;margin-top:14px}
#rs .pt{margin-top:8px;background:#ff453a;border-radius:20px;padding:6px 18px;font-size:1.2rem;font-weight:700}
#rs small{display:block;margin-top:10px;font-size:1.1rem;color:#ffe9a8}
#rx{position:absolute;top:calc(14px + env(safe-area-inset-top,0px));left:14px;z-index:3;width:56px;height:56px;border-radius:50%;border:0;background:#000a;color:#fff;font-size:1.7rem;cursor:pointer}
#rc{position:absolute;top:calc(24px + env(safe-area-inset-top,0px));right:18px;z-index:3;font-size:1.1rem;background:#000a;padding:8px 14px;border-radius:20px}
#rn{position:absolute;right:12px;top:50%;transform:translateY(-50%);z-index:3;display:flex;flex-direction:column;gap:16px}
#rn button{width:60px;height:60px;border-radius:50%;border:0;background:#ffffff33;color:#fff;font-size:1.6rem;cursor:pointer}
#rp{position:absolute;left:0;right:0;bottom:0;z-index:3;display:flex;gap:8px;justify-content:center;flex-wrap:wrap;padding:14px 14px calc(22px + env(safe-area-inset-bottom,0px));background:linear-gradient(transparent,#000d)}
#rp button{background:#ffffff22;color:#fff;border:1px solid #ffffff55;border-radius:22px;padding:13px 18px;font-size:1.1rem;font-weight:700;cursor:pointer}
#rp button.on{background:var(--ac);color:#04200f;border-color:var(--ac)}

@media(prefers-reduced-motion:reduce){*{animation-duration:.01ms!important;animation-iteration-count:1!important}}

.o1,.o2,.o3{opacity:.22}
#hm h3.t,#ahm h3.t,#mhm h3.t,#shm h3.t{text-align:left;color:var(--tx);letter-spacing:2px;font-size:1.3rem;margin:26px 0 8px}
.hero{height:300px;align-items:center;justify-content:space-between;gap:12px;padding:22px;overflow:hidden}
.hero em{font-style:normal;font-size:7rem;animation:float 4s ease-in-out infinite}
.hero>div{text-align:right;max-width:64%}
.hero h2{font-size:clamp(1.6rem,7vw,2.6rem);line-height:1.1;word-break:break-word}
.hero p{margin:8px 0 12px;color:#e6e6e6}
.imdb{margin-left:10px;font-weight:700;color:var(--yl)}
.cw{position:relative}
.row{display:flex;gap:14px;overflow-x:auto;scroll-snap-type:x mandatory;scrollbar-width:none;padding:4px 2px 8px;cursor:grab}
.row::-webkit-scrollbar{display:none}
.row .mv{flex:none;width:158px;scroll-snap-align:start}
.th{margin-top:12px}
.th .mv{width:92px;font-size:.72rem;padding:6px;border-radius:10px}
.th .mv em{font-size:2.2rem}
.th .mv small,.th .mv span{display:none}
.th .mv.on{outline:3px solid var(--ac)}
.ban{margin:14px 0;border-radius:18px;padding:24px;text-align:center;background:linear-gradient(110deg,#f5c542,#ff7a2f,#7a4dff);color:#111;font-weight:800;font-size:1.6rem;cursor:pointer}
.ban small{display:block;font-size:1rem;font-weight:600;margin-top:4px}
.ar{position:absolute;top:50%;transform:translateY(-50%);z-index:5;width:46px;height:46px;border-radius:50%;border:0;background:#000b;color:#fff;font-size:1.8rem;cursor:pointer}
.ar.l{left:-6px}.ar.r{right:-6px}
.rev{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:22px 44px;text-align:center;min-height:170px;animation:fade .5s}
.stars span{cursor:pointer;color:var(--mu);font-size:2rem}.stars span.on{color:var(--yl)}
select.f{width:100%;background:var(--bg);border:1px solid var(--bd);color:var(--tx);border-radius:12px;padding:16px;margin:6px 0;font:inherit;font-size:1.15rem}
#aiB{touch-action:none;cursor:grab}
.tabs{display:flex;gap:8px;margin-bottom:14px}.tabs button{flex:1;padding:14px;border-radius:12px;border:1px solid var(--bd);background:var(--bg);color:var(--mu);font:inherit;font-weight:700;cursor:pointer}.tabs button.on{background:var(--ac);color:#04200f;border-color:var(--ac)}
.row{user-select:none;-webkit-user-select:none}
.th{padding:6px 6px 10px}
#toast{position:fixed;left:50%;bottom:150px;transform:translateX(-50%);background:#000d;color:#fff;padding:12px 22px;border-radius:24px;z-index:90;font-size:1rem;white-space:nowrap}
.menu{position:fixed;inset:0;min-width:0;max-width:none;border:0;border-radius:0;padding:calc(14px + env(safe-area-inset-top,0px)) 18px 24px;z-index:90;display:flex;flex-direction:column;gap:12px;overflow:auto;background:var(--bg);box-shadow:none}
.menu .mh{display:flex;justify-content:space-between;align-items:center;font-size:1.6rem;margin-bottom:10px}
.menu>button{background:var(--card);border:1px solid var(--bd);padding:22px 20px;font-size:1.3rem;border-radius:16px}
.menu .mh .ib{width:64px;padding:0;text-align:center;border:1px solid var(--bd);background:var(--card)}
.row{user-select:none;-webkit-user-select:none}
.menu{z-index:96;overscroll-behavior:contain}
#toast{z-index:200}
#rc{display:none}
.th .mv{width:190px;font-size:1.05rem;padding:12px;border-radius:16px;box-shadow:0 10px 28px #000a;border:1px solid #f5c54266}
.th .mv em{font-size:4rem}
.th .mv small,.th .mv span{display:block}
.th .mv.on{outline:none}
.cats{display:flex;gap:8px;overflow-x:auto;padding:4px 0 12px;scrollbar-width:none}
.cats::-webkit-scrollbar{display:none}
.cats button{flex:none;padding:12px 18px;border-radius:22px;border:1px solid var(--bd);background:var(--card);color:var(--tx);font:inherit;font-weight:700;cursor:pointer}
.cats button.on{background:var(--ac);color:#04200f;border-color:var(--ac)}
#md{position:fixed;inset:0;z-index:95;background:var(--bg);overflow:auto;overscroll-behavior:contain}
#mdh{height:46vh;min-height:280px;display:flex;align-items:center;justify-content:center;font-size:8rem}
#mdx{position:absolute;top:calc(14px + env(safe-area-inset-top,0px));left:14px;z-index:2;width:56px;height:56px;border-radius:50%;border:0;background:#000a;color:#fff;font-size:1.7rem;cursor:pointer}
.mdb{padding:20px;max-width:760px;margin:0 auto}
.mdb h2{font-size:2rem;margin-bottom:8px}
.mdb p{color:var(--mu);margin:6px 0;line-height:1.7}
.mdb .btn{width:100%;margin-top:16px;font-size:1.3rem;padding:18px}
.gt{display:inline-block;margin:6px 6px 0 0;padding:6px 14px;border-radius:14px;background:var(--card);border:1px solid var(--bd);font-size:.95rem;color:var(--tx)}
.th{scroll-snap-type:none}.th .mv{scroll-snap-align:none}
.cats{flex-wrap:wrap;overflow:visible;gap:6px;padding:4px 0 12px}
.cats button{padding:6px 12px;font-size:.78rem;font-weight:600;border-radius:14px}
#rn,#rp{display:none!important}
.feat{background:none;border-radius:0;padding:0;margin-top:6px}
.pill{display:inline-block;background:#1f5a3f;color:#6ee79a;border-radius:20px;padding:8px 16px;font-weight:800;font-size:.8rem;letter-spacing:1.5px}
.fimg{position:relative;height:230px;border-radius:22px;margin:12px 0;display:flex;align-items:center;justify-content:center;overflow:hidden;cursor:pointer}
.fimg em{font-style:normal;font-size:6.5rem;animation:float 4s ease-in-out infinite}
.fimg b{position:absolute;left:14px;bottom:14px;background:#000a;color:#fff;border-radius:20px;padding:8px 14px;font-size:.95rem}
.feat h2{font-size:1.7rem;color:var(--tx);margin:6px 0}
.feat p{color:var(--mu);margin:0 0 14px}
.fb{display:flex;gap:10px}
.fb button{border:0;border-radius:18px;padding:12px 20px;font:inherit;font-weight:700;cursor:pointer}
.fb .b1{background:#1f5a3f;color:#6ee79a}.fb .b2{background:var(--card);color:var(--tx);border:1px solid var(--bd)}
#hm .t2,#ahm .t2,#mhm .t2,#shm .t2{font-size:1.5rem;margin:24px 0 10px;color:var(--tx)}
.tw{flex:none;width:calc((100% - 28px)/3)}
.th .mv{width:100%;font-size:.72rem;padding:8px;border-radius:18px}
.th .mv em{font-size:2.6rem}
.tl{display:block;margin-top:8px;color:var(--mu);font-size:.9rem}
@media(min-width:700px){.th .mv{font-size:1rem}.th .mv em{font-size:4rem}}
.cwc{display:flex;align-items:center;gap:14px;background:var(--card);border:1px solid var(--bd);border-radius:22px;padding:14px;cursor:pointer}
.cwp{flex:none;width:76px;height:96px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:2.6rem;background:var(--bg)}
.cwi{flex:1;min-width:0}
.cwi b{display:block;font-size:1.25rem}
.cwi small{display:block;color:var(--mu);margin:4px 0 10px}
.bar{height:6px;border-radius:4px;background:var(--bd)}.bar i{display:block;height:100%;border-radius:4px;background:var(--ac)}
.pl{flex:none;width:48px;height:48px;border-radius:50%;border:0;background:var(--tx);color:var(--bg);font-size:1.2rem;cursor:pointer}
.row,.row.th{scroll-snap-type:none!important}
header{flex-wrap:nowrap;gap:8px;padding:10px}
#logoBox{order:0;flex:none;max-width:26vw}
#logoImg{height:56px;max-width:26vw}
#logoTx svg{height:56px;max-width:26vw}
.mw{order:0}
.search{order:0;flex:1 1 0;min-width:0;height:52px;padding:0 12px;font-size:1.1rem}
.search input{font-size:1rem}
#dots{width:52px;height:52px;font-size:1.7rem;display:flex;align-items:center;justify-content:center;padding:0}
#mlg .mv,#grid .mv{animation:none}
#sg .mv{animation:none!important}
.rev.rvbox{text-align:left;padding:20px;min-height:0;background:linear-gradient(145deg,var(--card),color-mix(in srgb,var(--ac) 9%,var(--card)));border:1px solid color-mix(in srgb,var(--ac) 35%,var(--bd));box-shadow:0 10px 30px #0004;position:relative;overflow:hidden}
.rvc{animation:fade .5s}
.rvt{display:flex;align-items:center;gap:12px}
.rva{flex:none;width:52px;height:52px;border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:1.5rem;box-shadow:0 0 0 3px color-mix(in srgb,var(--ac) 45%,transparent)}
.rvn{flex:1;min-width:0}.rvn b{display:block;font-size:1.15rem}.rvn small{color:var(--ac);font-size:.85rem;font-weight:700}
.rvq{font-size:3.2rem;line-height:.6;color:var(--ac);opacity:.35;align-self:flex-start;padding-top:12px}
.rvc p{margin:14px 0;line-height:1.7;font-size:1.1rem;color:var(--tx)}
.rvf{display:flex;justify-content:space-between;align-items:center;gap:8px;flex-wrap:wrap}
.rvs{color:var(--yl);font-size:1.4rem;letter-spacing:2px}
.rvm{background:var(--bg);border:1px solid var(--bd);border-radius:14px;padding:5px 12px;font-size:.9rem;color:var(--mu)}
.rvd{display:flex;justify-content:center;gap:8px;margin-top:16px}
.rvd span{width:9px;height:9px;border-radius:5px;background:var(--bd);cursor:pointer;transition:.3s}.rvd span.on{width:26px;background:var(--ac)}
#toast{white-space:normal;max-width:86vw;text-align:center}
.act{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-top:12px}
.act button{padding:14px 6px;border-radius:14px;border:1px solid var(--bd);background:var(--card);color:var(--tx);font:inherit;font-weight:700;font-size:1rem;cursor:pointer}
.act button.on{border-color:var(--ac);color:var(--ac)}
.dot{position:absolute;top:6px;right:26%;width:12px;height:12px;border-radius:50%;background:#ff453a;border:2px solid var(--card)}
.avt{border-radius:50%;object-fit:cover;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;border:4px solid var(--card);margin:-52px auto 0;position:relative;box-shadow:0 6px 20px #0005}
.pvA .avt{margin:0}
.err{color:#ff453a;margin:6px 0;min-height:1em}
.pfh{background:var(--card);border:1px solid var(--bd);border-radius:24px;padding:0 18px 20px;text-align:center;overflow:hidden;animation:up .5s}
.pfc{height:96px;margin:0 -18px;background:linear-gradient(120deg,#1e4d36,#0e1f2e,#3b1f5e)}
.pfh h2{font-size:1.6rem;margin-top:10px}.pfh .un{color:var(--mu)}.pfh p{color:var(--mu);margin:8px 0;line-height:1.6}
.plb{display:inline-block;margin:8px 0;padding:5px 14px;border-radius:14px;background:var(--bg);border:1px solid var(--bd);font-weight:700;font-size:.9rem}
.plb.gold{color:var(--gd);border-color:var(--gd)}
.pfb{display:flex;gap:10px;margin-top:10px}.pfb .btn{flex:1;margin:0;padding:14px 8px}
.btn.pr{background:linear-gradient(110deg,#f5c542,#ff7a2f);color:#111}
.pfm{display:grid;gap:10px;margin-top:14px;grid-template-columns:1fr}
.pr2{display:flex;align-items:center;gap:14px;background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:18px;color:var(--tx);font:inherit;font-size:1.15rem;font-weight:600;cursor:pointer;text-align:left;transition:.2s}
.pr2:active{transform:scale(.98);border-color:var(--ac)}
.pr2 i{font-style:normal;font-size:1.6rem}.pr2 span{flex:1}
.pr2 em{font-style:normal;background:var(--ac);color:#04200f;border-radius:12px;padding:2px 10px;font-size:.9rem;font-weight:800}
.pr2 b{color:var(--mu);font-size:1.5rem}
.pph{display:flex;align-items:center;gap:12px;margin-bottom:14px}.pph h2{font-size:1.5rem}
.ib.sm{width:48px;height:48px;font-size:1.4rem}
.il{display:grid;gap:10px;grid-template-columns:repeat(auto-fill,minmax(min(100%,320px),1fr))}
.ir{display:flex;gap:12px;align-items:center;background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:10px;cursor:pointer}
.irp{flex:none;width:64px;height:88px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:2rem}
.iri{flex:1;min-width:0}.iri b{display:block;font-size:1.1rem;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}.iri small{display:block;color:var(--mu);margin:3px 0}
.rm{flex:none;width:40px;height:40px;border-radius:50%;border:1px solid var(--bd);background:var(--bg);color:var(--mu);cursor:pointer}
.nt{display:flex;gap:12px;background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:14px}
.nt.new{border-color:var(--ac);background:color-mix(in srgb,var(--ac) 8%,var(--card))}
.nti{font-size:1.6rem}.ntb p{color:var(--mu);margin:4px 0;line-height:1.5}.ntb small{color:var(--mu)}
.st{display:flex;justify-content:space-between;align-items:center;background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:16px 18px;font-size:1.1rem}
.sw{position:relative;width:54px;height:30px;flex:none}.sw input{opacity:0;width:100%;height:100%;position:absolute;margin:0;z-index:1;cursor:pointer}
.sw i{position:absolute;inset:0;background:var(--bd);border-radius:20px;transition:.25s}
.sw i::after{content:"";position:absolute;top:3px;left:3px;width:24px;height:24px;border-radius:50%;background:#fff;transition:.25s}
.sw input:checked+i{background:var(--ac)}.sw input:checked+i::after{transform:translateX(24px)}
.btn.sm2{padding:10px 16px;font-size:1rem;margin:0 0 12px;display:inline-block;cursor:pointer}
.pvA{display:flex;align-items:center;gap:16px;margin-bottom:12px}.pvb{display:flex;flex-direction:column;align-items:flex-start;gap:8px}.pvb .btn{margin:0}
.lb{display:block;margin-top:10px;font-weight:700}.meta{color:var(--mu);margin:10px 0}
@media(min-width:760px){.pfm{grid-template-columns:1fr 1fr}.pfc{height:130px}}

/* ===== v5 landing ===== */
#landing{display:block;min-height:100vh;padding:calc(18px + env(safe-area-inset-top,0px)) 18px 40px;text-align:left;background:#0d0d12;color:#f6f5ff}
.lhero{position:relative;overflow:hidden;border-radius:34px;padding:76px 28px 68px;background:radial-gradient(circle at 80% 14%,rgba(226,160,80,.62),transparent 34%),radial-gradient(circle at 68% 82%,rgba(195,50,112,.55),transparent 40%),linear-gradient(145deg,#2a1240,#262b66 55%,#131a3a)}
.leye{color:#f3c66b;font-weight:800;letter-spacing:.3em;font-size:.95rem}
.lh1{font-size:clamp(2.5rem,12vw,3.7rem);line-height:1.05;font-weight:800;letter-spacing:-.02em;margin:22px 0 26px;color:#f7f6ff}
.lpp{color:#d6d2e8;line-height:1.8;font-size:1.08rem;margin-bottom:34px}
.lbtn{display:inline-flex;align-items:center;gap:12px;background:#e9b845;color:#1a1203;border:0;border-radius:18px;padding:20px 34px;font-size:1.3rem;font-weight:800;cursor:pointer;font-family:inherit}
.lbtn:active{transform:scale(.96)}
.lcard{margin-top:20px;border-radius:28px;padding:40px 28px 44px;background:#1e1e26;border:1.5px solid #353541;cursor:pointer;transition:.2s}
.lcard:active{transform:scale(.98);border-color:#e9b845}
.lct{font-size:1.7rem;font-weight:800;color:#f7f6ff}
.lcd{margin-top:26px;font-size:1.12rem;color:#9d9da7}
/* menu */
.mrow{display:flex;justify-content:space-between;align-items:center;background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:20px;font-size:1.3rem}
/* like badge */
.mv .lk{position:absolute;top:8px;left:8px;background:#000a;border-radius:10px;padding:3px 9px;font-size:.85rem;color:#ff6b81;font-style:normal;font-weight:700}
.th .mv .lk{display:block}
/* reviews on detail */
.mrh{font-size:1.4rem;margin:26px 0 4px}
.mrf{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:16px;margin:10px 0}
.mrf .stars{margin-bottom:6px}
.mri{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:14px;margin:10px 0}
.mri .top{display:flex;align-items:center;gap:10px}
.mri .av2{flex:none;width:38px;height:38px;border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800}
.mri b{display:block}.mri small{color:var(--mu)}
.mri .st5{color:var(--yl);letter-spacing:2px;margin-left:auto}
.mri p{color:var(--tx);margin:10px 0 4px}
.mri .mrd{background:none;border:0;color:#ff453a;font:inherit;font-size:.9rem;cursor:pointer;padding:0}
.rvd{flex-wrap:wrap}
/* AI button: premium icon, hidden while scrolling */
#aiB{padding:0;background:none;overflow:visible;border-radius:50%;box-shadow:0 8px 26px #1fa8ff66,0 4px 14px #0009;transition:opacity .25s,visibility .25s}
#aiB img{width:100%;height:100%;display:block;border-radius:50%;pointer-events:none;-webkit-user-drag:none;user-select:none}
#aiB.scr{opacity:0;visibility:hidden;pointer-events:none}
#aiB{width:54px;height:54px}
.aiHi{width:38px;height:38px;border-radius:50%;box-shadow:0 2px 8px #0005}
/* smaller bottom nav */
nav{padding:5px 4px calc(5px + env(safe-area-inset-bottom,0px));border-radius:18px 18px 0 0}
nav button{gap:2px;font-size:.8rem;padding:7px 2px 6px;border-radius:14px}
nav button i{font-size:1.5rem}
nav button.on::before{top:-5px;height:3px}
footer{padding-bottom:100px}
/* menu: half-screen right panel */
.menu{inset:0 0 0 auto;width:50vw;min-width:250px;max-width:420px;border-left:1px solid var(--bd);border-radius:20px 0 0 20px;padding:calc(12px + env(safe-area-inset-top,0px)) 12px calc(16px + env(safe-area-inset-bottom,0px));gap:10px;box-shadow:-8px 0 30px #0007;background:var(--card)}
.menu .mh{font-size:1.3rem;margin-bottom:4px}
.menu .mh .ib{width:46px;height:46px;font-size:1.3rem}
.menu>button{padding:16px 14px;font-size:1.05rem;border-radius:14px;background:var(--bg)}
/* smaller bottom nav + blur when menu open */
nav{padding:3px 4px calc(3px + env(safe-area-inset-bottom,0px));border-radius:16px 16px 0 0;transition:filter .25s,opacity .25s}
nav button{gap:1px;font-size:.7rem;padding:4px 2px 3px;border-radius:12px}
nav button i{font-size:1.25rem}
nav button.on::before{top:-3px;height:3px}
body:has(#menu:not(.hide)) nav{filter:blur(5px);opacity:.45;pointer-events:none}
body.menuopen nav{filter:blur(5px);opacity:.45;pointer-events:none}
body.aiopen nav{filter:brightness(.45);opacity:.6;pointer-events:none}
body.menuopen,body.aiopen,html:has(body.menuopen),html:has(body.aiopen){overflow:hidden}
.menu{overscroll-behavior:contain}
/* AI Moderator: works on every page, also above the 3-dot menu */
body.inapp #aiB{bottom:calc(74px + env(safe-area-inset-bottom,0px));z-index:120}
body.inapp #aiP{bottom:calc(150px + env(safe-area-inset-bottom,0px));height:min(70vh,600px);z-index:121}
.sw.on i{background:var(--ac)}.sw.on i::after{transform:translateX(24px)}
/* ===== Premium plans: bright animated look ===== */
@keyframes bdr{to{background-position:0 0,300% 0}}
@keyframes glowG{0%,100%{box-shadow:0 0 12px #f5c54233}50%{box-shadow:0 0 34px #f5c542aa}}
@keyframes swp{0%{left:-70%}55%,100%{left:140%}}
@keyframes tw{0%,100%{opacity:.25;transform:scale(.7) rotate(0)}50%{opacity:1;transform:scale(1.25) rotate(20deg)}}
@keyframes txs{to{background-position:200% 0}}
.plan{position:relative;overflow:hidden;border:2px solid transparent;background:linear-gradient(var(--card),var(--card)) padding-box,linear-gradient(110deg,#f5c542,#fff6c9,#ff9f1c,#f5c542) border-box;background-size:100% 100%,300% 100%;animation:up .6s backwards,bdr 3.5s linear infinite,glowG 2.6s ease-in-out infinite}
.plan::after{content:"";position:absolute;top:0;left:-70%;width:40%;height:100%;background:linear-gradient(100deg,transparent,#ffffff55,transparent);transform:skewX(-20deg);animation:swp 3.6s ease-in-out infinite;pointer-events:none}
.plan.bsc{background:linear-gradient(var(--card),var(--card)) padding-box,linear-gradient(110deg,#9aa4b2,#ffffff,#6fb1ff,#9aa4b2) border-box;background-size:100% 100%,300% 100%}
.plan.pop{background:linear-gradient(var(--card),var(--card)) padding-box,linear-gradient(110deg,#3ddc84,#e9fff3,#1fa8ff,#3ddc84) border-box;background-size:100% 100%,300% 100%}
.plan.prm{background:linear-gradient(145deg,#33260a,#0d0a02 70%) padding-box,linear-gradient(110deg,#ffd60a,#fff8d0,#ff9f1c,#ffd60a) border-box;background-size:100% 100%,300% 100%;animation:up .6s backwards,bdr 2s linear infinite,glowG 1.8s ease-in-out infinite;padding:30px 24px}
.plan.prm::before{content:"✨";position:absolute;top:10px;right:14px;font-size:1.4rem;animation:tw 1.6s ease-in-out infinite}
.plan.prm h3{font-size:1.8rem;background:linear-gradient(90deg,#ffd60a,#fff,#ff9f1c,#ffd60a);background-size:200% 100%;-webkit-background-clip:text;background-clip:text;color:transparent;-webkit-text-fill-color:transparent;animation:txs 2.5s linear infinite}
.plan.prm b{color:#ffd60a;text-shadow:0 0 14px #ffd60a99}
.plan.prm p,.plan.prm small{color:#e8d9a0}
.plan.prm .btn{background:linear-gradient(90deg,#ffd60a,#fff3b0,#ff9f1c,#ffd60a);background-size:200% 100%;animation:shine 2s linear infinite;color:#1a1300;border:0;font-weight:800}
.ptl{background:linear-gradient(90deg,#ffd60a,#fff,#ff9f1c,#ffd60a);background-size:200% 100%;-webkit-background-clip:text;background-clip:text;color:transparent;-webkit-text-fill-color:transparent;animation:txs 2.5s linear infinite;filter:drop-shadow(0 0 8px #ffd60a66)}
/* ===== v7 changes ===== */
:root{--logo-bright:1.4}
#logoBox{animation:none}
#logoImg{filter:brightness(var(--logo-bright)) contrast(1.08) saturate(1.15)}
#logoTx svg{filter:brightness(var(--logo-bright)) saturate(1.2)}
nav button[data-go]{--c:#ffd60a}
nav button i{display:flex;align-items:center;justify-content:center}
nav button i svg{width:24px;height:24px;display:block}
nav button:not(.on) i{opacity:.8}
nav button.on i svg{filter:drop-shadow(0 0 5px #ffd60acc)}
.sh{display:flex;align-items:flex-end;justify-content:space-between;gap:10px}
.sh h3.t{margin:26px 0 8px}
.sa{background:none;border:0;color:var(--ac);font:inherit;font-size:.95rem;font-weight:700;cursor:pointer;padding:0 2px 10px;white-space:nowrap}
.row.rl .mv{width:128px}
.fl{display:flex;justify-content:center;flex-wrap:wrap;gap:10px;margin:4px 0 18px}
.fl button{background:none;border:0;border-bottom:1px solid var(--bd);color:var(--tx);font:inherit;font-size:1rem;font-weight:600;padding:6px 8px;cursor:pointer}
.fl button:active{color:var(--ac);border-color:var(--ac)}
#bell{position:relative;flex:none;width:52px;height:52px;font-size:1.5rem;padding:0;display:flex;align-items:center;justify-content:center;order:0}
/* AI panel: lower, opens on the same side as the AI button; button hides while panel is open */
body.inapp #aiP{bottom:calc(92px + env(safe-area-inset-bottom,0px));height:min(70vh,600px)}
body.aiopen #aiB{opacity:0;visibility:hidden;pointer-events:none}

/* ===== v8: Liquid Glass nav, notif page, AI panel fix ===== */
nav#nav{left:12px;right:12px;bottom:calc(12px + env(safe-area-inset-bottom,0px));width:auto;max-width:480px;margin:0 auto;padding:6px;gap:0;border-radius:36px;border:1px solid rgba(255,255,255,.22);background:rgba(40,40,46,.45);background:color-mix(in srgb,var(--card) 45%,transparent);-webkit-backdrop-filter:blur(26px) saturate(190%);backdrop-filter:blur(26px) saturate(190%);box-shadow:0 10px 34px rgba(0,0,0,.35),inset 0 1px 0 rgba(255,255,255,.3),inset 0 -1px 0 rgba(255,255,255,.06);touch-action:none;user-select:none;-webkit-user-select:none;-webkit-tap-highlight-color:transparent}
#lens{position:absolute;top:6px;bottom:6px;left:0;width:0;border-radius:30px;background:linear-gradient(180deg,rgba(255,255,255,.30),rgba(255,255,255,.08));border:1px solid rgba(255,255,255,.38);box-shadow:inset 0 1px 1px rgba(255,255,255,.6),0 4px 14px rgba(0,0,0,.25);-webkit-backdrop-filter:blur(8px) brightness(1.25);backdrop-filter:blur(8px) brightness(1.25);transition:transform .38s cubic-bezier(.3,1.3,.4,1),width .3s,opacity .2s;pointer-events:none;z-index:0;opacity:0}
nav.drag #lens{transition:width .2s,opacity .2s}
:root[data-theme="light"] #lens{background:linear-gradient(180deg,rgba(0,0,0,.10),rgba(0,0,0,.04));border-color:rgba(0,0,0,.14);box-shadow:inset 0 1px 1px rgba(255,255,255,.8),0 4px 14px rgba(0,0,0,.12)}
:root[data-theme="light"] nav#nav{border-color:rgba(0,0,0,.1);background:rgba(255,255,255,.55);background:color-mix(in srgb,var(--card) 55%,transparent)}
nav#nav button{position:relative;z-index:1;flex:1;max-width:none;padding:8px 2px 7px;font-size:.68rem;border-radius:30px;background:none!important;-webkit-tap-highlight-color:transparent}
nav#nav button.on::before{display:none}
nav#nav button.on{color:var(--tx)}
nav#nav button.hov{color:#ffd60a}
nav#nav button.hov i{transform:scale(1.15)}
nav#nav .dot{top:4px;right:22%}
body.inapp #aiB{bottom:calc(100px + env(safe-area-inset-bottom,0px))}
body.inapp #aiP{bottom:calc(170px + env(safe-area-inset-bottom,0px))}
#aiP{box-sizing:border-box;max-width:calc(100vw - 20px)}
#toast{bottom:calc(110px + env(safe-area-inset-bottom,0px))}
footer{padding-bottom:120px}
.nt.clk{cursor:pointer;align-items:flex-start;transition:.2s}.nt.clk:active{transform:scale(.98)}
.nt .ntb{flex:1;min-width:0}
.nt p.cl{display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.nt .ar2{align-self:center;color:var(--mu);font-size:1.6rem}
.nvw{background:var(--card);border:1px solid var(--bd);border-radius:20px;padding:22px;animation:up .4s}
.nvw .nvi{font-size:2.6rem}.nvw h2{font-size:1.5rem;margin:8px 0 4px}.nvw small{color:var(--mu)}
.nvw p{white-space:pre-line;line-height:1.8;font-size:1.1rem;color:var(--tx);margin:16px 0 4px;word-break:break-word}

/* ===== v9: white Liquid Glass (search, menu button, menu panel + options, nav) ===== */
:root{--g1:rgba(255,255,255,.24);--g2:rgba(255,255,255,.07);--gb:rgba(255,255,255,.36);--gh:rgba(255,255,255,.6);--gs:0 8px 22px rgba(0,0,0,.28);--b1:rgba(255,255,255,.16)}
:root[data-theme="light"]{--g1:rgba(255,255,255,.8);--g2:rgba(255,255,255,.42);--gb:rgba(255,255,255,.95);--gh:#fff;--gs:0 0 0 1px rgba(0,0,0,.07),0 8px 22px rgba(0,0,0,.12);--b1:rgba(255,255,255,.7)}
header{background:color-mix(in srgb,var(--bg) 50%,transparent);-webkit-backdrop-filter:none;backdrop-filter:none;border-bottom:0}
.search,#dots{background:linear-gradient(180deg,var(--g1),var(--g2));border:1px solid var(--gb);-webkit-backdrop-filter:blur(22px) saturate(180%);backdrop-filter:blur(22px) saturate(180%);box-shadow:inset 0 1px 1px var(--gh),inset 0 -1px 0 rgba(255,255,255,.1),var(--gs);color:var(--tx)}
.search:focus-within{border-color:var(--gh);box-shadow:inset 0 1px 1px var(--gh),0 0 0 3px rgba(255,255,255,.22),var(--gs)}
.search input::placeholder{color:var(--mu)}
#dots:active{border-color:var(--gh);transform:scale(.92)}
.menu{background:linear-gradient(180deg,var(--g1),var(--g2));-webkit-backdrop-filter:blur(30px) saturate(180%);backdrop-filter:blur(30px) saturate(180%);border-left:1px solid var(--gb);box-shadow:inset 1px 0 0 var(--gh),-10px 0 34px rgba(0,0,0,.35)}
.menu>button,.menu .mh .ib{background:var(--b1);border:1px solid var(--gb);color:var(--tx);box-shadow:inset 0 1px 1px var(--gh),inset 0 -1px 0 rgba(255,255,255,.08),0 4px 12px rgba(0,0,0,.12)}
.menu>button:active,.menu .mh .ib:active{background:var(--g1);border-color:var(--gh)}
nav#nav,:root[data-theme="light"] nav#nav{background:linear-gradient(180deg,var(--g1),var(--g2));border:1px solid var(--gb);-webkit-backdrop-filter:blur(26px) saturate(180%);backdrop-filter:blur(26px) saturate(180%);box-shadow:inset 0 1px 1px var(--gh),inset 0 -1px 0 rgba(255,255,255,.1),var(--gs)}
#lens{background:linear-gradient(180deg,rgba(255,255,255,.55),rgba(255,255,255,.22));border:1px solid rgba(255,255,255,.7);box-shadow:inset 0 1px 1px rgba(255,255,255,.9),0 4px 14px rgba(0,0,0,.22);-webkit-backdrop-filter:blur(6px);backdrop-filter:blur(6px)}
:root[data-theme="light"] #lens{background:linear-gradient(180deg,#fff,rgba(255,255,255,.7));border-color:#fff;box-shadow:inset 0 1px 1px #fff,0 0 0 1px rgba(0,0,0,.05),0 4px 14px rgba(0,0,0,.18)}
nav#nav button i,nav#nav button i svg,nav#nav button.on i,nav#nav button.on i svg{filter:none!important}
nav#nav button:not(.on) i{opacity:.75}
nav#nav button.hov{color:var(--tx)}
nav#nav button.hov i{transform:scale(1.1)}
body.aiopen nav#nav{filter:none;opacity:.5}

/* ===== v11: contact logos - auto-slide right to left, drag/swipe both ways, pause on touch ===== */
footer .soc{display:block;overflow-x:auto;overflow-y:hidden;scrollbar-width:none;-webkit-overflow-scrolling:touch;margin:0 -14px 18px;padding:8px 0 14px;cursor:grab;user-select:none;-webkit-user-select:none}
.soc::-webkit-scrollbar{display:none}
.soc.drag{cursor:grabbing}
.soc .trk{display:flex;width:max-content;margin:0 auto;padding:0 14px}
.soc .grp{display:flex;flex:none;gap:14px}
.soc a{flex:none;width:58px;height:58px;padding:0;border-radius:50%;border:1px solid rgba(255,255,255,.3);display:flex;align-items:center;justify-content:center;box-shadow:inset 0 1px 1px rgba(255,255,255,.4),0 6px 16px rgba(0,0,0,.25);-webkit-user-drag:none;-webkit-touch-callout:none}
.soc a:active{transform:scale(.92)}
.soc a svg{width:28px;height:28px;display:block;pointer-events:none}
.c-call{background:#34c759}.c-wa{background:#25D366}.c-tg{background:#2AABEE}.c-gm{background:#EA4335}.c-fb{background:#1877F2}.c-th,.c-x,.c-tt{background:#000}.c-yt{background:#f00}
.c-ig{background:radial-gradient(circle at 30% 107%,#fdf497 0,#fd5949 45%,#d6249f 60%,#285AEB 90%)}
#callSheet{position:fixed;inset:0;z-index:150;background:rgba(0,0,0,.5);display:flex;align-items:flex-end;justify-content:center;padding:16px 16px calc(16px + env(safe-area-inset-bottom,0px));animation:fade .2s}
.csb{width:100%;max-width:420px;border-radius:28px;padding:22px 20px 12px;text-align:center;background:var(--card);border:1px solid var(--bd);box-shadow:0 20px 50px rgba(0,0,0,.6);animation:up .3s}
.cst{font-weight:800;font-size:1.1rem;color:var(--mu)}
.csn{font-size:2.2rem;font-weight:800;letter-spacing:1px;margin:10px 0 16px;color:var(--tx);user-select:all;-webkit-user-select:all}
.csa{display:block;text-decoration:none;width:100%;margin:0 0 10px}
.csc{width:100%;background:var(--bg);color:var(--tx);border:1px solid var(--bd);margin:0 0 6px}
.csx{background:none;border:0;color:var(--mu);font:inherit;padding:12px;cursor:pointer}
#cs{position:fixed;left:12px;right:12px;bottom:calc(96px + env(safe-area-inset-bottom,0px));max-width:420px;margin:0 auto;z-index:210;padding:16px;border-radius:24px;text-align:center;color:var(--tx);background:linear-gradient(180deg,var(--g1),var(--g2));border:1px solid var(--gb);-webkit-backdrop-filter:blur(26px) saturate(180%);backdrop-filter:blur(26px) saturate(180%);box-shadow:var(--gs);animation:up .25s}
#cs b{display:block;font-size:1.3rem;margin-bottom:10px;word-break:break-all}
#cs a{display:block;padding:15px;border-radius:16px;background:var(--ac);color:#04200f;font-weight:800;font-size:1.15rem;text-decoration:none;margin:6px 0}
#cs button{width:100%;margin-top:6px;padding:13px;border-radius:14px;border:1px solid var(--gb);background:var(--b1);color:var(--tx);font:inherit;font-weight:700;cursor:pointer}
body.nobk main>div{animation:none!important}

/* ===== v13: wordmark, mic, edge guards, profile extras ===== */
#logoBox{flex-direction:column;gap:3px;justify-content:center}

#mic{flex:none;width:34px;height:34px;margin:0 -4px 0 2px;padding:0;border-radius:50%;border:1px solid var(--gb);background:var(--b1);color:var(--tx);display:none;align-items:center;justify-content:center;cursor:pointer;box-shadow:inset 0 1px 1px var(--gh)}
.search:focus-within #mic,#mic.on{display:flex}
#mic svg{width:18px;height:18px;fill:currentColor;pointer-events:none}
#mic.on{background:#ff3b30;border-color:#ff3b30;color:#fff;animation:micp 1s infinite}
@keyframes micp{50%{box-shadow:0 0 0 8px rgba(255,59,48,.22)}}
.eg{position:fixed;top:0;bottom:0;width:18px;z-index:120;touch-action:pan-y;display:none;-webkit-tap-highlight-color:transparent}
.eg.l{left:0}.eg.r{right:0}
body.inapp .eg{display:block}
@media (pointer:fine){.eg{display:none!important}}
body.rmo *,body.rmo *::before,body.rmo *::after{animation:none!important;transition:none!important}
.sh{margin:20px 4px 10px;font-size:1.05rem}
.acs{display:flex;flex-wrap:wrap;gap:12px;padding:4px}
.acs button{width:40px;height:40px;border-radius:50%;border:2px solid var(--gb);cursor:pointer;padding:0}
.acs button.on{outline:3px solid var(--tx);outline-offset:2px}
.fsz{display:flex;gap:10px}
.fsz button{flex:1;padding:12px 0;border-radius:14px;border:1px solid var(--bd);background:var(--card);color:var(--tx);font:inherit;font-weight:800;cursor:pointer}
.fsz button.on{background:var(--ac);color:#04200f;border-color:var(--ac)}
.stg{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.stc{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:16px;text-align:center}
.stc b{display:block;font-size:1.7rem;color:var(--ac)}
.stc span{font-size:.9rem;color:var(--mu)}
.bdg{display:flex;gap:12px;align-items:center;background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:14px;margin-bottom:10px;opacity:.55}
.bdg.on{opacity:1;border-color:var(--ac)}
.bdg i{font-style:normal;font-size:2rem;filter:grayscale(1)}
.bdg.on i{filter:none}
.bdg div{flex:1;min-width:0}
.bdg small{display:block;color:var(--mu)}
.bdg em{display:block;height:6px;border-radius:6px;background:var(--bd);margin-top:6px;overflow:hidden}
.bdg em u{display:block;height:100%;background:var(--ac)}
.chips{display:flex;flex-wrap:wrap;gap:8px;margin:6px 0 16px}
.chips button{padding:9px 14px;border-radius:30px;border:1px solid var(--bd);background:var(--card);color:var(--tx);font:inherit;cursor:pointer}
.chips button.on{background:var(--ac);color:#04200f;border-color:var(--ac);font-weight:800}
.invc{text-align:center;background:var(--card);border:1px solid var(--bd);border-radius:22px;padding:22px}
.invc b{display:block;font-size:1.6rem;letter-spacing:2px;margin:10px 0 16px;color:var(--ac)}
.invc .btn{width:100%;margin-top:8px}

/* ===== v14 ===== */
body[data-v="reels"] .search,body[data-v="profile"] .search{display:none!important}
body[data-v="reels"] header .mw,body[data-v="profile"] header .mw{margin-left:auto}
#ra{position:absolute;right:12px;top:50%;transform:translateY(-50%);z-index:4;display:flex;flex-direction:column;gap:18px}
#ra button{width:64px;min-height:64px;border-radius:32px;border:1px solid #ffffff44;background:#00000066;-webkit-backdrop-filter:blur(10px);backdrop-filter:blur(10px);color:#fff;font-size:1.7rem;line-height:1.1;padding:8px 0;cursor:pointer;display:flex;flex-direction:column;align-items:center;justify-content:center;transition:transform .2s}
#ra button small{font-size:.7rem;font-weight:700;margin-top:3px}
#ra button:active{transform:scale(.9)}
#ra button.on{border-color:var(--ac);box-shadow:0 0 0 2px var(--ac) inset}
.invc b.invl{font-size:1rem;letter-spacing:0;word-break:break-all}
/* smooth side menu, backdrop and overlays */
.menu,.menu.hide{display:flex!important}
.menu{animation:none!important;transform:translate3d(0,0,0);transition:transform .4s cubic-bezier(.22,1,.36,1),opacity .3s ease,visibility 0s linear 0s;will-change:transform}
.menu.hide{transform:translate3d(108%,0,0);opacity:0;visibility:hidden;pointer-events:none;transition:transform .32s cubic-bezier(.4,0,.2,1),opacity .25s ease,visibility 0s linear .32s}
#mbk{position:fixed;inset:0;z-index:95;background:rgba(0,0,0,.4);opacity:0;visibility:hidden;pointer-events:none;transition:opacity .3s ease,visibility 0s linear .3s}
body.menuopen #mbk{opacity:1;visibility:visible;transition:opacity .3s ease}
#md:not(.hide){animation:mdIn .34s cubic-bezier(.22,1,.36,1)}
#aiP:not(.hide){animation:aiIn .28s cubic-bezier(.22,1,.36,1)}
#rv:not(.hide){animation:mdIn .28s ease}
@keyframes mdIn{from{opacity:0;transform:translateY(26px)}to{opacity:1;transform:none}}
@keyframes aiIn{from{opacity:0;transform:translateY(14px) scale(.97)}to{opacity:1;transform:none}}
.eg{width:22px}

/* ===== v14 fixes ===== */
#mic{display:flex!important}
nav#nav{transform-origin:50% 100%;transition:filter .25s,opacity .25s}
#ra{top:auto!important;bottom:calc(96px + env(safe-area-inset-bottom,0px))!important;transform:none!important}
.navav{width:26px;height:26px;border-radius:50%;object-fit:cover;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:800;font-style:normal;color:#fff;border:2px solid var(--ac)}
.pnote{font-size:.82rem;line-height:1.5;color:var(--mu);background:var(--b1,rgba(127,127,127,.12));border-radius:12px;padding:10px 12px;margin-bottom:12px}
select.f{width:100%;appearance:auto}
.stbar{height:8px;border-radius:6px;background:rgba(127,127,127,.25);overflow:hidden;margin:8px 0}
.stbar i{display:block;height:100%;min-width:3px;background:var(--ac);border-radius:6px}

/* ===== v15 ===== */
#lens{display:none!important}
nav#nav{position:fixed!important;bottom:calc(3px + env(safe-area-inset-bottom,0px))!important;-webkit-transform:translateZ(0);transform:translateZ(0)}
nav#nav button.on{color:var(--ac)}
nav#nav button.on i{opacity:1}
#ra{bottom:calc(34px + env(safe-area-inset-bottom,0px))!important}
.hrt{position:fixed;z-index:120;font-size:92px;line-height:1;pointer-events:none;transform:translate(-50%,-50%);animation:hrt .85s ease-out forwards}
@keyframes hrt{0%{transform:translate(-50%,-50%) scale(.3);opacity:0}25%{transform:translate(-50%,-50%) scale(1.15);opacity:1}100%{transform:translate(-50%,-110%) scale(1);opacity:0}}
.chz{display:flex;flex-direction:column;min-height:calc(100vh - 230px);position:relative}
.chdots{position:absolute;right:-4px;top:-6px;background:none;border:0;color:var(--tx);font-size:1.9rem;padding:6px 12px;cursor:pointer;line-height:1}
.chmenu{position:absolute;right:0;top:40px;z-index:5;background:var(--card);border:1px solid var(--bd);border-radius:14px;padding:6px;box-shadow:0 8px 28px rgba(0,0,0,.45)}
.chmenu button{background:none;border:0;color:var(--tx);font:inherit;padding:12px 16px;cursor:pointer;white-space:nowrap;display:block;width:100%;text-align:left}
.chlogo{display:flex;justify-content:center;margin:40px 0 38px}
.chlogo img,.chlogo span{width:80px;height:80px;border-radius:50%;object-fit:cover}
.chlogo span{display:flex;align-items:center;justify-content:center;font-weight:800;color:#fff;font-size:1.05rem;background:linear-gradient(135deg,var(--ac),#7a3cff)}
.chc{display:flex;align-items:center;gap:16px;padding:14px 18px;border:1px solid var(--bd);border-radius:30px;margin-bottom:14px;background:var(--card);cursor:pointer}
.chc .avt{border-radius:50%;object-fit:cover;flex:none}
.chn{flex:1;font-size:1.2rem;font-weight:500;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.chc b{color:var(--mu);font-size:1.6rem;font-weight:400}
.chx{display:none;background:#ff453a;color:#fff;border:0;border-radius:50%;width:34px;height:34px;font-size:1rem;cursor:pointer;flex:none}
.chx.armed{width:auto;border-radius:17px;padding:0 14px;font-weight:700}
.chz.chrm .chx{display:block}.chz.chrm .chc b{display:none}.chz.chrm .chdots{width:auto;height:auto;border-radius:0;border:0;background:none}
.chalt{width:100%;padding:18px;border-radius:30px;border:0;background:var(--bd);color:var(--tx);font:inherit;font-weight:600;font-size:1.1rem;margin-top:4px;cursor:pointer}
.chbot{margin-top:auto;padding-top:44px;text-align:center}
.chnew{width:100%;padding:17px;border-radius:30px;border:2px solid var(--ac);background:none;color:var(--ac);font:inherit;font-weight:700;font-size:1.1rem;cursor:pointer}
.chmark{margin-top:18px;font-weight:800;letter-spacing:.5px;color:var(--mu)}
.lnk{background:none;border:0;color:var(--ac);font:inherit;padding:12px 4px;cursor:pointer;display:block;margin:6px auto 0}
</style>
</head>
<body>

<section id="landing">
  <div class="lhero">
    <div class="leye">WELCOME TO MVBD+</div>
    <div class="lh1">Entertainment starts here.</div>
    <div class="lpp">Welcome to MVBD+. Explore movies, discover anime, browse your favourite categories and save the titles you want to watch. Your entertainment space, all in one place.</div>
    <button class="lbtn" id="visitBtn">Watch Now <span>&#8594;</span></button>
  </div>
  <div class="lcard" data-enter="home"><div class="lct">Movies</div><div class="lcd">Explore movie titles and browse by genre.</div></div>
  <div class="lcard" data-enter="anime"><div class="lct">Anime</div><div class="lcd">Find anime and discover new stories.</div></div>
  <div class="lcard" data-enter="profile"><div class="lct">Your Profile</div><div class="lcd">Open your profile and account page.</div></div>
</section>

<div id="app" class="hide">
<svg width="0" height="0" style="position:absolute" aria-hidden="true" focusable="false"><defs><linearGradient id="pgold" x1="0" y1="0" x2="1" y2="1"><stop offset="0" stop-color="#f3dc8a"/><stop offset=".5" stop-color="#e6b422"/><stop offset="1" stop-color="#d98a1c"/></linearGradient></defs></svg>
<header>
  <div id="logoBox"><img id="logoImg" alt="MVBD" src="https://i.postimg.cc/44KSPnx4/att-oy-Oo2Gmpo-Zosd-MY-02obsni-vx-HEL1y-XD7Mh-QGmxk-Hc.jpg"><span id="logoTx" class="hide"></span></div>
  <label class="search">🔍<input id="q" placeholder="Search…" autocomplete="off"><button type="button" id="mic" aria-label="Voice search" title="Voice search"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 14a3 3 0 0 0 3-3V5a3 3 0 0 0-6 0v6a3 3 0 0 0 3 3zm5-3a5 5 0 0 1-10 0H5a7 7 0 0 0 6 6.92V21h2v-3.08A7 7 0 0 0 19 11h-2z"/></svg></button></label>
  
  <div class="mw"><button class="ib" id="dots" title="Menu" aria-label="Menu"><svg viewBox="0 0 24 24" width="1em" height="1em" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" aria-hidden="true"><path d="M4 6.5h16M4 12h16M4 17.5h16"/></svg></button></div>
</header>
<div id="mbk"></div>
<div class="menu hide" id="menu">
  <div class="mh"><b>Menu</b><button class="ib" id="mx">✕</button></div>
  <button data-go="req">📩 Request Movie / Series / Anime</button>
  <button data-go="subs">👑 Premium</button>
  <button data-go="hist">🕘 Watch History</button>
  <button data-go="saved">🔖 My List</button>
  <button data-go="dl">⬇️ Downloads</button>
  <button data-go="likes">❤️ My Likes</button>
  <button id="mDark" data-keep="1">🌙 Dark mode</button>
</div>
<div id="md" class="hide">
  <button id="mdx">←</button>
  <div id="mdh"></div>
  <div class="mdb"><h2 id="mdt"></h2><p id="mdm"></p><div id="mdg"></div><button class="btn" id="mdw">▶ Watch Now</button><div class="act"><button id="mds">🔖 Save</button><button id="mdl">🤍 Like</button><button id="mdd">⬇️ Download</button></div><div id="mdrv"></div></div>
</div>

<main>
  <div id="v-home">
    <div id="hm">
    </div>
    <div id="rs2" class="hide"><h3 class="t">RESULTS</h3><div class="grid" id="grid"></div><p class="note hide" id="none">কিছু পাওয়া যায়নি 😕</p></div>
  </div>

  <div id="v-series" class="hide"><div id="shm"></div></div>
  <div id="v-anime" class="hide"><div id="ahm"></div></div>
  <div id="v-reels" class="hide"><h3 class="t">REELS</h3><div class="grid rl" id="gridR"></div></div>
  <div id="v-saved" class="hide"><h3 class="t">MY LIST</h3><div class="tabs" id="svt"><button data-s="m" class="on">🎬 Movie</button><button data-s="s">📺 Series</button><button data-s="a">⚔️ Anime</button><button data-s="r">🎞 Reels</button></div><div class="grid" id="sg"></div><p class="note hide" id="sn"></p></div>
  <div id="v-subs" class="hide"><h3 class="t ptl">👑 GO PREMIUM</h3><p class="note" style="padding:0 0 16px">Ad-free • HD/4K • Downloads • Early access</p><div class="plans" id="plans"></div></div>
  <div id="v-about" class="hide"><div class="box"><h2>About MVBD+</h2><p>MVBD+ হলো একটি মুভি, সিরিজ ও অ্যানিমে স্ট্রিমিং প্ল্যাটফর্ম। আমাদের লক্ষ্য সহজে ও দ্রুত আপনার পছন্দের কনটেন্ট এক জায়গায় পৌঁছে দেওয়া।</p></div></div>
  <div id="v-terms" class="hide"><div class="box"><h2>📄 Terms of Service / সেবার শর্তাবলি</h2>
    <p><b>1. Use / ব্যবহার:</b> MVBD+ is for personal, non-commercial viewing. ব্যক্তিগত ও অ-বাণিজ্যিক দেখার জন্য।</p>
    <p><b>2. Account / অ্যাকাউন্ট:</b> Keep your password safe; you are responsible for activity on your account. পাসওয়ার্ড সুরক্ষিত রাখুন, অ্যাকাউন্টের কাজের দায়িত্ব আপনার।</p>
    <p><b>3. Content / কনটেন্ট:</b> You may not copy, resell or redistribute content from MVBD+. কনটেন্ট কপি, বিক্রি বা পুনরায় বিতরণ করা যাবে না।</p>
    <p><b>4. Plans / প্ল্যান:</b> Prices and features may change with notice. দাম ও সুবিধা নোটিশ দিয়ে পরিবর্তন হতে পারে।</p>
    <p><b>5. Termination / বন্ধ:</b> We may suspend accounts that break these terms. শর্ত ভাঙলে অ্যাকাউন্ট বন্ধ করা হতে পারে।</p>
    <p><b>6. Contact / যোগাযোগ:</b> Questions? Use the Contact Us section below. প্রশ্ন থাকলে নিচের Contact Us দেখুন।</p></div></div>
  <div id="v-privacy" class="hide"><div class="box"><h2>🔒 Privacy Policy / গোপনীয়তা নীতি</h2>
    <p><b>What we collect / কী সংগ্রহ করি:</b> Name, email, bio and your chosen plan, only when you create an account. অ্যাকাউন্ট খুললে নাম, email, bio ও প্ল্যান।</p>
    <p><b>How it is stored / কোথায় থাকে:</b> In this demo, data is saved in your own browser (local storage) and is not sent to any server. এই ডেমোতে ডেটা আপনার ব্রাউজারেই থাকে, কোনো সার্ভারে যায় না।</p>
    <p><b>Sharing / শেয়ার:</b> We do not sell your personal information. আপনার তথ্য আমরা বিক্রি করি না।</p>
    <p><b>Your choices / আপনার অধিকার:</b> You can edit your bio or log out anytime, and clear your browser data to remove everything. যেকোনো সময় Bio বদলাতে, Log out করতে বা ব্রাউজার ডেটা মুছতে পারেন।</p>
    <p><b>Contact / যোগাযোগ:</b> See Contact Us below. নিচের Contact Us দেখুন।</p></div></div>
  <div id="v-profile" class="hide"><div id="pbox"></div></div>
  <div id="v-req" class="hide"></div>
  <div id="v-dl" class="hide"></div>
  <div id="v-hist" class="hide"></div>
  <div id="v-likes" class="hide"></div>
</main>

<footer>
  <h4>Contact Us</h4>
  <div class="soc" id="soc"><div class="trk"><div class="grp"><a class="c-call" href="tel:01874743206" aria-label="Call" title="Call"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z" fill="#fff"/></svg></a><a class="c-wa" href="https://wa.me/8801874743206?s=p" target="_blank" rel="noopener" aria-label="WhatsApp" title="WhatsApp"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 3.2a8.8 8.8 0 0 0-7.5 13.4L3.2 20.8l4.3-1.1A8.8 8.8 0 1 0 12 3.2z" fill="none" stroke="#fff" stroke-width="1.8" stroke-linejoin="round"/><path transform="translate(6 6) scale(.5)" d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z" fill="#fff"/></svg></a><a class="c-tg" href="https://t.me/+8801874743206" target="_blank" rel="noopener" aria-label="Telegram" title="Telegram"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M20.7 4.1 3.4 10.8c-1.2.5-1.2 1.1-.2 1.4l4.4 1.4 1.7 5.2c.2.6.1.8.7.8.5 0 .7-.2 1-.5l2.1-2.1 4.4 3.3c.8.4 1.4.2 1.6-.8L22 5.6c.3-1.2-.5-1.7-1.3-1.5z" fill="#fff"/><path d="M9.3 13.6 17 8.2l-5.8 6.6-.3 3.1z" fill="#2AABEE" opacity=".55"/></svg></a><a class="c-gm" href="https://mail.google.com/mail/?view=cm&amp;fs=1&amp;to=emonkhannnn7@gmail.com" target="_blank" rel="noopener" aria-label="Gmail" title="Gmail"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z" fill="#fff"/></svg></a><a class="c-fb" href="https://facebook.com" target="_blank" rel="noopener" aria-label="Facebook" title="Facebook"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M13.5 22v-8h2.7l.5-3.3h-3.2V8.6c0-.9.4-1.7 1.8-1.7h1.5V4.1S15.8 4 14.6 4C12 4 10.3 5.6 10.3 8.3v2.4H7.5V14h2.8v8z" fill="#fff"/></svg></a><a class="c-th" href="https://www.threads.com/@emon23411?igshid=NTc4MTIwNjQ2YQ==" target="_blank" rel="noopener" aria-label="Threads" title="Threads"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M17.2 9.4C16.4 5.8 13.9 4.2 11.6 4.2 8 4.2 5.6 6.9 5.6 12s2.4 7.8 6.4 7.8c3.3 0 5.4-1.8 5.4-4.2 0-2.2-1.8-3.3-3.9-3.3-2 0-3.2.9-3.2 2.1 0 1.1 1 1.8 2.2 1.8 1.8 0 2.7-1.4 2.7-4.200V9.800" fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round"/></svg></a><a class="c-ig" href="https://www.instagram.com/emon23411?knvt=MWxmenVlMjQwdm9keQ%3D%3D&amp;utm_source=qr" target="_blank" rel="noopener" aria-label="Instagram" title="Instagram"><svg viewBox="0 0 24 24" aria-hidden="true"><rect x="3.5" y="3.5" width="17" height="17" rx="5" fill="none" stroke="#fff" stroke-width="1.9"/><circle cx="12" cy="12" r="4" fill="none" stroke="#fff" stroke-width="1.9"/><circle cx="17.2" cy="6.8" r="1.2" fill="#fff"/></svg></a><a class="c-x" href="https://x.com/emonmahmud63?s=11" target="_blank" rel="noopener" aria-label="X" title="X"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M18.2 2.2h3.3l-7.2 8.3 8.5 11.3h-6.7l-5.2-6.9-6 6.9H1.6l7.7-8.8L1.2 2.2H8l4.7 6.3 5.5-6.3zm-1.2 17.6h1.8L7 4.1H5.1l11.9 15.7z" fill="#fff"/></svg></a><a class="c-tt" href="https://www.tiktok.com/@emon____87?_r=1&amp;_t=ZS-9BbFAuU7xpO" target="_blank" rel="noopener" aria-label="TikTok" title="TikTok"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M16.6 2h-3.2v13.1a2.9 2.9 0 1 1-2.9-2.9c.3 0 .6 0 .9.1V9a6.1 6.1 0 1 0 5.2 6V8.6a7.5 7.5 0 0 0 4.4 1.4V6.8A4.5 4.5 0 0 1 16.6 2z" fill="#fff"/></svg></a><a class="c-yt" href="https://youtube.com/@emonchowdhury9515?si=QU-6WDWwrncW8v0b" target="_blank" rel="noopener" aria-label="YouTube" title="YouTube"><svg viewBox="0 0 24 24" aria-hidden="true"><rect x="2.5" y="5.5" width="19" height="13" rx="4" fill="#fff"/><path d="M10 9.2v5.6l5-2.8z" fill="#FF0000"/></svg></a></div></div>
  </div>
  <div class="fl"><button data-go="about">About us</button><button data-go="privacy">Privacy Policy</button><button data-go="terms">Terms of Service</button></div>
  © 2026 MVBD+. All rights reserved.
</footer>

<nav id="nav">
  <button data-go="home"><i><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 2.8 2.4 11.2h2.9V20a1.2 1.2 0 0 0 1.2 1.2h3.9v-6h3.2v6h3.9a1.2 1.2 0 0 0 1.2-1.2v-8.8h2.9z" fill="url(#pgold)"/></svg></i>Home</button>
  <button data-go="series"><i><svg viewBox="0 0 24 24" aria-hidden="true"><rect x="2.4" y="4.6" width="19.2" height="13.2" rx="2.6" fill="url(#pgold)"/><rect x="4.9" y="7" width="14.2" height="8.4" rx="1.3" style="fill:var(--card)"/><path d="M10.4 9.4v3.6l3.1-1.8z" fill="url(#pgold)"/><rect x="7.5" y="19.4" width="9" height="2" rx="1" fill="url(#pgold)"/></svg></i>Series</button>
  <button data-go="anime"><i><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M11 2.2l2.4 6.3 6.6 2.4-6.6 2.4L11 19.6l-2.4-6.3L2 10.9l6.6-2.4z" fill="url(#pgold)"/><path d="M19.2 15l.9 2.2 2.2.9-2.2.9-.9 2.2-.9-2.2-2.2-.9 2.2-.9z" fill="url(#pgold)"/></svg></i>Anime</button>
  <button data-go="reels"><i><svg viewBox="0 0 24 24" aria-hidden="true"><rect x="5.6" y="2" width="12.8" height="20" rx="3.2" fill="url(#pgold)"/><path d="M10.3 8.6v6.8l5-3.4z" style="fill:var(--card)"/></svg></i>Reels</button>
  <button data-go="profile"><i><svg viewBox="0 0 24 24" aria-hidden="true"><circle cx="12" cy="7.8" r="4.4" fill="url(#pgold)"/><path d="M3.4 21.2a8.6 7.2 0 0 1 17.2 0z" fill="url(#pgold)"/></svg></i>Profile<b class="dot hide" id="pdot"></b></button>
</nav>
</div>

<div id="rv" class="hide">
  <button id="rx">✕</button>
  <div id="rc"></div>
  <div id="rs"></div>
  <div id="rn"><button id="ru">▲</button><button id="rd">▼</button></div>
  <div id="rp"></div>
  <div id="ra"><button id="rlk" aria-label="Like">🤍<small>0</small></button><button id="rsv" aria-label="Save">🔖<small>Save</small></button></div>
</div>

<div id="toast" class="hide"></div>
<button id="aiB" class="hide" title="MVBD+ AI Moderator"><img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMjggMTI4Ij4KPGRlZnM+CjxyYWRpYWxHcmFkaWVudCBpZD0iYmciIGN4PSIuMyIgY3k9Ii4yMiIgcj0iLjk1Ij48c3RvcCBvZmZzZXQ9IjAiIHN0b3AtY29sb3I9IiM4ZGZjZDAiLz48c3RvcCBvZmZzZXQ9Ii41IiBzdG9wLWNvbG9yPSIjMWZhOGZmIi8+PHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjNGIxZmQ2Ii8+PC9yYWRpYWxHcmFkaWVudD4KPGxpbmVhckdyYWRpZW50IGlkPSJoZCIgeDE9IjAiIHkxPSIwIiB4Mj0iMCIgeTI9IjEiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iI2ZmZmZmZiIvPjxzdG9wIG9mZnNldD0iMSIgc3RvcC1jb2xvcj0iI2NmZTNmZiIvPjwvbGluZWFyR3JhZGllbnQ+CjxsaW5lYXJHcmFkaWVudCBpZD0ic2MiIHgxPSIwIiB5MT0iMCIgeDI9IjEiIHkyPSIxIj48c3RvcCBvZmZzZXQ9IjAiIHN0b3AtY29sb3I9IiMwZjJhNWMiLz48c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiMwNTBkMjQiLz48L2xpbmVhckdyYWRpZW50Pgo8cmFkaWFsR3JhZGllbnQgaWQ9ImV5IiBjeD0iLjUiIGN5PSIuNSIgcj0iLjUiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iI2U4ZmZmZiIvPjxzdG9wIG9mZnNldD0iLjU1IiBzdG9wLWNvbG9yPSIjM2RmMGZmIi8+PHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjMWZhOGZmIi8+PC9yYWRpYWxHcmFkaWVudD4KPGxpbmVhckdyYWRpZW50IGlkPSJnbCIgeDE9IjAiIHkxPSIwIiB4Mj0iMCIgeTI9IjEiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iI2ZmZiIgc3RvcC1vcGFjaXR5PSIuNTUiLz48c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiNmZmYiIHN0b3Atb3BhY2l0eT0iMCIvPjwvbGluZWFyR3JhZGllbnQ+CjxmaWx0ZXIgaWQ9Imd3IiB4PSItNTAlIiB5PSItNTAlIiB3aWR0aD0iMjAwJSIgaGVpZ2h0PSIyMDAlIj48ZmVHYXVzc2lhbkJsdXIgc3RkRGV2aWF0aW9uPSIyLjIiLz48L2ZpbHRlcj4KPC9kZWZzPgo8Y2lyY2xlIGN4PSI2NCIgY3k9IjY0IiByPSI2MiIgZmlsbD0idXJsKCNiZykiLz4KPGNpcmNsZSBjeD0iNjQiIGN5PSI2NCIgcj0iNjEiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2ZmZiIgc3Ryb2tlLW9wYWNpdHk9Ii4zNSIgc3Ryb2tlLXdpZHRoPSIyIi8+CjxsaW5lIHgxPSI2NCIgeTE9IjMwIiB4Mj0iNjQiIHkyPSI0MCIgc3Ryb2tlPSIjZmZmIiBzdHJva2Utd2lkdGg9IjQiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIvPgo8Y2lyY2xlIGN4PSI2NCIgY3k9IjI2IiByPSI2IiBmaWxsPSIjZmZkNTRhIi8+PGNpcmNsZSBjeD0iNjIiIGN5PSIyNCIgcj0iMiIgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuOCIvPgo8cmVjdCB4PSIyMCIgeT0iNjIiIHdpZHRoPSI5IiBoZWlnaHQ9IjIyIiByeD0iNC41IiBmaWxsPSIjZGJlOWZmIi8+PHJlY3QgeD0iOTkiIHk9IjYyIiB3aWR0aD0iOSIgaGVpZ2h0PSIyMiIgcng9IjQuNSIgZmlsbD0iI2RiZTlmZiIvPgo8cmVjdCB4PSIyOCIgeT0iNDAiIHdpZHRoPSI3MiIgaGVpZ2h0PSI2MiIgcng9IjI0IiBmaWxsPSJ1cmwoI2hkKSIvPgo8cmVjdCB4PSIzNSIgeT0iNDgiIHdpZHRoPSI1OCIgaGVpZ2h0PSI0MiIgcng9IjE3IiBmaWxsPSJ1cmwoI3NjKSIvPgo8ZyBmaWx0ZXI9InVybCgjZ3cpIj48Y2lyY2xlIGN4PSI1MyIgY3k9IjY3IiByPSI3IiBmaWxsPSIjM2RmMGZmIi8+PGNpcmNsZSBjeD0iNzUiIGN5PSI2NyIgcj0iNyIgZmlsbD0iIzNkZjBmZiIvPjwvZz4KPGNpcmNsZSBjeD0iNTMiIGN5PSI2NyIgcj0iNiIgZmlsbD0idXJsKCNleSkiLz48Y2lyY2xlIGN4PSI3NSIgY3k9IjY3IiByPSI2IiBmaWxsPSJ1cmwoI2V5KSIvPgo8Y2lyY2xlIGN4PSI1MSIgY3k9IjY1IiByPSIxLjgiIGZpbGw9IiNmZmYiLz48Y2lyY2xlIGN4PSI3MyIgY3k9IjY1IiByPSIxLjgiIGZpbGw9IiNmZmYiLz4KPHBhdGggZD0iTTU0IDc5IFE2NCA4NiA3NCA3OSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjM2RmMGZmIiBzdHJva2Utd2lkdGg9IjMuMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIi8+CjxwYXRoIGQ9Ik0xMDQgMzAgbDIuNiA3IDcgMi42IC03IDIuNiAtMi42IDcgLTIuNiAtNyAtNyAtMi42IDcgLTIuNnoiIGZpbGw9IiNmZmYiLz4KPHBhdGggZD0iTTIwIDM2IGwxLjYgNCA0IDEuNiAtNCAxLjYgLTEuNiA0IC0xLjYgLTQgLTQgLTEuNiA0IC0xLjZ6IiBmaWxsPSIjZmZmIiBmaWxsLW9wYWNpdHk9Ii44NSIvPgo8ZWxsaXBzZSBjeD0iNTAiIGN5PSIyMiIgcng9IjM0IiByeT0iMTYiIGZpbGw9InVybCgjZ2wpIiB0cmFuc2Zvcm09InJvdGF0ZSgtMTggNTAgMjIpIi8+Cjwvc3ZnPg==" alt="AI" draggable="false"></button>
<div id="aiP" class="hide">
  <div id="aiH"><span style="display:flex;align-items:center;gap:10px"><img class="aiHi" src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMjggMTI4Ij4KPGRlZnM+CjxyYWRpYWxHcmFkaWVudCBpZD0iYmciIGN4PSIuMyIgY3k9Ii4yMiIgcj0iLjk1Ij48c3RvcCBvZmZzZXQ9IjAiIHN0b3AtY29sb3I9IiM4ZGZjZDAiLz48c3RvcCBvZmZzZXQ9Ii41IiBzdG9wLWNvbG9yPSIjMWZhOGZmIi8+PHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjNGIxZmQ2Ii8+PC9yYWRpYWxHcmFkaWVudD4KPGxpbmVhckdyYWRpZW50IGlkPSJoZCIgeDE9IjAiIHkxPSIwIiB4Mj0iMCIgeTI9IjEiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iI2ZmZmZmZiIvPjxzdG9wIG9mZnNldD0iMSIgc3RvcC1jb2xvcj0iI2NmZTNmZiIvPjwvbGluZWFyR3JhZGllbnQ+CjxsaW5lYXJHcmFkaWVudCBpZD0ic2MiIHgxPSIwIiB5MT0iMCIgeDI9IjEiIHkyPSIxIj48c3RvcCBvZmZzZXQ9IjAiIHN0b3AtY29sb3I9IiMwZjJhNWMiLz48c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiMwNTBkMjQiLz48L2xpbmVhckdyYWRpZW50Pgo8cmFkaWFsR3JhZGllbnQgaWQ9ImV5IiBjeD0iLjUiIGN5PSIuNSIgcj0iLjUiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iI2U4ZmZmZiIvPjxzdG9wIG9mZnNldD0iLjU1IiBzdG9wLWNvbG9yPSIjM2RmMGZmIi8+PHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjMWZhOGZmIi8+PC9yYWRpYWxHcmFkaWVudD4KPGxpbmVhckdyYWRpZW50IGlkPSJnbCIgeDE9IjAiIHkxPSIwIiB4Mj0iMCIgeTI9IjEiPjxzdG9wIG9mZnNldD0iMCIgc3RvcC1jb2xvcj0iI2ZmZiIgc3RvcC1vcGFjaXR5PSIuNTUiLz48c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiNmZmYiIHN0b3Atb3BhY2l0eT0iMCIvPjwvbGluZWFyR3JhZGllbnQ+CjxmaWx0ZXIgaWQ9Imd3IiB4PSItNTAlIiB5PSItNTAlIiB3aWR0aD0iMjAwJSIgaGVpZ2h0PSIyMDAlIj48ZmVHYXVzc2lhbkJsdXIgc3RkRGV2aWF0aW9uPSIyLjIiLz48L2ZpbHRlcj4KPC9kZWZzPgo8Y2lyY2xlIGN4PSI2NCIgY3k9IjY0IiByPSI2MiIgZmlsbD0idXJsKCNiZykiLz4KPGNpcmNsZSBjeD0iNjQiIGN5PSI2NCIgcj0iNjEiIGZpbGw9Im5vbmUiIHN0cm9rZT0iI2ZmZiIgc3Ryb2tlLW9wYWNpdHk9Ii4zNSIgc3Ryb2tlLXdpZHRoPSIyIi8+CjxsaW5lIHgxPSI2NCIgeTE9IjMwIiB4Mj0iNjQiIHkyPSI0MCIgc3Ryb2tlPSIjZmZmIiBzdHJva2Utd2lkdGg9IjQiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIvPgo8Y2lyY2xlIGN4PSI2NCIgY3k9IjI2IiByPSI2IiBmaWxsPSIjZmZkNTRhIi8+PGNpcmNsZSBjeD0iNjIiIGN5PSIyNCIgcj0iMiIgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuOCIvPgo8cmVjdCB4PSIyMCIgeT0iNjIiIHdpZHRoPSI5IiBoZWlnaHQ9IjIyIiByeD0iNC41IiBmaWxsPSIjZGJlOWZmIi8+PHJlY3QgeD0iOTkiIHk9IjYyIiB3aWR0aD0iOSIgaGVpZ2h0PSIyMiIgcng9IjQuNSIgZmlsbD0iI2RiZTlmZiIvPgo8cmVjdCB4PSIyOCIgeT0iNDAiIHdpZHRoPSI3MiIgaGVpZ2h0PSI2MiIgcng9IjI0IiBmaWxsPSJ1cmwoI2hkKSIvPgo8cmVjdCB4PSIzNSIgeT0iNDgiIHdpZHRoPSI1OCIgaGVpZ2h0PSI0MiIgcng9IjE3IiBmaWxsPSJ1cmwoI3NjKSIvPgo8ZyBmaWx0ZXI9InVybCgjZ3cpIj48Y2lyY2xlIGN4PSI1MyIgY3k9IjY3IiByPSI3IiBmaWxsPSIjM2RmMGZmIi8+PGNpcmNsZSBjeD0iNzUiIGN5PSI2NyIgcj0iNyIgZmlsbD0iIzNkZjBmZiIvPjwvZz4KPGNpcmNsZSBjeD0iNTMiIGN5PSI2NyIgcj0iNiIgZmlsbD0idXJsKCNleSkiLz48Y2lyY2xlIGN4PSI3NSIgY3k9IjY3IiByPSI2IiBmaWxsPSJ1cmwoI2V5KSIvPgo8Y2lyY2xlIGN4PSI1MSIgY3k9IjY1IiByPSIxLjgiIGZpbGw9IiNmZmYiLz48Y2lyY2xlIGN4PSI3MyIgY3k9IjY1IiByPSIxLjgiIGZpbGw9IiNmZmYiLz4KPHBhdGggZD0iTTU0IDc5IFE2NCA4NiA3NCA3OSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSIjM2RmMGZmIiBzdHJva2Utd2lkdGg9IjMuMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIi8+CjxwYXRoIGQ9Ik0xMDQgMzAgbDIuNiA3IDcgMi42IC03IDIuNiAtMi42IDcgLTIuNiAtNyAtNyAtMi42IDcgLTIuNnoiIGZpbGw9IiNmZmYiLz4KPHBhdGggZD0iTTIwIDM2IGwxLjYgNCA0IDEuNiAtNCAxLjYgLTEuNiA0IC0xLjYgLTQgLTQgLTEuNiA0IC0xLjZ6IiBmaWxsPSIjZmZmIiBmaWxsLW9wYWNpdHk9Ii44NSIvPgo8ZWxsaXBzZSBjeD0iNTAiIGN5PSIyMiIgcng9IjM0IiByeT0iMTYiIGZpbGw9InVybCgjZ2wpIiB0cmFuc2Zvcm09InJvdGF0ZSgtMTggNTAgMjIpIi8+Cjwvc3ZnPg==" alt="">MVBD+ AI Moderator</span><button id="aiX">✕</button></div>
  <div id="aiM"></div>
  <div id="aiQ"></div>
  <form id="aiF"><input id="aiI" placeholder="প্রশ্ন লিখুন / Ask anything…" autocomplete="off"><button type="submit">➤</button></form>
</div>

<script>
var movies=[["Half CA – Season 1","2023",8.1,"🎓","🇮🇳 India"],["Half CA – Season 2","2023",8.0,"📚","🇮🇳 India"],["Front of the Class","2008",8.7,"🏫","🇺🇸 USA"],["Roid","2023",5.5,"💉","🇮🇳 India"],["Bijoyar Pore","2024",8.7,"🏆","🇧🇩 Bangladesh"],["Action Hero","2022",7.2,"💥","🇮🇳 India"],["Mystery Night","2021",6.9,"🕵️","🇬🇧 UK"],["Dark Waters","2020",7.4,"🌊","🇺🇸 USA"],["Last Train","2022",7.8,"🚆","🇰🇷 South Korea"],["Desert Storm","2021",7.1,"🏜️","🇺🇸 USA"],["Love in Dhaka","2023",7.6,"❤️","🇧🇩 Bangladesh"],["Shadow Game","2024",8.3,"🎭","🇫🇷 France"],["Red Alert","2020",6.8,"🚨","🇮🇳 India"],["Silent Voice","2019",8.0,"🔇","🇯🇵 Japan"],["The Heist","2022",7.5,"💰","🇪🇸 Spain"],["Monsoon Tale","2024",8.4,"🌧️","🇧🇩 Bangladesh"],["Iron City","2023",7.0,"🏙️","🇺🇸 USA"],["Ghost House","2021",6.6,"👻","🇹🇭 Thailand"],["Final Kick","2022",7.3,"⚽","🇧🇷 Brazil"],["Royal Blood","2024",8.1,"👑","🇬🇧 UK"],["Night Strike – Season 1","2023",8.2,"🔫","🇺🇸 USA"],["Iron Squad – Season 2","2024",8.0,"🛡️","🇺🇸 USA"],["Dhaka Shadows – Season 1","2024",8.4,"🌃","🇧🇩 Bangladesh"],["Bonolota – Season 1","2023",7.8,"🌿","🇧🇩 Bangladesh"],["Seoul Hearts – Season 1","2024",8.5,"💞","🇰🇷 South Korea"],["Midnight Seoul – Season 2","2023",8.1,"🌙","🇰🇷 South Korea"],["Mumbai Files – Season 1","2022",7.9,"🕶️","🇮🇳 India"],["Chai and Chaos – Season 3","2024",7.6,"☕","🇮🇳 India"],["Haunted Hill – Season 1","2023",7.2,"🏚️","🇺🇸 USA"],["Dark Corridor – Season 2","2024",7.5,"🕯️","🇹🇭 Thailand"],["Galaxy Wars – Season 1","2024",8.6,"🪐","🇺🇸 USA"],["Cyber Pulse – Season 2","2023",8.0,"🧠","🇯🇵 Japan"],["Laugh Factory – Season 1","2022",7.4,"😂","🇬🇧 UK"],["Office Drama – Season 4","2021",7.7,"💼","🇺🇸 USA"],["Family Ties BD – Season 2","2023",8.3,"👪","🇧🇩 Bangladesh"],["Courtroom Truth – Season 1","2024",8.2,"⚖️","🇮🇳 India"],["Dragon Realm – Season 1","2023",8.7,"🐲","🇺🇸 USA"],["Crystal Kingdom – Season 2","2024",8.1,"🔮","🇬🇧 UK"],["Golden Goal – Season 1","2023",7.9,"🥅","🇧🇷 Brazil"],["Cricket Fever – Season 2","2024",8.0,"🏏","🇮🇳 India"],["Royal Court – Season 1","2022",8.3,"🏰","🇬🇧 UK"],["Spy Games – Season 3","2023",8.1,"🎯","🇫🇷 France"],["Desert Rose – Season 1","2024",7.7,"🌹","🇪🇸 Spain"],["Zombie Zone – Season 1","2023",7.6,"🧟","🇺🇸 USA"],["Tokyo Detective – Season 2","2024",8.4,"🔍","🇯🇵 Japan"],["Love Letters BD – Season 1","2024",8.0,"💌","🇧🇩 Bangladesh"],["Mafia City – Season 2","2022",8.5,"🎩","🇺🇸 USA"],["Space Colony – Season 1","2024",8.2,"🛰️","🇺🇸 USA"]];
var anime=[["Blade Spirit","2024",8.5,"⚔️","🇯🇵 Japan"],["Moon Knight Saga","2023",8.2,"🌙","🇯🇵 Japan"],["Elf Chronicles","2022",7.9,"🧝","🇯🇵 Japan"],["Dragon Gate","2024",8.8,"🐉","🇨🇳 China"],["Ninja Rising","2023",8.0,"🥷","🇯🇵 Japan"],["Star Pilot","2022",7.7,"🚀","🇯🇵 Japan"],["Sakura Days","2021",7.5,"🌸","🇯🇵 Japan"],["Mecha Zero","2024",8.3,"🤖","🇯🇵 Japan"],["Spirit Academy","2024",8.4,"🏫","🇯🇵 Japan"],["Isekai Blacksmith","2023",8.0,"🔨","🇯🇵 Japan"],["Reborn Hero Chronicle","2024",8.2,"🦸","🇯🇵 Japan"],["Quiet Afternoon","2022",7.6,"🍵","🇯🇵 Japan"],["Cafe Under Rain","2023",7.8,"☔","🇯🇵 Japan"],["Steel Titan X","2024",8.5,"🦾","🇯🇵 Japan"],["Mecha Academy","2022",7.9,"🛠️","🇯🇵 Japan"],["Demon Hunter Rei","2023",8.7,"👹","🇯🇵 Japan"],["Shadow Exorcist","2022",8.1,"🕯️","🇯🇵 Japan"],["Wizard Kingdom Tale","2024",8.3,"🧙","🇯🇵 Japan"],["Phoenix Warriors","2021",8.0,"🔥","🇯🇵 Japan"],["Pirate Skies","2023",8.6,"☠️","🇯🇵 Japan"],["Love After Class","2022",7.4,"💕","🇯🇵 Japan"],["Samurai Dawn","2023",8.4,"🗡️","🇯🇵 Japan"],["Panda Detective","2021",7.3,"🐼","🇨🇳 China"],["Lotus Immortal","2024",8.2,"🪷","🇨🇳 China"],["Hero Academy Rise","2024",8.3,"💪","🇯🇵 Japan"],["Cyber Samurai 2099","2024",8.5,"🤖","🇯🇵 Japan"],["Neko Cafe Days","2022",7.5,"🐱","🇯🇵 Japan"],["Haunted Shrine","2023",7.7,"⛩️","🇯🇵 Japan"],["Crimson Case Files","2024",8.1,"🔎","🇯🇵 Japan"],["Football Dreams","2022",7.9,"🏟️","🇯🇵 Japan"],["Shonar Bangla Quest","2024",8.2,"🌾","🇧🇩 Bangladesh (Dub)"],["Padma Spirit Saga","2023",7.9,"🌊","🇧🇩 Bangladesh (Dub)"],["Jadur Pathshala","2024",8.0,"🪄","🇧🇩 Bangladesh (Dub)"],["Dhaka Ninja Boy","2022",7.6,"🥷","🇧🇩 Bangladesh (Dub)"]];
var ALL=movies.concat(anime);
var series=movies.filter(function(m){return /Season/.test(m[0])});
var hues=[150,200,30,260,340,90,10,180];
function $(id){return document.getElementById(id)}
function esc(s){return String(s).replace(/[&<>"]/g,function(c){return{"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]})}
function fmtN(n){return n>=1000?(n/1000).toFixed(n>=10000?0:1).replace(/\.0$/,"")+"K":String(n)}
function baseLikes(t){var h=0;for(var i=0;i<t.length;i++)h=(h*31+t.charCodeAt(i))>>>0;return 80+h%2400}
function lcMap(){var x=store("mvbd_lc");if(x){try{return JSON.parse(x)}catch(e){}}return mem.lc||{}}
function lcSet(o){mem.lc=o;store("mvbd_lc",JSON.stringify(o))}
function likeCount(t){return Math.max(0,baseLikes(t)+(lcMap()[t]||0))}
function refreshLk(t){document.querySelectorAll(".mv[data-t]").forEach(function(c){if(c.dataset.t===t){var e=c.querySelector(".lk");if(e)e.textContent="❤️ "+fmtN(likeCount(t))}})}
function card(m,i){return '<div class="mv" data-i="'+i+'" data-t="'+esc(m[0])+'" style="animation-delay:'+Math.min(i*45,900)+'ms;background:linear-gradient(transparent 40%,#000c),hsl('+hues[i%8]+',45%,28%)">'+(m[2]!==""?'<span>⭐ '+m[2]+'</span>':'')+'<em>'+m[3]+'</em>'+esc(m[0])+'<small style="font-weight:400;display:block">'+m[1]+'</small><small style="font-weight:600;display:block;color:#ffe9a8;margin-top:2px">'+m[4]+'</small></div>'}
function draw(list,el){$(el).innerHTML=list.map(card).join("")}
var views=["home","series","anime","reels","saved","subs","about","profile","terms","privacy","dl","likes","req","hist"];
function store(k,v){try{if(v===undefined)return localStorage.getItem(k);if(v===null)localStorage.removeItem(k);else localStorage.setItem(k,v)}catch(e){return null}}
var mem={user:null,accs:[],plan:null};
function getUser(){var s=store("mvbd_user");if(s){try{return JSON.parse(s)}catch(e){}}return mem.user}
function setUser(u){mem.user=u;store("mvbd_user",u?JSON.stringify(u):null)}

function go(v){
  if(v==="movie")v="home";if(views.indexOf(v)<0)v="home";curV=v;document.body.setAttribute("data-v",v);
  views.forEach(function(x){var e=$("v-"+x);e.classList.toggle("hide",x!==v);if(x===v){e.style.animation="none";void e.offsetHeight;e.style.animation=""}});
  document.querySelectorAll("#nav button").forEach(function(b){b.classList.toggle("on",b.dataset.go===v)});
  if(v!=="home"&&$("q").value){$("q").value="";$("q").oninput()}
  if(v==="profile"){PV="main";renderProfile()}if(v==="saved")renderSaved();
  if(v==="subs")renderPlans();if(v==="req")renderReq();if(v==="dl")renderDlPage();if(v==="hist")renderHistPage();if(v==="likes")renderLikePage();
  if(location.hash!=="#"+v){try{location.hash=v}catch(e){}}
  window.scrollTo(0,0);
  aiVis();
  if(window.posLens)posLens();
}
function aiVis(){
  var show=!$("app").classList.contains("hide")&&(curV==="home"||curV==="series"||curV==="anime")&&$("rv").classList.contains("hide");
  $("aiB").classList.toggle("hide",!show);
  if(!show)$("aiP").classList.add("hide");
}
function enter(t){$("landing").classList.add("hide");$("app").classList.remove("hide");$("aiB").classList.remove("hide");document.body.classList.add("inapp");go(t||(location.hash||"#home").slice(1));countUp()}

var mode="login";
function accs(){try{return JSON.parse(store("mvbd_accs")||"[]")}catch(e){return mem.accs||[]}}
function saveAccs(a){mem.accs=a;store("mvbd_accs",JSON.stringify(a))}
$("visitBtn").onclick=function(){enter("home")};
document.querySelectorAll(".lcard").forEach(function(c){c.onclick=function(){enter(c.dataset.enter)}});
document.querySelectorAll("[data-go]").forEach(function(b){b.onclick=function(){go(b.dataset.go)}});
$("logoBox").onclick=function(){go("home")};
$("dots").onclick=function(e){e.stopPropagation();$("menu").classList.toggle("hide")};
document.addEventListener("click",function(e){if(e.target.closest&&e.target.closest("#aiB,#aiP"))return;$("menu").classList.add("hide")});
function applyTheme(t){document.documentElement.setAttribute("data-theme",t);store("mvbd_theme",t);var m=document.querySelector("meta[name=theme-color]");if(m)m.setAttribute("content",t==="dark"?"#0a0a0a":"#f5f5f5");var c=document.getElementById("sT");if(c)c.checked=t==="dark";var md=document.getElementById("mDark");if(md)md.textContent=t==="dark"?"☀️ Light mode":"🌙 Dark mode"}
var st=store("mvbd_theme");
applyTheme(st||((window.matchMedia&&matchMedia("(prefers-color-scheme: light)").matches)?"light":"dark"));

var LOGO='<svg viewBox="0 0 220 100" xmlns="http://www.w3.org/2000/svg"><path d="M44 22 36 8M60 22 68 8" stroke="#3ddc84" stroke-width="4" stroke-linecap="round" fill="none"/><rect x="24" y="22" width="56" height="44" rx="11" fill="#3ddc84"/><rect x="31" y="29" width="42" height="30" rx="7" style="fill:var(--bg)"/><path d="M46 36 61 44 46 52Z" fill="#3ddc84"/><text x="86" y="62" font-family="Impact,Arial Black,sans-serif" font-size="46" font-weight="900" fill="currentColor" stroke="#3ddc84" stroke-width="1.5">MVBD</text><text x="150" y="82" font-family="Arial,sans-serif" font-size="12" font-weight="700" fill="#3ddc84" letter-spacing="4">STUDIO</text></svg>';
function fb(img,box){var f=function(){img.style.display="none";box.innerHTML=LOGO;box.classList.remove("hide")};img.onerror=f;if(img.complete&&img.naturalWidth===0)f()}
fb($("logoImg"),$("logoTx"));


/* Bangla search: Bangla letters are turned into English sounds, so Bangla and English give the same results */
var BNM={"ক":"k","খ":"k","গ":"g","ঘ":"g","ঙ":"ng","চ":"c","ছ":"c","জ":"j","ঝ":"j","ঞ":"n","ট":"t","ঠ":"t","ড":"d","ঢ":"d","ণ":"n","ত":"t","থ":"t","দ":"d","ধ":"d","ন":"n","প":"p","ফ":"f","ব":"b","ভ":"b","ম":"m","য":"j","র":"r","ল":"l","শ":"s","ষ":"s","স":"s","হ":"","ড়":"r","ঢ়":"r","য়":"","ৎ":"t","ং":"ng","ঃ":"","ঁ":"","ক্ষ":"ks"};
var BNA={"ভারত":"india","ভারতীয়":"india","আমেরিকা":"usa","যুক্তরাষ্ট্র":"usa","ব্রিটেন":"uk","বাংলাদেশি":"bangladesh","কোরিয়া":"korea","ইংল্যান্ড":"uk","জাপানি":"japan","চীন":"china","ফ্রান্স":"france","স্পেন":"spain","থাইল্যান্ড":"thailand","ব্রাজিল":"brazil"};
function bn2en(t){
  t=t.normalize("NFD").replace(/য়/g,"").replace(/ড়/g,"র").replace(/ঢ়/g,"র").replace(/শ্য/g,"শ").replace(/ক্ষ/g,"ks").replace(/ঞ্জ/g,"ng").replace(/ৎ/g,"ত");
  var o="";
  for(var i=0;i<t.length;i++){var c=t[i];
    if(c==="য"&&i>0&&t[i-1]==="্"){continue}
    if(BNM[c]!==undefined)o+=BNM[c];
    else if(/[\u0980-\u09FF]/.test(c))o+="a";
    else o+=c.toLowerCase();
  }
  return o;
}
function sKey(t){
  t=t.toLowerCase().replace(/[^a-z0-9 ]+/g," ").replace(/\bkn/g,"n").replace(/\bwr/g,"r");
  t=t.replace(/(tion|sion)/g,"shn").replace(/igh/g,"i").replace(/ph/g,"f").replace(/ck/g,"k").replace(/qu/g,"k").replace(/(th|dh|kh|gh|bh)/g,function(x){return x[0]}).replace(/sh/g,"s").replace(/ch/g,"C");
  t=t.replace(/c(?=[eiy])/g,"s").replace(/c/g,"k").replace(/C/g,"c").replace(/q/g,"k").replace(/x/g,"ks").replace(/z/g,"j").replace(/v/g,"b");
  t=t.replace(/[aeiouyhw ]/g,"").replace(/(.)\1+/g,"$1");
  return t;
}
$("q").oninput=function(){
  var f=this.value.trim().toLowerCase();
  if(f&&$("v-home").classList.contains("hide"))go("home");
  var ws=f.split(/\s+/).filter(Boolean);
  var res=f?ALL.filter(function(m){var n=(m[0]+' '+m[4]).toLowerCase();var nk=n.split(/[^a-z0-9]+/).filter(Boolean).map(sKey);return ws.every(function(w){if(n.indexOf(w)>-1)return true;if(!/[\u0980-\u09FF]/.test(w))return false;if(BNA[w]&&n.indexOf(BNA[w])>-1)return true;var k=sKey(bn2en(w));if(!k)return false;return nk.some(function(x){return k.length>1?x.indexOf(k)===0:x===k})})}):movies;
  $("hm").classList.toggle("hide",!!f);$("rs2").classList.toggle("hide",!f);
  draw(res,"grid");$("none").classList.toggle("hide",res.length>0||!f);
};
window.addEventListener("hashchange",function(){if($("app").classList.contains("hide"))return;var h=(location.hash||"#home").slice(1);if(h==="movie")h="home";if(h!==curV)go(h)});

var plans=[["Free","৳0","480p • 1 device • With ads"],["Basic","৳49","720p • 1 device"],["Standard","৳99","1080p • 2 devices • No ads"],["Premium","৳149","4K • 4 devices • No ads • Downloads"]];
function renderPlans(){
  var cur=dget("plan","Free");
  $("plans").innerHTML=plans.map(function(p,i){return '<div class="plan'+(p[0]==="Standard"?' pop':'')+(p[0]==="Premium"?' prm':'')+(p[0]==="Basic"?' bsc':'')+'" style="animation-delay:'+i*100+'ms"><h3>'+(p[0]==="Premium"?"👑 ":"")+p[0]+'</h3><b>'+p[1]+'<small>/month</small></b><p>'+p[2]+'</p><button class="btn" data-plan="'+p[0]+'">'+(cur===p[0]?"Current plan ✓":"Choose")+'</button></div>'}).join("");
  document.querySelectorAll("[data-plan]").forEach(function(b){b.onclick=function(){dset("plan",b.dataset.plan);pushN("👑 Plan: "+b.dataset.plan,"আপনার প্ল্যান "+b.dataset.plan+" এ বদলেছে।");renderPlans();updBadge()}});
}
draw(movies,"grid");var RL=[["🔥","Action"],["❤️","Romance"],["🕵️","Thriller"],["🎭","Drama"],["👻","Horror"],["🚀","Sci-Fi"],["🐉","Fantasy"],["⚽","Sports"],["🥷","Anime"],["💥","Blast"],["🌧️","Mood"],["👑","Royal"]];
function drawReels(){$("gridR").innerHTML=RL.map(function(r,i){return '<div class="mv" data-i="'+i+'" style="animation-delay:'+Math.min(i*45,900)+'ms;background:linear-gradient(transparent 40%,#000c),hsl('+hues[i%8]+',45%,28%)"><em>'+r[0]+'</em><b style="text-align:center">▶ '+r[1]+'</b></div>'}).join("")}
drawReels();
var REELM=RL.map(function(r){return[r[1]+" Reel","Reel","",r[0],"Reels"]});
function rIdx(m){return REELM.indexOf(m)}

/* ===== v2: hero, carousels, reviews, draggable AI ===== */
var aiMoved=0;
document.addEventListener("keydown",function(e){if(e.key==="Escape"){$("menu").classList.add("hide");$("aiP").classList.add("hide");if(!$("md").classList.contains("hide"))closeMovie()}});

/* movie details + Watch Now. Add video links here: VIDEOS["Roid"]="https://.../roid.mp4" */
var VIDEOS={};
var GEN={"Half CA – Season 1":["Drama","Comedy"],"Half CA – Season 2":["Drama","Comedy"],"Front of the Class":["Drama"],"Roid":["Thriller","Drama"],"Bijoyar Pore":["Drama","Sports"],"Action Hero":["Action","Comedy"],"Mystery Night":["Thriller"],"Dark Waters":["Thriller"],"Last Train":["Thriller","Action"],"Desert Storm":["Action"],"Love in Dhaka":["Romance"],"Shadow Game":["Thriller","Drama"],"Red Alert":["Action","Thriller"],"Silent Voice":["Drama","Romance"],"The Heist":["Action","Thriller"],"Monsoon Tale":["Romance","Drama"],"Iron City":["Sci-Fi","Action"],"Ghost House":["Horror"],"Final Kick":["Sports","Drama"],"Royal Blood":["Drama","Thriller"],"Blade Spirit":["Anime","Action"],"Moon Knight Saga":["Anime","Fantasy"],"Elf Chronicles":["Anime","Fantasy"],"Dragon Gate":["Anime","Fantasy","Action"],"Ninja Rising":["Anime","Action"],"Star Pilot":["Anime","Sci-Fi"],"Sakura Days":["Anime","Romance"],"Mecha Zero":["Anime","Sci-Fi","Mecha"],"Night Strike – Season 1":["Action","Thriller","Crime"],"Iron Squad – Season 2":["Action","Superhero"],"Dhaka Shadows – Season 1":["Thriller","Drama","Crime"],"Bonolota – Season 1":["Romance","Drama","Family"],"Seoul Hearts – Season 1":["Romance","Drama"],"Midnight Seoul – Season 2":["Thriller","Mystery"],"Mumbai Files – Season 1":["Thriller","Action","Crime"],"Chai and Chaos – Season 3":["Comedy","Family"],"Haunted Hill – Season 1":["Horror","Supernatural"],"Dark Corridor – Season 2":["Horror","Mystery"],"Galaxy Wars – Season 1":["Sci-Fi","Action","Adventure"],"Cyber Pulse – Season 2":["Sci-Fi","Thriller"],"Laugh Factory – Season 1":["Comedy"],"Office Drama – Season 4":["Comedy","Drama"],"Family Ties BD – Season 2":["Drama","Family"],"Courtroom Truth – Season 1":["Drama","Thriller","Crime"],"Dragon Realm – Season 1":["Fantasy","Action","Adventure"],"Crystal Kingdom – Season 2":["Fantasy","Adventure"],"Golden Goal – Season 1":["Sports","Drama"],"Cricket Fever – Season 2":["Sports"],"Royal Court – Season 1":["Drama","Romance","Historical"],"Spy Games – Season 3":["Action","Thriller","Mystery"],"Desert Rose – Season 1":["Romance","Drama","Historical"],"Zombie Zone – Season 1":["Horror","Action","Supernatural"],"Tokyo Detective – Season 2":["Thriller","Mystery","Crime"],"Love Letters BD – Season 1":["Romance"],"Mafia City – Season 2":["Action","Drama","Crime"],"Space Colony – Season 1":["Sci-Fi","Drama","Adventure"],"Spirit Academy":["Anime","School","Magic","Shounen"],"Isekai Blacksmith":["Anime","Isekai","Fantasy","Adventure"],"Reborn Hero Chronicle":["Anime","Isekai","Action"],"Quiet Afternoon":["Anime","Slice of Life"],"Cafe Under Rain":["Anime","Slice of Life","Romance"],"Steel Titan X":["Anime","Mecha","Sci-Fi","Action"],"Mecha Academy":["Anime","Mecha","School"],"Demon Hunter Rei":["Anime","Supernatural","Action","Shounen"],"Shadow Exorcist":["Anime","Supernatural","Horror"],"Wizard Kingdom Tale":["Anime","Magic","Fantasy","Adventure"],"Phoenix Warriors":["Anime","Shounen","Action","Adventure"],"Pirate Skies":["Anime","Adventure","Shounen"],"Love After Class":["Anime","Romance","School"],"Samurai Dawn":["Anime","Action","Historical"],"Panda Detective":["Anime","Mystery","Comedy","Family"],"Lotus Immortal":["Anime","Fantasy","Magic"],"Hero Academy Rise":["Anime","Superhero","School","Shounen"],"Cyber Samurai 2099":["Anime","Sci-Fi","Action"],"Neko Cafe Days":["Anime","Slice of Life","Comedy","Family"],"Haunted Shrine":["Anime","Horror","Supernatural"],"Crimson Case Files":["Anime","Crime","Mystery"],"Football Dreams":["Anime","Sports","Shounen"],"Shonar Bangla Quest":["Anime","Adventure","Fantasy"],"Padma Spirit Saga":["Anime","Supernatural","Family"],"Jadur Pathshala":["Anime","Magic","School"],"Dhaka Ninja Boy":["Anime","Action","Shounen"]};
var GX={"Mystery Night":["Mystery","Crime"],"Dark Waters":["Mystery"],"The Heist":["Crime"],"Red Alert":["Crime"],"Action Hero":["Superhero","Adventure"],"Desert Storm":["Adventure","Historical"],"Royal Blood":["Historical"],"Iron City":["Superhero"],"Front of the Class":["Family"],"Half CA – Season 1":["Family"],"Half CA – Season 2":["Family"],"Silent Voice":["Family"],"Last Train":["Mystery"],"Ghost House":["Supernatural"],"Dragon Gate":["Adventure","Supernatural"],"Elf Chronicles":["Adventure","Magic"],"Moon Knight Saga":["Supernatural","Magic"],"Blade Spirit":["Shounen","Supernatural"],"Ninja Rising":["Shounen","Adventure"],"Star Pilot":["Adventure"],"Sakura Days":["Slice of Life","School"]};Object.keys(GX).forEach(function(k){GEN[k]=(GEN[k]||[]).concat(GX[k])});
var curM=null;
function movieOf(c){var b=null;ALL.forEach(function(m){if(c.textContent.indexOf(m[0])>-1&&(!b||m[0].length>b[0].length))b=m});return b}
function openMovie(m){
  curM=m;var h=hues[ALL.indexOf(m)%8];
  $("mdh").style.background="linear-gradient(transparent 45%,var(--bg)),radial-gradient(circle at 50% 40%,hsl("+h+",60%,38%),hsl("+(h+70)+",50%,14%))";
  $("mdh").innerHTML=m[3];
  $("mdt").textContent=m[0];
  $("mdm").textContent=m[1]+" • "+m[4]+" • ⭐ IMDb "+m[2];
  $("mdg").innerHTML=(GEN[m[0]]||[]).map(function(g){return '<span class="gt">'+g+'</span>'}).join("");
  $("md").classList.remove("hide");$("md").scrollTop=0;
}

/* category: pick a style, get matching movies */
/* featured buttons + Continue Watching (remembers the last movie / video position) */
var RV;try{RV=JSON.parse(store("mvbd_rv")||"null")}catch(e){}
RV=RV||[{n:"Rahim",m:"Bijoyar Pore",s:5,t:"দারুণ মুভি! কোয়ালিটি অসাধারণ।"},{n:"Sara",m:"Dragon Gate",s:5,t:"Best anime collection, smooth streaming."},{n:"Tanvir",m:"Love in Dhaka",s:4,t:"সুন্দর গল্প, দ্রুত লোড হয়।"}];
var RI=0;
rvShow(0);

setInterval(function(){rvShow(RI+1)},6000);
/* draggable AI button: drag anywhere, position is remembered */
(function(){
  var b=$("aiB"),sx,sy,ox,oy,dn=0;
  function put(x,y){x=Math.max(0,Math.min(innerWidth-b.offsetWidth,x));y=Math.max(0,Math.min(innerHeight-b.offsetHeight,y));b.style.left=x+"px";b.style.top=y+"px";b.style.right="auto";b.style.bottom="auto"}
  b.addEventListener("pointerdown",function(e){dn=1;aiMoved=0;sx=e.clientX;sy=e.clientY;var r=b.getBoundingClientRect();ox=r.left;oy=r.top;b.setPointerCapture(e.pointerId)});
  b.addEventListener("pointermove",function(e){if(!dn)return;var dx=e.clientX-sx,dy=e.clientY-sy;if(!aiMoved&&Math.abs(dx)+Math.abs(dy)<8)return;aiMoved=1;put(ox+dx,oy+dy)});
  b.addEventListener("pointerup",function(){dn=0;if(aiMoved){var r=b.getBoundingClientRect();store("mvbd_ai",r.left+","+r.top)}});
  
  window.addEventListener("resize",function(){if(b.style.left){var r=b.getBoundingClientRect();put(r.left,r.top)}});var p=(store("mvbd_ai")||"").split(",");if(p.length===2)put(+p[0],+p[1]);
})();


function toast(t){var e=$("toast");e.textContent=t;e.classList.remove("hide");clearTimeout(e.t);e.t=setTimeout(function(){e.classList.add("hide")},1800)}

/* ===== Reels viewer ===== */
var R={i:0,p:1},rLast=Date.now();
function rTitle(i){return RL[i][1]+" Reel"}
function updReel(){var t=rTitle(R.i),l=liked().indexOf(t)>-1,sv=saved().indexOf(t)>-1;$("rlk").innerHTML=(l?"❤️":"🤍")+"<small>"+fmtN(likeCount(t))+"</small>";$("rlk").classList.toggle("on",l);$("rsv").innerHTML="🔖<small>"+(sv?"Saved":"Save")+"</small>";$("rsv").classList.toggle("on",sv)}
function rview(dir){
  rLast=Date.now();var m=RL[R.i],h=hues[(R.i+R.p)%8];
  var s=$("rs");
  s.style.background="radial-gradient(circle at 50% 35%,hsl("+h+",55%,32%),#000 75%)";
  s.className="";void s.offsetWidth;
  if(dir)s.className=dir>0?"sU":"sD";
  s.innerHTML='<div class="big">'+m[0]+'</div><h2>'+esc(m[1])+'</h2>';
  $("rc").textContent="";addHist(rTitle(R.i),0);updReel();
  $("rp").innerHTML=[1,2,3,4,5,6].map(function(n){return '<button data-p="'+n+'" class="'+(n===R.p?"on":"")+'">●</button>'}).join("");
}
function openReel(i){R.i=i;R.p=1;$("rv").classList.remove("hide");document.body.classList.add("lock");$("aiP").classList.add("hide");$("aiB").classList.add("hide");rview(0)}
function closeReel(){$("rv").classList.add("hide");document.body.classList.remove("lock");aiVis()}
function stepReel(d){R.i=(R.i+d+RL.length)%RL.length;R.p=1;rview(d)}
$("gridR").addEventListener("click",function(e){var c=e.target.closest(".mv");if(c)openReel(+c.dataset.i)});
$("rp").addEventListener("click",function(e){
  var b=e.target.closest("button");if(!b)return;
  var n=+b.dataset.p;
  R.p=n;rview(0);
});
$("rx").onclick=closeReel;
$("rlk").onclick=function(e){e.stopPropagation();rLast=Date.now();var t=rTitle(R.i),a=liked(),i=a.indexOf(t),m=lcMap();if(i>-1){a.splice(i,1);m[t]=(m[t]||0)-1;0}else{a.push(t);m[t]=(m[t]||0)+1;0}dset("liked",a);lcSet(m);updReel()};
$("rsv").onclick=function(e){e.stopPropagation();rLast=Date.now();var t=rTitle(R.i),a=saved(),i=a.indexOf(t);if(i>-1){a.splice(i,1);0}else{a.push(t);0}setSaved(a);updReel()};
$("ra").addEventListener("touchstart",function(e){e.stopPropagation()},{passive:true});
$("ra").addEventListener("touchend",function(e){e.stopPropagation()},{passive:true});
setInterval(function(){if(!$("rv").classList.contains("hide")&&0)stepReel(1)},1000);
$("ru").onclick=function(){stepReel(-1)};
$("rd").onclick=function(){stepReel(1)};
var ty=null;
$("rv").addEventListener("touchstart",function(e){ty=e.touches[0].clientY},{passive:true});
$("rv").addEventListener("touchend",function(e){if(ty===null)return;var dy=e.changedTouches[0].clientY-ty;ty=null;if(Math.abs(dy)>60)stepReel(dy<0?1:-1)},{passive:true});
var wLk=0;$("rv").addEventListener("wheel",function(e){e.preventDefault();var n=Date.now();if(n-wLk<420)return;wLk=n;stepReel(e.deltaY>0?1:-1)},{passive:false});
document.addEventListener("keydown",function(e){if($("rv").classList.contains("hide"))return;if(e.key==="Escape")closeReel();if(e.key==="ArrowDown")stepReel(1);if(e.key==="ArrowUp")stepReel(-1)});

/* ===== AI Moderator ===== */
var KB=[
[["plan","price","dam","দাম","subscription","premium","basic","standard","free","taka","৳","প্ল্যান","cost"],"আমাদের প্ল্যান (প্রতি মাসে):\n🆓 Free ৳0 — 480p, ১ ডিভাইস, বিজ্ঞাপনসহ\n⭐ Basic ৳49 — 720p, ১ ডিভাইস\n🔥 Standard ৳99 — 1080p, ২ ডিভাইস, নো অ্যাড\n👑 Premium ৳149 — 4K, ৪ ডিভাইস, নো অ্যাড, ডাউনলোড","Our plans (per month):\n🆓 Free ৳0 — 480p, 1 device, with ads\n⭐ Basic ৳49 — 720p, 1 device\n🔥 Standard ৳99 — 1080p, 2 devices, no ads\n👑 Premium ৳149 — 4K, 4 devices, no ads, downloads"],
[["download","ডাউনলোড"],"ডাউনলোড সুবিধা শুধু Premium প্ল্যানে (৳149/মাস) আছে।","Downloads are available only on the Premium plan (৳149/month)."],
[["ads","বিজ্ঞাপন","advert"],"Standard ও Premium প্ল্যানে কোনো বিজ্ঞাপন নেই। Free প্ল্যানে বিজ্ঞাপন থাকে।","Standard and Premium have no ads. The Free plan shows ads."],
[["4k","hd","quality","কোয়ালিটি","1080","720","480"],"Free 480p, Basic 720p, Standard 1080p এবং Premium 4K কোয়ালিটি পায়।","Free gets 480p, Basic 720p, Standard 1080p and Premium 4K."],
[["device","ডিভাইস"],"Free ও Basic: ১ ডিভাইস, Standard: ২ ডিভাইস, Premium: ৪ ডিভাইস।","Free and Basic: 1 device, Standard: 2 devices, Premium: 4 devices."],
[["account","signup","sign up","login","log in","register","profile","password","অ্যাকাউন্ট","লগইন","একাউন্ট"],"Profile ট্যাবে 'Create account' চাপুন। নাম, email ও password (কমপক্ষে ৪ অক্ষর) দিন। পরে Login করে Bio সেভ করতে পারবেন।","Open the Profile tab and tap 'Create account'. Enter your name, email and a password (min 4 characters). Then you can log in and save your Bio."],
[["search","খুঁজ","সার্চ","find"],"উপরের সার্চ বারে মুভি, অ্যানিমে বা দেশের নাম লিখলেই রেজাল্ট দেখাবে।","Type a movie, anime or country name in the search bar at the top to see results."],
[["country","দেশ","origin"],"প্রতিটি পোস্টারের নিচে মুভির দেশের নাম দেওয়া আছে। সার্চে দেশের নাম লিখেও খুঁজতে পারবেন।","Each poster shows the movie's country at the bottom. You can also search by country name."],
[["anime","অ্যানিমে","এনিমে"],"নিচের নেভিগেশনে Anime ট্যাবে সব অ্যানিমে পাবেন।","Find all anime in the Anime tab in the bottom navigation."],
[["reel","রিল"],"নিচের নেভিগেশনে Reels ট্যাবে কোনো রিলে ক্লিক করলে রিল চলে। swipe করলে নতুন রিল আসে।","In the Reels tab tap a reel to play it. Swipe to get the next reel."],
[["contact","call","phone","number","whatsapp","email","gmail","যোগাযোগ","নম্বর","ফোন","facebook","instagram"],"পেজের নিচে 'Contact Us' সেকশনে Call (01874743206), WhatsApp, Telegram, Gmail, Facebook, Threads, Instagram, X, TikTok ও YouTube এর আইকন আছে।","See 'Contact Us' at the bottom of the page for icons of Call (01874743206), WhatsApp, Telegram, Gmail, Facebook, Threads, Instagram, X, TikTok and YouTube."],
[["terms","শর্ত","service"],"পেজের নিচে Contact Us এর নিচে 'Terms of Service' আছে।","Find 'Terms of Service' at the bottom of the page, below Contact Us."],
[["privacy","গোপনীয়","policy","নীতি"],"পেজের নিচে Contact Us এর নিচে 'Privacy Policy' আছে। আমরা আপনার তথ্য বিক্রি করি না।","Find 'Privacy Policy' at the bottom of the page, below Contact Us. We do not sell your personal information."],
[["dark","light","theme","মোড"],"Profile → Settings থেকে Dark/Light mode বদলাতে পারবেন।","Switch Dark/Light mode from Profile → Settings."],
[["early","access"],"Premium সদস্যরা নতুন কনটেন্ট Early access এ পান।","Premium members get early access to new content."],
[["thanks","thank","ধন্যবাদ","shukriya"],"আপনাকেও ধন্যবাদ! 😊 আর কিছু জানতে চাইলে বলুন।","You're welcome! 😊 Ask me anything else."],
[["hi","hello","hey","salam","সালাম","হ্যালো","হাই"],"হ্যালো! 👋 আমি MVBD+ AI Moderator। মুভি, প্ল্যান, অ্যাকাউন্ট বা যোগাযোগ নিয়ে প্রশ্ন করুন।","Hello! 👋 I'm the MVBD+ AI Moderator. Ask me about movies, plans, accounts or contact."],
[["mvbd","about","what is","platform","সম্পর্কে","কী এটা","কি এটা"],"MVBD+ হলো মুভি, সিরিজ ও অ্যানিমে স্ট্রিমিং প্ল্যাটফর্ম। এখন 3652+ মুভি ও সিরিজ আছে, সব এক জায়গায়।","MVBD+ is a movie, series and anime streaming platform with 3652+ titles, all in one place."]
];
var AIQ=["Plans কত? / Plans?","Create account","Download?","Contact","Roid movie ache?"];
function addM(t,c){var d=document.createElement("div");d.className="m "+c;d.textContent=t;$("aiM").appendChild(d);$("aiM").scrollTop=1e5}
function isBn(t){return /[\u0980-\u09FF]/.test(t)}
var BNW=["koto","kemon","kivabe","kibhabe","ache","achhe","dam","kothay","ki","koro","nei","ase"];
function norm(s){return s.toLowerCase().replace(/[^a-z0-9\u0980-\u09FF]+/g," ").trim()}
var INTENT=["movie","film","series","anime","মুভি","সিরিজ","সিনেমা","ache","achhe","ase","আছে","নেই","নাই","nei","nai","available","dekhte","dekhbo","upload","have"];
var STOP=INTENT.concat(["ki","kono","ba","is","there","you","do","any","a","the","this","er","ar","কি","কী","কোনো","এই","একটা","does","got","kon","ta","ti","tar","name","naam","নাম"]);
function titleMatch(n){return ALL.filter(function(m){return (" "+n+" ").indexOf(" "+norm(m[0])+" ")>-1})}
function partialMatch(n){
  var tk=n.split(" ").filter(function(w){return w&&STOP.indexOf(w)<0&&w.length>=3});
  if(!tk.length)return [];
  return ALL.filter(function(m){var ws=norm(m[0]).split(" ");return tk.every(function(t){return ws.some(function(w){return w.indexOf(t)===0})})});
}
function has(l,k){
  if(/^[a-z0-9]+$/.test(k)&&k.length<=3)return l.indexOf(" "+k+" ")>-1;
  return l.indexOf(k)>-1;
}
function kbAns(l,bn){
  for(var i=0;i<KB.length;i++){
    if(KB[i][0].some(function(k){return has(l,k)}))return bn?KB[i][1]:KB[i][2];
  }
  return null;
}
function openAI(){
  if(document.activeElement&&document.activeElement.blur&&!document.activeElement.closest("#aiP"))document.activeElement.blur();
  $("aiP").classList.remove("hide");
  if(!$("aiM").children.length)addM("হ্যালো! 👋 আমি MVBD+ AI Moderator। কোনো মুভির নাম লিখে জিজ্ঞাসা করুন, আছে কিনা বলে দেব।\nHi! Ask me about any movie name, plans or account. I can answer in English or Bangla.","b");
}
$("aiB").onclick=function(){if(aiMoved){aiMoved=0;return}if($("aiP").classList.contains("hide"))openAI();else $("aiP").classList.add("hide")};
$("aiX").onclick=function(){$("aiP").classList.add("hide")};
$("aiF").addEventListener("submit",function(e){e.preventDefault();var i=$("aiI"),v=i.value;i.value="";ask(v)});
$("aiQ").innerHTML=AIQ.map(function(q,i){return '<button type="button" data-q="'+i+'">'+esc(q)+'</button>'}).join("");
$("aiQ").addEventListener("click",function(e){var b=e.target.closest("button");if(!b)return;openAI();ask(AIQ[+b.dataset.q])});
/* ===== v3: Movie/Anime pages, My List, auto-loop rows, All category ===== */
var curV="";
function isA(m){return anime.indexOf(m)>-1}
function byRate(l){return l.slice().sort(function(a,b){return b[2]-a[2]})}
function byYear(l){return l.slice().sort(function(a,b){return (+b[1])-(+a[1])||b[2]-a[2]})}
function gf(x){return function(l){return l.filter(function(m){return (GEN[m[0]]||[]).indexOf(x)>-1})}}
function cf(x){return function(l){return l.filter(function(m){return m[4].indexOf(x)>-1})}}
var CF=[["All",function(l){return l}],["Trending Now",function(l){return byRate(l).slice(0,12)}],["Latest Movies",function(l){return byYear(l).slice(0,12)}],["Popular Movies",function(l){return byRate(l).slice(0,12)}],["Action",gf("Action")],["Romance",gf("Romance")],["Thriller",gf("Thriller")],["Horror",gf("Horror")],["Sci-Fi",gf("Sci-Fi")],["Comedy",gf("Comedy")],["Drama",gf("Drama")],["Fantasy",gf("Fantasy")],["Sports",gf("Sports")],["Animation",gf("Anime")],["Korean Movies",cf("South Korea")],["Bangla Movies",cf("Bangladesh")],["Hollywood",cf("USA")],["Bollywood",cf("India")],["Crime",gf("Crime")],["Mystery",gf("Mystery")],["Adventure",gf("Adventure")],["Family",gf("Family")],["Historical",gf("Historical")],["Superhero",gf("Superhero")],["Supernatural",gf("Supernatural")],["Shounen",gf("Shounen")],["Isekai",gf("Isekai")],["Slice of Life",gf("Slice of Life")],["Mecha",gf("Mecha")],["School",gf("School")],["Magic",gf("Magic")],["Japanese",cf("Japan")],["Chinese",cf("China")],["British",cf("UK")],["Thai",cf("Thailand")],["French",cf("France")],["Spanish",cf("Spain")],["Brazilian",cf("Brazil")],["Top Rated 8+",function(l){return byRate(l).filter(function(m){return m[2]>=8})}],["New Releases",function(l){return byYear(l).filter(function(m){return +m[1]>=2024})}],["Classics",function(l){return byYear(l).filter(function(m){return +m[1]<=2021})}],["TV Series",function(l){return l.filter(function(m){return m[0].indexOf("Season")>-1||isA(m)})}]];
var PG={"":{ds:movies,nm:"Movies",n:3652,l:"Movie &amp; Series Uploaded",sub:"Explore Movies, Series and more.",v:"v-home"},
        s:{ds:series,nm:"Series",n:series.length,l:"Series Uploaded",sub:"Binge the best Series and more.",v:"v-series"},
        a:{ds:anime,nm:"Anime",n:1248,l:"Anime Uploaded",sub:"Explore the best Anime and more.",v:"v-anime"}};

function countUp(){document.querySelectorAll(".cnt").forEach(function(el){var n=0,t=+el.dataset.n,s=Math.ceil(t/60),l=el.dataset.l;var iv=setInterval(function(){n=Math.min(t,n+s);el.textContent=n+" "+l;if(n>=t)clearInterval(iv)},20)})}
function rvShow(i){
  if(!RV.length){document.querySelectorAll(".rvbox").forEach(function(e){e.innerHTML='<p class="meta">এখনও কোনো রিভিউ নেই</p>'});return}
  RI=(i+RV.length)%RV.length;var r=RV[RI],h=(r.n.charCodeAt(0)*37)%360;
  var html='<div class="rvc"><div class="rvt"><div class="rva" style="background:linear-gradient(135deg,hsl('+h+',65%,45%),hsl('+(h+50)+',65%,32%))">'+esc(r.n.charAt(0).toUpperCase())+'</div><div class="rvn"><b>'+esc(r.n)+'</b><small>✔ Verified Member</small></div><span class="rvq">❝</span></div><p>'+esc(r.t)+'</p><div class="rvf"><span class="rvs">'+"★".repeat(r.s)+"☆".repeat(5-r.s)+'</span><span class="rvm">🎬 '+esc(r.m)+'</span></div></div><div class="rvd">'+RV.map(function(x,k){return '<span data-i="'+k+'" class="'+(k===RI?"on":"")+'"></span>'}).join("")+'</div>';
  document.querySelectorAll(".rvbox").forEach(function(e){e.innerHTML=html});
}
document.addEventListener("click",function(e){var d=e.target.closest(".rvd span");if(d)rvShow(+d.dataset.i)});

function pageHTML(p,o){
  var N=(o.rn||o.nm).toUpperCase();
  function sh(t,g){return '<div class="sh"><h3 class="t">'+t+'</h3>'+(g?'<button class="sa" data-go="'+g+'">See all ›</button>':'')+'</div>'}
  var h='<div class="feat"><span class="pill">FEATURED TODAY</span><div class="fimg" id="'+p+'hero"></div><h2>Discover Your Next Favourite</h2><p>'+o.sub+'</p><div class="fb"><button class="b1" id="'+p+'fx">Explore Now</button><button class="b2" id="'+p+'fi">More Info</button></div></div>'
  +'<h3 class="t2">🔥 Trending Now</h3><div class="row th" id="'+p+'th"></div>'
  +'<div id="'+p+'cont"></div>'
  +'<h3 class="t">ALL CATEGORY</h3><p class="note" style="padding:0 0 8px;text-align:left">আপনার পছন্দের স্টাইলের মুভি বেছে নিন</p><div class="cats" id="'+p+'cats"></div><div class="cw"><div class="row" id="'+p+'cg"></div></div>'
  +'<h3 class="t">TOP '+N+'</h3><div class="cw"><div class="row" id="'+p+'r1"></div></div>'
  +'<h3 class="t">LATEST '+N+'</h3><div class="cw"><div class="row" id="'+p+'r2"></div></div>';
  h+='<div class="cnt" data-n="'+o.n+'" data-l="'+o.l+'">'+o.n+' '+o.l+'</div>'
  +'<h3 class="t">USER REVIEWS</h3><div class="cw"><div class="rev rvbox"></div></div>';
  return h;
}
var PGS={};
function shuf(a){a=a.slice();for(var i=a.length-1;i>0;i--){var j=Math.floor(Math.random()*(i+1)),t=a[i];a[i]=a[j];a[j]=t}return a}
function initPage(p){
  var o=PG[p],ds=o.ds,rd=o.rd||ds,st={cat:0,hi:0},HL=byRate(ds).slice(0,8),FP=shuf(byRate(ds).slice(0,Math.min(24,ds.length)));
  $(p+"hm").innerHTML=pageHTML(p,o);
  function hero(i){st.hi=i;var m=FP[i],h=hues[(i+3)%8],e=$(p+"hero");e.style.background="radial-gradient(circle at 50% 40%,hsl("+h+",60%,40%),hsl("+(h+70)+",50%,12%))";e.innerHTML='<em>'+m[3]+'</em><b>'+esc(m[0])+'</b>'}
  hero(0);PGS[p]={next:function(){hero((st.hi+1)%FP.length)}};
  $(p+"th").innerHTML=HL.concat(HL).map(function(m,k){return '<div class="tw">'+card(m,k)+'<small class="tl">Trending #'+(k%HL.length+1)+'</small></div>'}).join("");
  draw(byRate(rd),p+"r1");draw(byYear(rd),p+"r2");
  var cs=CF.filter(function(x){return x[1](ds).length});
  function showCat(){
    $(p+"cats").innerHTML=cs.map(function(x,i){return '<button data-i="'+i+'" class="'+(i===st.cat?"on":"")+'">'+x[0].replace("Movies",o.nm)+'</button>'}).join("");
    draw(cs[st.cat][1](ds),p+"cg");$(p+"cg").scrollLeft=0;
  }
  $(p+"cats").onclick=function(e){var b=e.target.closest("button");if(b){st.cat=+b.dataset.i;showCat()}};
  showCat();
  $(p+"hero").onclick=$(p+"fi").onclick=function(){openMovie(FP[st.hi])};
  $(p+"fx").onclick=function(){$(p+"cg").scrollIntoView({behavior:"smooth",block:"center"})};
  setInterval(function(){if(!$("app").classList.contains("hide")&&!$(o.v).classList.contains("hide")&&!$("q").value)hero((st.hi+1)%FP.length)},5000);
}

/* Continue Watching + My List */
function byTitle(t){return ALL.filter(function(x){return x[0]===t})[0]||REELM.filter(function(x){return x[0]===t})[0]}
var SV="m";
function renderSaved(){
  var l=saved().map(byTitle).filter(function(m){return m&&(SV==="r"?REELM.indexOf(m)>-1:SV==="a"?anime.indexOf(m)>-1:SV==="s"?series.indexOf(m)>-1:movies.indexOf(m)>-1&&series.indexOf(m)<0)});
  document.querySelectorAll("#svt button").forEach(function(b){b.classList.toggle("on",b.dataset.s===SV)});
  draw(l,"sg");
  $("sn").textContent=SV==="r"?"কোনো রিল Save করা নেই। Reels এ 🔖 Save চাপুন।":SV==="a"?"কোনো অ্যানিমে Save করা নেই। ডিটেইলস পেজে ＋ Save to My List চাপুন।":SV==="s"?"কোনো সিরিজ Save করা নেই। ডিটেইলস পেজে ＋ Save to My List চাপুন।":"কোনো মুভি Save করা নেই। ডিটেইলস পেজে ＋ Save to My List চাপুন।";
  $("sn").classList.toggle("hide",l.length>0);
}
$("svt").onclick=function(e){var b=e.target.closest("button");if(b){SV=b.dataset.s;renderSaved()}};
$("v-saved").addEventListener("click",function(e){var c=e.target.closest(".mv");if(c&&c.dataset.t){var m=byTitle(c.dataset.t);if(m)openMovie(m)}});
function renderCont(){
  ["","s","a"].forEach(function(p){
    var c=$(p+"cont");if(!c)return;
    var keys=p==="a"?["a"]:["m"],l=null,m=null;
    keys.forEach(function(k){var x=lastW(k),y=x&&byTitle(x.t);if(y&&PG[p].ds.indexOf(y)>-1&&(!l||(x.ts||0)>(l.ts||0))){l=x;m=y}});
    if(!m){c.innerHTML='<h3 class="t2">▶ Continue Watching</h3><div class="cwc" style="cursor:default"><div class="cwp">🎬</div><div class="cwi"><b>এখনও কিছু দেখা হয়নি</b><small>Watch Now চাপলে এখানে আসবে</small></div></div>'}
    else{
      c.innerHTML='<h3 class="t2">▶ Continue Watching</h3><div class="cwc"><div class="cwp" style="background:hsl('+hues[ALL.indexOf(m)%8]+',45%,28%)">'+m[3]+'</div><div class="cwi"><b>'+esc(m[0])+'</b><small>Resume where you left off</small><div class="bar"><i style="width:'+(l.pct||0)+'%"></i></div></div><button class="pl">▶</button></div>';
      c.querySelector(".cwc").onclick=function(){openMovie(m);if(VIDEOS[m[0]])$("mdw").click()};
    }
  });
  renderSaved();
}

/* Movie details: Watch Now, Save, close */
function closeMovie(){$("md").classList.add("hide");$("mdh").innerHTML="";renderCont();if(curV==="profile")renderProfile();updBadge()}
$("mdx").onclick=closeMovie;
var _om=openMovie;openMovie=function(m){_om(m);updSave()};
$("mds").onclick=function(){
  var a=saved(),i=a.indexOf(curM[0]);
  if(i>-1){a.splice(i,1);0}else{a.push(curM[0]);0}
  setSaved(a);updSave();renderSaved("");renderSaved("a");
};
["v-home","v-series","v-anime"].forEach(function(id){$(id).addEventListener("click",function(e){
  var b=e.target.closest("[data-go]");if(b){go(b.dataset.go);return}
  var c=e.target.closest(".mv");if(c&&c.dataset.t){var m=byTitle(c.dataset.t);if(m)openMovie(m)}
})});

/* Rows: drag + auto-slide right-to-left, jump back to start fast at the end */
function tween(r,to,ms){
  var from=r.scrollLeft,t0=null,tk=r._tk=(r._tk||0)+1;
  function f(t){if(r._tk!==tk)return;if(t0===null)t0=t;var k=Math.min(1,(t-t0)/ms),e=k<.5?2*k*k:1-Math.pow(-2*k+2,2)/2;r.scrollLeft=from+(to-from)*e;if(k<1)requestAnimationFrame(f)}
  requestAnimationFrame(f);
}
function bindRow(r){
  if(!r||r._b)return;r._b=1;
  ["touchstart","mouseover","wheel","pointerdown"].forEach(function(ev){r.addEventListener(ev,function(){r._h=Date.now();r._tk=(r._tk||0)+1},{passive:true})});
  var d=0,x=0,l=0;
  r.onmousedown=function(e){r._dm=0;d=1;x=e.pageX;l=r.scrollLeft};
  r.onmousemove=function(e){if(d){r.scrollLeft=l-(e.pageX-x);if(Math.abs(e.pageX-x)>5)r._dm=1}};
  r.addEventListener("click",function(e){if(r._dm){e.stopPropagation();e.preventDefault();r._dm=0}},true);
  window.addEventListener("mouseup",function(){d=0});
}
setInterval(function(){
  if(document.hidden)return;
  document.querySelectorAll(".row").forEach(function(r){
    bindRow(r);
    if(r.offsetParent===null||!r.children[0]||Date.now()-(r._h||0)<4000||TD||HOV||Date.now()-(r._ls||0)<3500)return;
    r._ls=Date.now();
    if(r.classList.contains("th")){
      if(r.children.length<2)return;
      var n=r.children.length/2,s=r.children[1].offsetLeft-r.children[0].offsetLeft;
      if(r.scrollLeft>=s*n)r.scrollLeft-=s*n;
      tween(r,(Math.round(r.scrollLeft/s)+1)*s,1600);return;
    }
    var max=r.scrollWidth-r.clientWidth;if(max<6)return;
    if(r.scrollLeft>=max-4)tween(r,0,1400);
    else tween(r,Math.min(max,r.scrollLeft+r.children[0].offsetWidth+14),1600);
  });
},1000);

["","s","a"].forEach(initPage);renderCont();rvShow(RI);
document.querySelectorAll(".row").forEach(bindRow);
/* ===== v4: Profile system (per-user data) ===== */
var PV="main";
function ukey(k){var u=getUser();return "mvbd_"+k+":"+(u?u.email:"guest")}
function dget(k,d){var kk=ukey(k),s=store(kk);if(s){try{return JSON.parse(s)}catch(e){}}return mem[kk]!==undefined?mem[kk]:d}
function dset(k,v){var kk=ukey(k);mem[kk]=v;store(kk,JSON.stringify(v))}
function lastW(t){return dget("last_"+t,null)}
function saveLast(t,sv){dset("last_"+t,sv)}
function saved(){return dget("saved",[])}
function setSaved(a){dset("saved",a)}
function liked(){return dget("liked",[])}
function dls(){return dget("dl",[])}
function notifs(){return dget("notif",[])}
function isPrem(){return dget("plan","Free")==="Premium"}
function SET(){var s=dget("set",{});return{notif:s.notif!==0,auto:s.auto!==0}}
function putSet(k,v){var s=dget("set",{});s[k]=v?1:0;dset("set",s)}
function ago(ts){var s=(Date.now()-ts)/1000;if(s<60)return "Just now";if(s<3600)return Math.floor(s/60)+" min ago";if(s<86400)return Math.floor(s/3600)+" h ago";if(s<172800)return "Yesterday";return new Date(ts).toLocaleDateString()}
function addHist(t,pct){var a=dget("hist",[]).filter(function(x){return x.t!==t});a.unshift({t:t,ts:Date.now(),pct:pct||0});dset("hist",a.slice(0,50))}
function setPct(t,pct){var a=dget("hist",[]);if(a[0]&&a[0].t===t&&a[0].pct!==pct){a[0].pct=pct;dset("hist",a)}}
function seedN(){if(!getUser()||dget("notif",null)!==null)return;var n=Date.now();dset("notif",[{id:n,t:"🎉 Welcome to MVBD+",b:"আপনার অ্যাকাউন্ট তৈরি হয়েছে। Movie, Series ও Anime উপভোগ করুন।",ts:n,r:0},{id:n+1,t:"👑 Premium অফার",b:"Premium এ 4K, Downloads ও সব Movie-Anime দেখুন।",ts:n,r:0}])}
function pushN(t,b){if(!getUser()||!SET().notif)return;seedN();var a=notifs();a.unshift({id:Date.now(),t:t,b:b,ts:Date.now(),r:0});dset("notif",a.slice(0,40));updBadge()}
function updBadge(){seedN();var n=getUser()?notifs().filter(function(x){return !x.r}).length:0;$("pdot").classList.toggle("hide",!n);if($("bdot"))$("bdot").classList.toggle("hide",!n)}

/* detail page: Save / Like / Download / Watch */
$("mdw").onclick=function(){
  var ti=curM[0],t=isA(curM)?"a":"m",u=VIDEOS[ti],l=lastW(t),sv=l&&l.t===ti?l:{t:ti,pct:0,sec:0};
  sv.ts=Date.now();saveLast(t,sv);addHist(ti,sv.pct);
  if(u){
    $("mdh").style.background="#000";$("mdh").innerHTML='<video src="'+esc(u)+'" controls '+(SET().auto?"autoplay ":"")+'playsinline style="width:100%;height:100%;background:#000"></video>';
    var v=$("mdh").firstChild;v.onloadedmetadata=function(){if(sv.sec)v.currentTime=sv.sec};
    v.ontimeupdate=function(){if(v.duration){sv.sec=v.currentTime;var p=Math.round(v.currentTime/v.duration*100);sv.pct=p;saveLast(t,sv);setPct(ti,p)}};
  }else toast("▶ এই মুভির ভিডিও লিংক এখনও যোগ করা হয়নি");
};

/* auth */
async function hp(p){try{var b=await crypto.subtle.digest("SHA-256",new TextEncoder().encode("mvbd:"+p));return Array.from(new Uint8Array(b)).map(function(x){return x.toString(16).padStart(2,"0")}).join("")}catch(e){return "p:"+btoa(unescape(encodeURIComponent(p)))}}
function genUser(em){var b=uname(String(em).split("@")[0])||"user",u=b,i=1,a=accs();while(a.some(function(x){return x.username===u}))u=b+(++i);return u}
function uname(s){return String(s).toLowerCase().replace(/[^a-z0-9_.]/g,"")}
function me(){var u=getUser();if(!u)return null;if(!u.username)u.username=uname(u.email.split("@")[0])||"user";return u}
function sess(m){return{name:m.name,email:m.email,username:m.username||uname(m.email.split("@")[0]),bio:m.bio||"",av:m.av||"",joined:m.joined||Date.now()}}
function migrate(em){["saved","last_m","last_a","liked","hist","dl","plan"].forEach(function(k){var g=store("mvbd_"+k+":guest"),n="mvbd_"+k+":"+em;if(g&&!store(n))store(n,g)})}
function avt(u,sz){var h=(u.name.charCodeAt(0)*37)%360;return u.av?'<img class="avt" src="'+u.av+'" style="width:'+sz+'px;height:'+sz+'px" alt="">':'<div class="avt" style="width:'+sz+'px;height:'+sz+'px;font-size:'+Math.round(sz*.42)+'px;background:linear-gradient(135deg,hsl('+h+',65%,45%),hsl('+(h+50)+',65%,30%))">'+esc(u.name.charAt(0).toUpperCase())+'</div>'}
function authView(){
  var su=mode==="signup";
  return '<div class="box"><div class="tabs"><button data-m="login" class="'+(su?'':'on')+'">Login</button><button data-m="signup" class="'+(su?'on':'')+'">Create Account</button></div>'
  +(su?'<input class="f" id="ln" placeholder="Full name" autocomplete="name">':'')
  +'<input class="f" id="le" '+(su?'type="text" inputmode="email" placeholder="Email or Phone number"':'placeholder="Email / Phone / Username"')+' autocapitalize="none" autocomplete="'+(su?'email':'username')+'"><input class="f" id="lp" type="password" placeholder="Password" autocomplete="'+(su?'new-password':'current-password')+'"><p id="err" class="err"></p><button class="btn" id="inB" style="width:100%">'+(su?"Create Account":"Login")+'</button></div>';
}
function afterAuth(){renderProfile();renderCont();updBadge()}
function normId(v){v=v.trim().toLowerCase();if(/^\+?[\d\s\-()]{6,}$/.test(v))v=v.replace(/[\s\-()]/g,"");if(/^01\d{9}$/.test(v))v="+88"+v;else if(/^8801\d{9}$/.test(v))v="+"+v;return v}
async function doAuth(){
  var su=mode==="signup",er=$("err"),id=normId($("le").value),p=$("lp").value,a=accs(),m;
  if(su){
    var n=$("ln").value.trim(),un=genUser(id);
    if(!n||!id||!p){er.textContent="সব ঘর পূরণ করুন";return}
    if(!/^\S+@\S+\.\S+$/.test(id)&&!/^\+?\d{10,15}$/.test(id)){er.textContent="সঠিক Email বা Phone number দিন / Enter a valid email or phone";return}
    if(p.length<4){er.textContent="Password কমপক্ষে 4 অক্ষর";return}
    if(a.some(function(x){return x.email===id})){er.textContent="এই email আগের থেকেই আছে";return}
    m={name:n,email:id,username:un,pass:await hp(p),bio:"",av:"",joined:Date.now()};
    a.push(m);saveAccs(a);migrate(m.email);
  }else{
    if(!id||!p){er.textContent="সব ঘর পূরণ করুন";return}
    var h=await hp(p);
    m=a.filter(function(x){return (x.email===id||(x.username||uname(x.email.split("@")[0]))===id)&&(x.pass===h||x.pass===p)})[0];
    if(!m){er.textContent="Email/Username বা password ভুল";return}
    if(m.pass===p){m.pass=h;saveAccs(a)}
  }
  setUser(sess(m));PV="main";afterAuth();
}
function saveProf(p){var u=me(),a=accs();Object.keys(p).forEach(function(k){u[k]=p[k]});a.forEach(function(x){if(x.email===u.email)Object.keys(p).forEach(function(k){x[k]=p[k]})});saveAccs(a);setUser(u);renderProfile()}
function delAcc(){
  var u=me();if(!u||!confirm("অ্যাকাউন্ট মুছে ফেলবেন? সব ডেটা মুছে যাবে।"))return;
  saveAccs(accs().filter(function(x){return x.email!==u.email}));
  var sfx=":"+u.email;
  try{Object.keys(localStorage).forEach(function(k){if(k.slice(-sfx.length)===sfx)localStorage.removeItem(k)})}catch(e){}
  Object.keys(mem).forEach(function(k){if(k.slice(-sfx.length)===sfx)delete mem[k]});
  forgetAcc(u.email);setUser(null);mode="login";PV="main";afterAuth();
}

/* profile screens */
function ph(t){return '<div class="pph"><button class="ib sm" data-p="main">←</button><h2>'+t+'</h2></div>'}
function irow(m,sub,right,pct){var h=hues[Math.max(0,ALL.indexOf(m))%8];return '<div class="ir" data-t="'+esc(m[0])+'"><div class="irp" style="background:linear-gradient(transparent 40%,#000a),hsl('+h+',45%,30%)">'+m[3]+'</div><div class="iri"><b>'+esc(m[0])+'</b><small>'+sub+'</small>'+(pct!=null?'<div class="bar"><i style="width:'+pct+'%"></i></div><small>'+pct+'% watched</small>':'')+'</div>'+right+'</div>'}
function rmB(k,t){return '<button class="rm" data-k="'+k+'" data-rm="'+esc(t)+'">✕</button>'}
function rmItem(k,t){if(k==="liked"){var _m=lcMap();_m[t]=(_m[t]||0)-1;lcSet(_m);setTimeout(function(){refreshLk(t)},0)}dset(k,dget(k,[]).filter(function(x){return (x.t||x)!==t}))}
function pfClick(e){
  var nt=e.target.closest(".nt[data-id]");if(nt){NID=+nt.dataset.id;PV="nview";renderProfile();window.scrollTo(0,0);return}
  var rm=e.target.closest(".rm");if(rm){e.stopPropagation();rmItem(rm.dataset.k,rm.dataset.rm);renderProfile();return}
  var ir=e.target.closest(".ir");if(ir){var m=byTitle(ir.dataset.t);if(m)openMovie(m);return}
  var t=e.target.closest("[data-p]");if(!t)return;var p=t.dataset.p;
  if(p==="prem"){go("subs");return}if(p==="terms"||p==="privacy"||p==="about"){go(p);return}if(p==="help"){openAI();return}if(p==="saved"){go("saved");return}
  PV=p;renderProfile();window.scrollTo(0,0);
}
function pHist(u,b){
  var a=dget("hist",[]).map(function(x){return[byTitle(x.t),x]}).filter(function(x){return x[0]});
  b.innerHTML=ph("🕘 History")+(a.length?'<button class="btn out sm2" id="clrH">Clear History</button><div class="il">'+a.map(function(x){return irow(x[0],kindOf(x[0])+" • "+ago(x[1].ts),rmB("hist",x[0][0]),x[1].pct||0)}).join("")+'</div>':'<p class="note">এখনও কিছু দেখা হয়নি। কোনো মুভিতে Watch Now চাপলে এখানে আসবে।</p>');
  if($("clrH"))$("clrH").onclick=function(){dset("hist",[]);renderProfile()};
}
function pLiked(u,b){
  var a=liked().map(byTitle).filter(Boolean);
  b.innerHTML=ph("❤️ Liked Movies")+(a.length?'<div class="il">'+a.map(function(m){return irow(m,kindOf(m)+(m[2]!==""?" • "+m[1]+" • ⭐ "+m[2]:""),rmB("liked",m[0]))}).join("")+'</div>':'<p class="note">কোনো Like করা নেই। ডিটেইলস পেজে 🤍 Like চাপুন।</p>');
}
function pDl(u,b){
  var a=dls().map(function(x){return[byTitle(x.t),x]}).filter(function(x){return x[0]});
  b.innerHTML=ph("⬇️ Downloaded Movies")+(a.length?'<div class="il">'+a.map(function(x){return irow(x[0],"Downloaded • "+ago(x[1].ts),rmB("dl",x[0][0]))}).join("")+'</div>':'<p class="note">কোনো Download নেই। Download শুধু Premium প্ল্যানে।</p>');
}
function pNotif(u,b){
  var a=notifs(),f=a.map(function(x){return !x.r});
  a.forEach(function(x){x.r=1});dset("notif",a);
  b.innerHTML=ph("🔔 Notifications")+(a.length?'<button class="btn out sm2" id="clrN">Clear all</button><div class="il">'+a.map(function(x,i){return '<div class="nt clk'+(f[i]?' new':'')+'" data-id="'+x.id+'"><div class="nti">🔔</div><div class="ntb"><b>'+esc(x.t)+'</b><p class="cl">'+esc(x.b)+'</p><small>'+ago(x.ts)+'</small></div><span class="ar2">›</span></div>'}).join("")+'</div>':'<p class="note">কোনো নোটিফিকেশন নেই 🔕</p>');
  if($("clrN"))$("clrN").onclick=function(){dset("notif",[]);renderProfile()};
}
var NID=0;
function pNview(u,b){
  var x=notifs().filter(function(n){return n.id===NID})[0];
  if(!x){PV="notif";return pNotif(u,b)}
  b.innerHTML='<div class="pph"><button class="ib sm" data-p="notif">←</button><h2>🔔 Notification</h2></div><div class="nvw"><div class="nvi">🔔</div><h2>'+esc(x.t)+'</h2><small>'+new Date(x.ts).toLocaleString()+' • '+ago(x.ts)+'</small><p>'+esc(x.b)+'</p></div><button class="btn out" id="ndel" style="width:100%;margin-top:14px">🗑 Delete</button>';
  $("ndel").onclick=function(){dset("notif",notifs().filter(function(n){return n.id!==NID}));PV="notif";renderProfile()};
}
function sw(id,on,label){return '<div class="st"><span>'+label+'</span><label class="sw"><input type="checkbox" id="'+id+'"'+(on?" checked":"")+'><i></i></label></div>'}
function pView(u,b){
  var pl=dget("plan","Free");
  b.innerHTML=ph("👤 View Profile")+'<div class="box"><div class="pvA">'+avt(u,110)+'<div class="pvb"><label class="btn sm2" for="avf">📷 Change photo</label><input type="file" id="avf" accept="image/*" class="hide">'+(u.av?'<button class="btn out sm2" id="avr">Remove</button>':'')+'</div></div>'
  +'<label class="lb">Name</label><input class="f" id="vn" value="'+esc(u.name)+'"><label class="lb">Email / Phone</label><input class="f" value="'+esc(u.email)+'" readonly><label class="lb">Bio</label><textarea class="f" id="vb" rows="3" placeholder="নিজের সম্পর্কে লিখুন…">'+esc(u.bio||"")+'</textarea><p class="meta">Plan: <b>'+esc(pl)+'</b> • Member since '+new Date(u.joined||Date.now()).toLocaleDateString()+'</p><p id="err" class="err"></p><button class="btn" id="vs" style="width:100%">Save Changes</button></div>';
  $("avf").onchange=function(){var f=this.files[0];if(!f)return;var r=new FileReader();r.onload=function(){var im=new Image();im.onload=function(){var c=document.createElement("canvas"),s=192,m=Math.min(im.width,im.height);c.width=c.height=s;c.getContext("2d").drawImage(im,(im.width-m)/2,(im.height-m)/2,m,m,0,0,s,s);saveProf({av:c.toDataURL("image/jpeg",.82)})};im.src=r.result};r.readAsDataURL(f)};
  if($("avr"))$("avr").onclick=function(){saveProf({av:""})};
  $("vs").onclick=function(){
    var n=$("vn").value.trim(),un=u.username,er=$("err");
    if(!n){er.textContent="নাম দিন";return}
    saveProf({name:n,username:un,bio:$("vb").value});toast("✓ Profile saved");
  };
}
updBadge();
/* ===== v5: menu, downloads, likes, member reviews ===== */
$("menu").addEventListener("click",function(e){if(e.target.closest("[data-keep]"))e.stopPropagation()});
new MutationObserver(function(){document.body.classList.toggle("aiopen",!$("aiP").classList.contains("hide"))}).observe($("aiP"),{attributes:true,attributeFilter:["class"]});
new MutationObserver(function(){document.body.classList.toggle("menuopen",!$("menu").classList.contains("hide"))}).observe($("menu"),{attributes:true,attributeFilter:["class"]});
/* menu open: page behind must not scroll */
function lockMv(e){
  var t=e.target,m=$("menu");
  if(t.closest&&t.closest("#aiP,#aiB"))return;
  if(t.closest&&t.closest("#menu")&&!document.body.classList.contains("aiopen")){if(m.scrollHeight>m.clientHeight+1)return}
  if(e.cancelable)e.preventDefault();
}
var lockOn=false;
function lockSync(){
  var on=document.body.classList.contains("menuopen")||document.body.classList.contains("aiopen");
  if(on===lockOn)return;lockOn=on;
  ["touchmove","wheel"].forEach(function(ev){document[on?"addEventListener":"removeEventListener"](ev,lockMv,{passive:false})});
}
new MutationObserver(lockSync).observe(document.body,{attributes:true,attributeFilter:["class"]});
/* Menu and AI behave the same: while one is open, tapping the page behind only closes it and never triggers the page.
   While AI is open, Home and the menu stay inactive. */
document.addEventListener("click",function(e){
  var t=e.target;if(!t||!t.closest)return;
  var m=$("menu"),a=$("aiP"),mo=!m.classList.contains("hide"),ao=!a.classList.contains("hide");
  if(!mo&&!ao)return;
  if(t.closest("#aiB,#aiP"))return;
  if(ao){e.preventDefault();e.stopPropagation();a.classList.add("hide");if(!t.closest("#menu"))m.classList.add("hide");return}
  if(t.closest("#menu"))return;
  e.preventDefault();e.stopPropagation();m.classList.add("hide");
},true);
/* fallback for browsers that send no click on non-button areas */
var _pd=null;
document.addEventListener("pointerdown",function(e){_pd={x:e.clientX,y:e.clientY}},true);
document.addEventListener("pointerup",function(e){
  var a=$("aiP"),m=$("menu");if(!_pd||a.classList.contains("hide"))return;
  var dx=e.clientX-_pd.x,dy=e.clientY-_pd.y;_pd=null;
  if(dx*dx+dy*dy>100)return;
  var t=e.target;if(!t||!t.closest||t.closest("#aiB,#aiP"))return;
  var inM=!!t.closest("#menu");
  setTimeout(function(){a.classList.add("hide");if(!inM)m.classList.add("hide")},80);
},true);
/* AI button hides while scrolling, shows when page stands still */
var _scT;
window.addEventListener("scroll",function(){var b=$("aiB");b.classList.add("scr");clearTimeout(_scT);_scT=setTimeout(function(){b.classList.remove("scr")},350)},{passive:true});
/* while AI is open, nothing outside it (search bar etc.) can take focus */
document.addEventListener("focusin",function(e){var t=e.target;if(!$("aiP").classList.contains("hide")&&t.closest&&!t.closest("#aiP"))t.blur()},true);
document.addEventListener("mousedown",function(e){var t=e.target;if(!$("aiP").classList.contains("hide")&&t.closest&&!t.closest("#aiP,#aiB"))e.preventDefault()},true);
$("mDark").onclick=function(){var d=document.documentElement.getAttribute("data-theme")!=="light";applyTheme(d?"light":"dark")};
applyTheme(document.documentElement.getAttribute("data-theme")||"dark");

function updSave(){
  var t=curM[0],s=saved().indexOf(t)>-1,l=liked().indexOf(t)>-1,d=dls().some(function(x){return x.t===t});
  var a=$("mds"),b=$("mdl"),c=$("mdd");
  a.textContent=s?"✓ Saved":"🔖 Save";a.classList.toggle("on",s);
  b.innerHTML=(l?"❤️ Liked":"🤍 Like")+"<br><small>"+fmtN(likeCount(t))+"</small>";b.classList.toggle("on",l);
  c.textContent=d?"✓ Downloaded":"⬇️ Download";c.classList.toggle("on",d);
}
$("mdl").onclick=function(){
  var t=curM[0],a=liked(),i=a.indexOf(t),m=lcMap();
  if(i>-1){a.splice(i,1);m[t]=(m[t]||0)-1;0}else{a.push(t);m[t]=(m[t]||0)+1;0}
  dset("liked",a);lcSet(m);updSave();refreshLk(t);
};
$("mdd").onclick=function(){
  var t=curM[0],a=dls(),i=a.findIndex(function(x){return x.t===t});
  if(i>-1){a.splice(i,1);dset("dl",a);toast("🗑 Download সরানো হয়েছে");updSave();return}
  if(!isPrem()){toast("⬇️ Download শুধু Premium প্ল্যানে। Menu → Premium");return}
  var cn=navigator.connection;if(dget("wifi",0)===1&&cn&&cn.type==="cellular"){toast("📶 Wi-Fi only চালু আছে — Wi-Fi এ Download করুন");return}
  a.unshift({t:t,ts:Date.now()});dset("dl",a);pushN("⬇️ Downloaded",t);toast("✓ Downloaded • ⋯ মেনু → Downloads এ দেখুন");updSave();
  if(VIDEOS[t]){var l=document.createElement("a");l.href=VIDEOS[t];l.download=t;document.body.appendChild(l);l.click();l.remove()}
};

function renderDlPage(){
  var a=dls().map(function(x){return[byTitle(x.t),x]}).filter(function(x){return x[0]});
  $("v-dl").innerHTML='<h3 class="t">⬇️ DOWNLOADS</h3>'+(a.length?'<div class="il">'+a.map(function(x){return irow(x[0],"Downloaded • "+ago(x[1].ts),rmB("dl",x[0][0]))}).join("")+'</div>':'<p class="note">কোনো Download নেই। Download শুধু Premium প্ল্যানে।</p>');
}
function renderHistPage(){
  var a=dget("hist",[]).map(function(x){return[byTitle(x.t),x]}).filter(function(x){return x[0]});
  $("v-hist").innerHTML='<h3 class="t">🕘 WATCH HISTORY</h3>'+(a.length?'<button class="btn out sm2" id="clrH2">Clear History</button><div class="il">'+a.map(function(x){return irow(x[0],kindOf(x[0])+" • "+ago(x[1].ts),rmB("hist",x[0][0]),x[1].pct||0)}).join("")+'</div>':'<p class="note">এখনও কিছু দেখা হয়নি। কোনো মুভিতে Watch Now চাপলে এখানে আসবে।</p>');
  if($("clrH2"))$("clrH2").onclick=function(){dset("hist",[]);renderHistPage();if(typeof renderContinue==="function")try{renderContinue()}catch(e){}};
}
function renderLikePage(){
  var a=liked().map(byTitle).filter(Boolean);
  $("v-likes").innerHTML='<h3 class="t">❤️ MY LIKES</h3>'+(a.length?'<div class="il">'+a.map(function(m){return irow(m,kindOf(m)+(m[2]!==""?" • ⭐ "+m[2]:"")+" • ❤️ "+fmtN(likeCount(m[0])),rmB("liked",m[0]))}).join("")+'</div>':'<p class="note">কোনো Like করা নেই। মুভি খুলে 🤍 Like চাপুন।</p>');
}
["v-dl","v-likes","v-hist"].forEach(function(id){$(id).addEventListener("click",function(e){
  var rm=e.target.closest(".rm");
  if(rm){e.stopPropagation();rmItem(rm.dataset.k,rm.dataset.rm);id==="v-dl"?renderDlPage():id==="v-hist"?renderHistPage():renderLikePage();return}
  var ir=e.target.closest(".ir");if(ir){var m=byTitle(ir.dataset.t);if(m)openMovie(m)}
})});

/* member reviews on movie page */
var MRS=0;
function rvSave(){store("mvbd_rv",JSON.stringify(RV))}
function rvItem(x){
  var h=(x.n.charCodeAt(0)*37)%360,u=me(),own=u&&x.u&&x.u===u.email;
  return '<div class="mri"><div class="top"><div class="av2" style="background:hsl('+h+',60%,40%)">'+esc(x.n.charAt(0).toUpperCase())+'</div><div><b>'+esc(x.n)+'</b><small>'+(x.ts?new Date(x.ts).toLocaleDateString():"Member")+'</small></div><span class="st5">'+"★".repeat(x.s)+"☆".repeat(5-x.s)+'</span></div><p>'+esc(x.t)+'</p>'+(own?'<button class="mrd" data-ts="'+x.ts+'">🗑 Delete</button>':'')+'</div>';
}
function renderMR(){
  var t=curM[0],u=me(),all=RV.filter(function(x){return x.m===t}),own=u&&all.filter(function(x){return x.u===u.email})[0];
  MRS=own?own.s:0;
  var avg=all.length?(all.reduce(function(a,x){return a+x.s},0)/all.length).toFixed(1):null;
  var h='<h3 class="mrh">⭐ Member Reviews</h3><p class="meta">'+(avg?("★ "+avg+" / 5 • "+all.length+" review"+(all.length>1?"s":"")):"এখনও কোনো রিভিউ নেই")+'</p>';
  if(u)h+='<div class="mrf"><div class="stars" id="mrst">'+[1,2,3,4,5].map(function(n){return '<span data-s="'+n+'" class="'+(n<=MRS?"on":"")+'">★</span>'}).join("")+'</div><textarea class="f" id="mrt" rows="3" placeholder="আপনার রিভিউ লিখুন…">'+esc(own?own.t:"")+'</textarea><p class="err" id="mre"></p><button class="btn" id="mrb">'+(own?"Update Review":"Submit Review")+'</button></div>';
  else h+='<div class="mrf"><p class="meta">রিভিউ দিতে Member হতে হবে।</p><button class="btn" id="mrl">Login / Create Account</button></div>';
  h+=all.slice().reverse().slice(0,30).map(rvItem).join("");
  $("mdrv").innerHTML=h;
}
$("mdrv").addEventListener("click",function(e){
  var sp=e.target.closest("[data-s]");
  if(sp){MRS=+sp.dataset.s;document.querySelectorAll("#mrst span").forEach(function(x){x.classList.toggle("on",+x.dataset.s<=MRS)});return}
  if(e.target.id==="mrl"){closeMovie();mode="login";go("profile");return}
  var d=e.target.closest(".mrd");
  if(d){if(!confirm("রিভিউ মুছবেন?"))return;RV=RV.filter(function(x){return String(x.ts)!==d.dataset.ts});rvSave();rvShow(0);renderMR();return}
  if(e.target.id==="mrb"){
    var u=me(),er=$("mre"),tx=$("mrt").value.trim();if(!u)return;
    if(!MRS){er.textContent="স্টার দিন ⭐";return}
    if(!tx){er.textContent="কিছু লিখুন";return}
    var t=curM[0],o=RV.filter(function(x){return x.m===t&&x.u===u.email})[0];
    if(o){o.s=MRS;o.t=tx;o.ts=Date.now();o.n=u.name}else RV.push({n:u.name,m:t,s:MRS,t:tx,u:u.email,ts:Date.now()});
    rvSave();rvShow(RV.length-1);toast("✓ রিভিউ সেভ হয়েছে");renderMR();
  }
});
var _o5=openMovie;openMovie=function(m){if(m&&m[4]==="Reels"){openReel(rIdx(m));return}_o5(m);renderMR()};
var _oAI=openAI;
function placeAI(){
  var p=$("aiP"),b=$("aiB"),vw=document.documentElement.clientWidth,w=Math.min(460,vw-20),r=b.getBoundingClientRect();
  var left=(r.width&&r.left+r.width/2<vw/2)?10:vw-w-10;
  left=Math.max(10,Math.min(vw-w-10,left));
  p.style.width=w+"px";p.style.maxWidth="none";p.style.marginLeft="0";p.style.left=left+"px";p.style.right="auto";
}
openAI=function(){_oAI();placeAI()};
window.addEventListener("resize",function(){if(!$("aiP").classList.contains("hide"))placeAI()});
/* ===== v6: request page, AI tweaks, touch-safe rows ===== */
var TD=0,HOV=0,REQT="movie",REQN="";
["touchstart","pointerdown"].forEach(function(ev){document.addEventListener(ev,function(e){if(e.target.closest&&e.target.closest(".row"))TD=1},{passive:true})});
["touchend","touchcancel","pointerup","pointercancel"].forEach(function(ev){document.addEventListener(ev,function(){TD=0},{passive:true})});
document.addEventListener("mouseover",function(e){HOV=!!(e.target.closest&&e.target.closest(".row"))});
document.addEventListener("mouseleave",function(){HOV=0});
function addReqBtn(n){
  var d=document.createElement("div");d.className="m b";
  var b=document.createElement("button");b.className="btn sm2";b.textContent="📩 Request Movie / Series / Anime";
  b.onclick=function(){REQN=n||"";$("aiP").classList.add("hide");go("req")};
  d.appendChild(b);$("aiM").appendChild(d);$("aiM").scrollTop=1e5;
}
KB.unshift([["request","রিকোয়েস্ট","অনুরোধ","chai","চাই","chaibo"],"কোনো মুভি/সিরিজ/অ্যানিমে চাইলে ⋯ মেনু → 'Request Movie / Series / Anime' এ গিয়ে Movie, Series বা Anime বেছে শুধু নাম লিখে পাঠান।","To request a movie, series or anime, open the ⋯ menu → 'Request Movie / Series / Anime', choose the type and type only the name."]);
KB[KB.length-1][0].push("website","ওয়েবসাইট","সাইট");
function renderReq(){
  var u=me(),l=dget("req",[]).slice(0,30);
  var h='<h3 class="t">📩 REQUEST</h3><p class="note" style="padding:0 0 12px">কোন Movie, Series বা Anime চান? শুধু নামটি লিখুন।</p>';
  if(!u){$("v-req").innerHTML=h+'<div class="box" style="margin-top:0"><p class="meta">Request পাঠাতে Member হতে হবে।</p><button class="btn" id="reqL" style="width:100%">Login / Create Account</button></div>';return}
  h+='<div class="tabs" id="reqt"><button data-r="movie" class="'+(REQT==="movie"?"on":"")+'">🎬 Movie</button><button data-r="series" class="'+(REQT==="series"?"on":"")+'">📺 Series</button><button data-r="anime" class="'+(REQT==="anime"?"on":"")+'">⚔️ Anime</button></div>';
  h+='<div class="box" style="margin-top:0"><input class="f" id="reqn" placeholder="'+(REQT==="anime"?"Anime":REQT==="series"?"Series":"Movie")+' name" value="'+esc(REQN)+'"><p class="err" id="reqe"></p><button class="btn" id="reqb" style="width:100%">Send Request</button></div>';
  if(l.length)h+='<h3 class="t2">My Requests</h3><div class="il">'+l.map(function(x){return '<div class="nt"><div class="nti">'+(x.k==="anime"?"⚔️":x.k==="series"?"📺":"🎬")+'</div><div class="ntb"><b>'+esc(x.n)+'</b><small>'+(x.k==="anime"?"Anime":x.k==="series"?"Series":"Movie")+' • '+ago(x.ts)+'</small></div></div>'}).join("")+'</div>';
  $("v-req").innerHTML=h;
}
$("v-req").addEventListener("click",function(e){
  if(e.target.id==="reqL"){mode="login";go("profile");return}
  var t=e.target.closest("[data-r]");
  if(t){var i=$("reqn");REQN=i?i.value:"";REQT=t.dataset.r;renderReq();return}
  if(e.target.id==="reqb"){
    var n=$("reqn").value.trim();
    if(!n){$("reqe").textContent="নাম লিখুন";return}
    var a=dget("req",[]);a.unshift({n:n,k:REQT,ts:Date.now()});dset("req",a);
    pushN("📩 Request sent",n);REQN="";toast("✓ Request পাঠানো হয়েছে");renderReq();
  }
});
/* Liquid Glass nav: tap a tab, or press and slide across the bar to scrub through tabs */
(function(){
  var nav=$("nav"),lens=document.createElement("span");lens.id="lens";nav.insertBefore(lens,nav.firstChild);
  var btns=[].slice.call(nav.querySelectorAll("button[data-go]")),down=0,drag=0,sx=0,cur=null,moved=0;
  function setLens(x,w,d){lens.style.width=w+"px";lens.style.transform="translateX("+x+"px)"+""}
  function posLens(){var a=nav.querySelector("button.on");if(!a||!a.offsetWidth){lens.style.opacity=0;return}lens.style.opacity=1;setLens(a.offsetLeft,a.offsetWidth,0)}
  window.posLens=posLens;
  function under(x){var best=btns[0],bd=1e9;btns.forEach(function(b){var q=b.getBoundingClientRect(),d=Math.abs(q.left+q.width/2-x);if(d<bd){bd=d;best=b}});return best}
  nav.addEventListener("pointerdown",function(e){if(e.pointerType==="mouse"&&e.button!==0)return;down=1;drag=0;sx=e.clientX});
  nav.addEventListener("pointermove",function(e){
    if(!down)return;
    if(!drag){if(Math.abs(e.clientX-sx)<8)return;drag=1;try{nav.setPointerCapture(e.pointerId)}catch(_){}nav.classList.add("drag");lens.style.opacity=1}
    var r=nav.getBoundingClientRect(),w=btns[0].offsetWidth,x=Math.max(btns[0].offsetLeft,Math.min(btns[btns.length-1].offsetLeft,e.clientX-r.left-w/2));
    setLens(x,w,1);
    var b=under(e.clientX);if(b!==cur){cur=b;btns.forEach(function(q){q.classList.toggle("hov",q===b)})}
  });
  function end(){
    if(!down)return;down=0;
    if(drag){nav.classList.remove("drag");btns.forEach(function(q){q.classList.remove("hov")});var b=cur;cur=null;moved=1;setTimeout(function(){moved=0},80);if(b){go(b.dataset.go);featNext(b.dataset.go)}posLens()}
    drag=0;
  }
  nav.addEventListener("pointerup",end);nav.addEventListener("pointercancel",end);
  nav.addEventListener("click",function(e){if(moved){e.stopPropagation();e.preventDefault()}},true);
  window.addEventListener("resize",posLens);
  if(window.ResizeObserver)new ResizeObserver(posLens).observe(nav);
  posLens();
})();
/* Contact logos: one of each, slides left/right automatically, swipe/drag both ways, stops on touch/hover, links open on tap */
(function(){
  var el=document.getElementById("soc");if(!el)return;
  var pos=0,exp=0,hold=0,down=0,hov=0,moved=0,dir=1,wait=Date.now()+1200,t0=0,dg=0,dx=0,sl0=0;
  var RM=window.matchMedia&&matchMedia("(prefers-reduced-motion: reduce)").matches;
  var NUM="01874743206",MAIL="emonkhannnn7@gmail.com",UA=navigator.userAgent,IOS=/iPhone|iPad|iPod/.test(UA),AND=/Android/.test(UA);
  function nav(u){try{window.location.href=u}catch(_){}}
  function opn(u){var a=document.createElement("a");a.href=u;a.target="_blank";a.rel="noopener";document.body.appendChild(a);a.click();a.remove()}
  function copyT(v){try{navigator.clipboard.writeText(v).then(function(){toast("📋 "+v+" copied")},function(){toast(v)})}catch(_){toast(v)}}
  /* try each step; if the page never loses focus (nothing opened) go to the next one */
  function chain(steps,fin){
    var i=0;
    (function run(){
      var f=0,m=function(){f=1};
      window.addEventListener("blur",m);window.addEventListener("pagehide",m);document.addEventListener("visibilitychange",m);
      steps[i]();
      setTimeout(function(){
        window.removeEventListener("blur",m);window.removeEventListener("pagehide",m);document.removeEventListener("visibilitychange",m);
        if(f)return;i++;if(i<steps.length)run();else if(fin)fin();
      },800);
    })();
  }
  function topn(u){try{window.top.location.href=u}catch(_){}}
  function sheet(k){
    var old=document.getElementById("cs");if(old)old.remove();
    var c=k==="call",d=document.createElement("div");d.id="cs";
    d.innerHTML='<b>'+(c?'📞 '+NUM:'✉️ '+MAIL)+'</b>'+(c?'<a href="tel:'+NUM+'" target="_top">📞 Call now</a>':'<a href="https://mail.google.com/mail/?view=cm&fs=1&to='+MAIL+'" target="_blank" rel="noopener">✉️ Open Gmail</a>')+'<button type="button" data-c="1">📋 Copy</button><button type="button" data-x="1">✕ Close</button>';
    d.addEventListener("click",function(e){var t=e.target;if(t.dataset&&t.dataset.c)copyT(c?NUM:MAIL);if(t.dataset&&t.dataset.x)d.remove()});
    document.body.appendChild(d);
  }
  function callNow(){chain([function(){nav("tel:"+NUM)},function(){topn("tel:"+NUM)},function(){opn("tel:"+NUM)}],function(){sheet("call")})}
  function mailNow(){
    var web="https://mail.google.com/mail/?view=cm&fs=1&to="+MAIL,mt="mailto:"+MAIL;
    var st=IOS?[function(){nav("googlegmail:///co?to="+MAIL)},function(){nav(mt)},function(){opn(web)}]
      :AND?[function(){nav("intent://send?to="+MAIL+"#Intent;scheme=mailto;package=com.google.android.gm;S.browser_fallback_url="+encodeURIComponent(mt)+";end")},function(){nav(mt)},function(){opn(web)}]
      :[function(){opn(web)}];
    chain(st,function(){sheet("mail")});
  }

  function showCall(){
    var o=document.getElementById("callSheet");if(o)o.remove();
    o=document.createElement("div");o.id="callSheet";
    o.innerHTML='<div class="csb"><div class="cst">📞 Call</div><div class="csn">'+NUM+'</div><a class="btn csa" href="tel:'+NUM+'">📞 Call Now</a><button type="button" class="btn csc" id="csCopy">📋 Copy number</button><button type="button" class="csx" id="csX">Close</button></div>';
    document.body.appendChild(o);
    o.addEventListener("click",function(ev){if(ev.target===o||ev.target.id==="csX")o.remove()});
    document.getElementById("csCopy").onclick=function(){
      var ok=0;try{var t=document.createElement("textarea");t.value=NUM;t.style.cssText="position:fixed;opacity:0";document.body.appendChild(t);t.select();ok=document.execCommand("copy");t.remove()}catch(_){}
      if(!ok){try{navigator.clipboard.writeText(NUM)}catch(_){}}
      toast("📋 "+NUM+" copied");
    };
  }
  function tick(t){
    requestAnimationFrame(tick);
    var dt=Math.min(64,t-(t0||t));t0=t;
    if(!vis||!el.offsetParent||document.hidden||RM||down||hov||dg)return;
    var now=Date.now(),max=el.scrollWidth-el.clientWidth;
    if(max<3||now-hold<1800||now<wait)return;
    pos+=dir*dt*0.02;
    if(pos>=max){pos=max;dir=-1;wait=now+1500}else if(pos<=0){pos=0;dir=1;wait=now+1500}
    exp=pos;el.scrollLeft=pos;
  }
  var vis=true;if(window.IntersectionObserver)new IntersectionObserver(function(en){vis=en[0].isIntersecting}).observe(el);
  requestAnimationFrame(tick);
  el.addEventListener("scroll",function(){if(Math.abs(el.scrollLeft-exp)>2){hold=Date.now();pos=exp=el.scrollLeft}},{passive:true});
  el.addEventListener("pointerdown",function(e){if(e.pointerType!=="mouse")down=1});
  ["pointerup","pointercancel"].forEach(function(ev){window.addEventListener(ev,function(){down=0;hold=Date.now()})});
  el.addEventListener("pointerenter",function(e){if(e.pointerType==="mouse")hov=1});
  el.addEventListener("pointerleave",function(){hov=0});
  el.addEventListener("mousedown",function(e){if(e.button)return;dg=1;moved=0;dx=e.pageX;sl0=el.scrollLeft;el.classList.add("drag")});
  window.addEventListener("mousemove",function(e){
    if(!dg)return;var d=e.pageX-dx;if(Math.abs(d)>5)moved=1;
    if(moved){el.scrollLeft=sl0-d;pos=exp=el.scrollLeft;hold=Date.now()}
  });
  window.addEventListener("mouseup",function(){dg=0;el.classList.remove("drag");hold=Date.now()});
  el.addEventListener("click",function(e){
    if(moved){e.preventDefault();e.stopPropagation();moved=0;return}
    var a=e.target.closest&&e.target.closest("a");if(!a)return;
    var h=a.getAttribute("href")||"";
    if(a.classList.contains("c-call")){e.preventDefault();showCall()}else if(a.classList.contains("c-gm")){e.preventDefault();mailNow()}
  },true);
  el.addEventListener("dragstart",function(e){e.preventDefault()});
})();
/* ===== v12: placeholder cycle, edge-swipe back, AI fixes ===== */
(function(){var q=$("q"),PH=["Search…","সার্চ করুন…"],i=0;q.placeholder=PH[0];setInterval(function(){i^=1;q.placeholder=PH[i]},60000)})();



/* AI Moderator: better matching (movie / series / anime / category), keyboard-safe panel */
function kindOf(m){return m[4]==="Reels"?"Reel":isA(m)?"Anime":series.indexOf(m)>-1?"Series":"Movie"}
function movieAns(list,bn){
  return list.slice(0,4).map(function(m){var k=kindOf(m);
    return bn?("✅ Yes (হ্যাঁ), "+k+" '"+m[0]+"' ("+m[1]+") আছে।\n⭐ "+m[2]+" • "+m[4]):("✅ Yes, "+k+" '"+m[0]+"' ("+m[1]+") is available.\n⭐ "+m[2]+" • "+m[4]);
  }).join("\n\n");
}
KB.unshift([["kemon aso","kemon acho","kmn aso","how are you","কেমন আছ","কেমন আছেন"],"আমি ভালো আছি! 😊 মুভি, সিরিজ বা অ্যানিমের নাম লিখে জিজ্ঞাসা করুন।","I'm good! 😊 Ask me about any movie, series or anime."]);
var CQ=[["bangla bangladesh বাংলা bd","Bangla",cf("Bangladesh")],["korean korea কোরিয়ান","Korean",cf("South Korea")],["hindi bollywood indian india","Bollywood",cf("India")],["hollywood english","Hollywood",cf("USA")],["japanese japan","Japanese",cf("Japan")],["scifi sci","Sci-Fi",gf("Sci-Fi")]]
  .concat(["Action","Romance","Thriller","Horror","Comedy","Drama","Fantasy","Crime","Mystery","Adventure","Sports","Family","Historical","Supernatural","Isekai","Mecha"].map(function(g){return[g.toLowerCase(),g,gf(g)]}));
function catKey(words){var c=null;CQ.forEach(function(q){if(!c&&q[0].split(" ").some(function(k){return words.indexOf(k)>-1}))c=q});return c}
function catAns(words,bn){
  var c=catKey(words),scope=ALL,sl="";
  if(words.some(function(w){return w==="anime"||w==="অ্যানিমে"||w==="এনিমে"})){scope=anime;sl="Anime"}
  else if(words.some(function(w){return w==="series"||w==="সিরিজ"})){scope=series;sl="Series"}
  else if(words.some(function(w){return w==="movie"||w==="movies"||w==="film"||w==="মুভি"||w==="সিনেমা"})){scope=movies.filter(function(m){return series.indexOf(m)<0});sl="Movie"}
  if(!c&&!sl)return null;
  var list=c?c[2](scope):scope,label=((c?c[1]+" ":"")+sl).trim(),noun=sl?label:label+" titles";
  if(!list.length)return bn?"❌ No (না), এখন "+noun+" নেই। চাইলে Request করতে পারেন।":"❌ No, there is no "+noun+" right now. You can request it.";
  var top=byRate(list).slice(0,6).map(function(m){return m[0]+" ("+m[2]+")"}).join(", ");
  return bn?"✅ Yes (হ্যাঁ), "+list.length+"টি "+noun+" আছে। যেমন: "+top:"✅ Yes, we have "+list.length+" "+noun+", e.g.: "+top;
}
function ask(t){
  t=t.trim();if(!t)return;addM(t,"u");
  var n=norm(t),l=" "+t.toLowerCase().replace(/[!?.,;:]/g," ").replace(/\s+/g," ")+" ",words=n.split(" ");
  var bn=isBn(t)||BNW.some(function(w){return words.indexOf(w)>-1}),a=null,nm="";
  var hasIntent=INTENT.some(function(w){return(" "+n+" ").indexOf(" "+w+" ")>-1});
  var rest=words.filter(function(w){return w&&STOP.indexOf(w)<0});
  var hit=titleMatch(n);
  if(!hit.length&&catKey(words)&&(hasIntent||words.length<=2))a=catAns(words,bn);
  if(!a){if(!hit.length)hit=partialMatch(n);if(hit.length)a=movieAns(hit,bn)}
  if(!a&&hasIntent&&!rest.length)a=catAns(words,bn);
  if(!a)a=kbAns(l,bn);
  if(!a&&hasIntent){
    nm=rest.join(" ");
    if(nm)a=bn?("❌ No (না), '"+nm+"' নামে কোনো মুভি/সিরিজ/অ্যানিমে এখন নেই। চাইলে Request করতে পারেন।"):("❌ No, '"+nm+"' is not available right now. You can request it.");
  }
  if(!a)a=bn?"দুঃখিত, বুঝতে পারিনি। মুভি/সিরিজ/অ্যানিমের নাম, Plans, Account, Download, Quality বা Contact নিয়ে জিজ্ঞাসা করুন।\nSorry, I didn't get that.":"Sorry, I didn't get that. Ask about a movie, series or anime name, Plans, Account, Download, Quality or Contact.\nদুঃখিত, বুঝতে পারিনি।";
  var miss=/^❌/.test(a);setTimeout(function(){addM(a,"b");if(miss)addReqBtn(nm)},350);
}
if(window.visualViewport){
  var fitAI=function(){
    var p=$("aiP"),vv=window.visualViewport;if(!p)return;
    if(p.classList.contains("hide")){p.style.bottom="";p.style.height="";return}
    var kb=window.innerHeight-vv.height-vv.offsetTop;
    if(kb>80){p.style.bottom=(kb+10)+"px";p.style.height=Math.max(220,Math.min(vv.height-20,600))+"px"}
    else{p.style.bottom="";p.style.height=""}
  };
  window.visualViewport.addEventListener("resize",fitAI);window.visualViewport.addEventListener("scroll",fitAI);
  $("aiI").addEventListener("blur",function(){setTimeout(fitAI,150)});
}
/* ===== v13: voice search, profile extras, display prefs ===== */
(function(){
  var SR=window.SpeechRecognition||window.webkitSpeechRecognition,mic=$("mic"),q=$("q");
  if(!mic)return;
  var C={"ক":"k","খ":"k","গ":"g","ঘ":"g","ঙ":"n","চ":"ch","ছ":"ch","জ":"j","ঝ":"j","ঞ":"n","ট":"t","ঠ":"t","ড":"d","ঢ":"d","ণ":"n","ত":"t","থ":"t","দ":"d","ধ":"d","ন":"n","প":"p","ফ":"f","ব":"b","ভ":"v","ম":"m","য":"j","র":"r","ল":"l","শ":"sh","ষ":"sh","স":"s","হ":"h","ৎ":"t","ং":"n","ঃ":"h","ঁ":"","অ":"a","আ":"a","ই":"i","ঈ":"i","উ":"u","ঊ":"u","ঋ":"r","এ":"e","ঐ":"i","ও":"o","ঔ":"o","া":"a","ি":"i","ী":"i","ু":"u","ূ":"u","ৃ":"r","ে":"e","ৈ":"i","ো":"o","ৌ":"o","্":"","\u09BC":"","\u09DC":"r","\u09DD":"r","\u09DF":"y"};
  function bn2lat(w){return Array.from(w).map(function(c){return C[c]!==undefined?C[c]:(/[a-z]/i.test(c)?c.toLowerCase():"")}).join("")}
  function skel(w){
    w=w.toLowerCase().replace(/[^a-z]/g,"").replace(/ph/g,"f").replace(/sh/g,"S").replace(/ch/g,"C").replace(/([kgtdj])h/g,"$1").replace(/c(?=[eiy])/g,"s").replace(/[cq]/g,"k").replace(/x/g,"ks").replace(/z/g,"j").replace(/[aeiouyw]/g,"").replace(/h/g,"").replace(/(.)\1+/g,"$1");
    return w;
  }
  var STOPV={"movie":1,"movies":1,"anime":1,"series":1,"season":1,"ache":1,"আছে":1,"মুভি":1,"অ্যানিমে":1,"এনিমে":1,"সিরিজ":1,"সিনেমা":1,"দেখাও":1,"খুঁজো":1};
  var VOC=null,VK=null;
  function vocab(){
    if(VOC)return;VOC={};VK={};
    ALL.forEach(function(m){m[0].toLowerCase().split(/[^a-z0-9]+/).forEach(function(w){if(w.length>1&&!/^\d+$/.test(w)&&w!=="season")VOC[w]=(VOC[w]||0)+1})});
    Object.keys(VOC).forEach(function(w){var k=skel(w);if(k)(VK[k]=VK[k]||[]).push(w)});
  }
  function mapTok(tk){
    var low=tk.toLowerCase().replace(/[^a-z0-9\u0980-\u09FF]/g,"");
    if(!low||STOPV[low])return null;
    if(/^[a-z0-9]+$/.test(low)&&VOC[low])return low;
    var k=skel(/[\u0980-\u09FF]/.test(low)?bn2lat(low):low);if(!k)return null;
    var c=VK[k];
    if(!c&&k.length>=3){var best=null;Object.keys(VK).forEach(function(x){if(x.indexOf(k)===0&&(!best||x.length<best.length))best=x});c=best?VK[best]:null}
    if(!c)return null;
    return c.slice().sort(function(a,b){return VOC[b]-VOC[a]})[0];
  }
  function mapT(t){vocab();var o=[];t.split(/\s+/).forEach(function(w){var r=mapTok(w);if(r)o.push(r)});return o}
  function fire(){q.dispatchEvent(new Event("input",{bubbles:true}))}
  var rec=null;
  function run(lang,tried){
    var r=new SR(),done=0,next=null,err="",started=0,wd=null;rec=r;
    r.lang=lang;r.interimResults=true;r.maxAlternatives=3;
    r.onstart=function(){started=1;mic.classList.add("on");toast("🎤 বলুন… / Speak now")};
    r.onresult=function(e){
      var last=e.results[e.results.length-1];
      if(!last.isFinal){q.value=last[0].transcript;fire();return}
      done=1;var best=null,raw=last[0].transcript.trim();
      for(var i=0;i<last.length;i++){var o=mapT(last[i].transcript);if(o.length){best=o;break}}
      q.value=best?best.join(" "):raw;fire();
      if(best&&$("none")&&!$("none").classList.contains("hide")){q.value=raw;fire()}
    };
    r.onerror=function(e){
      err=e.error;
      if(!tried&&(err==="language-not-supported"||err==="network"||err==="bad-grammar")){next=lang==="en-US"?"bn-BD":"en-US";return}
      var M={"not-allowed":"🎤 মাইক্রোফোন Permission দিন / Allow microphone","service-not-allowed":"🎤 মাইক্রোফোন Permission দিন / Allow microphone","audio-capture":"🎤 মাইক্রোফোন পাওয়া যায়নি / No microphone","network":"🎤 ইন্টারনেট দরকার / Internet needed","language-not-supported":"🎤 ভাষা সাপোর্ট নেই / Language not supported"};
      if(M[err])toast(M[err]);
    };
    r.onend=function(){
      clearTimeout(wd);mic.classList.remove("on");if(rec===r)rec=null;
      if(next){run(next,1);return}
      if(!done&&(!err||err==="no-speech"))toast("🎤 কিছু শুনতে পাইনি / Didn't catch that");
    };
    wd=setTimeout(function(){if(rec===r&&!started){try{r.abort()}catch(_){}mic.classList.remove("on");rec=null;toast("🎤 Voice চালু হয়নি — Permission/Internet দেখুন / Voice didn't start")}},4000);
    try{r.start();mic.classList.add("on")}catch(_){clearTimeout(wd);mic.classList.remove("on");rec=null;toast("🎤 Voice চালু হয়নি, আবার চাপুন / Couldn't start, tap again")}
  }
  ["mousedown","pointerdown","touchstart"].forEach(function(ev){mic.addEventListener(ev,function(e){if(e.cancelable)e.preventDefault()},{passive:false})});
  mic.addEventListener("click",function(e){
    e.preventDefault();e.stopPropagation();
    if(!SR){q.focus();toast("🎤 এই ব্রাউজারে Voice নেই — কীবোর্ডের 🎤 চাপুন / Use your keyboard's mic");return}
    if(rec){try{rec.abort()}catch(_){}rec=null;mic.classList.remove("on");return}
    run(window.APPLANG_SR||"bn-BD",0);
  });
})();

/* display prefs: accent colour, text size, reduce animations */
var DEF_AC=getComputedStyle(document.documentElement).getPropertyValue("--ac").trim()||"#3ddc84";
var BASE_FS=parseFloat(getComputedStyle(document.documentElement).fontSize)||16;
function applyPrefs(){
  var a=store("mvbd_acc"),f=parseFloat(store("mvbd_fs"))||1;
  document.documentElement.style.setProperty("--ac",a||DEF_AC);
  document.documentElement.style.fontSize=(BASE_FS*f)+"px";
  document.body.classList.toggle("rmo",store("mvbd_rm")==="1");
}
applyPrefs();

/* visit days (for streak) */
function dayKey(d){d=d||new Date();return d.getFullYear()+"-"+(d.getMonth()+1)+"-"+d.getDate()}
function recVisit(){if(!getUser())return;var a=dget("days",[]),k=dayKey();if(a.indexOf(k)<0){a.push(k);dset("days",a.slice(-60))}}
function streak(){var a=dget("days",[]),n=0,d=new Date();while(a.indexOf(dayKey(d))>-1){n++;d.setDate(d.getDate()-1)}return n}
function favG(){return dget("fav",[])}
function stData(){
  var h=dget("hist",[]),L=liked(),S=saved(),D=dls(),cnt={},w={a:0,s:0,m:0};
  h.concat(L.map(function(t){return{t:t}}),S.map(function(t){return{t:t}})).forEach(function(x){(GEN[x.t]||[]).forEach(function(g){if(g!=="Anime")cnt[g]=(cnt[g]||0)+1})});
  h.forEach(function(x){var m=byTitle(x.t);if(!m||m[4]==="Reels")return;if(isA(m))w.a++;else if(series.indexOf(m)>-1)w.s++;else w.m++});
  var fav=Object.keys(cnt).sort(function(a,b){return cnt[b]-cnt[a]})[0]||"—";
  return{watch:h.length,w:w,likes:L.length,saved:S.length,dl:D.length,streak:streak(),fav:fav}
}
var BADGES=[["🎬","First Watch","কিছু একটা দেখুন",function(d){return[d.watch,1]}],["🍿","Movie Buff","৫টি মুভি দেখুন",function(d){return[d.w.m,5]}],["⚔️","Anime Fan","৩টি অ্যানিমে দেখুন",function(d){return[d.w.a,3]}],["📺","Binge Master","৩টি সিরিজ দেখুন",function(d){return[d.w.s,3]}],["❤️","Critic","৫টি Like করুন",function(d){return[d.likes,5]}],["🔖","Collector","৫টি Save করুন",function(d){return[d.saved,5]}],["🔥","3-Day Streak","পরপর ৩ দিন আসুন",function(d){return[d.streak,3]}],["🎯","Taste Set","৩টি পছন্দের জনরা বাছুন",function(d){return[favG().length,3]}],["👑","Premium","Premium প্ল্যান নিন",function(d){return[isPrem()?1:0,1]}],["🌟","Veteran","৭ দিনের মেম্বার হন",function(d){var u=getUser();return[Math.floor((Date.now()-(u&&u.joined||Date.now()))/864e5),7]}]];
function pStats(u,b){
  var d=stData(),days=Math.max(1,Math.ceil((Date.now()-(u.joined||Date.now()))/864e5));
  var c=[[d.watch,"Watched"],[d.w.m+" / "+d.w.s+" / "+d.w.a,"Movie / Series / Anime"],[d.likes,"Liked"],[d.saved,"Saved"],[d.dl,"Downloads"],["🔥 "+d.streak,"Day streak"],[d.fav,"Favourite genre"],[days,"Days with us"]];
  b.innerHTML=ph("📊 My Stats")+'<div class="stg">'+c.map(function(x){return '<div class="stc"><b>'+esc(String(x[0]))+'</b><span>'+x[1]+'</span></div>'}).join("")+'</div>';
}
function badgeCount(){var d=stData();return BADGES.filter(function(x){var p=x[3](d);return p[0]>=p[1]}).length}
function pBadges(u,b){
  var d=stData();
  b.innerHTML=ph("🏆 Badges ("+badgeCount()+"/"+BADGES.length+")")+BADGES.map(function(x){var p=x[3](d),on=p[0]>=p[1],pc=Math.min(100,Math.round(p[0]/p[1]*100));return '<div class="bdg'+(on?' on':'')+'"><i>'+x[0]+'</i><div><b>'+x[1]+(on?' ✓':'')+'</b><small>'+x[2]+' • '+Math.min(p[0],p[1])+'/'+p[1]+'</small><em><u style="width:'+pc+'%"></u></em></div></div>'}).join("");
}
var GENRES=["Action","Romance","Thriller","Horror","Comedy","Drama","Fantasy","Sci-Fi","Crime","Mystery","Adventure","Sports","Family","Historical","Supernatural","Isekai","Mecha","School","Magic","Shounen","Slice of Life"];
function recoList(){
  var f=favG(),seen=dget("hist",[]).map(function(x){return x.t});
  if(!f.length)return[];
  return byRate(ALL.filter(function(m){return seen.indexOf(m[0])<0&&(GEN[m[0]]||[]).some(function(g){return f.indexOf(g)>-1})})).slice(0,10);
}
function pTaste(u,b){
  var f=favG(),r=recoList();
  b.innerHTML=ph("🎯 My Taste & Picks")+'<p class="note">পছন্দের জনরা বাছুন — আপনার জন্য সাজেশন নিচে দেখাবে।</p><div class="chips">'+GENRES.map(function(g){return '<button data-fav="'+g+'" class="'+(f.indexOf(g)>-1?'on':'')+'">'+g+'</button>'}).join("")+'</div><h4 class="sh">⭐ Recommended for you</h4>'+(r.length?'<div class="il">'+r.map(function(m){return irow(m,kindOf(m)+" • ⭐ "+m[2])}).join("")+'</div>':'<p class="note">কমপক্ষে একটি জনরা বাছুন।</p>');
  b.querySelectorAll("[data-fav]").forEach(function(x){x.onclick=function(ev){ev.stopPropagation();var a=favG(),i=a.indexOf(x.dataset.fav);if(i>-1)a.splice(i,1);else a.push(x.dataset.fav);dset("fav",a);pTaste(u,b)}});
}
var SITE_LINK="";/* put your website link here, e.g. "https://mvbdplus.com". Empty = this page's own address */
function siteLink(){if(SITE_LINK)return SITE_LINK;var l=location;return(l.origin&&l.origin!=="null")?l.origin+l.pathname:l.href.split("#")[0].split("?")[0]}
function copyLink(t){
  function fb(){try{var x=document.createElement("textarea");x.value=t;x.style.cssText="position:fixed;opacity:0";document.body.appendChild(x);x.select();document.execCommand("copy");x.remove();toast("📋 Link copied")}catch(e){toast(t)}}
  try{navigator.clipboard.writeText(t).then(function(){toast("📋 Link copied")},fb)}catch(e){fb()}
}
function pInvite(u,b){
  var url=siteLink();
  b.innerHTML=ph("🎁 Invite Friends")+'<div class="invc"><div style="font-size:2.4rem">🎁</div><p>বন্ধুদের MVBD+ এ ডাকুন!</p><b class="invl">'+esc(url)+'</b><button class="btn" id="invS">📤 Share link</button><button class="btn out" id="invC">📋 Copy link</button></div>';
  $("invS").onclick=function(ev){ev.stopPropagation();if(navigator.share){navigator.share({title:"MVBD+",url:url}).catch(function(){})}else copyLink(url)};
  $("invC").onclick=function(ev){ev.stopPropagation();copyLink(url)};
}
function pMain(u,b){
  var pl=dget("plan","Free"),n=notifs().filter(function(x){return !x.r}).length,P=pl==="Premium";
  var rows=[["stats","📊","My Stats",""],["badges","🏆","Badges",badgeCount()+"/"+BADGES.length],["taste","🎯","My Taste & Picks",favG().length||""],["invite","🎁","Invite Friends",""],["notif","🔔","Notifications",n?n+" new":""],["set","⚙️","Settings",""]];
  b.innerHTML='<div class="pfh"><div class="pfc"></div>'+avt(u,104)+'<h2>'+esc(u.name)+'</h2><div class="un">@'+esc(u.username)+'</div><span class="plb'+(P?' gold':'')+'">'+(P?"👑 ":"")+esc(pl)+' Plan</span>'+(u.bio?'<p>'+esc(u.bio)+'</p>':'')+'<div class="pfb"><button class="btn" data-p="view">👤 View Profile</button></div></div>'
  +'<div class="pfm">'+rows.map(function(r){return '<button class="pr2" data-p="'+r[0]+'"><i>'+r[1]+'</i><span>'+r[2]+'</span>'+(r[3]!==""?'<em>'+r[3]+'</em>':'')+'<b>›</b></button>'}).join("")+'</div><button class="btn out" id="outB" style="width:100%;margin-top:16px">Log out</button>';
  $("outB").onclick=function(){setUser(null);chRm=0;mode=savedList().length?"chooser":"login";PV="main";afterAuth()};
}
var QORD=["480p","720p","1080p","4K"],QMAX={Free:"480p",Basic:"720p",Standard:"1080p",Premium:"4K"};
function MORESET(u){
  var vq=dget("vq","Auto");
  return '<div class="il" style="margin-top:14px">'+sw("sW",dget("wifi",0)===1,"📶 Download on Wi-Fi only")+sw("sSub",dget("subs",0)===1,"💬 Subtitles on by default")+'</div>'
  +'<h4 class="sh">🎞 Video quality</h4><div class="fsz">'+["Auto"].concat(QORD).map(function(q){return '<button data-vq="'+q+'" class="'+(vq===q?"on":"")+'">'+q+'</button>'}).join("")+'</div>'
  +'<h4 class="sh">🔐 Account &amp; help</h4><div class="pfm">'
  +[["pass","🔑","Change password"],["help","❓","Help &amp; Support (AI)"]].map(function(r){return '<button class="pr2" data-p="'+r[0]+'"><i>'+r[1]+'</i><span>'+r[2]+'</span><b>›</b></button>'}).join("")+'</div>'
  +'<h4 class="sh">🧹 Clean up</h4><button class="btn out" id="clrC" style="width:100%">▶ Clear Continue Watching</button><button class="btn out" id="clrN2" style="width:100%;margin-top:10px">🔔 Clear notifications</button>';
}
function pPass(u,b){
  b.innerHTML=ph("🔑 Change password")+'<div class="box"><input class="f" id="pw0" type="password" placeholder="Current password" autocomplete="current-password"><input class="f" id="pw1" type="password" placeholder="New password (min 4)" autocomplete="new-password"><input class="f" id="pw2" type="password" placeholder="Repeat new password" autocomplete="new-password"><p class="err" id="pwe"></p><button class="btn" id="pws" style="width:100%">Save password</button></div>';
  $("pws").onclick=async function(ev){
    ev.stopPropagation();var er=$("pwe"),a=accs(),m=a.filter(function(x){return x.email===u.email})[0],o=$("pw0").value,n=$("pw1").value;
    if(!m){er.textContent="অ্যাকাউন্ট পাওয়া যায়নি";return}
    var h=await hp(o);if(!(m.pass===h||m.pass===o)){er.textContent="বর্তমান password ভুল";return}
    if(n.length<4){er.textContent="নতুন password কমপক্ষে 4 অক্ষর";return}
    if(n!==$("pw2").value){er.textContent="দুটি password মেলেনি";return}
    m.pass=await hp(n);saveAccs(a);pushN("🔑 Password changed","আপনার password বদলানো হয়েছে।");toast("✓ Password changed");PV="set";renderProfile();
  };
}
function pSet(u,b){
  var s=SET(),dark=document.documentElement.getAttribute("data-theme")!=="light";
  var acc=store("mvbd_acc")||"",fs=store("mvbd_fs")||"1",rm=store("mvbd_rm")==="1";
  var ACC=[["Default",DEF_AC],["Blue","#4da3ff"],["Purple","#b66dff"],["Pink","#ff5fa2"],["Orange","#ff9f1c"],["Red","#ff5a5a"]];
  var FS=[["A-","0.92"],["A","1"],["A+","1.1"],["A++","1.2"]];
  b.innerHTML=ph("⚙️ Settings")+'<div class="il">'+sw("sT",dark,"🌙 Dark theme")+sw("sN",s.notif,"🔔 Notifications")+sw("sA",s.auto,"▶ Autoplay video")+sw("sM",rm,"🐢 Reduce animations")+'</div>'
  +'<h4 class="sh">🎨 Accent colour</h4><div class="acs">'+ACC.map(function(c){return '<button data-acc="'+(c[0]==="Default"?"":c[1])+'" title="'+c[0]+'" class="'+((acc===(c[0]==="Default"?"":c[1]))?"on":"")+'" style="background:'+c[1]+'"></button>'}).join("")+'</div>'
  +'<h4 class="sh">🔤 Text size</h4><div class="fsz">'+FS.map(function(f){return '<button data-fs="'+f[1]+'" class="'+(fs===f[1]?"on":"")+'">'+f[0]+'</button>'}).join("")+'</div>'
  +MORESET(u)+'<button class="btn out" id="clrW" style="width:100%;margin-top:18px">🕘 Clear watch history</button><button class="btn out" id="delB" style="width:100%;margin-top:12px">🗑 Delete Account</button>';
  $("sT").onchange=function(){applyTheme(this.checked?"dark":"light")};
  $("sN").onchange=function(){putSet("notif",this.checked)};
  $("sA").onchange=function(){putSet("auto",this.checked)};
  $("sM").onchange=function(){store("mvbd_rm",this.checked?"1":"0");applyPrefs()};
  b.querySelectorAll("[data-acc]").forEach(function(x){x.onclick=function(ev){ev.stopPropagation();if(x.dataset.acc)store("mvbd_acc",x.dataset.acc);else store("mvbd_acc",null);applyPrefs();pSet(u,b)}});
  b.querySelectorAll("[data-fs]").forEach(function(x){x.onclick=function(ev){ev.stopPropagation();store("mvbd_fs",x.dataset.fs);applyPrefs();pSet(u,b)}});
  $("sW").onchange=function(){dset("wifi",this.checked?1:0)};
  $("sSub").onchange=function(){dset("subs",this.checked?1:0)};
  b.querySelectorAll("[data-vq]").forEach(function(x){x.onclick=function(ev){ev.stopPropagation();var q=x.dataset.vq,mx=QMAX[dget("plan","Free")];if(q!=="Auto"&&QORD.indexOf(q)>QORD.indexOf(mx)){toast("⬆️ "+q+" এর জন্য প্ল্যান আপগ্রেড করুন (Menu → Premium)");return}dset("vq",q);toast("🎞 Quality: "+q);pSet(u,b)}});
  $("clrC").onclick=function(){dset("last_m",null);dset("last_a",null);renderCont();toast("▶ Continue Watching cleared")};
  $("clrN2").onclick=function(){dset("notif",[]);updBadge();toast("🔔 Notifications cleared")};
  $("clrW").onclick=function(){dset("hist",[]);toast("🕘 History cleared");if(typeof renderContinue==="function")try{renderContinue()}catch(e){}};
  $("delB").onclick=delAcc;
}
function renderProfile(){
  var u=me(),b=$("pbox");b.onclick=null;b.onkeydown=null;
  if(!u){
    b.innerHTML=authView();
    b.querySelectorAll(".tabs button").forEach(function(x){x.onclick=function(){mode=x.dataset.m;renderProfile()}});
    b.onkeydown=function(ev){if(ev.key==="Enter"&&$("inB"))$("inB").click()};
    $("inB").onclick=doAuth;return;
  }
  seedN();recVisit();b.onclick=pfClick;
  ({main:pMain,hist:pHist,liked:pLiked,dl:pDl,notif:pNotif,nview:pNview,set:pSet,view:pView,stats:pStats,badges:pBadges,taste:pTaste,invite:pInvite,pass:pPass}[PV]||pMain)(u,b);
  updBadge();
}
/* Navigation stack: views, profile sub-pages and the side menu are all steps.
   Edge swipe goes back one step: page -> menu -> page it was opened from ... until Home (stops there). */
var featNext;
(function(){
  var stk=[],busy=0,tdn=0,_go=go,_rp=renderProfile,SP={},leave=0;
  function sc(y){try{window.scrollTo({top:y,left:0,behavior:"instant"})}catch(e){window.scrollTo(0,y)}}
  function restore(v){var y=SP[v]||0;if(!y)return;sc(y);requestAnimationFrame(function(){sc(y)});setTimeout(function(){if(!tdn&&Math.abs(window.pageYOffset-y)>4)sc(y)},120)}
  function nb(){document.body.classList.add("nobk");clearTimeout(nb.t);nb.t=setTimeout(function(){document.body.classList.remove("nobk")},700)}
  function same(a,b){return !!a&&!!b&&!!a.m===!!b.m&&a.v===b.v&&(a.pv||"")===(b.pv||"")}
  function top(){return stk[stk.length-1]}
  function push(st){
    if(same(top(),st))return;
    if(st.v==="home"&&!st.m){stk=[st];return}
    if(stk.length>1&&same(stk[stk.length-2],st)&&!st.m&&!top().m){stk.pop();return}
    stk.push(st);if(stk.length>60)stk.shift();
  }
  function cs(){return curV==="profile"?{v:"profile",pv:PV}:{v:curV}}
  go=function(v){
    if(v==="movie")v="home";if(views.indexOf(v)<0)v="home";
    var live=!$("app").classList.contains("hide")&&curV;
    if(!busy&&live&&curV!==v)SP[curV]=window.pageYOffset;
    var r=_go.apply(this,arguments);
    if(!busy)push(cs());
    return r;
  };
  renderProfile=function(){_rp.apply(this,arguments);if(!busy&&curV==="profile"&&getUser())push(cs())};
  function show(st){
    _go(st.v);
    if(st.v==="profile"&&st.pv&&st.pv!==PV){PV=st.pv;_rp()}
    restore(st.v);
  }
  function appBack(){
    var rv=$("rv"),md=$("md"),ap=$("aiP"),mn=$("menu"),cs2=$("cs"),csh=$("callSheet");
    if(rv&&!rv.classList.contains("hide")){closeReel();return}
    if(md&&!md.classList.contains("hide")){closeMovie();return}
    if(ap&&!ap.classList.contains("hide")){ap.classList.add("hide");return}
    if(csh){csh.remove();return}
    if(cs2){cs2.remove();return}
    if($("app").classList.contains("hide"))return;
    busy=1;nb();
    try{
      if(!mn.classList.contains("hide")){
        if(top()&&top().m)stk.pop();
        mn.classList.add("hide");return;
      }
      if(stk.length>1){
        stk.pop();
        var t=top();
        if(t.m){
          var below=stk[stk.length-2]||{v:"home"};
          show(below);mn.classList.remove("hide");
        }else show(t);
      }else if(curV!=="home"){stk=[{v:"home"}];show(stk[0])}
    }finally{setTimeout(function(){busy=0},0)}
  }
  window.appBack=appBack;
  new MutationObserver(function(){
    if(busy)return;
    var open=!$("menu").classList.contains("hide");
    if(open){if(!top()||!top().m)stk.push({m:1})}
    else if(top()&&top().m)stk.pop();
  }).observe($("menu"),{attributes:true,attributeFilter:["class"]});
  document.addEventListener("touchstart",function(){tdn=1},{passive:true});
  ["touchend","touchcancel"].forEach(function(ev){document.addEventListener(ev,function(){tdn=0},{passive:true})});
  function mk(side){
    var d=document.createElement("div"),t=null;d.className="eg "+side;document.body.appendChild(d);
    d.addEventListener("touchstart",function(e){
      if(e.touches.length!==1){t=null;return}
      var p=e.touches[0];t={x:p.clientX,y:p.clientY,s:side==="l"?1:-1,d:0};
    },{passive:true});
    d.addEventListener("touchmove",function(e){
      if(!t||t.d)return;var p=e.touches[0],dx=(p.clientX-t.x)*t.s,dy=Math.abs(p.clientY-t.y);
      if(dx>56&&dx>dy*1.4){t.d=1;appBack()}
    },{passive:true});
    ["touchend","touchcancel"].forEach(function(ev){d.addEventListener(ev,function(){t=null},{passive:true})});
  }
  mk("l");mk("r");
  var FM={home:"",series:"s",anime:"a"};
  featNext=function(v){var k=FM[v];if(k!==undefined&&PGS[k])PGS[k].next()};
  $("nav").addEventListener("click",function(e){var b=e.target.closest("button[data-go]");if(b)featNext(b.dataset.go)});
})();
/* ===== v14: language, storage, more settings, nav avatar, nav press ===== */
(function(){
  var LG="bn|বাংলা|bn-BD|হোম|সিরিজ|অ্যানিমে|রিলস|প্রোফাইল|সার্চ…;en|English|en-US|Home|Series|Anime|Reels|Profile|Search…;hi|हिन्दी|hi-IN|होम|सीरीज़|एनीमे|रील्स|प्रोफ़ाइल|खोजें…;ur|اردو|ur-PK|ہوم|سیریز|اینیمے|ریلز|پروفائل|تلاش…;ar|العربية|ar-SA|الرئيسية|مسلسلات|أنمي|ريلز|الملف|بحث…;es|Español|es-ES|Inicio|Series|Anime|Reels|Perfil|Buscar…;fr|Français|fr-FR|Accueil|Séries|Anime|Reels|Profil|Rechercher…;de|Deutsch|de-DE|Start|Serien|Anime|Reels|Profil|Suchen…;pt|Português|pt-BR|Início|Séries|Anime|Reels|Perfil|Buscar…;ru|Русский|ru-RU|Главная|Сериалы|Аниме|Рилс|Профиль|Поиск…;zh|中文|zh-CN|首页|剧集|动漫|短视频|我的|搜索…;ja|日本語|ja-JP|ホーム|シリーズ|アニメ|リール|プロフィール|検索…;ko|한국어|ko-KR|홈|시리즈|애니|릴스|프로필|검색…;tr|Türkçe|tr-TR|Ana Sayfa|Diziler|Anime|Reels|Profil|Ara…;id|Bahasa Indonesia|id-ID|Beranda|Serial|Anime|Reels|Profil|Cari…;ms|Bahasa Melayu|ms-MY|Utama|Siri|Anime|Reels|Profil|Cari…;th|ไทย|th-TH|หน้าแรก|ซีรีส์|อนิเมะ|รีลส์|โปรไฟล์|ค้นหา…;fa|فارسی|fa-IR|خانه|سریال|انیمه|ریلز|پروفایل|جستجو…;ta|தமிழ்|ta-IN|முகப்பு|தொடர்|அனிமே|ரீல்ஸ்|சுயவிவரம்|தேடு…;ne|नेपाली|ne-NP|गृह|शृंखला|एनिमे|रिल्स|प्रोफाइल|खोज्नुहोस्…".split(";").map(function(x){return x.split("|")});
  var RTL={ar:1,ur:1,fa:1,he:1},NAVK=["home","series","anime","reels","profile"];
  function curLang(){return store("mvbd_lang")||"bn"}
  function applyLang(c){
    var L=LG.filter(function(x){return x[0]===c})[0]||LG[0];c=L[0];store("mvbd_lang",c);
    document.documentElement.lang=c;document.documentElement.dir=RTL[c]?"rtl":"ltr";window.APPLANG_SR=L[2];
    NAVK.forEach(function(k,i){var b=document.querySelector('#nav button[data-go="'+k+'"]');if(!b)return;
      [].slice.call(b.childNodes).forEach(function(n){if(n.nodeType===3&&n.nodeValue.trim())n.nodeValue=L[3+i]})});
    var q=$("q");if(q)q.placeholder=L[8];
  }
  window.applyLang=applyLang;applyLang(curLang());

  /* nav: profile picture */
  function updNavAv(){
    var i=document.querySelector('#nav button[data-go="profile"] i');if(!i)return;if(!i._o)i._o=i.innerHTML;
    var u=null;try{u=me()}catch(e){}
    if(!u){i.innerHTML=i._o;return}
    var h=(u.name.charCodeAt(0)*37)%360;
    i.innerHTML=u.av?'<img class="navav" src="'+u.av+'" alt="">':'<span class="navav" style="background:linear-gradient(135deg,hsl('+h+',65%,45%),hsl('+(h+50)+',65%,30%))">'+esc(u.name.charAt(0).toUpperCase())+'</span>';
  }
  var _su=setUser;setUser=function(u){_su(u);updNavAv()};updNavAv();
  var _rp=renderProfile;renderProfile=function(){_rp.apply(this,arguments);updNavAv()};

  /* settings extras */
  function fmtB(n){var u=["B","KB","MB","GB","TB"],i=0;while(n>=1024&&i<4){n/=1024;i++}return (i?n.toFixed(n>=100?0:2):Math.round(n))+" "+u[i]}
  var LIMIT=20*1024*1024*1024;
  function lsUsed(){var t=0;try{Object.keys(localStorage).forEach(function(k){t+=(k.length+(localStorage.getItem(k)||"").length)*2})}catch(e){}return t}
  function stHtml(used){
    var p=Math.min(100,used/LIMIT*100);
    return '<b>'+fmtB(used)+'</b> / 20 GB used • '+p.toFixed(4)+'%<div class="stbar"><i style="width:'+Math.max(p,.3)+'%"></i></div><small>Free: '+fmtB(Math.max(0,LIMIT-used))+' • Limit: 20 GB</small>';
  }
  var TG=[["nextEp",1,"⏭ Autoplay next episode"],["skipIntro",0,"⏩ Auto-skip intro"],["dsaver",0,"📉 Data saver"],["hdr",1,"✨ HDR / Dolby support"],["mature",1,"🔞 Show mature content"],["kids",0,"🧒 Kids mode"],["twofa",0,"🛡 Two-step verification"],["hapt",1,"📳 Haptic feedback"],["newrel",1,"🆕 New release alerts"],["actv",1,"👥 Show my activity to friends"]];
  var _ps=pSet;pSet=function(u,b){
    _ps(u,b);
    var h=b.querySelector(".pph");
    var top='<h4 class="sh">🌐 Language / ভাষা (20)</h4><div class="box"><select class="f" id="langSel">'+LG.map(function(x){return '<option value="'+x[0]+'"'+(x[0]===curLang()?" selected":"")+'>'+x[1]+'</option>'}).join("")+'</select></div>'
      +'<h4 class="sh">💾 Storage</h4><div class="box" id="stBox">'+stHtml(lsUsed())+'</div>';
    var fz=b.querySelector(".fsz");if(fz)fz.insertAdjacentHTML("afterend",top);else if(h)h.insertAdjacentHTML("afterend",top);
    var more='<h4 class="sh">⚡ More options</h4><div class="il">'+TG.map(function(t){return sw("tg_"+t[0],dget(t[0],t[1])==1,t[2])}).join("")+'</div>'
      +'<button class="btn out" id="clrCache" style="width:100%;margin-top:12px">🧹 Clear cache</button><button class="btn out" id="fbk" style="width:100%;margin-top:10px">📨 Send feedback / Request</button>';
    var d=$("clrW");if(d)d.insertAdjacentHTML("beforebegin",more);
    $("langSel").onchange=function(ev){ev.stopPropagation();applyLang(this.value);toast("🌐 "+this.options[this.selectedIndex].text)};
    $("langSel").onclick=function(ev){ev.stopPropagation()};
    TG.forEach(function(t){var e=$("tg_"+t[0]);if(e)e.onchange=function(){dset(t[0],this.checked?1:0)}});
    $("clrCache").onclick=function(ev){ev.stopPropagation();try{sessionStorage.clear();if(window.caches)caches.keys().then(function(k){k.forEach(function(x){caches.delete(x)})})}catch(e){}toast("🧹 Cache cleared")};
    $("fbk").onclick=function(ev){ev.stopPropagation();go("req")};
    if(navigator.storage&&navigator.storage.estimate)navigator.storage.estimate().then(function(e){var s=$("stBox");if(s)s.innerHTML=stHtml(Math.max(e.usage||0,lsUsed()))}).catch(function(){});
  };
  var _pp=pPass;pPass=function(u,b){
    _pp(u,b);var bx=b.querySelector(".box");
    if(!bx)return;(bx.insertAdjacentHTML("beforeend",'<button class="lnk" id="fgS">Forgot password?</button>'),$("fgS").onclick=function(ev){ev.stopPropagation();PV="forgot";renderProfile()});bx.insertAdjacentHTML("afterbegin",'<p class="pnote">ℹ️ এটা শুধু MVBD+ অ্যাকাউন্টের password। আপনার Gmail/Email এর password বদলাবে না — Email শুধু login ID হিসেবে ব্যবহার হয়।<br><i>This changes only your MVBD+ password, not your Gmail/email password.</i></p>');
  };
})();

/* ===== v15: saved profiles, forgot password, double-tap like ===== */
function savedList(){var l;try{l=JSON.parse(store("mvbd_sacc")||"[]")}catch(e){l=[]}var a=accs();return l.filter(function(e){return a.some(function(x){return x.email===e})})}
function rememberAcc(e){var l=savedList().filter(function(x){return x!==e});l.unshift(e);store("mvbd_sacc",JSON.stringify(l.slice(0,8)))}
function forgetAcc(e){store("mvbd_sacc",JSON.stringify(savedList().filter(function(x){return x!==e})))}
(function(){var _s=setUser;setUser=function(u){_s(u);if(u)rememberAcc(u.email)}})();

function logoHtml(){var im=$("logoImg"),src=im&&im.src;return src?'<img src="'+esc(src)+'" alt="MVBD+" onerror="this.outerHTML=\'<span>MVBD+</span>\'">':'<span>MVBD+</span>'}
var chRm=0;
function renderChooser(){
  var b=$("pbox"),a=accs(),l=savedList();
  b.innerHTML='<div class="chz'+(chRm?' chrm':'')+'" id="chz"><button class="chdots" id="chDots" aria-label="More">'+(chRm?'<span style="font-size:1rem;font-weight:700">Done</span>':'⋯')+'</button><div class="chmenu hide" id="chMenu"><button id="chRm">🗑 Remove account</button></div>'
   +'<div class="chlogo">'+logoHtml()+'</div>'
   +l.map(function(e){var m=a.filter(function(x){return x.email===e})[0];return '<div class="chc" data-e="'+esc(e)+'">'+avt({name:m.name,av:m.av},56)+'<span class="chn">'+esc(m.name)+'</span><b>›</b><button class="chx" data-x="'+esc(e)+'" aria-label="Remove">✕</button></div>'}).join("")
   +'<button class="chalt" id="chUse">Use another profile</button>'
   +'<div class="chbot"><button class="chnew" id="chNew">Create new account</button><div class="chmark">MVBD+</div></div></div>';
  $("chDots").onclick=function(ev){ev.stopPropagation();if(chRm){chRm=0;renderChooser();return}$("chMenu").classList.toggle("hide")};
  $("chRm").onclick=function(ev){ev.stopPropagation();chRm=1;renderChooser();toast("✕ চাপুন, তারপর Remove চাপুন")};
  $("chUse").onclick=function(){chRm=0;mode="login";renderProfile()};
  $("chNew").onclick=function(){chRm=0;mode="signup";renderProfile()};
  b.querySelectorAll(".chc").forEach(function(c){c.onclick=function(ev){
    var x=ev.target.closest&&ev.target.closest(".chx");
    if(chRm){
      ev.stopPropagation();
      if(!x)return;
      if(x.dataset.arm==="1"){forgetAcc(x.dataset.x);if(!savedList().length){chRm=0;mode="login"}renderProfile();return}
      b.querySelectorAll(".chx").forEach(function(o){o.dataset.arm="";o.textContent="✕";o.classList.remove("armed")});
      x.dataset.arm="1";x.textContent="Remove";x.classList.add("armed");return;
    }
    var m=accs().filter(function(q){return q.email===c.dataset.e})[0];if(!m)return;
    setUser(sess(m));PV="main";afterAuth()}});
}
function renderForgot(u){
  var b=$("pbox"),back=u?'<button class="lnk" id="fgBk">← Back</button>':'<button class="lnk" id="fgBk">← Back to login</button>';
  b.innerHTML='<div class="box"><h2>🔑 Reset password</h2><p>'+(u?'নিশ্চিত করতে আপনার Email/Phone লিখুন।':'আপনার Email বা Phone number লিখুন।')+'</p>'
   +'<input class="f" id="fgI" placeholder="Email or Phone number" autocapitalize="none" inputmode="email"><div id="fgN" class="hide"><input class="f" id="fg1" type="password" placeholder="New password (min 4)" autocomplete="new-password"><input class="f" id="fg2" type="password" placeholder="Repeat new password" autocomplete="new-password"></div>'
   +'<p class="err" id="fgE"></p><button class="btn" id="fgGo" style="width:100%">Next</button>'+back
   +'<p style="font-size:.85rem">ℹ️ এই অ্যাপে server নেই, তাই Gmail/SMS এ কোড যায় না। Reset শুধু এই ডিভাইসে কাজ করে।</p></div>';
  var step=1,acc=null;
  $("fgBk").onclick=function(ev){ev.stopPropagation();if(u){PV="pass"}else{mode="login"}renderProfile()};
  $("fgGo").onclick=async function(ev){
    ev.stopPropagation();var er=$("fgE");er.textContent="";
    if(step===1){
      var id=normId($("fgI").value);if(!id){er.textContent="Email/Phone লিখুন";return}
      acc=accs().filter(function(x){return x.email===id||(x.username||"")===id})[0];
      if(!acc||(u&&acc.email!==u.email)){er.textContent="এই Email/Phone এর সাথে কোনো account মেলেনি";return}
      step=2;$("fgN").classList.remove("hide");$("fgI").readOnly=true;this.textContent="Save new password";$("fg1").focus();return;
    }
    var n=$("fg1").value;
    if(n.length<4){er.textContent="নতুন password কমপক্ষে 4 অক্ষর";return}
    if(n!==$("fg2").value){er.textContent="দুটি password মেলেনি";return}
    var a=accs();a.forEach(function(x){if(x.email===acc.email)x.pass=n});
    var h=await hp(n);a.forEach(function(x){if(x.email===acc.email)x.pass=h});saveAccs(a);
    toast("✓ Password changed");
    if(u){PV="set"}else{mode="login"}renderProfile();
  };
}
(function(){
  var _r=renderProfile;
  renderProfile=function(){
    var u=me();
    if(!u){
      if(mode==="login"&&!window._chk&&savedList().length){mode="chooser"}
      window._chk=1;
      if(mode==="chooser"&&!savedList().length)mode="login";
      if(mode==="chooser"){$("pbox").onclick=null;$("pbox").onkeydown=null;renderChooser();return}
      if(mode==="forgot"){$("pbox").onclick=null;renderForgot(null);return}
      _r.apply(this,arguments);
      if(mode==="login"&&$("inB")){
        $("inB").insertAdjacentHTML("afterend",'<button class="lnk" id="fgB">Forgot password?</button>'+(savedList().length?'<button class="lnk" id="bkB">← Saved profiles</button>':''));
        $("fgB").onclick=function(){mode="forgot";renderProfile()};
        if($("bkB"))$("bkB").onclick=function(){mode="chooser";renderProfile()};
      }else if(mode==="signup"&&$("inB")&&savedList().length){
        $("inB").insertAdjacentHTML("afterend",'<button class="lnk" id="bkB">← Saved profiles</button>');
        $("bkB").onclick=function(){mode="chooser";renderProfile()};
      }
      return;
    }
    if(PV==="forgot"){$("pbox").onkeydown=null;renderForgot(u);return}
    _r.apply(this,arguments);
  };
})();

/* Reels: double-tap the screen = like */
(function(){
  var rv=$("rv"),lt=0,sx=0,sy=0;
  function burst(x,y){var h=document.createElement("div");h.className="hrt";h.textContent="❤️";h.style.left=x+"px";h.style.top=y+"px";document.body.appendChild(h);setTimeout(function(){if(h.parentNode)h.parentNode.removeChild(h)},900)}
  function like(x,y){burst(x,y);if(liked().indexOf(rTitle(R.i))<0)$("rlk").onclick({stopPropagation:function(){}})}
  rv.addEventListener("touchstart",function(e){sx=e.touches[0].clientX;sy=e.touches[0].clientY},{passive:true});
  rv.addEventListener("touchend",function(e){
    if(e.target.closest&&e.target.closest("#ra,#rx,button"))return;
    var t=e.changedTouches[0];if(Math.abs(t.clientX-sx)>14||Math.abs(t.clientY-sy)>14){lt=0;return}
    var n=Date.now();if(n-lt<320){lt=0;like(t.clientX,t.clientY)}else lt=n;
  },{passive:true});
  rv.addEventListener("dblclick",function(e){if(e.target.closest&&e.target.closest("#ra,button"))return;like(e.clientX,e.clientY)});
})();
</script>
</body>
</html>