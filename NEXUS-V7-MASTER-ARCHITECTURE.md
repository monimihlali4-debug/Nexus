
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#070b0a">
<meta name="description" content="NEXUS V7 - Next Generation Personal Intelligence">
<title>NEXUS V7 | Intelligence System</title>

<style>
:root {
  --bg:#070b0a;
  --panel:#101816;
  --panel2:#14201c;
  --green:#35f0a0;
  --green2:#12b981;
  --text:#ecf8f2;
  --muted:#91a69c;
  --border:rgba(91,224,164,.17);
  --danger:#ff7272;
  --gold:#e7c878;
}
*{box-sizing:border-box}
body{
  margin:0;
  background:
    radial-gradient(ellipse at 80% 0%,rgba(22,120,81,.15),transparent 42%),
    var(--bg);
  color:var(--text);
  font-family:Inter,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
  min-height:100vh;
}
button,input,textarea{font:inherit}
button{cursor:pointer}
.app{display:flex;min-height:100vh}
.sidebar{
  width:255px;
  background:#090f0d;
  border-right:1px solid var(--border);
  padding:24px 16px;
  display:flex;
  flex-direction:column;
  gap:20px;
}
.brand{display:flex;align-items:center;gap:12px;padding:4px 8px}
.logo{
  width:43px;height:43px;border-radius:14px;
  display:grid;place-items:center;
  color:#06140e;font-size:21px;font-weight:900;
  background:linear-gradient(135deg,#66ffc0,#0ba66e);
  box-shadow:0 0 28px #1bc78644;
}
.brand h1{font-size:18px;letter-spacing:3px;margin:0}
.brand small{color:var(--muted);font-size:9px;letter-spacing:2px}
.section-label{
  color:#64786e;font-size:10px;letter-spacing:2px;
  padding:4px 10px;text-transform:uppercase
}
.nav{display:grid;gap:6px}
.nav button{
  background:transparent;border:1px solid transparent;
  color:#9eb1a7;text-align:left;padding:12px;
  border-radius:10px;font-size:13px;
}
.nav button:hover,.nav button.active{
  background:#14231c;color:var(--green);
  border-color:var(--border)
}
.sidebar-bottom{margin-top:auto}
.owner-card{
  background:linear-gradient(145deg,#14251e,#0d1512);
  border:1px solid var(--border);border-radius:14px;
  padding:14px;font-size:12px;
}
.owner-card strong{color:var(--green)}
.main{flex:1;min-width:0;padding:25px 30px}
.topbar{
  display:flex;justify-content:space-between;align-items:center;
  gap:12px;margin-bottom:28px
}
.eyebrow{font-size:10px;color:var(--green);letter-spacing:3px}
.topbar h2{font-size:20px;margin:6px 0}
.status{
  display:flex;align-items:center;gap:8px;
  color:var(--muted);font-size:11px
}
.dot{width:8px;height:8px;background:var(--green);border-radius:50%;
  box-shadow:0 0 10px var(--green)}
.view{display:none;animation:appear .25s ease}
.view.active{display:block}
@keyframes appear{from{opacity:0;transform:translateY(5px)}to{opacity:1;transform:translateY(0)}}
.hero{
  min-height:220px;border:1px solid var(--border);
  border-radius:22px;padding:30px;
  background:
    radial-gradient(circle at 82% 48%,#1c805044,transparent 27%),
    linear-gradient(120deg,#13251d,#0c1411);
  display:flex;align-items:center;justify-content:space-between;
  gap:20px;overflow:hidden
}
.hero h2{font-size:clamp(28px,5vw,45px);margin:12px 0}
.hero p{color:var(--muted);max-width:530px;line-height:1.7;font-size:13px}
.core{
  width:130px;height:130px;flex-shrink:0;border-radius:50%;
  border:1px solid #45e9a566;
  display:grid;place-items:center;
  background:radial-gradient(circle,#3bffad33,#10221a 65%);
  box-shadow:0 0 50px #1fce8540,inset 0 0 30px #3cff9c22;
  animation:pulse 4s ease-in-out infinite
}
.core span{font-size:35px;color:var(--green)}
@keyframes pulse{50%{transform:scale(1.05);box-shadow:0 0 70px #1fce8560}}
.grid{
  display:grid;grid-template-columns:repeat(4,minmax(0,1fr));
  gap:13px;margin:18px 0
}
.metric,.panel{
  background:var(--panel);border:1px solid var(--border);
  border-radius:15px;padding:17px
}
.metric small{color:var(--muted);font-size:11px}
.metric strong{display:block;font-size:24px;margin-top:10px}
.metric .sub{font-size:10px;color:var(--green);margin-top:5px}
.content-grid{
  display:grid;grid-template-columns:1.3fr .7fr;gap:15px
}
.panel h3{font-size:14px;margin:0 0 14px}
.panel p{color:var(--muted);font-size:12px;line-height:1.7}
.module-list{display:grid;gap:9px}
.module{
  display:flex;justify-content:space-between;align-items:center;
  gap:10px;padding:12px;border-radius:10px;
  background:#121d18;border:1px solid #ffffff08;font-size:12px
}
.module small{color:var(--muted)}
.tag{
  color:var(--green);font-size:9px;
  border:1px solid var(--border);padding:5px 7px;border-radius:20px
}
.btn{
  border:1px solid var(--border);background:#173225;
  color:var(--green);padding:11px 15px;border-radius:9px;
  font-size:12px
}
.btn:hover{background:#204a35}
.btn.primary{background:var(--green);color:#07140d;font-weight:800}
.btn.secondary{background:#17201c;color:var(--text)}
.btn.danger{color:var(--danger)}
.actions{display:flex;gap:9px;flex-wrap:wrap}
.chat-layout{display:flex;flex-direction:column;height:65vh;min-height:450px}
.chat-log{
  flex:1;overflow:auto;display:flex;flex-direction:column;
  gap:12px;padding:12px 3px
}
.message{
  max-width:85%;padding:13px 15px;border-radius:13px;
  font-size:13px;line-height:1.65;white-space:pre-wrap
}
.message.system{background:#15231c;border:1px solid var(--border);align-self:flex-start}
.message.user{background:#16472f;align-self:flex-end}
.chat-form{display:flex;gap:8px;padding-top:12px;border-top:1px solid var(--border)}
.chat-form input,.field{
  min-width:0;flex:1;background:#080e0c;color:var(--text);
  border:1px solid var(--border);border-radius:10px;padding:13px;
  outline:none
}
.chat-form input:focus,.field:focus{border-color:var(--green)}
.task-form{display:flex;gap:8px;margin-bottom:15px}
.task-list{display:grid;gap:8px}
.task{
  display:flex;align-items:center;gap:10px;
  padding:12px;background:#121d18;border-radius:10px;
  font-size:12px
}
.task input{accent-color:var(--green)}
.task.done span{text-decoration:line-through;color:#71847a}
textarea.field{width:100%;min-height:120px;resize:vertical}
.memory-list{display:grid;gap:10px}
.memory-item{padding:14px;background:#121d18;border-radius:10px}
.memory-item strong{font-size:12px}
.memory-item p{margin:7px 0 0}
.setting{
  display:flex;justify-content:space-between;gap:15px;
  padding:15px 0;border-bottom:1px solid var(--border)
}
.setting strong{font-size:12px}
.setting small{display:block;color:var(--muted);margin-top:5px}
.footer{color:#60736a;font-size:10px;text-align:center;margin-top:28px}
.notice{
  border:1px solid #c4a14b44;background:#c4a14b10;
  color:#d9c58e;padding:13px;border-radius:10px;
  font-size:11px;line-height:1.6;margin-bottom:15px
}
.empty{color:var(--muted);font-size:12px;padding:15px 0}
@media(max-width:900px){
 .sidebar{width:210px}
 .grid{grid-template-columns:repeat(2,1fr)}
 .content-grid{grid-template-columns:1fr}
}
@media(max-width:650px){
 .app{display:block}
 .sidebar{width:100%;padding:12px;border-right:0;border-bottom:1px solid var(--border)}
 .brand{padding:4px}
 .nav{display:flex;overflow-x:auto;gap:5px}
 .nav button{white-space:nowrap;padding:10px;font-size:11px}
 .section-label,.sidebar-bottom{display:none}
 .main{padding:18px 13px}
 .topbar{margin-bottom:18px}
 .hero{padding:22px;min-height:190px}
 .core{width:75px;height:75px}
 .core span{font-size:24px}
 .grid{gap:8px}
 .metric{padding:12px}
 .metric strong{font-size:20px}
 .chat-layout{height:62vh}
}
</style>
</head>

<body>
<div class="app">

<aside class="sidebar">
  <div class="brand">
    <div class="logo">N</div>
    <div>
      <h1>NEXUS</h1>
      <small>VERSION 7.0</small>
    </div>
  </div>

  <div>
    <div class="section-label">Intelligence</div>
    <nav class="nav">
      <button class="active" data-view="dashboard">◈ Overview</button>
      <button data-view="assistant">✧ AI Workspace</button>
      <button data-view="research">⌕ Research Lab</button>
      <button data-view="memory">▤ Project Memory</button>
      <button data-view="tasks">✓ Mission Control</button>
    </nav>
  </div>

  <div>
    <div class="section-label">Command systems</div>
    <nav class="nav">
      <button data-view="business">⌘ GTHC Intelligence</button>
      <button data-view="diagnostics">◉ Diagnostics</button>
      <button data-view="security">⬡ Security Centre</button>
      <button data-view="settings">⚙ System Settings</button>
    </nav>
  </div>

  <div class="sidebar-bottom">
    <div class="owner-card">
      <strong>OWNER CONTROL</strong>
      <p>Local prototype mode</p>
      <small>Backend authentication not connected.</small>
    </div>
  </div>
</aside>

<main class="main">
  <header class="topbar">
    <div>
      <div class="eyebrow">GTHC • CHIEF SCIENTIST EDITION</div>
      <h2 id="pageTitle">Intelligence Overview</h2>
    </div>
    <div class="status"><span class="dot"></span> Interface online</div>
  </header>

  <section class="view active" id="dashboard">
    <div class="hero">
      <div>
        <div class="eyebrow">NEXT GENERATION INTELLIGENCE</div>
        <h2>Think beyond<br>the possible.</h2>
        <p>NEXUS is designed to connect your ideas, personal goals, research and GTHC strategy into one intelligent workspace.</p>
        <div class="actions">
          <button class="btn primary" onclick="showView('assistant')">Open AI Workspace ↗</button>
          <button class="btn secondary" onclick="showView('diagnostics')">System diagnostics</button>
        </div>
      </div>
      <div class="core"><span>✧</span></div>
    </div>

    <div class="grid">
      <div class="metric"><small>VERSION</small><strong>V7.0</strong><div class="sub">Master build</div></div>
      <div class="metric"><small>MODULES PLANNED</small><strong>28</strong><div class="sub">Architecture targets</div></div>
      <div class="metric"><small>LOCAL TASKS</small><strong id="taskCount">0</strong><div class="sub">Saved on this device</div></div>
      <div class="metric"><small>AI CONNECTION</small><strong style="font-size:17px">Pending</strong><div class="sub">Backend required</div></div>
    </div>

    <div class="content-grid">
      <div class="panel">
        <h3>Core intelligence architecture</h3>
        <div class="module-list">
          <div class="module"><span>N7-001 • Core Intelligence</span><span class="tag">Designed</span></div>
          <div class="module"><span>N7-002 • Cognitive Reasoning</span><span class="tag">Designed</span></div>
          <div class="module"><span>N7-003 • Owner Understanding</span><span class="tag">Designed</span></div>
          <div class="module"><span>N7-004 • Context Architecture</span><span class="tag">Designed</span></div>
          <div class="module"><span>N7-005 • Long-Term Memory</span><span class="tag">Local only</span></div>
          <div class="module"><span>N7-016 • Truth Verification</span><span class="tag">Designed</span></div>
        </div>
      </div>
      <div class="panel">
        <h3>Chief Scientist directive</h3>
        <p>Build intelligence that distinguishes verified facts, assumptions, unknowns and predictions.</p>
        <p>Every important action must be permission-based, measurable and reversible where possible.</p>
        <button class="btn" onclick="showView('research')">Enter Research Lab</button>
      </div>
    </div>
  </section>

  <section class="view" id="assistant">
    <div class="notice">AI connection status: not connected. This workspace can store and display your local messages, but it cannot provide genuine AI reasoning until a secure AI backend is installed.</div>
    <div class="panel chat-layout">
      <div>
        <h3>NEXUS • Intelligence Workspace</h3>
        <p>Describe an idea, ask a question or prepare a mission.</p>
      </div>
      <div class="chat-log" id="chatLog">
        <div class="message system">NEXUS V7 interface initialized.\n\nI am ready to organise your ideas and prepare work. My live AI intelligence connection has not yet been configured.</div>
      </div>
      <form class="chat-form" id="chatForm">
        <input id="chatInput" placeholder="Enter your command or idea..." autocomplete="off" required>
        <button class="btn primary" type="submit">Send</button>
      </form>
    </div>
  </section>

  <section class="view" id="research">
    <div class="panel">
      <h3>Scientific Research Laboratory</h3>
      <p>Prepare research questions, hypotheses and verification plans. This local tool does not independently search scientific databases.</p>
      <label class="eyebrow">RESEARCH QUESTION</label>
      <textarea class="field" id="researchQuestion" placeholder="What do we want to investigate?"></textarea>
      <br><br>
      <button class="btn primary" onclick="prepareResearch()">Prepare research framework</button>
      <div id="researchOutput" class="memory-item" style="margin-top:15px;display:none"></div>
    </div>
    <div class="panel" style="margin-top:15px">
      <h3>Verification principles</h3>
      <div class="module-list">
        <div class="module"><span>Verified information</span><span class="tag">Evidence needed</span></div>
        <div class="module"><span>Assumptions</span><span class="tag">Label clearly</span></div>
        <div class="module"><span>Predictions</span><span class="tag">Not facts</span></div>
        <div class="module"><span>Unknown information</span><span class="tag">Investigate</span></div>
      </div>
    </div>
  </section>

  <section class="view" id="memory">
    <div class="panel">
      <h3>Project Memory Vault</h3>
      <p>Save project notes in this browser. These are not cloud-synchronised or encrypted account memory.</p>
      <input class="field" id="memoryTitle" placeholder="Memory title">
      <br><br>
      <textarea class="field" id="memoryContent" placeholder="Write an important idea, decision or project detail..."></textarea>
      <br><br>
      <button class="btn primary" onclick="saveMemory()">Save project memory</button>
      <div class="memory-list" id="memoryList" style="margin-top:18px"></div>
    </div>
  </section>

  <section class="view" id="tasks">
    <div class="panel">
      <h3>Mission Control</h3>
      <p>Break large ambitions into trackable actions.</p>
      <form class="task-form" id="taskForm">
        <input class="field" id="taskInput" placeholder="Enter a mission..." required>
        <button class="btn primary">Add</button>
      </form>
      <div class="task-list" id="taskList"></div>
    </div>
  </section>

  <section class="view" id="business">
    <div class="panel">
      <h3>Global Technology Holding Company</h3>
      <p>Strategic workspace for GTHC projects, business development and founder-controlled operations.</p>
      <div class="module-list">
        <div class="module"><span>Group strategy</span><span class="tag">Workspace</span></div>
        <div class="module"><span>Project development</span><span class="tag">Workspace</span></div>
        <div class="module"><span>Business performance</span><span class="tag">Awaiting data</span></div>
        <div class="module"><span>Financial intelligence</span><span class="tag">Awaiting data</span></div>
        <div class="module"><span>Risk and opportunity analysis</span><span class="tag">Planned</span></div>
      </div>
      <p>Financial decisions must use real business records, not invented figures.</p>
    </div>
  </section>

  <section class="view" id="diagnostics">
    <div class="panel">
      <h3>System Diagnostics</h3>
      <p>Checks available in this browser session.</p>
      <div class="module-list" id="diagnosticList">
        <div class="module"><span>Application interface</span><span class="tag">Checking</span></div>
        <div class="module"><span>Local storage</span><span class="tag">Checking</span></div>
        <div class="module"><span>AI backend</span><span class="tag">Not connected</span></div>
        <div class="module"><span>Owner authentication</span><span class="tag">Not configured</span></div>
        <div class="module"><span>Cloud backup</span><span class="tag">Not configured</span></div>
      </div>
      <br>
      <button class="btn primary" onclick="runDiagnostics()">Run diagnostics</button>
      <p id="diagnosticResult"></p>
    </div>
  </section>

  <section class="view" id="security">
    <div class="notice">This is not a secure owner login. Do not store passwords, API keys, financial secrets or confidential business data in this prototype.</div>
    <div class="panel">
      <h3>Security and Permission Centre</h3>
      <div class="setting">
        <div><strong>Owner authentication</strong><small>Requires a secure backend and verified identity.</small></div>
        <span class="tag">Not configured</span>
      </div>
      <div class="setting">
        <div><strong>Voice identity</strong><small>Voice recognition must not be the only authentication factor.</small></div>
        <span class="tag">Planned</span>
      </div>
      <div class="setting">
        <div><strong>External actions</strong><small>Require explicit user approval before execution.</small></div>
        <span class="tag">Principle</span>
      </div>
      <div class="setting">
        <div><strong>Secret management</strong><small>Secrets belong on a protected server, never in public HTML.</small></div>
        <span class="tag">Required</span>
      </div>
    </div>
  </section>

  <section class="view" id="settings">
    <div class="panel">
      <h3>System Settings</h3>
      <div class="setting">
        <div><strong>System name</strong><small>NEXUS V7 • Chief Scientist Edition</small></div>
        <span class="tag">Active</span>
      </div>
      <div class="setting">
        <div><strong>Display mode</strong><small>Obsidian and emerald interface</small></div>
        <span class="tag">Active</span>
      </div>
      <div class="setting">
        <div><strong>Data storage</strong><small>Browser local storage on this device</small></div>
        <span class="tag">Local</span>
      </div>
      <div class="setting">
        <div><strong>Application version</strong><small>7.0.0 initial interface build</small></div>
        <span class="tag">V7.0</span>
      </div>
      <br>
      <button class="btn danger" onclick="clearLocalData()">Clear local prototype data</button>
    </div>
  </section>

  <div class="footer">NEXUS V7 • GTHC • BUILT FOR RESPONSIBLE INTELLIGENCE</div>
</main>
</div>

<script>
"use strict";

const STORAGE = {
  tasks: "nexus_v7_tasks",
  memories: "nexus_v7_memories",
  messages: "nexus_v7_messages"
};

function readData(key) {
  try {
    const data = localStorage.getItem(key);
    return data ? JSON.parse(data) : [];
  } catch (error) {
    return [];
  }
}

function writeData(key, data) {
  try {
    localStorage.setItem(key, JSON.stringify(data));
    return true;
  } catch (error) {
    alert("Unable to save. Browser storage may be full or unavailable.");
    return false;
  }
}

const titles = {
  dashboard:"Intelligence Overview",
  assistant:"AI Workspace",
  research:"Scientific Research Lab",
  memory:"Project Memory Vault",
  tasks:"Mission Control",
  business:"GTHC Intelligence",
  diagnostics:"System Diagnostics",
  security:"Security Centre",
  settings:"System Settings"
};

function showView(name) {
  const target = document.getElementById(name);
  if (!target) return;

  document.querySelectorAll(".view").forEach(view => {
    view.classList.toggle("active", view.id === name);
  });

  document.querySelectorAll("[data-view]").forEach(button => {
    button.classList.toggle("active", button.dataset.view === name);
  });

  document.getElementById("pageTitle").textContent = titles[name] || "NEXUS";
  window.scrollTo({top:0,behavior:"smooth"});
}

document.querySelectorAll("[data-view]").forEach(button => {
  button.addEventListener("click", () => showView(button.dataset.view));
});

// TASK MANAGEMENT
function renderTasks() {
  const tasks = readData(STORAGE.tasks);
  const list = document.getElementById("taskList");
  list.innerHTML = "";

  document.getElementById("taskCount").textContent =
    tasks.filter(task => !task.done).length;

  if (!tasks.length) {
    list.innerHTML = '<div class="empty">No missions created yet.</div>';
    return;
  }

  tasks.forEach(task => {
    const row = document.createElement("div");
    row.className = "task" + (task.done ? " done" : "");

    const checkbox = document.createElement("input");
    checkbox.type = "checkbox";
    checkbox.checked = task.done;
    checkbox.addEventListener("change", () => {
      const current = readData(STORAGE.tasks);
      const item = current.find(t => t.id === task.id);
      if (item) item.done = checkbox.checked;
      writeData(STORAGE.tasks,current);
      renderTasks();
    });

    const label = document.createElement("span");
    label.textContent = task.text;
    label.style.flex = "1";

    const remove = document.createElement("button");
    remove.className = "btn secondary";
    remove.textContent = "Delete";
    remove.addEventListener("click", () => {
      writeData(STORAGE.tasks,
        readData(STORAGE.tasks).filter(t => t.id !== task.id));
      renderTasks();
    });

    row.append(checkbox,label,remove);
    list.appendChild(row);
  });
}

document.getElementById("taskForm").addEventListener("submit", event => {
  event.preventDefault();
  const input = document.getElementById("taskInput");
  const text = input.value.trim();
  if (!text) return;

  const tasks = readData(STORAGE.tasks);
  tasks.unshift({
    id: Date.now(),
    text,
    done:false,
    createdAt:new Date().toISOString()
  });

  if (writeData(STORAGE.tasks,tasks)) {
    input.value = "";
    renderTasks();
  }
});

// PROJECT MEMORY
function renderMemories() {
  const memories = readData(STORAGE.memories);
  const list = document.getElementById("memoryList");
  list.innerHTML = "";

  if (!memories.length) {
    list.innerHTML = '<div class="empty">No project memories saved.</div>';
    return;
  }

  memories.forEach(memory => {
    const item = document.createElement("div");
    item.className = "memory-item";

    const heading = document.createElement("strong");
    heading.textContent = memory.title;

    const body = document.createElement("p");
    body.textContent = memory.content;

    const date = document.createElement("small");
    date.textContent = new Date(memory.date).toLocaleString();
    date.style.color = "#91a69c";

    const remove = document.createElement("button");
    remove.className = "btn secondary";
    remove.textContent = "Delete memory";
    remove.style.marginTop = "10px";
    remove.addEventListener("click", () => {
      writeData(STORAGE.memories,
        readData(STORAGE.memories).filter(m => m.id !== memory.id));
      renderMemories();
    });

    item.append(heading,body,date,remove);
    list.appendChild(item);
  });
}

function saveMemory() {
  const title = document.getElementById("memoryTitle").value.trim();
  const content = document.getElementById("memoryContent").value.trim();

  if (!title || !content) {
    alert("Enter both a title and memory.");
    return;
  }

  const memories = readData(STORAGE.memories);
  memories.unshift({
    id:Date.now(),
    title,
    content,
    date:new Date().toISOString()
  });

  if (writeData(STORAGE.memories,memories)) {
    document.getElementById("memoryTitle").value = "";
    document.getElementById("memoryContent").value = "";
    renderMemories();
  }
}

// CHAT INTERFACE
function addMessage(text, role) {
  const log = document.getElementById("chatLog");
  const message = document.createElement("div");
  message.className = "message " + role;
  message.textContent = text;
  log.appendChild(message);
  log.scrollTop = log.scrollHeight;
}

document.getElementById("chatForm").addEventListener("submit", event => {
  event.preventDefault();

  const input = document.getElementById("chatInput");
  const text = input.value.trim();
  if (!text) return;

  addMessage(text,"user");

  const messages = readData(STORAGE.messages);
  messages.push({role:"user",text,date:new Date().toISOString()});
  writeData(STORAGE.messages,messages);

  input.value = "";

  addMessage(
    "Your request has been recorded in this local interface. A real NEXUS AI response requires the secure AI backend, which is not connected yet. I will not pretend that this prototype has performed AI reasoning.",
    "system"
  );
});

// RESEARCH FRAMEWORK
function prepareResearch() {
  const question = document.getElementById("researchQuestion").value.trim();
  const output = document.getElementById("researchOutput");

  if (!question) {
    alert("Enter a research question first.");
    return;
  }

  output.style.display = "block";
  output.replaceChildren();

  const heading = document.createElement("strong");
  heading.textContent = "Research preparation framework";

  const details = document.createElement("p");
  details.textContent =
    "Question: " + question +
    "\n\n1. Define the research objective." +
    "\n2. Identify what evidence is needed." +
    "\n3. List possible hypotheses." +
    "\n4. Find credible primary sources." +
    "\n5. Check limitations and conflicting evidence." +
    "\n6. Separate verified findings from assumptions." +
    "\n7. Record conclusions and unresolved questions.";

  details.style.whiteSpace = "pre-wrap";
  output.append(heading,details);
}

// DIAGNOSTICS
function runDiagnostics() {
  const list = document.getElementById("diagnosticList");
  const result = document.getElementById("diagnosticResult");
  const storageWorks = (() => {
    try {
      const key = "__nexus_test";
      localStorage.setItem(key,"ok");
      localStorage.removeItem(key);
      return true;
    } catch (error) {
      return false;
    }
  })();

  const checks = [
    ["Application interface","Available"],
    ["Local storage",storageWorks ? "Available" : "Unavailable"],
    ["AI backend","Not connected"],
    ["Owner authentication","Not configured"],
    ["Cloud backup","Not configured"]
  ];

  list.innerHTML = "";

  checks.forEach(([name,status]) => {
    const row = document.createElement("div");
    row.className = "module";

    const label = document.createElement("span");
    label.textContent = name;

    const tag = document.createElement("span");
    tag.className = "tag";
    tag.textContent = status;

    row.append(label,tag);
    list.appendChild(row);
  });

  result.textContent =
    "Diagnostic completed. This checks the local interface only; it is not a security audit or backend health check.";
}

// LOCAL DATA RESET
function clearLocalData() {
  const confirmed = confirm(
    "Delete all NEXUS V7 local tasks, memories and saved chat history from this browser?"
  );
  if (!confirmed) return;

  Object.values(STORAGE).forEach(key => localStorage.removeItem(key));
  renderTasks();
  renderMemories();
  document.getElementById("chatLog").innerHTML = "";
  addMessage("Local prototype data has been cleared.","system");
  alert("Local prototype data cleared.");
}

// INITIALISE
renderTasks();
renderMemories();
runDiagnostics();
</script>
</body>
</html>
