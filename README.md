<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Exorma — 1 PB Free Cloud</title>
  <meta name="theme-color" content="#0b5fff" />
  <link rel="preconnect" href="https://www.gstatic.com" crossorigin>
  <link rel="preconnect" href="https://www.googleapis.com" crossorigin>
  <style>
    :root{
      --bg:#0b1020;
      --card:#121831;
      --ink:#e8ecf8;
      --ink-dim:#b9c2df;
      --accent:#0b5fff;
      --accent-2:#6aa3ff;
      --ok:#14b87a;
      --warn:#f7b731;
      --err:#ff4d4d;
      --border:#243055;
      --muted:#0a0f22;
      --code:#0a0e1c;
      --shadow:0 10px 30px rgba(0,0,0,.35);
      --radius:14px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;font:14px/1.45 system-ui,-apple-system,Segoe UI,Roboto,Inter,Arial;
      color:var(--ink);background:linear-gradient(180deg,#060915 0%,#0b1020 100%) fixed;
    }
    a{color:var(--accent)}
    header{
      position:sticky;top:0;z-index:50;
      backdrop-filter:saturate(1.2) blur(10px);
      background:rgba(6,10,21,.6);border-bottom:1px solid var(--border);
    }
    .bar{
      display:flex;align-items:center;gap:16px;max-width:1200px;margin:0 auto;padding:12px 16px;
    }
    .brand{
      display:flex;align-items:center;gap:10px;font-weight:700;letter-spacing:.3px;
    }
    .logo{
      width:28px;height:28px;border-radius:6px;background:
        conic-gradient(from 220deg at 50% 50%, #3f8cff, #7a5cff, #00c2ff);
      box-shadow:0 0 24px rgba(58,116,255,.5) inset;
    }
    .pill{
      padding:4px 10px;border:1px solid var(--border);border-radius:999px;color:var(--ink-dim)
    }
    .spacer{flex:1}
    .btn{
      appearance:none;border:1px solid var(--border);background:linear-gradient(180deg,#162044,#0f1733);
      color:var(--ink);padding:10px 14px;border-radius:10px;cursor:pointer;
      transition:.15s;box-shadow:var(--shadow)
    }
    .btn:hover{transform:translateY(-1px);border-color:#314070}
    .btn.primary{background:linear-gradient(180deg,#1560ff,#0b46c7);border-color:#1e57ff}
    .btn.ghost{background:transparent;box-shadow:none}
    .btn.warn{background:linear-gradient(180deg,#f7b731,#eaa116);border-color:#f7b731;color:#1a1300}
    .btn.danger{background:linear-gradient(180deg,#ff5b5b,#ea3f3f);border-color:#ff5b5b}
    .layout{
      max-width:1200px;margin:18px auto;padding:0 16px;display:grid;grid-template-columns:280px 1fr;gap:16px;
    }
    .card{background:linear-gradient(180deg,#121832,#0e1530);border:1px solid var(--border);border-radius:var(--radius);box-shadow:var(--shadow)}
    .hero{
      margin:16px auto 8px;max-width:1200px;padding:0 16px;
    }
    .hero .card{padding:18px;display:flex;align-items:center;gap:16px;flex-wrap:wrap}
    .badge{font-size:12px;color:#0b1738;background:#d9e6ff;border-radius:999px;padding:4px 10px;font-weight:600}
    .title{font-size:22px;font-weight:800;margin:2px 0 6px}
    .dim{color:var(--ink-dim)}
    .sidebar{padding:12px;display:flex;flex-direction:column;gap:10px}
    .stat{
      padding:12px;border:1px dashed var(--border);border-radius:12px;background:linear-gradient(180deg,#0f1530,#0c132b);
    }
    .row{display:flex;align-items:center;justify-content:space-between;gap:10px;margin:6px 0}
    .progress{
      width:100%;height:10px;background:var(--muted);border-radius:999px;overflow:hidden;border:1px solid var(--border)
    }
    .progress > i{display:block;height:100%;background:linear-gradient(90deg,#0b5fff,#6aa3ff)}
    .nav{display:flex;flex-direction:column;gap:6px;margin-top:8px}
    .nav .btn{width:100%;justify-content:flex-start}
    .main{padding:12px}
    .tabs{display:flex;gap:8px;border-bottom:1px solid var(--border);padding:6px}
    .tab{padding:8px 12px;border-radius:10px;cursor:pointer;color:var(--ink-dim)}
    .tab.active{background:#0f1733;color:var(--ink);border:1px solid var(--border)}
    .toolbar{display:flex;gap:8px;flex-wrap:wrap;margin:12px 6px}
    .grid{border:1px solid var(--border);border-radius:12px;overflow:hidden}
    table{width:100%;border-collapse:collapse;background:linear-gradient(180deg,#0f1530,#0b122a)}
    th,td{padding:12px;border-bottom:1px solid var(--border);text-align:left}
    tr:hover{background:#0d142d}
    .right{text-align:right}
    .mono{font-family:ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace}
    .muted{color:var(--ink-dim)}
    .hidden{display:none !important}
    .footer{max-width:1200px;margin:12px auto 40px;padding:0 16px}
    .notice{padding:10px;border:1px solid var(--border);border-radius:10px;background:linear-gradient(180deg,#0b1128,#0a0f22)}
    .chip{display:inline-block;padding:2px 8px;border:1px solid var(--border);border-radius:999px;margin-right:6px;color:var(--ink-dim)}
    .inline-input{
      display:flex;align-items:center;gap:8px;background:#0b1128;border:1px solid var(--border);border-radius:10px;padding:6px 8px
    }
    input,select{
      background:transparent;border:none;color:var(--ink);flex:1;outline:none
    }
    .codebox{
      background:var(--code);border:1px solid var(--border);border-radius:14px;padding:10px
    }
    textarea{width:100%;min-height:180px;background:transparent;color:var(--ink);border:none;outline:none;resize:vertical}
    .console{
      background:#03060f;border:1px solid var(--border);border-radius:10px;padding:8px;min-height:120px;max-height:240px;overflow:auto
    }
    @media (max-width:980px){.layout{grid-template-columns:1fr}}
  </style>
</head>
<body>
  <header>
    <div class="bar">
      <div class="brand"><div class="logo"></div> Exorma</div>
      <span class="pill">1 PB free</span>
      <span class="pill">Secure • Fast • Simple</span>
      <div class="spacer"></div>
      <div id="authArea" class="row">
        <span id="userEmail" class="muted"></span>
        <button id="btnGoogle" class="btn primary">Continue with Google</button>
        <button id="btnLogout" class="btn ghost hidden">Sign out</button>
      </div>
    </div>
  </header>

  <section class="hero">
    <div class="card">
      <div>
        <div class="badge">New</div>
        <div class="title">Your limitless cloud, connected to your files.</div>
        <div class="dim">Store, fetch, and run — Exorma ties your browser, local folders, and the internet together.</div>
      </div>
      <div class="spacer"></div>
      <div class="row" style="gap:8px">
        <button id="quickConnect" class="btn">Connect file system</button>
        <button id="quickUpload" class="btn">Upload</button>
        <input id="hiddenUpload" type="file" multiple class="hidden" />
      </div>
    </div>
  </section>

  <section class="layout">
    <aside class="sidebar card">
      <div class="stat">
        <div class="row">
          <div>
            <div class="muted">Plan</div>
            <div class="mono">Exorma Free</div>
          </div>
          <div class="badge">1 PB</div>
        </div>
        <div class="row">
          <div class="muted">Usage</div>
          <div><span id="usageText" class="mono">0 B</span></div>
        </div>
        <div class="progress"><i id="usageBar" style="width:0%"></i></div>
      </div>

      <div class="nav">
        <button data-tab="files" class="btn">Files</button>
        <button data-tab="download" class="btn">Internet downloads</button>
        <button data-tab="runner" class="btn">Run programs</button>
        <button data-tab="settings" class="btn">Settings</button>
      </div>
    </aside>

    <main class="main card">
      <div class="tabs">
        <div class="tab active" data-tab="files">Files</div>
        <div class="tab" data-tab="download">Internet downloads</div>
        <div class="tab" data-tab="runner">Run programs</div>
        <div class="tab" data-tab="settings">Settings</div>
      </div>

      <!-- Files -->
      <section id="tab-files">
        <div class="toolbar">
          <button id="btnConnect" class="btn">Connect file explorer</button>
          <button id="btnNewFolder" class="btn">New folder</button>
          <button id="btnUpload" class="btn">Upload</button>
          <div class="inline-input" style="min-width:260px">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="#7f8bb0"><path d="M15.5 14h-.79l-.28-.27A6.471 6.471 0 0 0 16 9.5 6.5 6.5 0 1 0 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79L20 21.5 21.5 20l-6-6zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z"></path></svg>
            <input id="search" placeholder="Search files" />
          </div>
          <div class="spacer"></div>
          <span class="chip mono" id="storageMode">Storage: Demo</span>
        </div>

        <div class="grid">
          <table>
            <thead>
              <tr>
                <th style="width:36px"></th>
                <th>Name</th>
                <th>Type</th>
                <th>Size</th>
                <th class="right">Actions</th>
              </tr>
            </thead>
            <tbody id="fileRows"></tbody>
          </table>
        </div>
      </section>

      <!-- Internet downloads -->
      <section id="tab-download" class="hidden">
        <div class="toolbar">
          <div class="inline-input" style="flex:1;min-width:300px">
            <span class="muted">URL</span>
            <input id="downloadUrl" placeholder="https://example.com/file.iso" />
          </div>
          <button id="btnFetch" class="btn primary">Fetch & save</button>
        </div>
        <div class="notice">
          Tip: For large files, prefer a connected folder (File System Access) to save directly to your drive.
        </div>
        <div style="margin-top:12px">
          <div class="progress"><i id="dlBar" style="width:0%"></i></div>
          <div class="row"><span class="muted">Progress</span><span class="mono" id="dlText">0%</span></div>
        </div>
      </section>

      <!-- Run programs -->
      <section id="tab-runner" class="hidden">
        <div class="toolbar">
          <select id="runtime">
            <option value="js" selected>JavaScript (sandboxed)</option>
          </select>
          <button id="btnRun" class="btn primary">Run</button>
          <button id="btnClear" class="btn ghost">Clear</button>
        </div>
        <div class="codebox">
          <div class="muted" style="margin-bottom:6px">Program</div>
          <textarea id="code" spellcheck="false" class="mono">// Example: compute primes
function primes(n){
  const out=[]; outer: for(let x=2;x<=n;x++){
    for(let y=2;y*y<=x;y++){ if(x%y===0) continue outer; }
    out.push(x);
  } return out;
}
console.log('Primes up to 100:', primes(100));</textarea>
        </div>
        <div style="margin-top:12px">
          <div class="muted">Console</div>
          <div id="console" class="console mono"></div>
        </div>
      </section>

      <!-- Settings -->
      <section id="tab-settings" class="hidden">
        <div class="row">
          <div>
            <div class="title" style="font-size:18px;margin:0">Storage adapters</div>
            <div class="dim">Choose where Exorma saves files.</div>
          </div>
        </div>
        <div class="row" style="gap:8px;margin-top:12px">
          <button id="useDemo" class="btn">Use Demo (in-browser)</button>
          <button id="useOPFS" class="btn">Use Browser storage (OPFS)</button>
          <button id="usePicker" class="btn">Use Connected folder</button>
        </div>
        <div style="margin-top:16px" class="notice">
          • Demo stores files in memory (resets on refresh). • OPFS persists in this browser profile. • Connected folder writes to a folder you choose (Chromium-based browsers over HTTPS).
        </div>

        <div style="margin-top:20px">
          <div class="title" style="font-size:18px;margin:0">Google sign‑in</div>
          <div class="dim">Enable login/signup with your Google account.</div>
          <div class="codebox" style="margin-top:8px">
<pre class="mono" style="white-space:pre-wrap">1) Create a Firebase project
2) Enable Google as a provider (Authentication)
3) Paste your config into the script block at the end of this file (FIREBASE_CONFIG)
4) Host over HTTPS</pre>
          </div>
        </div>
      </section>
    </main>
  </section>

  <section class="footer">
    <div class="notice">
      Exorma is a front‑end template. To truly deliver “1 PB free,” add a backend for storage, bandwidth, auth rules, and quota enforcement. Browser features like File System Access and OPFS vary by browser and require HTTPS.
    </div>
  </section>

  <!-- Firebase SDKs (auth only). Replace with your versions if needed. -->
  <script src="https://www.gstatic.com/firebasejs/10.12.4/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.4/firebase-auth-compat.js"></script>

  <script>
  // ==========================
  // Minimal state and helpers
  // ==========================
  const $ = (s, p=document) => p.querySelector(s);
  const $$ = (s, p=document) => [...p.querySelectorAll(s)];
  const fmtBytes = (n=0) => {
    const k = 1024, units = ['B','KB','MB','GB','TB','PB'];
    let i=0; while(n >= k && i < units.length-1){ n/=k; i++; }
    return `${n.toFixed(n<10 && i>0?2:0)} ${units[i]}`;
  };
  const toast = (msg, type='info') => {
    console.log(`[${type}]`, msg);
  };

  // ==========================
  // Storage adapters
  // ==========================
  // Unified API expected by UI:
  // - list(path) -> [{name,isDir,size}]
  // - mkdir(path,name)
  // - writeFile(path,fileName,blob/stream)
  // - readFile(path,fileName) -> Blob
  // - remove(path, name)
  // - connect() optional
  const Adapters = {};

  // Demo (in-memory)
  Adapters.demo = (() => {
    const fs = { "/": { type: "dir", children: {} } };
    const getNode = (path) => {
      const parts = path.split('/').filter(Boolean);
      let cur = fs["/"];
      for(const p of parts){ cur = cur.children[p]; if(!cur) return null; }
      return cur;
    };
    const list = async (path="/") => {
      const dir = getNode(path) || fs["/"];
      return Object.entries(dir.children).map(([name,node]) => ({
        name, isDir: node.type==='dir', size: node.size||0
      }));
    };
    const mkdir = async (path="/", name) => {
      const dir = getNode(path) || fs["/"];
      if(!dir.children[name]) dir.children[name] = { type:"dir", children:{} };
    };
    const writeFile = async (path="/", name, data) => {
      const dir = getNode(path) || fs["/"];
      const blob = data instanceof Blob ? data : new Blob([data]);
      dir.children[name] = { type:"file", blob, size: blob.size };
    };
    const readFile = async (path="/", name) => {
      const dir = getNode(path) || fs["/"];
      const node = dir.children[name];
      if(!node || node.type!=='file') throw new Error('Not found');
      return node.blob;
    };
    const remove = async (path="/", name) => {
      const dir = getNode(path) || fs["/"];
      delete dir.children[name];
    };
    const usage = async () => {
      let total = 0;
      const walk = (node) => {
        if(node.type==='file') total += node.size || 0;
        if(node.type==='dir') Object.values(node.children).forEach(walk);
      };
      walk(fs["/"]);
      return total;
    };
    return { name:'Demo', list, mkdir, writeFile, readFile, remove, usage };
  })();

  // OPFS (Origin Private File System)
  Adapters.opfs = (() => {
    const root = () => navigator.storage.getDirectory();
    const resolve = async (path="/") => {
      const parts = path.split('/').filter(Boolean);
      let dir = await root();
      for(const p of parts){ dir = await dir.getDirectoryHandle(p, { create:false }); }
      return dir;
    };
    const list = async (path="/") => {
      const dir = await resolve(path).catch(()=>root());
      const out = [];
      for await (const [name, handle] of (await dir).entries()) {
        if(handle.kind === 'file'){
          const file = await handle.getFile();
          out.push({ name, isDir:false, size:file.size });
        } else {
          out.push({ name, isDir:true, size:0 });
        }
      }
      return out.sort((a,b)=> (b.isDir - a.isDir) || a.name.localeCompare(b.name));
    };
    const mkdir = async (path="/", name) => {
      const dir = await resolve(path).catch(()=>root());
      await dir.getDirectoryHandle(name, { create:true });
    };
    const writeFile = async (path="/", name, data) => {
      const dir = await resolve(path).catch(()=>root());
      const fh = await dir.getFileHandle(name, { create:true });
      const ws = await fh.createWritable();
      if (data?.getReader) {
        // stream
        const reader = data.getReader();
        while(true){
          const {value, done} = await reader.read();
          if(done) break;
          if(value) await ws.write(value);
        }
      } else if (data instanceof Blob) {
        await ws.write(data);
      } else {
        await ws.write(new Blob([data]));
      }
      await ws.close();
    };
    const readFile = async (path="/", name) => {
      const dir = await resolve(path).catch(()=>root());
      const fh = await dir.getFileHandle(name);
      return (await fh.getFile());
    };
    const remove = async (path="/", name) => {
      const dir = await resolve(path).catch(()=>root());
      try { await dir.removeEntry(name, { recursive:true }); } catch(e){}
    };
    const usage = async () => {
      let used = 0;
      const walk = async (dirHandle) => {
        for await (const [name, handle] of dirHandle.entries()){
          if(handle.kind === 'file'){
            const f = await handle.getFile(); used += f.size;
          } else await walk(handle);
        }
      };
      await walk(await root());
      return used;
    };
    return { name:'OPFS', list, mkdir, writeFile, readFile, remove, usage };
  })();

  // Connected folder via showDirectoryPicker
  Adapters.picker = (() => {
    let dirHandle = null, currentPath = '/';
    const connect = async () => {
      dirHandle = await window.showDirectoryPicker({ mode:'readwrite' });
      return true;
    };
    const getDir = async (path="/") => {
      const parts = path.split('/').filter(Boolean);
      let d = dirHandle;
      for(const p of parts){ d = await d.getDirectoryHandle(p, { create:false }); }
      return d;
    };
    const list = async (path="/") => {
      if(!dirHandle) throw new Error('Not connected');
      const dir = await getDir(path).catch(()=>dirHandle);
      const out=[];
      for await (const [name, handle] of dir.entries()){
        if(handle.kind==='file'){
          const f = await handle.getFile();
          out.push({ name, isDir:false, size:f.size });
        } else out.push({ name, isDir:true, size:0 });
      }
      return out.sort((a,b)=> (b.isDir - a.isDir) || a.name.localeCompare(b.name));
    };
    const mkdir = async (path="/", name) => {
      const dir = await getDir(path).catch(()=>dirHandle);
      await dir.getDirectoryHandle(name, { create:true });
    };
    const writeFile = async (path="/", name, data) => {
      const dir = await getDir(path).catch(()=>dirHandle);
      const fh = await dir.getFileHandle(name, { create:true });
      const ws = await fh.createWritable();
      if (data?.getReader) {
        const reader = data.getReader();
        while(true){
          const {value, done} = await reader.read();
          if(done) break;
          if(value) await ws.write(value);
        }
      } else if (data instanceof Blob) {
        await ws.write(data);
      } else {
        await ws.write(new Blob([data]));
      }
      await ws.close();
    };
    const readFile = async (path="/", name) => {
      const dir = await getDir(path).catch(()=>dirHandle);
      const fh = await dir.getFileHandle(name);
      return (await fh.getFile());
    };
    const remove = async (path="/", name) => {
      const dir = await getDir(path).catch(()=>dirHandle);
      await dir.removeEntry(name, { recursive:true });
    };
    const usage = async () => 0; // unknown quickly; left as 0 for simplicity
    return { name:'Connected', list, mkdir, writeFile, readFile, remove, usage, connect };
  })();

  // ==========================
  // App state
  // ==========================
  const state = {
    currentTab: 'files',
    currentPath: '/',
    adapter: Adapters.demo,
    user: null
  };

  // ==========================
  // UI wiring
  // ==========================
  const rows = $('#fileRows');
  const usageText = $('#usageText');
  const usageBar = $('#usageBar');
  const storageMode = $('#storageMode');
  const hiddenUpload = $('#hiddenUpload');

  const refreshUsage = async () => {
    try{
      const used = await state.adapter.usage?.() ?? 0;
      usageText.textContent = fmtBytes(used);
      const pct = Math.min(used / (1024**5) * 100, 100); // vs 1 PB
      usageBar.style.width = `${pct}%`;
    }catch(e){ /* ignore */ }
  };

  const listFiles = async () => {
    rows.innerHTML = '';
    try {
      const term = ($('#search').value || '').toLowerCase();
      const items = await state.adapter.list(state.currentPath);
      const filtered = items.filter(it => it.name.toLowerCase().includes(term));
      if(filtered.length === 0){
        rows.innerHTML = `<tr><td></td><td class="muted" colspan="4">Empty</td></tr>`;
      } else {
        for(const it of filtered){
          const tr = document.createElement('tr');
          tr.innerHTML = `
            <td>${it.isDir ? '📁' : '📄'}</td>
            <td class="mono">${it.name}</td>
            <td>${it.isDir ? 'Folder' : 'File'}</td>
            <td>${it.isDir ? '-' : fmtBytes(it.size)}</td>
            <td class="right">
              ${it.isDir ? `<button class="btn ghost" data-open="${it.name}">Open</button>`:
                `<button class="btn ghost" data-dl="${it.name}">Download</button>`}
              <button class="btn ghost danger" data-del="${it.name}">Delete</button>
            </td>
          `;
          rows.appendChild(tr);
        }
      }
    } catch (e) {
      rows.innerHTML = `<tr><td></td><td colspan="4" class="muted">Error: ${e.message}</td></tr>`;
    }
    await refreshUsage();
  };

  const switchTab = (tab) => {
    state.currentTab = tab;
    $$('.tab').forEach(t => t.classList.toggle('active', t.dataset.tab===tab));
    ['files','download','runner','settings'].forEach(id=>{
      $('#tab-'+id).classList.toggle('hidden', id!==tab);
    });
  };

  // Tab clicks
  $$('.tab').forEach(t => t.addEventListener('click', () => switchTab(t.dataset.tab)));
  $$('.nav .btn').forEach(b => b.addEventListener('click', () => switchTab(b.dataset.tab)));

  // Search
  $('#search').addEventListener('input', listFiles);

  // File actions
  rows.addEventListener('click', async (e) => {
    const btn = e.target.closest('button'); if(!btn) return;
    const name = btn.dataset.open || btn.dataset.dl || btn.dataset.del;
    if(btn.dataset.open){
      state.currentPath = (state.currentPath.endsWith('/')? state.currentPath : state.currentPath + '/') + name;
      await listFiles();
    } else if(btn.dataset.dl){
      try{
        const blob = await state.adapter.readFile(state.currentPath, name);
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url; a.download = name; a.click();
        URL.revokeObjectURL(url);
      }catch(err){ toast(err.message,'error'); }
    } else if(btn.dataset.del){
      if(confirm(`Delete "${name}"?`)){
        await state.adapter.remove(state.currentPath, name);
        await listFiles();
      }
    }
  });

  // New folder
  $('#btnNewFolder').addEventListener('click', async () => {
    const name = prompt('Folder name'); if(!name) return;
    await state.adapter.mkdir(state.currentPath, name);
    await listFiles();
  });

  // Upload
  const handleFilesUpload = async (files) => {
    for(const f of files){
      await state.adapter.writeFile(state.currentPath, f.name, f);
    }
    await listFiles();
  };
  $('#btnUpload').addEventListener('click', () => hiddenUpload.click());
  $('#quickUpload').addEventListener('click', () => hiddenUpload.click());
  hiddenUpload.addEventListener('change', (e) => handleFilesUpload(e.target.files));

  // Connect picker
  const ensurePicker = async () => {
    if(!window.showDirectoryPicker){ alert('Your browser does not support the File System Access API. Use Chromium-based browsers over HTTPS.'); return false; }
    try { await Adapters.picker.connect(); state.adapter = Adapters.picker; storageMode.textContent = 'Storage: Connected'; await listFiles(); return true; }
    catch(e){ toast(e.message,'error'); return false; }
  };
  $('#btnConnect').addEventListener('click', ensurePicker);
  $('#quickConnect').addEventListener('click', ensurePicker);

  // Settings: switch adapters
  $('#useDemo').addEventListener('click', async () => { state.adapter = Adapters.demo; storageMode.textContent = 'Storage: Demo'; await listFiles(); });
  $('#useOPFS').addEventListener('click', async () => {
    if(!navigator.storage?.getDirectory){ alert('OPFS not supported in this browser.'); return; }
    state.adapter = Adapters.opfs; storageMode.textContent = 'Storage: OPFS'; await listFiles();
  });
  $('#usePicker').addEventListener('click', ensurePicker);

  // Breadcrumb (optional simple back behavior)
  document.addEventListener('keydown', async (e) => {
    if(e.key==='Backspace' && (e.ctrlKey || e.metaKey)) {
      if(state.currentPath !== '/'){
        const parts = state.currentPath.split('/').filter(Boolean);
        parts.pop();
        state.currentPath = '/' + parts.join('/');
        await listFiles();
      }
    }
  });

  // ==========================
  // Internet downloads
  // ==========================
  const dlBar = $('#dlBar'); const dlText = $('#dlText');
  const setDl = (p) => { dlBar.style.width = `${p}%`; dlText.textContent = `${p.toFixed(1)}%`; };
  setDl(0);

  async function fetchToStorage(url) {
    const res = await fetch(url);
    if(!res.ok) throw new Error(`HTTP ${res.status}`);
    const name = (new URL(url)).pathname.split('/').filter(Boolean).pop() || 'download.bin';
    const length = +(res.headers.get('content-length') || 0);
    let loaded = 0;

    // Stream tee so we can track progress
    const reader = res.body?.getReader?.();
    if(reader && state.adapter.writeFile){
      const stream = new ReadableStream({
        async pull(controller){
          const { done, value } = await reader.read();
          if (done) { controller.close(); return; }
          controller.enqueue(value);
          loaded += value.byteLength;
          if(length) setDl(Math.min(100, loaded/length*100));
          else setDl(Math.min(99, setDl+1));
        }
      });
      await state.adapter.writeFile(state.currentPath, name, stream);
    } else {
      const blob = await res.blob();
      await state.adapter.writeFile(state.currentPath, name, blob);
      setDl(100);
    }
    toast('Saved: '+name, 'ok');
    await listFiles();
  }

  $('#btnFetch').addEventListener('click', async () => {
    const url = $('#downloadUrl').value.trim();
    if(!url){ alert('Enter a URL'); return; }
    setDl(0);
    try { await fetchToStorage(url); }
    catch(e){ alert('Download failed: ' + e.message); setDl(0); }
  });

  // ==========================
  // Runner (JavaScript sandbox)
  // ==========================
  const writeConsole = (msg, cls='') => {
    const line = document.createElement('div');
    line.textContent = msg;
    if(cls) line.style.color = cls;
    $('#console').appendChild(line);
    $('#console').scrollTop = $('#console').scrollHeight;
  };

  let runnerFrame = null;
  const ensureFrame = () => {
    if(runnerFrame) return runnerFrame;
    const iframe = document.createElement('iframe');
    iframe.setAttribute('sandbox','allow-scripts');
    iframe.style.display = 'none';
    document.body.appendChild(iframe);
    runnerFrame = iframe.contentWindow;
    runnerFrame.document.open();
    runnerFrame.document.write(`
      <!doctype html><meta charset="utf-8"><script>
        (function(){
          const send = (type, ...args) => parent.postMessage({ type, args: args.map(a=> String(a)) }, '*');
          console.log = (...a)=>send('log', ...a);
          console.error = (...a)=>send('err', ...a);
          console.warn = (...a)=>send('warn', ...a);
          onmessage = (e) => {
            const code = e.data?.code || '';
            try { const ret = (0, eval)(code); if(ret !== undefined) console.log(ret); }
            catch(err){ console.error(err && err.stack || String(err)); }
          };
        })();
      <\/script>`);
    runnerFrame.document.close();
    window.addEventListener('message', ev => {
      if(!ev.data || !ev.data.type) return;
      if(ev.data.type==='log') ev.data.args.forEach(a => writeConsole(a));
      if(ev.data.type==='warn') ev.data.args.forEach(a => writeConsole(a, '#f7b731'));
      if(ev.data.type==='err') ev.data.args.forEach(a => writeConsole(a, '#ff4d4d'));
    });
    return runnerFrame;
  };

  $('#btnRun').addEventListener('click', () => {
    $('#console').innerHTML = '';
    ensureFrame().postMessage({ code: $('#code').value }, '*');
  });
  $('#btnClear').addEventListener('click', () => $('#console').innerHTML = '');

  // ==========================
  // Google auth (Firebase)
  // ==========================
  // 1) Replace FIREBASE_CONFIG with your project config
  const FIREBASE_CONFIG = {
    // apiKey: "YOUR_API_KEY",
    // authDomain: "YOUR_AUTH_DOMAIN",
    // projectId: "YOUR_PROJECT_ID",
    // appId: "YOUR_APP_ID",
  };

  let fbApp = null, fbAuth = null;
  try {
    if(Object.keys(FIREBASE_CONFIG).length){
      fbApp = firebase.initializeApp(FIREBASE_CONFIG);
      fbAuth = firebase.auth();
    }
  } catch(e) {
    console.warn('Firebase init skipped:', e.message);
  }

  const btnGoogle = $('#btnGoogle');
  const btnLogout = $('#btnLogout');
  const userEmail = $('#userEmail');

  const updateAuthUI = (user) => {
    state.user = user || null;
    userEmail.textContent = user ? user.email : '';
    btnGoogle.classList.toggle('hidden', !!user);
    btnLogout.classList.toggle('hidden', !user);
  };

  if(fbAuth){
    fbAuth.onAuthStateChanged(user => updateAuthUI(user));
    btnGoogle.addEventListener('click', async () => {
      try {
        const provider = new firebase.auth.GoogleAuthProvider();
        await fbAuth.signInWithPopup(provider);
      } catch(e) { alert('Sign-in failed: ' + e.message); }
    });
    btnLogout.addEventListener('click', async () => { await fbAuth.signOut(); });
  } else {
    // Fallback: fake session just for demo
    btnGoogle.addEventListener('click', () => {
      updateAuthUI({ email: 'demo@exorma.cloud' });
      toast('Demo login');
    });
    btnLogout.addEventListener('click', () => updateAuthUI(null));
  }

  // ==========================
  // Boot
  // ==========================
  (async function boot(){
    storageMode.textContent = `Storage: ${state.adapter.name}`;
    await listFiles();
  })();
  </script>
</body>
</html>
