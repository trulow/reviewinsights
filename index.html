<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width,initial-scale=1"/>
  <title>Amazon Review Analyzer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@500;600&family=IBM+Plex+Sans:wght@400;500;600;700&display=swap" rel="stylesheet"/>
  <style>
    /* ── Reset & tokens ─────────────────────────────────────────────────────── */
    *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

    :root{
      --bg:#0d1117;--card:#161b22;--border:#30363d;
      --input:#0d1117;--input-c:#e6edf3;
      --label:#8b949e;--head:#e6edf3;--body:#c9d1d9;--muted:#6e7681;
      --div:#21262d;--wc:#484f58;--track:#21262d;--tog:#21262d;
      --btn:#238636;--btn-h:#2ea043;--sec-b:#30363d;--sec-c:#8b949e;
      --err-bg:#3d1f1f;--err-b:#6e1a1a;--err-c:#f87171;
      --ring:rgba(35,134,54,.25);--focus:#238636;
    }
    body.light{
      --bg:#f7f8fa;--card:#fff;--border:#e5e7eb;
      --input:#fafafa;--input-c:#111827;
      --label:#374151;--head:#111827;--body:#374151;--muted:#6b7280;
      --div:#f3f4f6;--wc:#9ca3af;--track:#f3f4f6;--tog:#f3f4f6;
      --btn:#2563eb;--btn-h:#1d4ed8;--sec-b:#d1d5db;--sec-c:#6b7280;
      --err-bg:#fef2f2;--err-b:#fecaca;--err-c:#b91c1c;
      --ring:rgba(37,99,235,.12);--focus:#2563eb;
    }

    /* ── Base ───────────────────────────────────────────────────────────────── */
    body{font-family:'IBM Plex Sans',sans-serif;background:var(--bg);color:var(--body);min-height:100vh;padding:32px 16px 48px;transition:background .25s,color .25s}
    .wrap{max-width:720px;margin:0 auto}

    /* ── Header ─────────────────────────────────────────────────────────────── */
    .hdr{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:24px;gap:12px}
    .hdr h1{font-size:22px;font-weight:700;color:var(--head);margin-bottom:4px}
    .hdr p{font-size:13.5px;color:var(--muted)}

    /* ── Theme toggle ───────────────────────────────────────────────────────── */
    #tog{background:var(--tog);border:1px solid var(--border);border-radius:8px;padding:7px 13px;font-size:13px;font-weight:600;color:var(--muted);cursor:pointer;display:flex;align-items:center;gap:6px;flex-shrink:0;transition:opacity .15s;font-family:inherit}
    #tog:hover{opacity:.75}

    /* ── Card ───────────────────────────────────────────────────────────────── */
    .card{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:20px 24px;margin-bottom:12px;box-shadow:0 1px 4px rgba(0,0,0,.3)}

    /* ── Inputs ─────────────────────────────────────────────────────────────── */
    .api-row{display:flex;gap:8px;align-items:center;margin-bottom:6px}
    .api-row label{font-size:13px;font-weight:600;color:var(--label);white-space:nowrap}
    .field{background:var(--input);border:1.5px solid var(--border);border-radius:8px;color:var(--input-c);transition:border-color .2s,box-shadow .2s;font-family:inherit}
    .field:focus{outline:none;border-color:var(--focus);box-shadow:0 0 0 3px var(--ring)}
    .field::placeholder{color:var(--wc)}
    #apiKey{flex:1;padding:8px 12px;font-size:13.5px;font-family:'IBM Plex Mono',monospace}
    .hint{font-size:11.5px;color:var(--muted);margin-bottom:16px}
    .hint a{color:var(--muted)}
    .lbl{display:block;font-size:13px;font-weight:600;color:var(--label);margin-bottom:8px}
    #rev{width:100%;resize:vertical;padding:10px 14px;font-size:14px;line-height:1.65;min-height:130px}
    .row{display:flex;justify-content:space-between;align-items:center;margin-top:10px}
    #wc{font-size:12px;color:var(--wc)}

    /* ── Buttons ────────────────────────────────────────────────────────────── */
    .btn-p,.btn-s{border-radius:8px;font-size:13px;font-weight:600;cursor:pointer;font-family:inherit;transition:background .15s,opacity .15s}
    .btn-p{background:var(--btn);color:#fff;border:none;padding:9px 24px;font-size:13.5px;display:flex;align-items:center;gap:7px}
    .btn-p:hover:not(:disabled){background:var(--btn-h)}
    .btn-p:disabled{opacity:.45;cursor:not-allowed}
    .btn-s{background:transparent;color:var(--sec-c);border:1px solid var(--sec-b);padding:8px 20px}
    .btn-s:hover{opacity:.75}

    /* ── Error ──────────────────────────────────────────────────────────────── */
    #err{display:none;background:var(--err-bg);border:1px solid var(--err-b);color:var(--err-c);border-radius:8px;padding:10px 14px;font-size:13px;margin-bottom:14px}

    /* ── Results ────────────────────────────────────────────────────────────── */
    #res{display:none}
    @keyframes fadeIn{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
    .fade-in{animation:fadeIn .35s ease forwards}

    #sumBar{background:var(--card);border:1px solid var(--border);border-radius:10px;padding:14px 20px;margin-bottom:14px;font-family:'IBM Plex Mono',monospace;font-size:14px;font-weight:600;color:var(--head);line-height:1.8;word-break:break-word}

    .sec-head{display:flex;align-items:center;gap:8px;margin-bottom:10px}
    .sec-head h2{font-size:15px;font-weight:700;color:var(--head)}
    .ico{font-size:17px}
    .txt{font-size:14px;color:var(--body);line-height:1.75}
    .err-mark{color:#ef4444;font-weight:700}

    .spell-list{margin:8px 0 0;padding-left:18px}
    .spell-list li{font-size:13.5px;color:#ef4444;margin-bottom:3px}

    .bar-wrap{margin-bottom:16px}
    .bar-track{height:7px;background:var(--track);border-radius:99px;overflow:hidden}
    .bar-fill{height:100%;border-radius:99px;transition:width .9s ease}

    .s-intro{font-size:14px;color:var(--body);line-height:1.7;margin-bottom:8px}
    .s-list{margin:0 0 18px;padding-left:22px}
    .s-list li,.g-list li{font-size:14px;color:var(--body);margin-bottom:5px;line-height:1.6}
    .g-head{font-size:14px;font-weight:700;color:var(--head);border-top:1px solid var(--div);padding-top:14px;margin-bottom:8px}
    .g-list{margin:0 0 16px;padding-left:22px}
    .g-list li{margin-bottom:6px;line-height:1.65}
    .sum-txt{font-size:13.5px;color:var(--muted);line-height:1.7;border-top:1px solid var(--div);padding-top:12px;font-style:italic}
    .reset-row{text-align:center;padding-bottom:8px}

    @keyframes spin{to{transform:rotate(360deg)}}
    .spin{display:inline-block;animation:spin .75s linear infinite}
  </style>
</head>
<body>
<div class="wrap">

  <div class="hdr">
    <div>
      <h1>🔍 Amazon Review Analyzer</h1>
      <p>Checks guideline compliance, spelling, and insightfulness.</p>
    </div>
    <button id="tog"><span id="togIco">☀️</span><span id="togLbl">Light mode</span></button>
  </div>

  <div class="api-row">
    <label for="apiKey">🔑 API Key</label>
    <input id="apiKey" type="password" class="field" placeholder="sk-ant-api03-…" autocomplete="off"/>
  </div>
  <p class="hint">Never stored — sent only to Anthropic. Get one at <a href="https://console.anthropic.com" target="_blank">console.anthropic.com</a>.</p>

  <div class="card">
    <label class="lbl" for="rev">Paste review text</label>
    <textarea id="rev" class="field" rows="6" placeholder="Paste the full Amazon review here…"></textarea>
    <div class="row">
      <span id="wc">0 words</span>
      <button id="analyzeBtn" class="btn-p" disabled>Analyze Review</button>
    </div>
  </div>

  <div id="err"></div>

  <div id="res">
    <div id="sumBar"></div>

    <div class="card">
      <div class="sec-head"><span id="cIco" class="ico"></span><h2>Guideline Compliance</h2></div>
      <p id="cTxt" class="txt"></p>
    </div>

    <div class="card">
      <div class="sec-head"><span id="sIco" class="ico"></span><h2>Spelling</h2></div>
      <p id="sTxt" class="txt"></p>
      <ul id="sErr" class="spell-list"></ul>
    </div>

    <div class="card">
      <div class="sec-head"><span id="iIco" class="ico"></span><h2 id="iHead"></h2></div>
      <div class="bar-wrap"><div class="bar-track"><div id="bar" class="bar-fill"></div></div></div>
      <p id="iIntro" class="s-intro"></p>
      <ul id="iStr" class="s-list"></ul>
      <p id="iSugHead" class="g-head"></p>
      <ol id="iSug" class="g-list"></ol>
      <p id="iSum" class="sum-txt"></p>
    </div>

    <div class="reset-row"><button id="resetBtn" class="btn-s">Analyze Another Review</button></div>
  </div>

</div>
<script>
// ── DOM refs (cached once) ───────────────────────────────────────────────────
const $ = id => document.getElementById(id);
const tog=$('tog'), togIco=$('togIco'), togLbl=$('togLbl');
const apiKey=$('apiKey'), rev=$('rev'), wc=$('wc'), analyzeBtn=$('analyzeBtn');
const errBox=$('err'), res=$('res');
const sumBar=$('sumBar');
const cIco=$('cIco'), cTxt=$('cTxt');
const sIco=$('sIco'), sTxt=$('sTxt'), sErr=$('sErr');
const iIco=$('iIco'), iHead=$('iHead'), bar=$('bar');
const iIntro=$('iIntro'), iStr=$('iStr'), iSugHead=$('iSugHead'), iSug=$('iSug'), iSum=$('iSum');
const resetBtn=$('resetBtn');

// ── Theme ────────────────────────────────────────────────────────────────────
let dark = true;
tog.addEventListener('click', () => {
  dark = !dark;
  document.body.classList.toggle('light', !dark);
  togIco.textContent = dark ? '☀️' : '🌙';
  togLbl.textContent = dark ? 'Light mode' : 'Dark mode';
});

// ── Word count & button state ────────────────────────────────────────────────
const updateBtn = () => {
  const words = rev.value.trim().split(/\s+/).filter(Boolean).length;
  wc.textContent = words + ' words';
  analyzeBtn.disabled = !words || !apiKey.value.trim();
};
rev.addEventListener('input', updateBtn);
apiKey.addEventListener('input', updateBtn);

// ── Score helpers ────────────────────────────────────────────────────────────
const emoji  = s => s >= 72 ? '✅' : s >= 52 ? '👍' : s >= 32 ? '⚠️' : '💩';
const color  = s => s >= 72 ? '#22c55e' : s >= 52 ? '#3b82f6' : s >= 32 ? '#f59e0b' : '#ef4444';
const target = s => s >= 90 ? '100' : s >= 80 ? '90+' : s >= 72 ? '88+' : s >= 52 ? '72+' : s >= 32 ? '52+' : '32+';
const intro  = s => s >= 88 ? 'This is a strong, balanced, and highly useful review. You clearly provide:'
                  : s >= 72 ? 'This is a strong and experience-based review. You provide:'
                  : s >= 52 ? 'This review has some helpful content. You provide:'
                  : s >= 32 ? 'This review has limited helpful content. What\'s present includes:'
                  : 'This review lacks first-hand experience. The limited content present includes:';

// ── Helpers ──────────────────────────────────────────────────────────────────
const hide = el => { el.style.display = 'none'; };
const show = el => { el.style.display = 'block'; };
const setList = (ul, items, text = s => s) => {
  ul.innerHTML = '';
  items.forEach(item => { const li = document.createElement('li'); li.textContent = text(item); ul.appendChild(li); });
};

// ── System prompt ────────────────────────────────────────────────────────────
const PROMPT = `You are an Amazon review quality analyst. Evaluate the given product review across three dimensions and return ONLY valid JSON (no markdown, no backticks, no preamble).

Return this exact JSON structure:
{
  "guidelineCompliance": {
    "pass": true,
    "explanation": "<paragraph — see tone instructions below>"
  },
  "spelling": {
    "pass": true,
    "errors": [],
    "explanation": "<No spelling errors found. OR list errors>"
  },
  "insightfulness": {
    "score": 0,
    "grade": "Excellent",
    "strengths": ["<short bullet phrase>"],
    "suggestions": [
      {"number": 1, "text": "<actionable suggestion>"},
      {"number": 2, "text": "<actionable suggestion>"},
      {"number": 3, "text": "<actionable suggestion>"},
      {"number": 4, "text": "<actionable suggestion>"}
    ],
    "summary": "<closing overall sentence — see tone instructions below>"
  }
}

SCORING RUBRIC — score out of 100:

IMPORTANT: Evaluate relative to the product type. Do NOT penalize for criteria irrelevant to the product. A usage limitation ("only works on drywall", "requires open network") counts as a valid honest caveat — do not penalize for "no critique" if a limitation is present.

CORE ELEMENTS — 10 points each, up to 60 points:
1. Personal first-hand usage (not copied specs or manufacturer claims)
2. Specific real-world context (when/where/how they used it)
3. Concrete performance observation — specific, not vague
4. Honest limitation, caveat, or criticism (including usage restrictions)
5. Feature or capability assessment relevant to the product type
6. Buyer guidance — who it suits, who it doesn't, or what scenario it fits

DEPTH ELEMENTS — up to 40 points, pick most applicable for product type:
+8  — Explains WHY something works or doesn't
+8  — Covers multiple dimensions of the product (e.g. ease of use AND performance AND durability)
+8  — Specific detail that validates a claim (weight held, distance, duration, named scenario)
+8  — Unique or differentiating feature highlighted
+6  — Reviewer background or context that adds credibility
+6  — Long-term or repeated use noted
+6  — Comparison to alternatives or prior experience
+4  — Additional practical tip or real-world scenario for future buyers

PENALTIES:
-25 — Copied product description or manufacturer claims
-15 — Purely positive with zero caveat, limitation, or criticism of any kind
-15 — Purely negative with nothing positive
-10 — Entirely vague throughout (e.g. "great product, love it" with no specifics)
-5  — Under 25 words
-5  — Mentions shipping, seller, or delivery issues

CALIBRATION ANCHOR EXAMPLES — use these to anchor your scoring:

ANCHOR A — Score: 82
Review: "These drywall hangers were surprisingly easy to use and saved me from dragging out a toolbox. I just pressed them into the wall and they felt secure right away. They held up a heavier frame without any wobbling, which gave me some peace of mind. I like that they leave only a tiny hole if you decide to move things around later. They seem sturdy and reusable, so they are great for anyone who likes to redecorate often. Just make sure you are using them on drywall since that is what they are designed for."
Why 82: Hits all 6 core elements. Earns depth for WHY (peace of mind from stability), multiple dimensions (install + performance + wall damage + reuse), practical tip. Loses points for no quantified weight, no comparison, no long-term data.

ANCHOR B — Score: 86
Review: "I set this up in my home lab so I could remotely access a couple of machines, and it has been surprisingly smooth. The video feed is clear and responsive enough that using the mouse and keyboard feels natural, even over the internet. I really appreciate that it runs on an open system, which makes it fun to tinker with and customize if you are into that kind of thing. Setup took a bit of reading at first, but once it was configured, switching between local and remote access was pretty straightforward. It feels like a solid option for anyone managing servers, a NAS, or even just a headless desktop at home. If you like having full control over your gear without relying on heavy software installs, this is a pretty powerful little tool."
Why 86: All 6 core elements. Strong depth: WHY (open system = customizable), multiple dimensions (video + setup + use cases), differentiating feature (open platform), specific buyer scenarios. Loses for no long-term data, no specs, no comparison.

ANCHOR C — Score: 91
Review: "I wore this jacket on a few warm rides and the airflow is definitely the highlight. The mesh panels let a lot of air through, which makes a big difference in hot weather. It comes with armor in the shoulders and elbows, and it stays in place fairly well once you adjust the straps. That said, the material feels on the thinner side and a bit cheaper than I expected. I am not completely confident about how it would hold up in a serious fall, so that is something to keep in mind. For casual summer riding and shorter trips it works fine, but I would weigh your priorities if maximum durability is your main concern."
Why 91: All 6 core elements strongly. Excellent depth: WHY (mesh = airflow), multiple dimensions (airflow + armor + material + durability), honest safety caveat, trade-off buyer guidance. Only missing quantified ride time and comparison.

ANCHOR D — Score: 81
Review: "I installed these short levers and they instantly gave the bike a cleaner, more aggressive look. The finish looks sharp and the metal feels solid, not flimsy or cheap. I really like the adjustable reach since it made it easy to dial in a comfortable position for my hands. The shorter length works well with two fingers and feels more responsive when riding. Installation was straightforward as long as you take your time and line everything up properly. Overall they feel like a nice balance of style and function without being over the top."
Why 81: All 6 core elements. WHY (adjustable reach = comfort, shorter = responsive), multiple dimensions (aesthetics + build + ergonomics + install + riding feel). Loses for no long-term data, no comparison, no specs. Score 79-83.

ANCHOR E — Score: 81
Review: "I have been using this Bluetooth headset for calls during the day and I am honestly impressed with how long the battery lasts. I can go several days without even thinking about charging it, and the little display on the case makes it easy to see how much power is left. It feels really light in my ear and does not bother me even after wearing it through back to back meetings. Call quality has been clear on both ends, and people have not complained about background noise when I am walking around. It also pairs quickly with my phone and laptop, which makes switching between devices pretty painless. Overall it feels like a solid everyday option if you spend a lot of time on calls and want something simple and reliable."
Why 81: All 6 core elements. Multiple dimensions (battery + comfort + call quality + noise + pairing). WHY (display = easy monitoring, light = comfortable extended wear). Missing: no drawbacks, no quantified hours, no comparison. Score 79-83.

ANCHOR F — Score: 79
Review: "I picked these up after removing my stock mirrors and they were exactly what I needed to clean up the look. The threads fit properly and I liked that it came with both the right and left side pieces, so there was no guessing. Installation was simple and I was able to tighten them by hand without any hassle. They sit flush and really help cover up those open holes so the bike looks more finished. The material feels solid and the color has a nice clean finish that does not look cheap. For such a small part, they make a noticeable difference in how tidy the front end looks."
Why 79: All 6 core elements. WHY (flush fit = finished look). Simpler product, less multi-dimension depth, no caveat. Score 76-80.

ANCHOR G — Score: 82
Review: "I swapped these in to replace my stock front signals and they instantly gave the bike a cleaner look. The smoked lens blends in nicely when they are off, but once they light up they are surprisingly bright and easy to see. Installation was pretty straightforward and the included spacers helped get a snug fit without any weird gaps. The build quality feels solid and they seem well sealed, which gives me some confidence riding in the rain. I did notice the blink rate was a bit faster at first, so keep that in mind if you are sensitive to that. Overall they are a nice upgrade if you want something sleeker without sacrificing visibility."
Why 82: All 6 core elements. Multiple dimensions (aesthetics + brightness + install + build + weather sealing). Genuine drawback (blink rate). WHY (sealed = rain confidence, smoked = clean off / bright on). Score 80-84.

ANCHOR H — Score: 74
Review: "I swapped these in to replace the bulky stock signals and they instantly cleaned up the look of the bike. The smoked lens gives it a sleek touch, but they still light up bright and clear when signaling. I was honestly surprised by how visible they are, even during the day. Installation was pretty straightforward and everything lined up the way it should. They feel solid and well sealed, so I am not worried about riding in the rain. If you want something that looks more modern without being complicated to install, these are a nice upgrade."
Why 74: Same product as G but thinner — no spacer detail, no drawback, broader language. Covers core but lacks G's depth. Score 72-76.

CRITICAL: Anchors G and H are near-identical reviews. G=82 because it has a drawback, specific install detail, and dual-state contrast. H=74 because it lacks all three. Use this pair to calibrate similar reviews.

ANCHOR I — Score: 80
Review: "I grabbed this adapter because I still prefer using wired headphones, and it has been really convenient being able to charge my phone at the same time. The sound quality is actually pretty solid and I did not notice any static or weird noise during calls or music. Fast charging works as expected and my phone still powers up quickly even while I am listening to something. It feels lightweight and easy to toss in a bag without taking up much space. I like that it is simple to use and does not require any setup, just plug it in and it works. If you miss having a headphone jack but also need to keep your battery up, this is a handy little solution."
Why 80: All 6 core elements. Multiple dimensions (audio + charging + portability + ease of use). WHY (simultaneous charge + audio = convenience). Missing: no drawbacks, no long-term use, no compatibility specifics. Score 78-82.

ANCHOR J — Score: 85
Review: "I brought this out for a game night and it honestly became the main attraction at the table. The shuffling is smooth and way faster than having someone do it by hand, which keeps the game moving without awkward pauses. I really liked the automatic dealing feature, especially for poker since it rotates properly and saves us from tracking everything ourselves. It runs pretty quietly, so it does not overpower conversation, and the battery lasted through several hours of play without needing a recharge. Setup took a few minutes to figure out, but once we got the hang of it, it was easy to customize for different games. If you host card nights often, this definitely adds a fun and surprisingly practical upgrade to the whole experience."
Why 85: All 6 core elements. Wide coverage (shuffle + deal + noise + battery + setup + customization). WHY throughout. Vivid buyer guidance. No drawbacks, no deck specs. Score 83-87.

ANCHOR K — Score: 80
Review: "This mat is a great size for small counter spaces and fits neatly without taking up too much room. It feels thick and sturdy, and once you place it down it does not slide around. I was glad there was no strong odor when I opened it, so it was ready to use right away. The raised surface helps keep items elevated so they can dry instead of sitting in pooled liquid. It also does a nice job catching drips and protecting the surface underneath. Cleanup is simple since you can just rinse it off and let it dry."
Why 80: All 6 core elements. 7 distinct dimensions. WHY (raised surface = airflow/drying, no odor = ready immediately). Missing: no long-term use, no material, no drawback. Score 78-82. Do NOT score below 78 — breadth across 7 dimensions compensates.

ANCHOR L — Score: 84
Review: "I started using these electrolyte packets during workouts and they have been a nice addition to my routine. The fruit punch flavor is refreshing without being overly sweet, which I appreciate during longer sessions. It mixes easily in a water bottle and does not leave any weird aftertaste. I also like that the ingredient list is simple and not packed with a bunch of unnecessary extras. It seems to help me stay better hydrated, especially on hotter days or after intense training. Overall it is a convenient option to keep in a gym bag when you need a quick hydration boost."
Why 84: All 6 core elements. 7 dimensions (context + flavor + sweetness + mixability + aftertaste + ingredients + hydration + portability). WHY in several places. Specific conditions (hotter days, intense training). Missing: no drawbacks, no duration, no mixing ratio. Score 82-86. Do NOT score below 80.

GRADE LABELS:
- 88-100: Excellent
- 72-87:  Excellent
- 52-71:  Good
- 32-51:  Average
- 0-31:   Poor

TONE INSTRUCTIONS:

guidelineCompliance.explanation:
- Compliant: Start "Your review follows the community guidelines." Explain what they did right. End "No violations detected."
- Non-compliant: Start "❌ This review violates Amazon's community guidelines." Explain the violation precisely.

insightfulness strengths: Short phrase naming the specific insight with parenthetical detail from the review, e.g. "Real-world usage context (warm weather riding, multiple rides)". Reference actual details from THIS review only.

insightfulness.summary: 2-3 sentences. (1) What makes it strong/weak. (2) Why those elements matter to buyers. (3) "Overall, this review [comfortably meets / narrowly meets / falls short of] the '[Grade]' standard [short reason]."

GUIDELINE COMPLIANCE RULES:
- Must reflect personal experience, NOT copied product descriptions
- No shipping/delivery/seller/ordering complaints
- No product damage on arrival
- No individual pricing complaints
- No profanity or harassment
- No personal information
- No medical cure/treatment claims
- No promotional content or links
- No incentivized review indicators`;

// ── Analyze ──────────────────────────────────────────────────────────────────
analyzeBtn.addEventListener('click', async () => {
  const review = rev.value.trim();
  const key = apiKey.value.trim();
  if (!review || !key) return;

  analyzeBtn.disabled = true;
  analyzeBtn.innerHTML = '<span class="spin">⟳</span> Analyzing…';
  hide(errBox); hide(res);

  try {
    const r = await fetch('https://api.anthropic.com/v1/messages', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'x-api-key': key,
        'anthropic-version': '2023-06-01',
        'anthropic-dangerous-direct-browser-access': 'true'
      },
      body: JSON.stringify({
        model: 'claude-sonnet-4-20250514',
        max_tokens: 1500,
        system: PROMPT,
        messages: [{ role: 'user', content: `Analyze this Amazon product review:\n\n${review}` }]
      })
    });

    if (!r.ok) {
      const e = await r.json().catch(() => ({}));
      throw new Error(e?.error?.message || `API error ${r.status}`);
    }

    const d = await r.json();
    const txt = (d.content || []).map(b => b.text || '').join('');
    render(JSON.parse(txt.replace(/```json|```/g, '').trim()));

  } catch (e) {
    errBox.textContent = e.message || 'Something went wrong. Please check your API key and try again.';
    show(errBox);
  } finally {
    analyzeBtn.disabled = false;
    analyzeBtn.innerHTML = 'Analyze Review';
    updateBtn();
  }
});

// ── Render ───────────────────────────────────────────────────────────────────
function render(d) {
  const sc = d.insightfulness.score;
  const gr = d.insightfulness.grade;
  const em = emoji(sc);

  // Summary bar
  sumBar.innerHTML =
    `1 - Guideline Compliance: ${d.guidelineCompliance.pass ? '✅' : '❌'}&nbsp;&nbsp;` +
    `2 - Spelling: ${d.spelling.pass ? '✅' : '❌'}&nbsp;&nbsp;` +
    `3 - Insightfulness: ${sc}/100 – ${em} ${gr}`;

  // Compliance
  cIco.textContent = d.guidelineCompliance.pass ? '✅' : '❌';
  cTxt.innerHTML = d.guidelineCompliance.pass ? '' : '<strong class="err-mark">❌ </strong>';
  cTxt.appendChild(document.createTextNode(d.guidelineCompliance.explanation));

  // Spelling
  sIco.textContent = d.spelling.pass ? '✅' : '❌';
  sTxt.textContent = d.spelling.explanation;
  setList(sErr, d.spelling.pass ? [] : (d.spelling.errors || []));

  // Insightfulness
  iIco.textContent = em;
  iHead.textContent = `Insightfulness Evaluation (${sc}/100 – ${em} ${gr})`;
  bar.style.background = color(sc);
  bar.style.width = '0%';
  setTimeout(() => { bar.style.width = sc + '%'; }, 50);
  iIntro.textContent = intro(sc);
  setList(iStr, d.insightfulness.strengths || []);
  iSugHead.textContent = `Suggestions to Increase Insightfulness (toward ${target(sc)}):`;
  setList(iSug, d.insightfulness.suggestions || [], s => s.text);
  iSum.textContent = d.insightfulness.summary;

  // Animate in
  res.style.display = 'block';
  res.classList.remove('fade-in');
  void res.offsetWidth;
  res.classList.add('fade-in');
}

// ── Reset ────────────────────────────────────────────────────────────────────
resetBtn.addEventListener('click', () => {
  rev.value = '';
  hide(res); hide(errBox);
  updateBtn();
  rev.focus();
});
</script>
</body>
</html>
