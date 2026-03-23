# Summary of Learning

<pre style="background:#0a0e1a; border-radius:16px; padding:2rem; margin:1.5rem 0; border:1px solid rgba(255,255,255,0.06); box-shadow:0 8px 30px rgba(0,0,0,0.3); font-family:monospace; line-height:1.4; font-size:0.6rem; text-align:center; overflow-x:auto;">
<span style="color:#6190ff;"> █████╗ ██╗</span>    <span style="color:#818cf8;">██████╗ ██╗   ██╗</span>    <span style="color:#22d3ee;">██████╗ ███████╗███████╗██╗ ██████╗ ███╗  ██╗</span>
<span style="color:#6190ff;">██╔══██╗██║</span>    <span style="color:#818cf8;">██╔══██╗╚██╗ ██╔╝</span>    <span style="color:#22d3ee;">██╔══██╗██╔════╝██╔════╝██║██╔════╝ ████╗ ██║</span>
<span style="color:#6190ff;">███████║██║</span>    <span style="color:#818cf8;">██████╔╝ ╚████╔╝</span>     <span style="color:#22d3ee;">██║  ██║█████╗  ███████╗██║██║  ██╗ ██╔██╗██║</span>
<span style="color:#6190ff;">██╔══██║██║</span>    <span style="color:#818cf8;">██╔══██╗  ╚██╔╝</span>      <span style="color:#22d3ee;">██║  ██║██╔══╝  ╚════██║██║██║  ╚██╗██║╚████║</span>
<span style="color:#6190ff;">██║  ██║██║</span>    <span style="color:#818cf8;">██████╔╝   ██║</span>       <span style="color:#22d3ee;">██████╔╝███████╗███████║██║╚██████╔╝██║ ╚███║</span>
<span style="color:#6190ff;">╚═╝  ╚═╝╚═╝</span>    <span style="color:#818cf8;">╚═════╝    ╚═╝</span>       <span style="color:#22d3ee;">╚═════╝ ╚══════╝╚══════╝╚═╝ ╚═════╝ ╚═╝  ╚══╝</span>

</pre>

<div style="text-align:center; margin-top:0.5rem;">
<style>
.flap-complete { display:inline-flex; gap:0; justify-content:center; }
.fc { display:inline-block; background:rgba(255,255,255,0.04); border:1px solid rgba(255,255,255,0.06); border-radius:2px; padding:0.2rem 0.35rem; margin:0 1px; font-family:monospace; font-size:0.8rem; font-weight:700; color:rgba(255,255,255,0.8); line-height:1.3; opacity:0; animation:fcFlip 0.08s ease forwards; }
.fc.space { background:none; border:none; min-width:0.5em; }
@keyframes fcFlip { 0%{opacity:0;transform:rotateX(90deg)} 60%{transform:rotateX(-10deg)} 100%{opacity:1;transform:rotateX(0)} }
</style>
<div class="flap-complete" id="flapComplete"></div>
<script>
(function(){
var text = "LAB COMPLETE";
var el = document.getElementById("flapComplete");
if(!el) return;
var chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
text.split("").forEach(function(ch, i){
  var span = document.createElement("span");
  span.className = "fc" + (ch===" "?" space":"");
  span.style.animationDelay = (i*60)+"ms";
  if(ch!==" "){
    var count=0, max=4+Math.floor(Math.random()*4);
    var iv=setInterval(function(){
      if(count>=max){span.textContent=ch;clearInterval(iv);return;}
      span.textContent=chars[Math.floor(Math.random()*chars.length)];
      count++;
    },50);
  }
  el.appendChild(span);
});
})();
</script>
</div>

---

**You made it.** This lab took you from the fundamentals of AI all the way through to building working multimodal search systems. Here's a look back at what you covered:

| Module | What You Learned |
|--------|-----------------|
| **Module 1** — Pre-Requisites | Set up Google Colab, API keys, Webex tokens, and your lab environment |
| **Module 2** — AI/ML Revolution | Explored the foundations of AI/ML and how they power modern GenAI systems |
| **Module 3** — Tokenization | Broke text into tokens and chunks — the first step in any NLP pipeline |
| **Module 4** — Embeddings & Vector DB | Converted text into vectors, stored them in ChromaDB, SingleStore & Pinecone, and performed semantic search |
| **Module 5** — Gemini Embedding 2 | Built a multimodal search engine using Google's latest embedding model across text, images, and audio |
| **Module 6** — Context Windows & RAG | Built a Retrieval Augmented Generation pipeline to ground LLM responses with real documents |
| **Module 7** — RAG through File Search | Used Gemini's managed File Search tool to build RAG without managing your own vector database |
| **Module 8** — Multimodal RAG | Extended RAG to work with images and visual data alongside text |
| **Module 9** — GenAI Frameworks | Explored popular frameworks for building AI-powered applications |
| **Module 10** — Groq & Open Source Models | Used Groq's LPU engine with open-source models like GPT-OSS for cost-free inference |
| **Module 11** — Hugging Face APIs | Used open-source models with OpenAI-compatible endpoints |

---

!!! tip "The Thread Connecting All of This"
    Every module built on the last. Tokenization feeds into embeddings. Embeddings feed into vector databases. Vector databases power RAG. And RAG is how you connect LLMs to your own data. Whether that's Cisco documentation, meeting recordings, or a library. The same patterns you practiced here are what production AI systems use every day.

---

**Where you take this next is up to you.** You now have the building blocks to connect AI with your workflows e.g. Webex, build intelligent assistants that search across your organization's data, or create bots that understand text, images, and voice in the same conversation. The concepts don't change only the scale.

---

<p style="text-align:center; font-family:monospace; font-size:0.75rem; color:rgba(255,255,255,0.4); margin-bottom:1rem;">
<span style="color:#34d399;">$</span> echo "Thank you for attending"
</p>

<p style="text-align:center; color:rgba(255,255,255,0.7);">
Thank you for taking the time to explore <strong>AI by Design</strong> with us. Your feedback helps make this better. Reach out anytime.
</p>

<p style="text-align:center; margin-top:1.2rem;">
<a href="mailto:oilyas@cisco.com" style="display:inline-block; padding:0.5rem 1.2rem; background:linear-gradient(135deg,#3b9eff,#6366f1); color:#fff; border-radius:8px; font-weight:600; font-size:0.85rem; text-decoration:none; margin:0.3rem;">Send Feedback</a>
<a href="https://www.linkedin.com/in/omerilyas4ccie/" target="_blank" style="display:inline-block; padding:0.5rem 1.2rem; background:rgba(255,255,255,0.04); border:1px solid rgba(255,255,255,0.12); color:rgba(255,255,255,0.65); border-radius:8px; font-weight:600; font-size:0.85rem; text-decoration:none; margin:0.3rem;">Connect on LinkedIn</a>
</p>
