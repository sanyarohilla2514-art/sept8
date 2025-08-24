<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>will you go out with me?</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      font-family: arial, sans-serif;
      background: #161820;
      color: #b0c4de;
      overflow: hidden;
    }
    #bg-art {
      position: fixed;
      left: 0;
      top: 0;
      width: 100vw;
      height: 100vh;
      z-index: 0;
      opacity: 0.07;
      background: url('https://i.imgur.com/9U0QyLP.png') repeat center center; /* bunnies and lambs drawing */
      background-size: 600px 420px;
      pointer-events: none;
    }
    .center-box, #main-question, #lavender-drawings, #wait-tumho, #slideshow-bg {
      position: absolute;
      left: 0; top: 0;
      width: 100vw; height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 2;
    }
    .hidden { display: none !important; }
    #texting-box {
      min-width: 270px;
      width: 320px;
      max-width: 85vw;
      background: #b0c4de;
      border-radius: 18px;
      box-shadow: 0 2px 25px 0 #b0c4de33;
      color: #222;
      font-size: 0.98rem;
      padding: 30px 18px 30px 18px;
      min-height: 80px;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .msg {
      background: #edf3fa;
      color: #222;
      padding: 9px 13px;
      border-radius: 16px;
      margin: 0 0 5px 0;
      font-size: 0.98em;
      width: fit-content;
      max-width: 78%;
      word-break: break-word;
    }
    .from-me { align-self: flex-end; background: #b0c4de; color: #222; }
    .from-her { align-self: flex-start; background: #dbeafe; color: #222; }
    #main-question-box {
      background: #b0c4de;
      color: #222;
      border-radius: 17px;
      font-size: 1.06rem;
      box-shadow: 0 2px 18px #b0c4de55;
      padding: 28px 17px 15px 17px;
      margin-bottom: 22px;
      width: 320px;
      text-align: center;
      font-family: arial,sans-serif;
      letter-spacing: 0.01em;
    }
    #option-btns {
      display: flex;
      flex-direction: row;
      gap: 23px;
      margin-top: 8px;
      width: 320px;
      justify-content: center;
    }
    button {
      background: #b0c4de;
      color: #222;
      font-family: arial, sans-serif;
      border: none;
      border-radius: 12px;
      padding: 14px 28px;
      font-size: 0.98rem;
      text-transform: lowercase;
      font-weight: bold;
      box-shadow: 0 2px 12px #b0c4de33;
      cursor: pointer;
      outline: none;
      transition: background 0.23s, color 0.23s, transform 0.23s;
    }
    button:hover { background: #9baebd; color: #222; }
    #btn-no {
      position: relative;
      left: 0;
      transition: left 0.13s, top 0.13s, transform 0.2s;
    }
    #lavender-drawings {
      flex-direction: column;
      background: transparent;
      animation: none;
      z-index: 3;
    }
    .lavender-animate {
      animation: lavender-approach 2s cubic-bezier(.74,0,.89,.43) forwards;
    }
    @keyframes lavender-approach {
      from { transform: scale(0.5) translateY(180px); opacity: 0; }
      to   { transform: scale(1.06) translateY(0); opacity: 1; }
    }
    #lavender-art-box {
      margin-bottom: 35px;
      z-index: 4;
      display: flex;
    }
    #wait-tumho {
      z-index: 4;
    }
    #wait-tumho-box {
      background: #b0c4de;
      color: #222;
      border-radius: 16px;
      font-size: 1.00rem;
      padding: 23px 23px;
      font-family: arial,sans-serif;
      box-shadow: 0 2px 12px #b0c4de33;
      margin-bottom: 12px;
      text-align: center;
    }
    #wait-tumho-btn {
      background: #b0c4de;
      color: #222;
      margin-top: 12px;
      padding: 13px 32px;
      font-size: 1.04rem;
      border-radius: 13px;
      font-family: arial,sans-serif;
      font-weight: bold;
      letter-spacing: 0.02em;
    }
    #slideshow-bg {
      background: #161820;
      z-index: 10;
    }
    #slide-img {
      max-width: 100vw;
      max-height: 100vh;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
      border-radius: 0;
      opacity: 0;
      z-index: 10;
      position: absolute;
      left: 0; top: 0;
      transition: opacity 1.5s;
      background: #161820;
    }
    @media (max-width: 600px){
      #main-question-box, #texting-box, #option-btns, #wait-tumho-box  { width:95vw; min-width: 0; max-width: 97vw;}
    }
  </style>
</head>
<body>
  <div id="bg-art"></div>
  <!-- Chat / texting scene -->
  <div id="chat-bg" class="center-box">
    <div id="texting-box"></div>
  </div>
  <!-- Main question -->
  <div id="main-question" class="center-box hidden">
    <div id="main-question-box">
      okay second hand embarrassment horhi h😭<br>
      i didn’t know initiating was this difficult..<br>
      i want to go out with you..<br>
      will you?
    </div>
    <div id="option-btns">
      <button id="btn-no">no</button>
      <button id="btn-shock">dont mind me i’m in shock</button>
    </div>
  </div>
  <!-- Lavender scene -->
  <div id="lavender-drawings" class="center-box hidden">
    <div id="lavender-art-box">
      <!-- SVG lavender hands/flowers -->
      <svg width="120" height="200" viewBox="0 0 120 200">
        <g>
          <ellipse cx="70" cy="192" rx="32" ry="10" fill="#bba8e3"/>
          <ellipse cx="50" cy="160" rx="19" ry="15" fill="#c3cfe2"/>
          <!-- hands -->
          <ellipse cx="45" cy="185" rx="15" ry="19" fill="#eedbd8" stroke="#bb9a8d" stroke-width="2"/>
          <ellipse cx="85" cy="182" rx="15" ry="16" fill="#eedbd8" stroke="#bb9a8d" stroke-width="2"/>
          <!-- stems -->
          <rect x="66" y="100" width="6" height="80" fill="#719d5c" rx="3"/>
          <rect x="80" y="100" width="6" height="70" fill="#719d5c" rx="3"/>
          <rect x="53" y="110" width="5" height="70" fill="#719d5c" rx="2"/>
          <!-- flowers -->
          <g>
            <ellipse cx="70" cy="100" rx="10" ry="17" fill="#9d71b8"/>
            <ellipse cx="70" cy="117" rx="10" ry="16" fill="#ae94d3"/>
            <ellipse cx="70" cy="133" rx="9" ry="12" fill="#c2bbdf"/>
            <ellipse cx="85" cy="112" rx="8" ry="19" fill="#ae94d3"/>
            <ellipse cx="60" cy="120" rx="7" ry="12" fill="#b3accc"/>
            <ellipse cx="55" cy="137" rx="7" ry="9" fill="#c2bbdf"/>
          </g>
        </g>
      </svg>
    </div>
  </div>
  <!-- Tum Ho prompt -->
  <div id="wait-tumho" class="center-box hidden">
    <div id="wait-tumho-box">
      play “tum ho” in your phone now
      <br>
      <button id="wait-tumho-btn">ok</button>
    </div>
  </div>
  <!-- Slideshow -->
  <div id="slideshow-bg" class="center-box hidden">
    <img id="slide-img" src="" draggable="false"/>
  </div>
  <script>
    const chats = [
      {text: "hii", from: "me"},
      {text: "hii", from: "her"},
      {text: "umm are you single?", from: "me"},
      {text: "yes i am. why do you ask?", from: "her"},
    ];
    // Use lowercase for all, font is Arial everywhere!
    function sleep(ms){return new Promise(res => setTimeout(res, ms));}
    async function startChats(){
      const box = document.getElementById("texting-box");
      for(const msg of chats){
        const div=document.createElement("div");
        div.className="msg from-"+(msg.from==="me"?"me":"her");
        div.innerText=msg.text;
        box.append(div);
        await sleep(2000);
      }
      await sleep(900);
      document.getElementById("chat-bg").classList.add('hidden');
      document.getElementById("main-question").classList.remove('hidden');
    }

    // Runaway NO button
    const btnNo = document.getElementById('btn-no');
    btnNo.addEventListener('mouseenter', e=>{
      const parent = document.getElementById("option-btns");
      const maxX = parent.offsetWidth - btnNo.offsetWidth - 12;
      const maxY = parent.offsetHeight - btnNo.offsetHeight - 8;
      btnNo.style.left = (Math.random()*maxX-6) + "px";
      btnNo.style.top  = (Math.random()*maxY-3) + "px";
    });
    btnNo.addEventListener('click', e=>{
      const parent = document.getElementById("option-btns");
      const maxX = parent.offsetWidth - btnNo.offsetWidth - 12;
      const maxY = parent.offsetHeight - btnNo.offsetHeight - 8;
      btnNo.style.left = (Math.random()*maxX-6) + "px";
      btnNo.style.top  = (Math.random()*maxY-3) + "px";
    });

    // Lavender animation, then show "tum ho" prompt
    document.getElementById('btn-shock').onclick = async ()=>{
      document.getElementById("main-question").classList.add("hidden");
      const lav = document.getElementById("lavender-drawings");
      lav.classList.remove("hidden");
      const lavArt = document.getElementById("lavender-art-box");
      lavArt.classList.add("lavender-animate");
      await sleep(2200);
      lav.classList.add("hidden");
      document.getElementById("wait-tumho").classList.remove("hidden");
    };

    // Show slideshow after prompt
    document.getElementById('wait-tumho-btn').onclick = ()=>{
      document.getElementById("wait-tumho").classList.add("hidden");
      document.getElementById("slideshow-bg").classList.remove("hidden");
      startSlideshow();
    }

    // Slideshow with fade
    const images=[
      "attached_image_1.jpg",
      "attached_image_2.jpg",
      "attached_image_3.jpg",
      "attached_image_4.jpg",
      "attached_image_5.jpg",
      "attached_image_6.jpg",
      "attached_image_7.jpg",
      "attached_image_8.jpg",
      "attached_image_9.jpg",
      "attached_image_10.jpg"
    ];
    async function startSlideshow(){
      const img = document.getElementById('slide-img');
      let idx = 0;
      while(true){
        img.style.opacity = "0";
        await sleep(450);
        img.src = images[idx];
        img.onload = ()=>{ img.style.opacity = "1";};
        idx = (idx+1)%images.length;
        await sleep(3400);
      }
    }
    // Start!
    window.onload = startChats;
  </script>
</body>
</html>
