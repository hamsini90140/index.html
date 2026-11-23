# index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Moonsip Café</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bagel+Fat+One&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#fff6ec; --ink:#2b2140; --card:#ffffff; --matcha:#b8e0a5; --lilac:#d9c7ff; --pink:#ffc2d9; --butter:#ffe58a; --muted:#6d6283; --line:#2b2140;
  box-sizing:border-box; padding-top:env(safe-area-inset-top,0px); padding-bottom:env(safe-area-inset-bottom,0px);
}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#1c1830;--ink:#fff2e3;--card:#2a2444;--matcha:#4d7a42;--lilac:#6a4fb0;--pink:#b24c7c;--butter:#a8892a;--muted:#b9acd1;--line:#fff2e3}}
:root[data-theme="dark"]{--bg:#1c1830;--ink:#fff2e3;--card:#2a2444;--matcha:#4d7a42;--lilac:#6a4fb0;--pink:#b24c7c;--butter:#a8892a;--muted:#b9acd1;--line:#fff2e3}
html{scroll-padding-top:env(safe-area-inset-top,0px);scroll-behavior:smooth}
*,*::before,*::after{box-sizing:inherit}
body{margin:0;background:var(--bg);color:var(--ink);font-family:'DM Sans',system-ui,sans-serif;line-height:1.55;overflow-x:hidden}
h1,h2,h3{font-family:'Bagel Fat One','Arial Rounded MT Bold',system-ui,sans-serif;font-weight:400;line-height:1.05;margin:0}
a{color:inherit}
:focus-visible{outline:3px solid var(--ink);outline-offset:3px}
.wrap{max-width:1040px;margin:0 auto;padding:0 20px}
section{padding:56px 0}
h2{font-size:clamp(2rem,6vw,3.2rem);margin-bottom:8px}
.sub{color:var(--muted);margin:0 0 28px}
.btn{display:inline-block;background:var(--butter);color:#2b2140;border:2.5px solid var(--line);border-radius:999px;padding:12px 22px;font-weight:700;text-decoration:none;box-shadow:4px 4px 0 var(--line);transition:transform .15s,box-shadow .15s;cursor:pointer;font-size:1rem;font-family:inherit}
.btn:hover{transform:translate(2px,2px);box-shadow:2px 2px 0 var(--line)}
.btn.alt{background:var(--card);color:var(--ink)}
nav{position:sticky;top:env(safe-area-inset-top,0px);z-index:20;padding:12px 0}
nav .wrap{display:flex;justify-content:space-between;align-items:center;gap:12px}
.pill{background:var(--card);border:2.5px solid var(--line);border-radius:999px;padding:8px 16px;font-weight:700;text-decoration:none;font-size:.92rem}
.links{display:flex;gap:8px;flex-wrap:wrap;justify-content:flex-end}
.logo{font-family:'Bagel Fat One',system-ui,sans-serif;font-size:1.4rem;text-decoration:none}
body::before{content:"";position:fixed;inset:0 0 auto;height:env(safe-area-inset-top,0px);background:var(--bg);z-index:10}

/* hero */
.hero{padding-top:28px}
.hero .wrap{display:grid;grid-template-columns:1.2fr 1fr;gap:32px;align-items:center}
.hero h1{font-size:clamp(3rem,11vw,6.2rem);letter-spacing:-.01em}
.hero h1 span{display:inline-block;background:var(--matcha);border:3px solid var(--line);border-radius:28px;padding:0 .2em;transform:rotate(-2.5deg);margin:.05em 0}
.hero p{font-size:1.15rem;max-width:30em;margin:18px 0 26px}
.cta{display:flex;gap:14px;flex-wrap:wrap}
.cup{position:relative;aspect-ratio:1/1.05;background:var(--lilac);border:3px solid var(--line);border-radius:48% 52% 44% 56%/52% 46% 54% 48%;display:grid;place-items:center;font-size:clamp(6rem,22vw,10rem);box-shadow:8px 8px 0 var(--line);animation:bob 5s ease-in-out infinite}
.sticker{position:absolute;background:var(--pink);border:2.5px solid var(--line);border-radius:999px;padding:6px 14px;font-weight:700;font-size:.9rem;color:#2b2140}
.s1{top:8%;left:-4%;transform:rotate(-8deg)}.s2{bottom:10%;right:-3%;transform:rotate(6deg);background:var(--butter)}
@keyframes bob{50%{transform:translateY(-10px) rotate(1.5deg)}}

.marquee{border-block:3px solid var(--line);background:var(--butter);color:#2b2140;overflow:hidden;white-space:nowrap;padding:12px 0;font-family:'Bagel Fat One',system-ui,sans-serif;font-size:1.3rem}
.marquee div{display:inline-block;padding-left:100%;animation:run 22s linear infinite}
@keyframes run{to{transform:translateX(-100%)}}

/* menu */
.tabs{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:22px}
.tab{background:var(--card);color:var(--ink);border:2.5px solid var(--line);border-radius:999px;padding:9px 18px;font:700 1rem 'DM Sans',sans-serif;cursor:pointer}
.tab[aria-selected="true"]{background:var(--lilac);color:#2b2140;box-shadow:3px 3px 0 var(--line)}
.items{display:grid;grid-template-columns:repeat(auto-fill,minmax(250px,1fr));gap:16px}
.item{background:var(--card);border:2.5px solid var(--line);border-radius:26px;padding:18px;display:flex;gap:14px;align-items:flex-start}
.item .e{font-size:2.2rem;line-height:1}
.item h3{font-size:1.2rem;margin-bottom:4px}
.item p{margin:0;color:var(--muted);font-size:.93rem}
.price{margin-left:auto;font-weight:700;background:var(--matcha);color:#2b2140;border-radius:999px;padding:2px 10px;font-size:.9rem;white-space:nowrap}

/* specials */
.specials .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px}
.sp{border:3px solid var(--line);border-radius:34px;padding:26px;color:#2b2140;box-shadow:6px 6px 0 var(--line)}
.sp:nth-child(1){background:var(--pink);transform:rotate(-1.2deg)}
.sp:nth-child(2){background:var(--matcha);transform:rotate(1deg)}
.sp:nth-child(3){background:var(--lilac);transform:rotate(-.8deg)}
.sp .e{font-size:2.6rem}.sp h3{font-size:1.5rem;margin:8px 0}.sp p{margin:0 0 10px}
.tag{display:inline-block;background:#fff;border:2px solid #2b2140;border-radius:999px;padding:2px 12px;font-weight:700;font-size:.85rem}

/* reviews */
.rev{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:18px}
.r{background:var(--card);border:2.5px solid var(--line);border-radius:26px 26px 26px 6px;padding:20px}
.r .st{letter-spacing:2px;color:#e8a100}
.r p{margin:8px 0 12px}.r b{font-size:.92rem;color:var(--muted)}

/* hours + location */
.two{display:grid;grid-template-columns:1fr 1fr;gap:22px}
.box{background:var(--card);border:3px solid var(--line);border-radius:32px;padding:26px}
.box h2{font-size:2rem;margin-bottom:14px}
.hrs{list-style:none;margin:0;padding:0}
.hrs li{display:flex;justify-content:space-between;padding:9px 12px;border-radius:14px;gap:12px}
.hrs li.today{background:var(--butter);color:#2b2140;font-weight:700}
.map{margin-top:16px;height:120px;border:2.5px dashed var(--line);border-radius:22px;background:repeating-linear-gradient(45deg,var(--matcha) 0 14px,var(--bg) 14px 28px);display:grid;place-items:center;font-size:2.4rem}
footer{text-align:center;padding:30px 20px 40px;color:var(--muted);font-size:.92rem}
@media (max-width:760px){.hero .wrap,.two{grid-template-columns:1fr}.cup{max-width:320px;margin:0 auto;width:100%}.s1{left:2%}.s2{right:2%}}
@media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important;scroll-behavior:auto}}
</style>
</head>
<body>
<nav><div class="wrap"><a class="logo" href="#top">moonsip ☾</a>
<div class="links"><a class="pill" href="#menu">menu</a><a class="pill" href="#specials">specials</a><a class="pill" href="#reviews">reviews</a><a class="pill" href="#visit">visit</a></div></div></nav>

<header class="hero" id="top"><div class="wrap">
<div>
<h1>sip slow, <span>stay</span> long.</h1>
<p>Your cozy corner for matcha, strong coffee and fresh bakes. Bring your laptop, your besties, or just your mood.</p>
<div class="cta"><a class="btn" href="#menu">See the menu</a><a class="btn alt" href="#visit">Find us</a></div>
</div>
<div class="cup" aria-hidden="true">🍵<span class="sticker s1">fresh matcha</span><span class="sticker s2">open late</span></div>
</div></header>

<div class="marquee" aria-hidden="true"><div>matcha ✦ cold brew ✦ croissants ✦ cheesecake ✦ good vibes ✦ study sessions ✦ date nights ✦ matcha ✦ cold brew ✦ croissants ✦ cheesecake ✦ good vibes ✦</div></div>

<section id="menu"><div class="wrap">
<h2>the menu</h2><p class="sub">Tap a category. Prices are samples, so swap in your own.</p>
<div class="tabs" role="tablist" id="tabs"></div>
<div class="items" id="items" role="tabpanel"></div>
</div></section>

<section class="specials" id="specials"><div class="wrap">
<h2>today’s specials</h2><p class="sub">Limited batches. When they’re gone, they’re gone.</p>
<div class="grid">
<div class="sp"><div class="e">🍓</div><h3>Strawberry Cloud Latte</h3><p>Strawberry milk, espresso and a sweet cream cloud on top.</p><span class="tag">₹240</span></div>
<div class="sp"><div class="e">🥐</div><h3>Pistachio Croissant</h3><p>Flaky, buttery and filled with pistachio cream. Baked at 8 am.</p><span class="tag">₹180</span></div>
<div class="sp"><div class="e">🧋</div><h3>Taro Pearl Cooler</h3><p>Purple taro, chewy pearls and cold foam. It’s giving dessert.</p><span class="tag">₹210</span></div>
</div></div></section>

<section id="reviews"><div class="wrap">
<h2>the girlies &amp; guys say</h2><p class="sub">Real vibes from our regulars.</p>
<div class="rev">
<div class="r"><div class="st">★★★★★</div><p>The matcha is so creamy and the playlist is immaculate. My new study spot, no question.</p><b>Aanya, college student</b></div>
<div class="r"><div class="st">★★★★★</div><p>Cutest café ever. The strawberry latte is aesthetic and actually tastes amazing.</p><b>Rohan, content creator</b></div>
<div class="r"><div class="st">★★★★☆</div><p>Great wifi, soft seats and the cheesecake is dangerous. Gets busy on weekends!</p><b>Meera, designer</b></div>
</div></div></section>

<section id="visit"><div class="wrap two">
<div class="box"><h2>opening hours</h2><ul class="hrs" id="hrs"></ul></div>
<div class="box"><h2>find us</h2>
<p><b>Moonsip Café</b><br>12 Rainbow Lane, Main Street<br>Your City, 000000</p>
<p>📞 +00 00000 00000<br>📸 @moonsip.cafe</p>
<div class="map" aria-hidden="true">📍</div>
<p style="margin-top:16px"><a class="btn" href="#top">Get directions</a></p></div>
</div></section>

<footer>made with 🍵 and good energy · moonsip café</footer>

<script>
const menu={
 "coffee":[["☕","Iced Latte","Double shot, cold milk, ice.","190"],["🤎","Caramel Cold Brew","Smooth, slow steeped, caramel drizzle.","220"],["🥛","Oat Flat White","Velvety oat milk, strong espresso.","200"]],
 "matcha & tea":[["🍵","Iced Matcha Latte","Ceremonial matcha with milk.","230"],["🍑","Peach Iced Tea","Fruity, light and refreshing.","160"],["🌸","Rose Chai","Spiced chai with rose petals.","170"]],
 "bites":[["🥐","Butter Croissant","Flaky and golden.","120"],["🍰","Basque Cheesecake","Creamy with a burnt top.","260"],["🥪","Pesto Grilled Sandwich","Cheesy, crunchy and warm.","210"]]
};
const tabs=document.getElementById('tabs'),items=document.getElementById('items');
function show(k){
  [...tabs.children].forEach(b=>b.setAttribute('aria-selected',b.dataset.k===k));
  items.innerHTML=menu[k].map(m=>`<div class="item"><div class="e">${m[0]}</div><div><h3>${m[1]}</h3><p>${m[2]}</p></div><span class="price">₹${m[3]}</span></div>`).join('');
}
Object.keys(menu).forEach((k,i)=>{const b=document.createElement('button');b.className='tab';b.role='tab';b.textContent=k;b.dataset.k=k;b.onclick=()=>show(k);tabs.appendChild(b)});
show('coffee');
const days=[["Sunday","9 am – 11 pm"],["Monday","8 am – 10 pm"],["Tuesday","8 am – 10 pm"],["Wednesday","8 am – 10 pm"],["Thursday","8 am – 10 pm"],["Friday","8 am – 12 am"],["Saturday","9 am – 12 am"]];
const t=new Date().getDay();
document.getElementById('hrs').innerHTML=days.map((d,i)=>`<li class="${i===t?'today':''}"><span>${d[0]}</span><span>${d[1]}</span></li>`).join('');
</script>
</body>
</html>
