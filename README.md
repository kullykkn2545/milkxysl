<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Milk Pansa × YSL Generator</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500&family=Inter:wght@300;400;500&display=swap');

body{
  margin:0;
  background:#000;
  color:#d4af37;
  font-family:'Inter', sans-serif;
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
}

.wrapper{
  width:90%;
  max-width:700px;
  text-align:center;
}

h1{
  font-family:'Playfair Display', serif;
  letter-spacing:3px;
  font-size:26px;
  margin-bottom:40px;
}

.counter{
  font-size:13px;
  color:#888;
  margin-bottom:20px;
}

.caption-box{
  border-top:1px solid #d4af37;
  border-bottom:1px solid #d4af37;
  padding:40px 20px;
  font-size:18px;
  min-height:160px;
  line-height:1.7;
  margin-bottom:40px;
  white-space:pre-line;
}

button{
  background:transparent;
  border:1px solid #d4af37;
  color:#d4af37;
  padding:12px 30px;
  margin:10px;
  letter-spacing:1px;
  font-size:13px;
  cursor:pointer;
}

button:hover{
  background:#d4af37;
  color:#000;
}

.footer{
  position:fixed;
  bottom:15px;
  width:100%;
  text-align:center;
  font-size:11px;
  color:#555;
  letter-spacing:2px;
}
</style>
</head>

<body>

<div class="wrapper">
  <h1>MILK PANSA × YSL</h1>

  <div class="counter" id="counter">
    Used 0 / 150
  </div>

  <div class="caption-box" id="captionBox">
    Click GENERATE to reveal ✨
  </div>

  <button onclick="generateCaption()">GENERATE</button>
  <button onclick="copyCaption()">COPY</button>
</div>

<script>

const hashtags = `

#YSLxMilkPansa
#SaintLaurent
#SaintLaurentPFW26
#YSL #MilkPansa
#PFW2026
#YvesSaintLaurent #ParisFashionWeek
#PFWWomen
#FW26
`;

let captions = [

"Milk Pansa glowing in timeless YSL elegance ✨",
"Milk Pansa redefining luxury in YSL 🔥",
"YSL aura perfectly matches Milk Pansa 💎",
"Milk Pansa serving iconic YSL energy 👑",
"YSL never looked better than on Milk Pansa ✨",
"Milk Pansa radiating Saint Laurent confidence 🔥",
"Milk Pansa turning YSL into pure art 🎨",
"YSL glam amplified by Milk Pansa 💫",
"Milk Pansa walking in full YSL power 👠",
"Luxury is Milk Pansa in YSL 💎",

"Milk Pansa owning the YSL spotlight ✨",
"YSL elegance embodied by Milk Pansa 👑",
"Milk Pansa shining brighter than YSL gold 🔥",
"Saint Laurent magic meets Milk Pansa 💫",
"Milk Pansa elevating every YSL look 💎",
"YSL couture made for Milk Pansa ✨",
"Milk Pansa bringing YSL runway to life 👠",
"YSL glow enhanced by Milk Pansa 🔥",
"Milk Pansa defining YSL sophistication 💎",
"YSL style perfected by Milk Pansa ✨",

"Milk Pansa in YSL is pure confidence 🔥",
"Milk Pansa creating a YSL fashion moment 💫",
"YSL glamour shining through Milk Pansa 👑",
"Milk Pansa rewriting YSL fashion rules ✨",
"YSL luxury wrapped around Milk Pansa 💎",
"Milk Pansa glowing in Saint Laurent light 🔥",
"YSL masterpiece starring Milk Pansa 👑",
"Milk Pansa turning heads in YSL ✨",
"YSL elegance meets Milk Pansa grace 💫",
"Milk Pansa owning every YSL frame 🔥",

"Milk Pansa shining in YSL couture 💎",
"YSL aura glowing with Milk Pansa ✨",
"Milk Pansa walking like YSL royalty 👑",
"YSL brilliance amplified by Milk Pansa 🔥",
"Milk Pansa radiating timeless Saint Laurent charm 💫",
"YSL dream carried by Milk Pansa ✨",
"Milk Pansa glowing with Paris fashion energy 🔥",
"YSL chic perfected by Milk Pansa 💎",
"Milk Pansa owning YSL elegance effortlessly ✨",
"YSL glow reflecting Milk Pansa power 🔥",

"Milk Pansa embodying Saint Laurent spirit 👑",
"YSL sophistication elevated by Milk Pansa 💫",
"Milk Pansa turning YSL into a statement ✨",
"YSL glam intensified by Milk Pansa 🔥",
"Milk Pansa shining in luxury YSL mood 💎",
"YSL aura wrapped around Milk Pansa ✨",
"Milk Pansa defining Saint Laurent glamour 🔥",
"YSL elegance shining through Milk Pansa 👑",
"Milk Pansa elevating YSL fashion vibes 💫",
"YSL power flowing through Milk Pansa ✨",

"Milk Pansa glowing in iconic YSL style 🔥",
"YSL couture perfected by Milk Pansa 💎",
"Milk Pansa embodying modern YSL chic ✨",
"YSL sparkle matching Milk Pansa shine 🔥",
"Milk Pansa shining under Saint Laurent lights 💫",
"YSL magic surrounding Milk Pansa 👑",
"Milk Pansa bringing elegance to YSL runway ✨",
"YSL aesthetic enhanced by Milk Pansa 🔥",
"Milk Pansa defining Paris fashion glow 💎",
"YSL icon energy meets Milk Pansa ✨",

"Milk Pansa glowing in Saint Laurent glamour 🔥",
"YSL fashion poetry starring Milk Pansa 💫",
"Milk Pansa elevating YSL to another level 👑",
"YSL elegance reimagined by Milk Pansa ✨",
"Milk Pansa owning luxury YSL vibes 🔥",
"YSL chic flowing through Milk Pansa 💎",
"Milk Pansa turning YSL into gold ✨",
"YSL glow amplified by Milk Pansa 🔥",
"Milk Pansa shining like a YSL muse 👑",
"YSL aura captured by Milk Pansa 💫",

"Milk Pansa redefining Paris luxury ✨",
"YSL beauty embodied by Milk Pansa 🔥",
"Milk Pansa glowing with runway confidence 💎",
"YSL power styled by Milk Pansa 👑",
"Milk Pansa in YSL is iconic ✨",
"YSL elegance highlighted by Milk Pansa 🔥",
"Milk Pansa shining in Saint Laurent couture 💫",
"YSL energy radiating from Milk Pansa 👑",
"Milk Pansa turning fashion into art ✨",
"YSL sophistication glowing with Milk Pansa 🔥",

"Milk Pansa embracing Saint Laurent elegance 💎",
"YSL glam perfected by Milk Pansa ✨",
"Milk Pansa glowing like Paris lights 🔥",
"YSL aura enhanced by Milk Pansa 👑",
"Milk Pansa walking in YSL confidence 💫",
"YSL couture brought to life by Milk Pansa ✨",
"Milk Pansa shining in black and gold 🔥",
"YSL legacy meets Milk Pansa 👑",
"Milk Pansa radiating timeless chic 💎",
"YSL glamour elevated by Milk Pansa ✨",

"Milk Pansa owning the Paris runway 🔥",
"YSL elegance glowing through Milk Pansa 👑",
"Milk Pansa shining in couture perfection 💫",
"YSL aesthetic defined by Milk Pansa ✨",
"Milk Pansa turning elegance into power 🔥",
"YSL spirit embodied by Milk Pansa 💎",
"Milk Pansa glowing in fashion royalty 👑",
"YSL aura shining brighter with Milk Pansa ✨",
"Milk Pansa redefining iconic glam 🔥",
"YSL glow wrapped in Milk Pansa confidence 💫",

"Milk Pansa shining in Saint Laurent dream ✨",
"YSL couture glowing with Milk Pansa 🔥",
"Milk Pansa walking in iconic elegance 👑",
"YSL brilliance meets Milk Pansa 💎",
"Milk Pansa elevating fashion effortlessly ✨",
"YSL glamour defined by Milk Pansa 🔥",
"Milk Pansa glowing in luxury vibes 💫",
"YSL elegance enhanced by Milk Pansa 👑",
"Milk Pansa turning glam into legend ✨",
"YSL energy perfected by Milk Pansa 🔥",

"Milk Pansa shining like a fashion icon 💎",
"YSL magic glowing with Milk Pansa ✨",
"Milk Pansa owning timeless chic 🔥",
"YSL aura elevated by Milk Pansa 👑",
"Milk Pansa radiating pure sophistication 💫",
"YSL elegance styled by Milk Pansa ✨",
"Milk Pansa glowing in runway glory 🔥",
"YSL glam shining through Milk Pansa 💎",
"Milk Pansa turning luxury into power 👑",
"YSL fashion moment starring Milk Pansa ✨",

"Milk Pansa shining in golden elegance 🔥",
"YSL couture carried by Milk Pansa 💫",
"Milk Pansa embodying iconic fashion 👑",
"YSL glow redefined by Milk Pansa ✨",
"Milk Pansa glowing beyond expectations 🔥",
"YSL spirit shining through Milk Pansa 💎",
"Milk Pansa owning every couture moment 👑",
"YSL elegance amplified by Milk Pansa ✨",
"Milk Pansa radiating high fashion energy 🔥",
"YSL masterpiece perfected by Milk Pansa 💫"

];

let current = "";
let usedCount = 0;
let total = captions.length;

function updateCounter(){
  document.getElementById("counter").innerText =
    `Used ${usedCount} / ${total}`;
}

function generateCaption(){
  if(captions.length === 0){
    document.getElementById("captionBox").innerText =
      "All 150 captions used 🔥";
    return;
  }

  let randomIndex = Math.floor(Math.random()*captions.length);
  current = captions[randomIndex] + hashtags;
  document.getElementById("captionBox").innerText = current;
}

function copyCaption(){
  if(!current) return;

  navigator.clipboard.writeText(current).then(()=>{
    let textOnly = current.replace(hashtags,"").trim();
    captions = captions.filter(c => c !== textOnly);

    usedCount++;
    updateCounter();

    current = "";
    document.getElementById("captionBox").innerText =
      "Caption copied ✔ Generate next ✨";
  });
}

updateCounter();

</script>

</body>
</html>
