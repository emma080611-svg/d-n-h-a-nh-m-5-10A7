<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Bảng tuần hoàn tương tác</title>
<style>
:root{box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);
--bg:#eaf4ff;--card:#fff;--tx:#12305e;--mu:#5a7194;--ac:#1d4fb8;--bd:#c7dcf5;--hl:#ff8a1f}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0d1a2e;--card:#16273f;--tx:#e6f0ff;--mu:#93a9c8;--ac:#5b9bff;--bd:#2a4268}}
:root[data-theme="dark"]{--bg:#0d1a2e;--card:#16273f;--tx:#e6f0ff;--mu:#93a9c8;--ac:#5b9bff;--bd:#2a4268}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,-apple-system,"Segoe UI",Roboto,sans-serif;padding:14px}
h1{font-size:22px;margin:0 0 4px}
h1 span{color:var(--hl)}
p.sub{margin:0 0 12px;color:var(--mu);font-size:14px}
.bar{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:10px}
.bar input{flex:1;min-width:160px;padding:8px 12px;border-radius:20px;border:1px solid var(--bd);background:var(--card);color:var(--tx);font-size:14px}
.chip{border:1px solid var(--bd);background:var(--card);color:var(--tx);border-radius:16px;padding:5px 10px;font-size:12px;cursor:pointer}
.chip.on{background:var(--ac);color:#fff;border-color:var(--ac)}
.wrap{overflow-x:auto;padding-bottom:8px}
#grid{display:grid;grid-template-columns:repeat(18,minmax(46px,1fr));grid-template-rows:repeat(7,auto) 14px repeat(2,auto);gap:3px;min-width:900px}
.el{border-radius:6px;padding:3px 2px;text-align:center;cursor:pointer;border:2px solid transparent;color:#12305e;transition:transform .12s}
.el:hover{transform:scale(1.15);z-index:2;border-color:var(--hl)}
.el.dim{opacity:.18}
.el small{display:block;font-size:9px;text-align:left;padding-left:3px}
.el b{font-size:16px;display:block;line-height:1.1}
.el i{font-style:normal;font-size:8px;display:block;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.c-kl{background:#ffb4a8}.c-kt{background:#ffd29a}.c-cm{background:#ffe99a}.c-nm{background:#b8ecb0}.c-ha{background:#9fe6e6}.c-kh{background:#c9b8f5}.c-cd{background:#ffc0e0}.c-pk{background:#b4cdf7}.c-lt{background:#a8e0d0}.c-ac{background:#e5b8f0}
#ov{position:fixed;inset:0;background:rgba(5,15,40,.6);display:none;align-items:flex-start;justify-content:center;overflow:auto;padding:max(14px,env(safe-area-inset-top,0px)) 12px 20px;z-index:20}
#ov.show{display:flex}
.modal{background:var(--card);border-radius:20px;max-width:760px;width:100%;padding:16px;border:1px solid var(--bd);position:relative;margin:auto}
.x{position:absolute;right:12px;top:10px;border:0;background:var(--bd);color:var(--tx);width:30px;height:30px;border-radius:50%;font-size:16px;cursor:pointer}
.top{display:flex;gap:16px;flex-wrap:wrap}
.big{width:170px;border-radius:16px;padding:10px;text-align:center;color:#12305e;border:3px solid #2f5fd0;flex:none}
.big .n{font-size:20px;font-weight:700}.big .s{font-size:54px;font-weight:800;line-height:1}.big .nm{font-weight:700}.big .m{font-size:13px;margin-bottom:6px}
#qr{background:#fff;padding:6px;border-radius:8px;display:inline-block;line-height:0}
.big .hint{font-size:10px;margin-top:4px}
.right{flex:1;min-width:230px}
.tabs{display:flex;flex-direction:column;gap:6px}
.tab{display:flex;align-items:center;gap:10px;text-align:left;border:1px solid var(--bd);background:var(--bg);color:var(--tx);padding:9px 12px;border-radius:12px;font-size:14px;cursor:pointer;font-weight:600}
.tab em{font-style:normal;font-size:18px}
.tab.on{background:var(--ac);color:#fff;border-color:var(--ac)}
.pane{margin-top:14px;border:1px dashed var(--bd);border-radius:14px;padding:14px;min-height:150px;font-size:14px;line-height:1.55}
.vid{background:linear-gradient(135deg,#1d4fb8,#0b2a6b);border-radius:12px;aspect-ratio:16/9;display:flex;align-items:center;justify-content:center;color:#fff;flex-direction:column;gap:8px;text-decoration:none}
.vid span{font-size:46px}
.apps{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:8px}
.apps div{background:var(--bg);border-radius:10px;padding:12px;text-align:center}
.apps div b{display:block;font-size:30px}
.opt{display:block;width:100%;text-align:left;margin:6px 0;padding:9px 12px;border-radius:10px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);font-size:14px;cursor:pointer}
.opt.ok{background:#2e9e4f;color:#fff}.opt.no{background:#d44;color:#fff}
.ex{background:var(--bg);padding:8px 12px;border-radius:10px;margin-top:10px;font-size:13px}
</style>
</head>
<body>
<h1>🚀 <span>LEVEL UP:</span> Bảng tuần hoàn tương tác</h1>
<p class="sub">Bấm vào một nguyên tố để xem video, hình ảnh ứng dụng, mô hình nguyên tử, thí nghiệm và câu hỏi. Quét mã QR để học trên điện thoại.</p>
<div class="bar"><input id="q" placeholder="Tìm theo ký hiệu, tên hoặc số hiệu…"><span id="chips" style="display:contents"></span></div>
<div class="wrap"><div id="grid"></div></div>
<div id="ov"><div class="modal"><button class="x" onclick="closeM()">✕</button><div class="top"><div class="big" id="big"></div><div class="right"><div class="tabs" id="tabs"></div></div></div><div class="pane" id="pane"></div></div></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<script>
const RAW="H Hydrogen 1,008|He Helium 4,0026|Li Lithium 6,94|Be Beryllium 9,0122|B Boron 10,81|C Carbon 12,011|N Nitrogen 14,007|O Oxygen 15,999|F Fluorine 18,998|Ne Neon 20,180|Na Sodium 22,990|Mg Magnesium 24,305|Al Aluminium 26,982|Si Silicon 28,085|P Phosphorus 30,974|S Sulfur 32,06|Cl Chlorine 35,45|Ar Argon 39,948|K Potassium 39,098|Ca Calcium 40,078|Sc Scandium 44,956|Ti Titanium 47,867|V Vanadium 50,942|Cr Chromium 51,996|Mn Manganese 54,938|Fe Iron 55,845|Co Cobalt 58,933|Ni Nickel 58,693|Cu Copper 63,546|Zn Zinc 65,38|Ga Gallium 69,723|Ge Germanium 72,630|As Arsenic 74,922|Se Selenium 78,971|Br Bromine 79,904|Kr Krypton 83,798|Rb Rubidium 85,468|Sr Strontium 87,62|Y Yttrium 88,906|Zr Zirconium 91,224|Nb Niobium 92,906|Mo Molybdenum 95,95|Tc Technetium 98|Ru Ruthenium 101,07|Rh Rhodium 102,91|Pd Palladium 106,42|Ag Silver 107,87|Cd Cadmium 112,41|In Indium 114,82|Sn Tin 118,71|Sb Antimony 121,76|Te Tellurium 127,60|I Iodine 126,90|Xe Xenon 131,29|Cs Caesium 132,91|Ba Barium 137,33|La Lanthanum 138,91|Ce Cerium 140,12|Pr Praseodymium 140,91|Nd Neodymium 144,24|Pm Promethium 145|Sm Samarium 150,36|Eu Europium 151,96|Gd Gadolinium 157,25|Tb Terbium 158,93|Dy Dysprosium 162,50|Ho Holmium 164,93|Er Erbium 167,26|Tm Thulium 168,93|Yb Ytterbium 173,05|Lu Lutetium 174,97|Hf Hafnium 178,49|Ta Tantalum 180,95|W Tungsten 183,84|Re Rhenium 186,21|Os Osmium 190,23|Ir Iridium 192,22|Pt Platinum 195,08|Au Gold 196,97|Hg Mercury 200,59|Tl Thallium 204,38|Pb Lead 207,2|Bi Bismuth 208,98|Po Polonium 209|At Astatine 210|Rn Radon 222|Fr Francium 223|Ra Radium 226|Ac Actinium 227|Th Thorium 232,04|Pa Protactinium 231,04|U Uranium 238,03|Np Neptunium 237|Pu Plutonium 244|Am Americium 243|Cm Curium 247|Bk Berkelium 247|Cf Californium 251|Es Einsteinium 252|Fm Fermium 257|Md Mendelevium 258|No Nobelium 259|Lr Lawrencium 266|Rf Rutherfordium 267|Db Dubnium 268|Sg Seaborgium 269|Bh Bohrium 270|Hs Hassium 277|Mt Meitnerium 278|Ds Darmstadtium 281|Rg Roentgenium 282|Cn Copernicium 285|Nh Nihonium 286|Fl Flerovium 289|Mc Moscovium 290|Lv Livermorium 293|Ts Tennessine 294|Og Oganesson 294";
const CATS={kl:"Kim loại kiềm",kt:"Kiềm thổ",cm:"Kim loại chuyển tiếp",pk:"Kim loại yếu",cd:"Á kim",nm:"Phi kim",ha:"Halogen",kh:"Khí hiếm",lt:"Lanthanide",ac:"Actinide"};
const inl=(z,a)=>a.includes(z);
function cat(z){
 if(inl(z,[3,11,19,37,55,87]))return"kl";if(inl(z,[4,12,20,38,56,88]))return"kt";
 if(inl(z,[2,10,18,36,54,86,118]))return"kh";if(inl(z,[9,17,35,53,85,117]))return"ha";
 if(inl(z,[5,14,32,33,51,52]))return"cd";if(inl(z,[1,6,7,8,15,16,34]))return"nm";
 if(z>=57&&z<=71)return"lt";if(z>=89&&z<=103)return"ac";
 if((z>=21&&z<=30)||(z>=39&&z<=48)||(z>=72&&z<=80)||(z>=104&&z<=112))return"cm";return"pk";}
function pos(z){
 if(z==1)return[1,1];if(z==2)return[1,18];
 if(z<=4)return[2,z-2];if(z<=10)return[2,z+8];
 if(z<=12)return[3,z-10];if(z<=18)return[3,z];
 if(z<=36)return[4,z-18];if(z<=54)return[5,z-36];
 if(z<=56)return[6,z-54];if(z<=71)return[9,z-54];if(z<=86)return[6,z-68];
 if(z<=88)return[7,z-86];if(z<=103)return[10,z-86];return[7,z-100];}
const E=RAW.split("|").map((s,i)=>{const[a,b,c]=s.split(" ");return{z:i+1,s:a,n:b,m:c,c:cat(i+1)}});

// Thông tin riêng cho một số nguyên tố (các nguyên tố khác dùng mẫu chung)
const INFO={
O:{app:[["🫁","Hô hấp của sinh vật"],["🔥","Duy trì sự cháy"],["🏥","Bình thở oxy y tế"],["🔩","Hàn cắt kim loại"]],
 exp:"Đốt que đóm còn tàn đỏ trong bình khí oxygen: que đóm bùng cháy sáng. Chứng tỏ oxygen duy trì sự cháy mạnh hơn không khí.",
 q:{q:"Oxygen có vai trò gì trong hô hấp và sự cháy?",o:["Làm tắt ngọn lửa","Duy trì sự hô hấp và sự cháy","Chỉ có trong nước, không có trong không khí","Không tham gia phản ứng hoá học"],a:1,e:"Oxygen là chất oxi hoá: cung cấp cho quá trình hô hấp tế bào và giúp các chất cháy được."}},
H:{app:[["🚀","Nhiên liệu tên lửa"],["🔋","Pin nhiên liệu hydrogen"],["🧪","Sản xuất NH₃"],["🎈","Khinh khí cầu (xưa)"]],
 exp:"Cho kẽm vào dung dịch HCl, thu khí H₂ rồi đưa que lửa lại gần: nghe tiếng nổ nhỏ “póp”.",
 q:{q:"Hydrogen là nguyên tố có đặc điểm nào?",o:["Nặng nhất","Nhẹ nhất","Là khí hiếm","Là kim loại kiềm thổ"],a:1,e:"Hydrogen có khối lượng nguyên tử nhỏ nhất, khoảng 1,008."}},
C:{app:[["💎","Kim cương"],["✏️","Than chì, bút chì"],["🏭","Than, nhiên liệu"],["🧬","Chất nền của sự sống"]],
 exp:"Đốt than trong bình oxygen rồi sục khí vào nước vôi trong: nước vôi vẩn đục do tạo CaCO₃.",
 q:{q:"Kim cương và than chì đều được cấu tạo từ nguyên tố nào?",o:["Silicon","Carbon","Oxygen","Lưu huỳnh"],a:1,e:"Đây là hai dạng thù hình khác nhau của carbon."}},
Na:{app:[["🧂","Muối ăn NaCl"],["💡","Đèn hơi sodium"],["🧼","Xà phòng, xút NaOH"],["🧊","Chất làm lạnh lò phản ứng"]],
 exp:"Thả mẩu Na nhỏ vào nước có phenolphthalein: Na chạy trên mặt nước, có khí thoát ra, dung dịch hoá hồng (tạo NaOH).",
 q:{q:"Sodium tác dụng với nước tạo ra gì?",o:["NaOH và H₂","NaCl và O₂","Na₂O và CO₂","Chỉ có H₂O₂"],a:0,e:"2Na + 2H₂O → 2NaOH + H₂↑"}},
Fe:{app:[["🏗️","Thép xây dựng"],["🚗","Ô tô, máy móc"],["🩸","Hemoglobin trong máu"],["🍳","Dụng cụ nhà bếp"]],
 exp:"Đốt dây sắt cuốn lò xo trong bình oxygen: sắt cháy sáng chói, tạo các hạt Fe₃O₄ màu nâu đen.",
 q:{q:"Sắt có vai trò gì trong cơ thể người?",o:["Tạo xương","Thành phần của hemoglobin vận chuyển O₂","Tạo men răng","Điều hoà thân nhiệt trực tiếp"],a:1,e:"Hemoglobin chứa sắt, giúp hồng cầu vận chuyển oxygen."}},
Au:{app:[["💍","Trang sức"],["💻","Mạch điện tử"],["🏦","Dự trữ giá trị"],["🛰️","Lớp phủ vệ tinh"]],
 exp:"Gold không bị gỉ trong không khí ẩm và không tan trong HCl hay H₂SO₄ loãng. Chỉ tan trong nước cường toan.",
 q:{q:"Vì sao vàng được dùng làm trang sức lâu bền?",o:["Rất dễ gỉ","Rất trơ về mặt hoá học","Rất nhẹ","Dễ bay hơi"],a:1,e:"Vàng hầu như không phản ứng với oxygen và nước."}},
Cl:{app:[["🚰","Khử trùng nước"],["🧴","Thuốc tẩy"],["🧂","Muối NaCl"],["🧱","Nhựa PVC"]],
 exp:"Cho giấy màu ẩm vào bình khí chlorine: màu bị mất do tạo HClO có tính tẩy màu (thực hiện trong tủ hút).",
 q:{q:"Chlorine thuộc nhóm nguyên tố nào?",o:["Kim loại kiềm","Khí hiếm","Halogen","Kiềm thổ"],a:2,e:"Chlorine nằm ở nhóm VIIA (17), nhóm halogen."}}
};

const grid=document.getElementById("grid");
E.forEach(e=>{
 const[r,c]=pos(e.z);const d=document.createElement("div");
 d.className="el c-"+e.c;d.style.gridRow=r;d.style.gridColumn=c;d.dataset.z=e.z;
 d.innerHTML=`<small>${e.z}</small><b>${e.s}</b><i>${e.n}</i>`;
 d.onclick=()=>openM(e);grid.appendChild(d);});
// ô chú thích phân nhóm La–Lu, Ac–Lr
[["*",6,3],["*",7,3]].forEach(([t,r,c])=>{const d=document.createElement("div");d.style.cssText=`grid-row:${r};grid-column:${c};text-align:center;color:var(--mu)`;d.textContent=t;grid.appendChild(d)});

// bộ lọc
let cur=null;const chips=document.getElementById("chips");
Object.entries(CATS).forEach(([k,v])=>{const b=document.createElement("button");b.className="chip";b.textContent=v;b.onclick=()=>{cur=cur==k?null:k;filter()};b.dataset.k=k;chips.appendChild(b)});
document.getElementById("q").oninput=filter;
function filter(){
 const t=document.getElementById("q").value.trim().toLowerCase();
 chips.querySelectorAll(".chip").forEach(b=>b.classList.toggle("on",b.dataset.k==cur));
 grid.querySelectorAll(".el").forEach(d=>{const e=E[d.dataset.z-1];
  const okT=!t||e.s.toLowerCase()==t||e.n.toLowerCase().includes(t)||String(e.z)==t;
  d.classList.toggle("dim",!(okT&&(!cur||e.c==cur)))});}

// cấu hình electron theo từng lớp
function shells(z){
 const ord=[[1,2],[2,2],[2,6],[3,2],[3,6],[4,2],[3,10],[4,6],[5,2],[4,10],[5,6],[6,2],[4,14],[5,10],[6,6],[7,2],[5,14],[6,10],[7,6]];
 const s=[];let left=z;for(const[n,cap]of ord){if(left<=0)break;const t=Math.min(cap,left);s[n-1]=(s[n-1]||0)+t;left-=t}
 return s.map(v=>v||0);}
function bohr(e){
 const sh=shells(e.z);let g=`<circle r="14" fill="#ff8a1f"/><text y="4" text-anchor="middle" font-size="11" font-weight="700" fill="#fff">${e.z}+</text>`;
 sh.forEach((n,i)=>{const R=26+i*16;const dur=6+i*3;
  g+=`<circle r="${R}" fill="none" stroke="#8aa9d8" stroke-dasharray="3 3"/><g><animateTransform attributeName="transform" type="rotate" from="0" to="${i%2?-360:360}" dur="${dur}s" repeatCount="indefinite"/>`;
  for(let k=0;k<n;k++){const a=2*Math.PI*k/n;g+=`<circle cx="${(R*Math.cos(a)).toFixed(1)}" cy="${(R*Math.sin(a)).toFixed(1)}" r="3.2" fill="#2f7bff"/>`}
  g+="</g>"});
 const W=26+sh.length*16+10;
 return `<svg viewBox="${-W} ${-W} ${2*W} ${2*W}" style="width:100%;max-width:300px;display:block;margin:auto">${g}</svg><p style="text-align:center;margin:6px 0 0">Cấu hình lớp: <b>${sh.join(" – ")}</b> (electron mỗi lớp)</p>`;}

// Gắn video YouTube cụ thể cho từng nguyên tố: ký hiệu → đường dẫn video
const VIDEOS={
 H:"https://www.youtube.com/watch?v=WkQVUNE9krg",
 He:"https://www.youtube.com/watch?v=jDmBLMPxNc4",
 Li:"https://www.youtube.com/watch?v=KPpnAnyoLH0",
 Be:"https://www.youtube.com/watch?v=Bjb-9CO1-3M",
 Na:"https://www.youtube.com/watch?v=qENmIDO8p_M",
 // O:"https://www.youtube.com/watch?v=MA_VIDEO",
};
let E0=null;
const TABS=[["🎬","Video 30–60 giây"],["🖼️","Hình ảnh ứng dụng"],["⚛️","Mô hình nguyên tử"],["🧪","Thí nghiệm"],["❓","Câu hỏi tương tác"]];
function openM(e){
 E0=e;const col=getComputedStyle(grid.querySelector(`[data-z="${e.z}"]`)).backgroundColor;
 const big=document.getElementById("big");big.style.background=col;
 big.innerHTML=`<div class="n">${e.z}</div><div class="s">${e.s}</div><div class="nm">${e.n}</div><div class="m">${e.m}</div><div id="qr"></div><div class="hint">Quét QR để học thêm</div>`;
 try{new QRCode(document.getElementById("qr"),{text:"https://en.wikipedia.org/wiki/"+e.n,width:96,height:96,correctLevel:QRCode.CorrectLevel.M})}catch(_){document.getElementById("qr").textContent="QR"}
 const tb=document.getElementById("tabs");tb.innerHTML="";
 TABS.forEach((t,i)=>{const b=document.createElement("button");b.className="tab";b.innerHTML=`<em>${t[0]}</em>${t[1]}`;b.onclick=()=>tab(i);tb.appendChild(b)});
 document.getElementById("ov").classList.add("show");tab(4);}
function closeM(){document.getElementById("ov").classList.remove("show")}
document.getElementById("ov").onclick=ev=>{if(ev.target.id=="ov")closeM()};
document.addEventListener("keydown",ev=>{if(ev.key=="Escape")closeM()});

function quizOf(e){
 const I=INFO[e.s];if(I)return I.q;
 const w=[e.z+1,e.z-1>0?e.z-1:e.z+3,e.z+5].map(String);
 const o=[String(e.z),...w];
 return{q:`Số hiệu nguyên tử của ${e.n} (${e.s}) là bao nhiêu?`,o,a:0,e:`${e.n} có số hiệu nguyên tử ${e.z}, nghĩa là có ${e.z} proton trong hạt nhân.`};}

function tab(i){
 const e=E0,I=INFO[e.s]||{};
 document.querySelectorAll(".tab").forEach((b,k)=>b.classList.toggle("on",k==i));
 const p=document.getElementById("pane");
 if(i==0){p.innerHTML=`<a class="vid" target="_blank" rel="noopener" href="${VIDEOS[e.s]||"https://www.youtube.com/results?search_query="+encodeURIComponent(e.n+" element chemistry 60 seconds")}"><span>▶</span><b>Video ${e.n} trong 60 giây</b><small>${VIDEOS[e.s]?"Bấm để xem video trên YouTube":"Chưa gắn video riêng, bấm để tìm trên YouTube"}</small></a>`}
 if(i==1){const a=I.app||[["🔬","Nghiên cứu khoa học"],["🏭","Công nghiệp"],["🏥","Y học & đời sống"],["💡","Công nghệ mới"]];
  p.innerHTML=`<div class="apps">${a.map(x=>`<div><b>${x[0]}</b>${x[1]}</div>`).join("")}</div>`+(I.app?"":`<p style="color:var(--mu);font-size:12px">Nội dung chung. Hãy bổ sung ứng dụng thực tế của ${e.n} trong đối tượng INFO.</p>`)}
 if(i==2){p.innerHTML=bohr(e)}
 if(i==3){p.innerHTML=`<b>Thí nghiệm gợi ý</b><p>${I.exp||`Quan sát tính chất vật lí và phản ứng của ${e.n} với oxygen, nước hoặc acid (theo hướng dẫn của giáo viên, đảm bảo an toàn phòng thí nghiệm).`}</p>`}
 if(i==4){const q=quizOf(e);
  p.innerHTML=`<b>${q.q}</b>`+q.o.map((t,k)=>`<button class="opt" data-k="${k}">${String.fromCharCode(65+k)}. ${t}</button>`).join("")+`<div class="ex" id="ex" style="display:none"></div>`;
  p.querySelectorAll(".opt").forEach(b=>b.onclick=()=>{
   p.querySelectorAll(".opt").forEach(x=>{x.disabled=true;const k=+x.dataset.k;if(k==q.a)x.classList.add("ok");else if(x==b)x.classList.add("no")});
   const ex=document.getElementById("ex");ex.style.display="block";ex.textContent=(+b.dataset.k==q.a?"✅ Chính xác! ":"❌ Chưa đúng. ")+q.e});}
}
</script>
</body>
</html>
