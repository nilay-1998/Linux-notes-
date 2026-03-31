# Linux-notes
- { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
background: var(–bg);
color: var(–text);
font-family: ‘Syne’, sans-serif;
line-height: 1.6;
overflow-x: hidden;
}

/* === HEADER === */
header {
position: sticky; top: 0; z-index: 100;
background: rgba(13,17,23,0.92);
backdrop-filter: blur(12px);
border-bottom: 1px solid var(–border);
padding: 0 2rem;
display: flex; align-items: center; justify-content: space-between;
height: 56px;
}

.logo {
font-family: ‘JetBrains Mono’, monospace;
font-weight: 700; font-size: 1rem;
color: var(–green);
display: flex; align-items: center; gap: 8px;
}

.logo::before {
content: ‘$’;
color: var(–text-muted);
}

nav { display: flex; gap: 4px; overflow-x: auto; }

nav a {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.72rem; font-weight: 600;
color: var(–text-dim);
text-decoration: none;
padding: 6px 12px;
border-radius: 6px;
transition: all 0.2s;
white-space: nowrap;
}

nav a:hover { background: var(–surface); color: var(–green); }

/* === HERO === */
.hero {
padding: 80px 2rem 60px;
text-align: center;
position: relative;
overflow: hidden;
}

.hero::before {
content: ‘’;
position: absolute; inset: 0;
background: radial-gradient(ellipse 60% 50% at 50% 0%, rgba(57,211,83,0.08) 0%, transparent 70%);
pointer-events: none;
}

.hero-badge {
display: inline-flex; align-items: center; gap: 8px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.75rem;
color: var(–green);
background: rgba(57,211,83,0.1);
border: 1px solid rgba(57,211,83,0.3);
padding: 6px 14px; border-radius: 100px;
margin-bottom: 24px;
}

.hero-badge::before { content: ‘●’; animation: pulse 2s infinite; }

@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }

.hero h1 {
font-size: clamp(2.5rem, 6vw, 4.5rem);
font-weight: 800;
line-height: 1.1;
letter-spacing: -0.03em;
margin-bottom: 16px;
}

.hero h1 span { color: var(–green); }

.hero p {
font-size: 1.1rem; color: var(–text-dim);
max-width: 560px; margin: 0 auto 40px;
}

/* Terminal window in hero */
.hero-terminal {
max-width: 680px; margin: 0 auto;
background: var(–surface);
border: 1px solid var(–border);
border-radius: 12px;
overflow: hidden;
text-align: left;
box-shadow: 0 32px 64px rgba(0,0,0,0.5), 0 0 0 1px rgba(255,255,255,0.04);
}

.term-bar {
background: var(–surface2);
border-bottom: 1px solid var(–border);
padding: 10px 16px;
display: flex; align-items: center; gap: 8px;
}

.dot { width: 12px; height: 12px; border-radius: 50%; }
.dot.r { background: #f85149; }
.dot.y { background: #e6c84a; }
.dot.g { background: #39d353; }

.term-title {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.72rem; color: var(–text-muted);
margin-left: 8px; flex: 1; text-align: center;
}

.term-body {
padding: 20px 24px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.82rem;
line-height: 2;
}

.term-body .prompt { color: var(–green); }
.term-body .cmd { color: var(–text); }
.term-body .out { color: var(–text-dim); }
.term-body .out.hi { color: var(–cyan); }
.term-body .comment { color: var(–text-muted); }

/* === MAIN LAYOUT === */
main {
max-width: 1100px;
margin: 0 auto;
padding: 0 2rem 80px;
}

/* === SECTION === */
.section {
margin-bottom: 72px;
scroll-margin-top: 70px;
}

.section-header {
display: flex; align-items: center; gap: 16px;
margin-bottom: 32px;
padding-bottom: 16px;
border-bottom: 1px solid var(–border);
}

.section-num {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.72rem; font-weight: 700;
color: var(–green);
background: rgba(57,211,83,0.1);
border: 1px solid rgba(57,211,83,0.25);
padding: 4px 10px; border-radius: 6px;
}

.section-title {
font-size: 1.6rem; font-weight: 800;
letter-spacing: -0.02em;
}

.section-icon {
font-size: 1.4rem;
margin-left: auto;
}

/* === CARDS GRID === */
.cards { display: grid; gap: 16px; }
.cards.cols2 { grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); }
.cards.cols3 { grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); }

.card {
background: var(–surface);
border: 1px solid var(–border);
border-radius: 10px;
padding: 20px 22px;
transition: border-color 0.2s, transform 0.2s;
}

.card:hover {
border-color: var(–green-dim);
transform: translateY(-2px);
}

.card-label {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.68rem; font-weight: 700;
color: var(–orange);
text-transform: uppercase; letter-spacing: 0.08em;
margin-bottom: 8px;
}

.card h3 {
font-size: 1rem; font-weight: 700;
margin-bottom: 8px;
}

.card p { font-size: 0.9rem; color: var(–text-dim); line-height: 1.6; }

/* === CODE BLOCK === */
.code-block {
background: var(–surface);
border: 1px solid var(–border);
border-radius: 10px;
overflow: hidden;
margin: 16px 0;
}

.code-header {
background: var(–surface2);
border-bottom: 1px solid var(–border);
padding: 8px 16px;
display: flex; align-items: center; justify-content: space-between;
}

.code-label {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.7rem; color: var(–text-muted);
}

.code-lang {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.68rem; color: var(–cyan);
background: rgba(88,196,221,0.1);
padding: 2px 8px; border-radius: 4px;
}

pre {
padding: 18px 20px;
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.82rem;
line-height: 1.85;
overflow-x: auto;
color: var(–text);
}

.c-cmd { color: var(–green); }
.c-flag { color: var(–cyan); }
.c-path { color: var(–yellow); }
.c-comment { color: var(–text-muted); font-style: italic; }
.c-out { color: var(–text-dim); }
.c-err { color: var(–red); }
.c-hi { color: var(–orange); }
.c-var { color: var(–purple); }
.c-str { color: #a5d6ff; }

/* === DIAGRAM === */
.diagram {
background: var(–surface);
border: 1px solid var(–border);
border-radius: 10px;
padding: 28px;
margin: 16px 0;
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.8rem;
line-height: 1.9;
overflow-x: auto;
}

.diagram .box { color: var(–cyan); }
.diagram .arrow { color: var(–text-muted); }
.diagram .label { color: var(–yellow); }
.diagram .dim { color: var(–text-muted); }
.diagram .hi { color: var(–green); font-weight: 700; }
.diagram .warn { color: var(–orange); }

/* === TABLE === */
.tbl-wrap { overflow-x: auto; border-radius: 10px; border: 1px solid var(–border); margin: 16px 0; }

table { width: 100%; border-collapse: collapse; }

thead tr { background: var(–surface2); }

th {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.72rem; font-weight: 700;
color: var(–green);
text-transform: uppercase; letter-spacing: 0.06em;
padding: 12px 16px; text-align: left;
border-bottom: 1px solid var(–border);
}

td {
padding: 11px 16px;
font-size: 0.88rem;
border-bottom: 1px solid rgba(48,54,61,0.5);
vertical-align: top;
}

tbody tr:last-child td { border-bottom: none; }
tbody tr:hover td { background: rgba(255,255,255,0.02); }

td code, td .mono {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.8rem;
color: var(–cyan);
background: rgba(88,196,221,0.08);
padding: 2px 6px; border-radius: 4px;
}

/* === CALLOUT === */
.callout {
display: flex; gap: 14px;
padding: 14px 18px;
border-radius: 8px;
margin: 12px 0;
font-size: 0.9rem;
line-height: 1.6;
}

.callout.tip { background: rgba(57,211,83,0.07); border-left: 3px solid var(–green); }
.callout.warn { background: rgba(240,136,62,0.07); border-left: 3px solid var(–orange); }
.callout.danger { background: rgba(248,81,73,0.07); border-left: 3px solid var(–red); }
.callout.info { background: rgba(88,196,221,0.07); border-left: 3px solid var(–cyan); }

.callout-icon { font-size: 1.1rem; flex-shrink: 0; margin-top: 1px; }
.callout p { color: var(–text-dim); }
.callout strong { color: var(–text); }

/* === INLINE CODE === */
code {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.83em;
color: var(–cyan);
background: rgba(88,196,221,0.08);
padding: 2px 6px; border-radius: 4px;
}

/* === PERMISSION VISUAL === */
.perm-visual {
display: flex; gap: 4px; flex-wrap: wrap;
margin: 16px 0; align-items: center;
}

.perm-group {
display: flex; gap: 2px;
}

.perm-bit {
width: 36px; height: 36px;
display: flex; align-items: center; justify-content: center;
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.85rem; font-weight: 700;
border-radius: 6px;
}

.perm-bit.on { background: rgba(57,211,83,0.2); color: var(–green); border: 1px solid rgba(57,211,83,0.4); }
.perm-bit.off { background: rgba(255,255,255,0.03); color: var(–text-muted); border: 1px solid var(–border); }
.perm-bit.type { background: rgba(88,196,221,0.15); color: var(–cyan); border: 1px solid rgba(88,196,221,0.3); }

.perm-sep { color: var(–text-muted); font-family: ‘JetBrains Mono’, monospace; padding: 0 6px; align-self: center; font-size: 1.2rem; }

.perm-label {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.65rem; color: var(–text-muted);
text-align: center; margin-top: 4px;
letter-spacing: 0.04em;
}

.perm-col { display: flex; flex-direction: column; align-items: center; }

/* === PROCESS TREE === */
.process-tree {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.8rem;
line-height: 2;
padding: 20px 24px;
background: var(–surface);
border: 1px solid var(–border);
border-radius: 10px;
margin: 16px 0;
}

/* === FILESYSTEM TREE === */
.fs-tree { font-family: ‘JetBrains Mono’, monospace; font-size: 0.82rem; line-height: 2; }
.fs-tree .dir { color: var(–cyan); font-weight: 600; }
.fs-tree .file { color: var(–text-dim); }
.fs-tree .link { color: var(–yellow); }
.fs-tree .exec { color: var(–green); }

/* === TWO COL === */
.two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
@media (max-width: 700px) { .two-col { grid-template-columns: 1fr; } }

/* === HIGHLIGHT ROW === */
.hi-row { display: flex; flex-wrap: wrap; gap: 12px; margin: 16px 0; }

.hi-chip {
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.78rem;
padding: 6px 14px; border-radius: 6px;
border: 1px solid;
}

.hi-chip.green { color: var(–green); background: rgba(57,211,83,0.08); border-color: rgba(57,211,83,0.25); }
.hi-chip.cyan { color: var(–cyan); background: rgba(88,196,221,0.08); border-color: rgba(88,196,221,0.25); }
.hi-chip.yellow { color: var(–yellow); background: rgba(230,200,74,0.08); border-color: rgba(230,200,74,0.25); }
.hi-chip.orange { color: var(–orange); background: rgba(240,136,62,0.08); border-color: rgba(240,136,62,0.25); }
.hi-chip.purple { color: var(–purple); background: rgba(188,140,255,0.08); border-color: rgba(188,140,255,0.25); }

/* === PIPE DIAGRAM === */
.pipe-flow {
display: flex; align-items: center; flex-wrap: wrap; gap: 8px;
padding: 20px; background: var(–surface);
border: 1px solid var(–border); border-radius: 10px; margin: 16px 0;
font-family: ‘JetBrains Mono’, monospace; font-size: 0.8rem;
}

.pipe-box {
background: var(–surface2);
border: 1px solid var(–border);
border-radius: 6px;
padding: 8px 14px;
color: var(–cyan);
}

.pipe-arrow { color: var(–green); font-size: 1.2rem; }
.pipe-label { color: var(–text-muted); font-size: 0.7rem; text-align: center; margin-top: 2px; }
.pipe-col { display: flex; flex-direction: column; align-items: center; }

/* === DIVIDER === */
hr { border: none; border-top: 1px solid var(–border); margin: 48px 0; }

/* === FOOTER === */
footer {
text-align: center;
padding: 40px 2rem;
border-top: 1px solid var(–border);
font-family: ‘JetBrains Mono’, monospace;
font-size: 0.75rem; color: var(–text-muted);
}

footer span { color: var(–green); }

/* === SCROLLBAR === */
::-webkit-scrollbar { width: 6px; height: 6px; }
::-webkit-scrollbar-track { background: var(–bg); }
::-webkit-scrollbar-thumb { background: var(–border); border-radius: 3px; }
::-webkit-scrollbar-thumb:hover { background: var(–text-muted); }

/* === ANIMATIONS === */
.section { opacity: 0; transform: translateY(16px); transition: opacity 0.5s ease, transform 0.5s ease; }
.section.visible { opacity: 1; transform: none; }

/* === RESPONSIVE === */
@media (max-width: 600px) {
nav a { display: none; }
.hero h1 { font-size: 2rem; }
main { padding: 0 1rem 60px; }
pre { font-size: 0.75rem; }
}
</style>

</head>
<body>

<header>
  <div class="logo"> linux-notes</div>
  <nav>
    <a href="#filesystem">Filesystem</a>
    <a href="#permissions">Permissions</a>
    <a href="#processes">Processes</a>
    <a href="#networking">Networking</a>
    <a href="#users">Users</a>
    <a href="#storage">Storage</a>
    <a href="#shell">Shell</a>
    <a href="#systemd">Systemd</a>
  </nav>
</header>

<!-- HERO -->

<div class="hero">
  <div class="hero-badge">Linux Field Notes — RHCSA Edition</div>
  <h1>Master <span>Linux</span><br>from the Terminal</h1>
  <p>A comprehensive, visual guide covering filesystem, permissions, processes, networking, storage, and more — with real examples.</p>

  <div class="hero-terminal">
    <div class="term-bar">
      <div class="dot r"></div><div class="dot y"></div><div class="dot g"></div>
      <div class="term-title">nilay@rhel9 ~ — bash</div>
    </div>
    <div class="term-body">
      <div><span class="prompt">[nilay@rhel9 ~]$</span> <span class="cmd">uname -r</span></div>
      <div><span class="out hi">5.14.0-284.11.1.el9_2.x86_64</span></div>
      <div><span class="prompt">[nilay@rhel9 ~]$</span> <span class="cmd">cat /etc/redhat-release</span></div>
      <div><span class="out">Red Hat Enterprise Linux release 9.2 (Plow)</span></div>
      <div><span class="prompt">[nilay@rhel9 ~]$</span> <span class="cmd">whoami</span></div>
      <div><span class="out hi">nilay</span></div>
      <div><span class="prompt">[nilay@rhel9 ~]$</span> <span class="cmd">uptime</span></div>
      <div><span class="out"> 10:32:05 up 3 days,  4:17,  2 users,  load average: 0.12, 0.08, 0.05</span></div>
    </div>
  </div>
</div>

<main>

<!-- ===== 1. FILESYSTEM ===== -->

<section class="section" id="filesystem">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2 class="section-title">Linux Filesystem Hierarchy</h2>
    <span class="section-icon">🗂️</span>
  </div>

  <p style="color:var(--text-dim); margin-bottom:20px;">Everything in Linux is a file. The Filesystem Hierarchy Standard (FHS) defines a consistent directory structure across all distributions.</p>

  <div class="diagram">
<pre style="padding:0; background:none; border:none;">
<span class="hi">                         /  (root)</span>
<span class="arrow">          ┌──────────┬────┼────┬──────────┬──────────┐</span>
       <span class="label">/bin</span>     <span class="label">/etc</span>  <span class="label">/home</span>  <span class="label">/var</span>     <span class="label">/usr</span>     <span class="label">/tmp</span>
<span class="dim">    binaries  configs  users   logs   programs  temp</span>
       <span class="arrow">│</span>         <span class="arrow">│</span>       <span class="arrow">│</span>      <span class="arrow">│</span>      <span class="arrow">│</span>
   <span class="dim">ls,cp,mv  hosts  nilay/  log/  bin/lib</span>
</pre>
  </div>

  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Directory</th><th>Purpose</th><th>Key Files</th></tr></thead>
      <tbody>
        <tr><td><code>/</code></td><td>Root of entire filesystem tree</td><td>—</td></tr>
        <tr><td><code>/bin</code></td><td>Essential user binaries (all users)</td><td><code>ls, cp, mv, bash</code></td></tr>
        <tr><td><code>/sbin</code></td><td>System binaries (root use)</td><td><code>fdisk, ifconfig, reboot</code></td></tr>
        <tr><td><code>/etc</code></td><td>System-wide configuration files</td><td><code>fstab, passwd, hosts, ssh/</code></td></tr>
        <tr><td><code>/home</code></td><td>User home directories</td><td><code>/home/nilay</code></td></tr>
        <tr><td><code>/root</code></td><td>Root user's home directory</td><td>—</td></tr>
        <tr><td><code>/var</code></td><td>Variable data (logs, spool, mail)</td><td><code>log/messages, log/secure</code></td></tr>
        <tr><td><code>/tmp</code></td><td>Temporary files (cleared on reboot)</td><td>—</td></tr>
        <tr><td><code>/usr</code></td><td>User programs and libraries</td><td><code>bin/, lib/, share/</code></td></tr>
        <tr><td><code>/proc</code></td><td>Virtual FS — kernel & process info</td><td><code>cpuinfo, meminfo, /proc/PID</code></td></tr>
        <tr><td><code>/sys</code></td><td>Virtual FS — hardware/driver info</td><td>—</td></tr>
        <tr><td><code>/dev</code></td><td>Device files</td><td><code>sda, tty, null, random</code></td></tr>
        <tr><td><code>/boot</code></td><td>Bootloader + kernel images</td><td><code>vmlinuz, initramfs, grub/</code></td></tr>
        <tr><td><code>/mnt</code> / <code>/media</code></td><td>Mount points for filesystems</td><td>—</td></tr>
        <tr><td><code>/opt</code></td><td>Optional/third-party software</td><td>—</td></tr>
      </tbody>
    </table>
  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Navigation & File Commands</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># Navigate the filesystem</span>
<span class="c-cmd">pwd</span>                          <span class="c-comment"># Print working directory</span>
<span class="c-cmd">cd</span> <span class="c-path">/var/log</span>                   <span class="c-comment"># Change directory (absolute)</span>
<span class="c-cmd">cd</span> <span class="c-flag">..</span>                         <span class="c-comment"># Go up one level</span>
<span class="c-cmd">cd</span> <span class="c-flag">~</span>                          <span class="c-comment"># Go to home directory</span>
<span class="c-cmd">ls</span> <span class="c-flag">-lah</span> <span class="c-path">/etc</span>                  <span class="c-comment"># Long list, human sizes, hidden</span>

<span class="c-comment"># File operations</span>
<span class="c-cmd">cp</span> <span class="c-flag">-r</span> <span class="c-path">/src/dir /dst/</span>         <span class="c-comment"># Copy recursively</span>
<span class="c-cmd">mv</span> <span class="c-path">oldname newname</span>            <span class="c-comment"># Move / rename</span>
<span class="c-cmd">rm</span> <span class="c-flag">-rf</span> <span class="c-path">/tmp/test/</span>            <span class="c-comment"># Remove (careful!)</span>
<span class="c-cmd">mkdir</span> <span class="c-flag">-p</span> <span class="c-path">/opt/app/logs</span>        <span class="c-comment"># Create nested dirs</span>
<span class="c-cmd">find</span> <span class="c-path">/var</span> <span class="c-flag">-name</span> <span class="c-str">”*.log”</span> <span class="c-flag">-mtime</span> <span class="c-hi">+7</span>  <span class="c-comment"># Find logs older than 7 days</span>
<span class="c-cmd">stat</span> <span class="c-path">/etc/passwd</span>              <span class="c-comment"># File metadata (size, inode, dates)</span>

<span class="c-comment"># Search inside files</span>
<span class="c-cmd">grep</span> <span class="c-flag">-rn</span> <span class="c-str">“FAILED”</span> <span class="c-path">/var/log/</span>   <span class="c-comment"># Recursive grep with line numbers</span>
<span class="c-cmd">grep</span> <span class="c-flag">-i</span> <span class="c-str">“error”</span> <span class="c-path">/var/log/messages</span>  <span class="c-comment"># Case-insensitive</span>
</pre>

  </div>

  <div class="callout tip">
    <span class="callout-icon">💡</span>
    <p><strong>Pro Tip:</strong> On RHEL 9, <code>/bin</code>, <code>/sbin</code>, and <code>/lib</code> are symlinks to <code>/usr/bin</code>, <code>/usr/sbin</code>, and <code>/usr/lib</code>. The system was merged to simplify maintenance.</p>
  </div>
</section>

<!-- ===== 2. PERMISSIONS ===== -->

<section class="section" id="permissions">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2 class="section-title">File Permissions & Ownership</h2>
    <span class="section-icon">🔐</span>
  </div>

  <p style="color:var(--text-dim); margin-bottom:20px;">Linux uses a 9-bit permission model split into three groups: Owner, Group, and Others. Plus a file type bit at the front.</p>

  <!-- Visual permission breakdown -->

  <div class="code-block">
    <div class="code-header"><span class="code-label">Permission String Breakdown</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-cmd">ls -l</span> <span class="c-path">/etc/passwd</span>
<span class="c-out">-rw-r--r--  1  root  root  1847  Mar 10 09:12  /etc/passwd</span>
<span class="c-comment"> ↑↑↑↑↑↑↑↑↑↑   ↑     ↑     ↑      ↑            ↑</span>
<span class="c-comment"> │││││││││└─ others: read only</span>
<span class="c-comment"> ││││││└───  group:  read only</span>
<span class="c-comment"> │││└──────  owner:  read+write</span>
<span class="c-comment"> └─────────  type: - = file, d = dir, l = symlink</span>
</pre>
  </div>

  <div style="margin: 20px 0;">
    <p style="font-family:'JetBrains Mono',monospace; font-size:0.8rem; color:var(--text-muted); margin-bottom:12px;">VISUAL: <code>-rwxr-xr--</code> decoded</p>
    <div class="perm-visual">
      <div class="perm-col">
        <div class="perm-bit type">-</div>
        <div class="perm-label">type</div>
      </div>
      <div class="perm-sep">│</div>
      <div class="perm-col">
        <div class="perm-group">
          <div class="perm-col"><div class="perm-bit on">r</div><div class="perm-label">r</div></div>
          <div class="perm-col"><div class="perm-bit on">w</div><div class="perm-label">w</div></div>
          <div class="perm-col"><div class="perm-bit on">x</div><div class="perm-label">x</div></div>
        </div>
        <div class="perm-label" style="font-size:0.7rem; color:var(--green);">OWNER (7)</div>
      </div>
      <div class="perm-sep">│</div>
      <div class="perm-col">
        <div class="perm-group">
          <div class="perm-col"><div class="perm-bit on">r</div><div class="perm-label">r</div></div>
          <div class="perm-col"><div class="perm-bit off">-</div><div class="perm-label">-</div></div>
          <div class="perm-col"><div class="perm-bit on">x</div><div class="perm-label">x</div></div>
        </div>
        <div class="perm-label" style="font-size:0.7rem; color:var(--cyan);">GROUP (5)</div>
      </div>
      <div class="perm-sep">│</div>
      <div class="perm-col">
        <div class="perm-group">
          <div class="perm-col"><div class="perm-bit on">r</div><div class="perm-label">r</div></div>
          <div class="perm-col"><div class="perm-bit off">-</div><div class="perm-label">-</div></div>
          <div class="perm-col"><div class="perm-bit off">-</div><div class="perm-label">-</div></div>
        </div>
        <div class="perm-label" style="font-size:0.7rem; color:var(--orange);">OTHERS (4)</div>
      </div>
    </div>
  </div>

  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Octal</th><th>Symbol</th><th>Meaning</th></tr></thead>
      <tbody>
        <tr><td><code>4</code></td><td><code>r--</code></td><td>Read only</td></tr>
        <tr><td><code>5</code></td><td><code>r-x</code></td><td>Read + Execute</td></tr>
        <tr><td><code>6</code></td><td><code>rw-</code></td><td>Read + Write</td></tr>
        <tr><td><code>7</code></td><td><code>rwx</code></td><td>Full access</td></tr>
        <tr><td><code>0</code></td><td><code>---</code></td><td>No permission</td></tr>
        <tr><td><code>755</code></td><td><code>rwxr-xr-x</code></td><td>Executable — owner full, others read+exec</td></tr>
        <tr><td><code>644</code></td><td><code>rw-r--r--</code></td><td>Config file — owner rw, others read</td></tr>
        <tr><td><code>700</code></td><td><code>rwx------</code></td><td>Private script — only owner access</td></tr>
        <tr><td><code>600</code></td><td><code>rw-------</code></td><td>SSH private key — owner rw only</td></tr>
      </tbody>
    </table>
  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">chmod, chown, umask</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># chmod — change permissions</span>
<span class="c-cmd">chmod</span> <span class="c-hi">755</span> <span class="c-path">script.sh</span>              <span class="c-comment"># octal notation</span>
<span class="c-cmd">chmod</span> <span class="c-flag">u+x,g-w,o-r</span> <span class="c-path">file.txt</span>     <span class="c-comment"># symbolic notation</span>
<span class="c-cmd">chmod</span> <span class="c-flag">-R</span> <span class="c-hi">750</span> <span class="c-path">/opt/app/</span>         <span class="c-comment"># recursive</span>

<span class="c-comment"># chown — change ownership</span>
<span class="c-cmd">chown</span> <span class="c-var">nilay</span><span class="c-hi">:</span><span class="c-var">devops</span> <span class="c-path">app.conf</span>    <span class="c-comment"># user:group</span>
<span class="c-cmd">chown</span> <span class="c-flag">-R</span> <span class="c-var">www-data</span><span class="c-hi">:</span><span class="c-var">www-data</span> <span class="c-path">/var/www</span>

<span class="c-comment"># umask — default permission mask</span>
<span class="c-cmd">umask</span>                           <span class="c-comment"># Show current (e.g. 0022)</span>
<span class="c-cmd">umask</span> <span class="c-hi">027</span>                       <span class="c-comment"># New files: 640, dirs: 750</span>
<span class="c-comment"># Formula: file perms = 666 - umask | dir = 777 - umask</span>

<span class="c-comment"># Special bits</span>
<span class="c-cmd">chmod</span> <span class="c-hi">4755</span> <span class="c-path">/usr/bin/sudo</span>      <span class="c-comment"># SUID — runs as file owner</span>
<span class="c-cmd">chmod</span> <span class="c-hi">2755</span> <span class="c-path">/usr/bin/write</span>     <span class="c-comment"># SGID — runs with group perms</span>
<span class="c-cmd">chmod</span> <span class="c-hi">1777</span> <span class="c-path">/tmp</span>               <span class="c-comment"># Sticky bit — only owner deletes</span>
</pre>

  </div>

  <div class="callout warn">
    <span class="callout-icon">⚠️</span>
    <p><strong>Security Rule:</strong> SSH keys at <code>~/.ssh/id_rsa</code> must be <code>chmod 600</code>. The <code>~/.ssh/</code> directory must be <code>700</code>. Loose permissions will cause SSH to refuse the key.</p>
  </div>
</section>

<!-- ===== 3. PROCESSES ===== -->

<section class="section" id="processes">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2 class="section-title">Process Management</h2>
    <span class="section-icon">⚙️</span>
  </div>

  <div class="diagram">
<pre style="padding:0; background:none; border:none;">
<span class="hi">PROCESS LIFECYCLE</span>

<span class="box">  ┌─────────┐</span>     <span class="arrow">fork()</span>      <span class="box">┌─────────┐</span>
<span class="box">  │  PARENT │</span> ──────────────→ <span class="box">│  CHILD  │</span>
<span class="box">  │  (PID)  │</span>                 <span class="box">│ (PID+1) │</span>
<span class="box">  └─────────┘</span>                 <span class="box">└────┬────┘</span>
↑                            │
<span class="label">wait() for child</span>           <span class="label">exec() new program</span>
│
<span class="box">┌─────────┴───────┐</span>
│                 │
<span class="label">Running</span>          <span class="label">Sleeping (I/O wait)</span>
│
<span class="label">exit()</span> → <span class="warn">Zombie</span> (if parent doesn’t wait)
</pre>

  </div>

  <div class="process-tree">
<span style="color:var(--green); font-weight:700;">systemd (PID 1)</span>
├── <span style="color:var(--cyan);">sshd (PID 842)</span>
│   └── <span style="color:var(--text);">sshd: nilay (PID 2301)</span>
│       └── <span style="color:var(--yellow);">bash (PID 2302)</span>
│           └── <span style="color:var(--text-dim);">vim script.sh (PID 2410)</span>
├── <span style="color:var(--cyan);">crond (PID 1021)</span>
├── <span style="color:var(--cyan);">httpd (PID 1104)</span>
│   ├── <span style="color:var(--text-dim);">httpd worker (PID 1105)</span>
│   └── <span style="color:var(--text-dim);">httpd worker (PID 1106)</span>
└── <span style="color:var(--cyan);">NetworkManager (PID 756)</span>
  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Process Commands</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># View processes</span>
<span class="c-cmd">ps</span> <span class="c-flag">aux</span>                         <span class="c-comment"># All processes (BSD style)</span>
<span class="c-cmd">ps</span> <span class="c-flag">-ef</span>                         <span class="c-comment"># Full format (UNIX style)</span>
<span class="c-cmd">ps</span> <span class="c-flag">aux</span> <span class="c-hi">|</span> <span class="c-cmd">grep</span> <span class="c-str">"httpd"</span>          <span class="c-comment"># Filter by name</span>
<span class="c-cmd">pstree</span> <span class="c-flag">-p</span>                       <span class="c-comment"># Visual process tree with PIDs</span>

<span class="c-comment"># Real-time monitoring</span>
<span class="c-cmd">top</span>                             <span class="c-comment"># Interactive process viewer</span>
<span class="c-cmd">htop</span>                            <span class="c-comment"># Better version of top</span>
<span class="c-cmd">top</span> <span class="c-flag">-u</span> <span class="c-var">nilay</span>                   <span class="c-comment"># Only user’s processes</span>

<span class="c-comment"># Find process by name/port</span>
<span class="c-cmd">pidof</span> <span class="c-var">sshd</span>                      <span class="c-comment"># Get PID of sshd</span>
<span class="c-cmd">pgrep</span> <span class="c-flag">-l</span> <span class="c-var">httpd</span>                  <span class="c-comment"># List matching processes</span>
<span class="c-cmd">ss</span> <span class="c-flag">-tlnp</span>                        <span class="c-comment"># Sockets + owning process</span>

<span class="c-comment"># Signals (kill)</span>
<span class="c-cmd">kill</span> <span class="c-hi">-15</span> <span class="c-var">2410</span>                   <span class="c-comment"># SIGTERM — graceful stop</span>
<span class="c-cmd">kill</span> <span class="c-hi">-9</span> <span class="c-var">2410</span>                    <span class="c-comment"># SIGKILL — force kill</span>
<span class="c-cmd">killall</span> <span class="c-var">httpd</span>                   <span class="c-comment"># Kill all by name</span>
<span class="c-cmd">pkill</span> <span class="c-flag">-u</span> <span class="c-var">nilay</span>                  <span class="c-comment"># Kill all of a user</span>

<span class="c-comment"># Background / foreground</span>
<span class="c-cmd">sleep</span> 100 <span class="c-hi">&</span>                     <span class="c-comment"># Run in background</span>
<span class="c-cmd">jobs</span>                            <span class="c-comment"># List background jobs</span>
<span class="c-cmd">fg</span> <span class="c-hi">%1</span>                           <span class="c-comment"># Bring job 1 to foreground</span>
<span class="c-cmd">bg</span> <span class="c-hi">%1</span>                           <span class="c-comment"># Resume job 1 in background</span>

<span class="c-comment"># Priority (nice value: -20 high → 19 low)</span>
<span class="c-cmd">nice</span> <span class="c-flag">-n 10</span> <span class="c-cmd">tar</span> <span class="c-flag">-czf</span> backup.tar.gz <span class="c-path">/data</span>
<span class="c-cmd">renice</span> <span class="c-flag">-n 5</span> <span class="c-flag">-p</span> <span class="c-var">2410</span>          <span class="c-comment"># Change priority of running process</span>
</pre>

  </div>

  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Signal</th><th>Number</th><th>Action</th></tr></thead>
      <tbody>
        <tr><td><code>SIGHUP</code></td><td><code>1</code></td><td>Hangup — reload config</td></tr>
        <tr><td><code>SIGINT</code></td><td><code>2</code></td><td>Interrupt — Ctrl+C</td></tr>
        <tr><td><code>SIGTERM</code></td><td><code>15</code></td><td>Terminate gracefully (default)</td></tr>
        <tr><td><code>SIGKILL</code></td><td><code>9</code></td><td>Kill immediately — cannot be caught</td></tr>
        <tr><td><code>SIGSTOP</code></td><td><code>19</code></td><td>Pause process — Ctrl+Z</td></tr>
        <tr><td><code>SIGCONT</code></td><td><code>18</code></td><td>Continue paused process</td></tr>
      </tbody>
    </table>
  </div>
</section>

<!-- ===== 4. NETWORKING ===== -->

<section class="section" id="networking">
  <div class="section-header">
    <span class="section-num">04</span>
    <h2 class="section-title">Networking</h2>
    <span class="section-icon">🌐</span>
  </div>

  <div class="diagram">
<pre style="padding:0; background:none; border:none;">
<span class="hi">NETWORK STACK VIEW</span>

<span class="box">┌─────────────────────────────┐</span>
<span class="box">│      Application (SSH/HTTP) │</span> ← port 22, 80, 443
<span class="box">├─────────────────────────────┤</span>
<span class="box">│       Transport (TCP/UDP)   │</span> ← sockets
<span class="box">├─────────────────────────────┤</span>
<span class="box">│       Network (IP)          │</span> ← routing, IP addresses
<span class="box">├─────────────────────────────┤</span>
<span class="box">│       Data Link (Ethernet)  │</span> ← MAC address, NIC
<span class="box">├─────────────────────────────┤</span>
<span class="box">│       Physical              │</span> ← cables, wifi
<span class="box">└─────────────────────────────┘</span>
<span class="label">eth0 / ens3 / enp0s3</span>
</pre>

  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Network Configuration & Diagnostics</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># Show interfaces and addresses</span>
<span class="c-cmd">ip</span> <span class="c-flag">addr show</span>                    <span class="c-comment"># All interfaces (modern)</span>
<span class="c-cmd">ip</span> <span class="c-flag">addr show</span> <span class="c-var">eth0</span>             <span class="c-comment"># Specific interface</span>
<span class="c-cmd">ip</span> <span class="c-flag">link</span>                         <span class="c-comment"># Layer 2 info</span>

<span class="c-comment"># Routing</span>
<span class="c-cmd">ip</span> <span class="c-flag">route show</span>                   <span class="c-comment"># Routing table</span>
<span class="c-cmd">ip</span> <span class="c-flag">route add</span> <span class="c-hi">192.168.2.0/24</span> <span class="c-flag">via</span> <span class="c-hi">10.0.0.1</span>
<span class="c-cmd">ip</span> <span class="c-flag">route del default</span>

<span class="c-comment"># DNS & connectivity</span>
<span class="c-cmd">cat</span> <span class="c-path">/etc/resolv.conf</span>           <span class="c-comment"># DNS servers</span>
<span class="c-cmd">cat</span> <span class="c-path">/etc/hosts</span>                  <span class="c-comment"># Local hostname mappings</span>
<span class="c-cmd">ping</span> <span class="c-flag">-c 4</span> <span class="c-hi">8.8.8.8</span>              <span class="c-comment"># ICMP ping</span>
<span class="c-cmd">traceroute</span> <span class="c-hi">8.8.8.8</span>              <span class="c-comment"># Hop-by-hop path</span>
<span class="c-cmd">dig</span> <span class="c-hi">google.com</span> <span class="c-flag">+short</span>          <span class="c-comment"># DNS lookup</span>
<span class="c-cmd">nslookup</span> <span class="c-hi">amazon.com</span>            <span class="c-comment"># Alternate DNS query</span>
<span class="c-cmd">curl</span> <span class="c-flag">-I</span> <span class="c-str">https://example.com</span>    <span class="c-comment"># HTTP headers</span>

<span class="c-comment"># Open ports & sockets</span>
<span class="c-cmd">ss</span> <span class="c-flag">-tlnp</span>                        <span class="c-comment"># TCP listen ports + process</span>
<span class="c-cmd">ss</span> <span class="c-flag">-tunp</span>                        <span class="c-comment"># TCP+UDP connections</span>
<span class="c-cmd">netstat</span> <span class="c-flag">-an</span>                     <span class="c-comment"># (legacy) all connections</span>

<span class="c-comment"># NetworkManager (RHEL 9)</span>
<span class="c-cmd">nmcli</span> <span class="c-flag">device status</span>            <span class="c-comment"># Interface status</span>
<span class="c-cmd">nmcli</span> <span class="c-flag">connection show</span>          <span class="c-comment"># Connections</span>
<span class="c-cmd">nmcli</span> <span class="c-flag">con mod</span> <span class="c-str">“eth0”</span> <span class="c-flag">ipv4.addresses</span> <span class="c-hi">192.168.1.10/24</span>
<span class="c-cmd">nmcli</span> <span class="c-flag">con up</span> <span class="c-str">“eth0”</span>
</pre>

  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Firewall — firewalld (RHEL/CentOS)</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-cmd">firewall-cmd</span> <span class="c-flag">--state</span>           <span class="c-comment"># running/not running</span>
<span class="c-cmd">firewall-cmd</span> <span class="c-flag">--list-all</span>         <span class="c-comment"># Show active zone rules</span>
<span class="c-cmd">firewall-cmd</span> <span class="c-flag">--zone=public --add-port=</span><span class="c-hi">8080/tcp</span> <span class="c-flag">--permanent</span>
<span class="c-cmd">firewall-cmd</span> <span class="c-flag">--add-service=</span><span class="c-var">http</span> <span class="c-flag">--permanent</span>
<span class="c-cmd">firewall-cmd</span> <span class="c-flag">--reload</span>           <span class="c-comment"># Apply permanent rules</span>
<span class="c-cmd">firewall-cmd</span> <span class="c-flag">--zone=drop --add-source=</span><span class="c-hi">10.0.0.5</span> <span class="c-comment"># Block IP</span>
</pre>
  </div>
</section>

<!-- ===== 5. USERS & GROUPS ===== -->

<section class="section" id="users">
  <div class="section-header">
    <span class="section-num">05</span>
    <h2 class="section-title">Users, Groups & sudo</h2>
    <span class="section-icon">👤</span>
  </div>

  <div class="two-col">
    <div class="code-block">
      <div class="code-header"><span class="code-label">/etc/passwd format</span><span class="code-lang">text</span></div>
      <pre>
<span class="c-var">nilay</span>:<span class="c-hi">x</span>:<span class="c-cmd">1001</span>:<span class="c-cmd">1001</span>:<span class="c-str">Nilay Meshram</span>:<span class="c-path">/home/nilay</span>:<span class="c-out">/bin/bash</span>
  <span class="c-comment">↑     ↑   ↑    ↑     ↑            ↑            ↑</span>
<span class="c-comment">user  pw  UID  GID  comment        home         shell</span>
</pre>
    </div>
    <div class="code-block">
      <div class="code-header"><span class="code-label">/etc/shadow format</span><span class="code-lang">text</span></div>
      <pre>
<span class="c-var">nilay</span>:<span class="c-hi">$6$salt$hashed</span>:<span class="c-cmd">19000</span>:<span class="c-out">0</span>:<span class="c-err">99999</span>:<span class="c-out">7</span>:::
  <span class="c-comment">↑     ↑              ↑      ↑    ↑      ↑</span>
<span class="c-comment">user  hash           last  min  max   warn</span>
</pre>
    </div>
  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">User Management</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># Create / modify / delete users</span>
<span class="c-cmd">useradd</span> <span class="c-flag">-m -s</span> /bin/bash <span class="c-flag">-c</span> <span class="c-str">"Dev User"</span> <span class="c-var">devuser</span>
<span class="c-cmd">passwd</span> <span class="c-var">devuser</span>                 <span class="c-comment"># Set password</span>
<span class="c-cmd">usermod</span> <span class="c-flag">-aG</span> <span class="c-var">wheel devuser</span>      <span class="c-comment"># Add to wheel (sudo) group</span>
<span class="c-cmd">usermod</span> <span class="c-flag">-L</span> <span class="c-var">devuser</span>             <span class="c-comment"># Lock account</span>
<span class="c-cmd">userdel</span> <span class="c-flag">-r</span> <span class="c-var">devuser</span>             <span class="c-comment"># Delete user + home dir</span>
<span class="c-cmd">chage</span> <span class="c-flag">-l</span> <span class="c-var">devuser</span>               <span class="c-comment"># Password aging info</span>
<span class="c-cmd">chage</span> <span class="c-flag">-M 90 -W 7</span> <span class="c-var">devuser</span>      <span class="c-comment"># Expire in 90d, warn 7d before</span>

<span class="c-comment"># Groups</span>
<span class="c-cmd">groupadd</span> <span class="c-var">devops</span>                 <span class="c-comment"># Create group</span>
<span class="c-cmd">gpasswd</span> <span class="c-flag">-a</span> <span class="c-var">nilay devops</span>         <span class="c-comment"># Add nilay to devops</span>
<span class="c-cmd">id</span> <span class="c-var">nilay</span>                        <span class="c-comment"># Show UID, GID, groups</span>
<span class="c-cmd">groups</span> <span class="c-var">nilay</span>                    <span class="c-comment"># List user’s groups</span>

<span class="c-comment"># sudo — /etc/sudoers (edit with visudo!)</span>
<span class="c-var">nilay</span>  <span class="c-hi">ALL=(ALL) NOPASSWD: ALL</span>  <span class="c-comment"># Full sudo without password</span>
<span class="c-var">devops</span> <span class="c-hi">ALL=(ALL)</span> <span class="c-path">/bin/systemctl,/usr/bin/journalctl</span>  <span class="c-comment"># Restrict commands</span>

<span class="c-cmd">sudo</span> <span class="c-flag">-l</span>                         <span class="c-comment"># List allowed sudo commands</span>
<span class="c-cmd">sudo</span> <span class="c-flag">-i</span>                         <span class="c-comment"># Login as root</span>
<span class="c-cmd">sudo</span> <span class="c-flag">-u</span> <span class="c-var">devuser</span> <span class="c-cmd">bash</span>           <span class="c-comment"># Run bash as devuser</span>
</pre>

  </div>

  <div class="callout danger">
    <span class="callout-icon">🚫</span>
    <p><strong>Never use <code>chmod 777</code></strong> on files in production. Anyone on the system — or via a compromised service — can read, write, and execute. Always apply least privilege.</p>
  </div>
</section>

<!-- ===== 6. STORAGE / LVM ===== -->

<section class="section" id="storage">
  <div class="section-header">
    <span class="section-num">06</span>
    <h2 class="section-title">Storage, LVM & Mounting</h2>
    <span class="section-icon">💾</span>
  </div>

  <div class="diagram">
<pre style="padding:0; background:none; border:none;">
<span class="hi">LVM ARCHITECTURE</span>

Physical Disks: <span class="label">/dev/sda1   /dev/sdb1   /dev/sdc1</span>
│               │             │
PV (Physical         └───────────────┴─────────────┘
Volumes)                             │
<span class="box">Volume Group (VG)</span>
<span class="label">vg_data (total: 500GB)</span>
│
┌──────────────────┼──────────────────┐
│                  │                   │
<span class="box">LV: lv_home</span>       <span class="box">LV: lv_var</span>        <span class="box">LV: lv_data</span>
<span class="label">100GB</span>             <span class="label">50GB</span>              <span class="label">300GB</span>
│                  │                   │
<span class="hi">/home</span>            <span class="hi">/var</span>             <span class="hi">/data</span>
</pre>

  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">LVM Workflow — Create & Extend</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment">## ── STEP 1: Create Physical Volumes ──</span>
<span class="c-cmd">pvcreate</span> <span class="c-path">/dev/sdb</span>
<span class="c-cmd">pvdisplay</span>                       <span class="c-comment"># Show PV details</span>
<span class="c-cmd">pvs</span>                             <span class="c-comment"># Summary</span>

<span class="c-comment">## ── STEP 2: Create Volume Group ──</span>
<span class="c-cmd">vgcreate</span> <span class="c-var">vg_data</span> <span class="c-path">/dev/sdb</span>
<span class="c-cmd">vgextend</span> <span class="c-var">vg_data</span> <span class="c-path">/dev/sdc</span>      <span class="c-comment"># Add another disk to VG</span>
<span class="c-cmd">vgs</span>                             <span class="c-comment"># Summary</span>

<span class="c-comment">## ── STEP 3: Create Logical Volumes ──</span>
<span class="c-cmd">lvcreate</span> <span class="c-flag">-L 50G -n</span> <span class="c-var">lv_data vg_data</span>
<span class="c-cmd">mkfs.xfs</span> <span class="c-path">/dev/vg_data/lv_data</span>  <span class="c-comment"># Format XFS</span>
<span class="c-cmd">mount</span> <span class="c-path">/dev/vg_data/lv_data /data</span>

<span class="c-comment">## ── STEP 4: Extend Online (no downtime!) ──</span>
<span class="c-cmd">lvextend</span> <span class="c-flag">-L +20G</span> <span class="c-path">/dev/vg_data/lv_data</span>
<span class="c-cmd">xfs_growfs</span> <span class="c-path">/data</span>               <span class="c-comment"># Resize XFS (online)</span>
<span class="c-comment"># For ext4: resize2fs /dev/vg_data/lv_data</span>

<span class="c-comment">## ── /etc/fstab — persistent mounts ──</span>
<span class="c-out">/dev/vg_data/lv_data  /data  xfs  defaults  0  0</span>
<span class="c-cmd">mount</span> <span class="c-flag">-a</span>                        <span class="c-comment"># Test fstab without reboot</span>
</pre>

  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Disk Inspection</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-cmd">lsblk</span>                           <span class="c-comment"># Block devices tree</span>
<span class="c-cmd">lsblk</span> <span class="c-flag">-f</span>                       <span class="c-comment"># With filesystem info</span>
<span class="c-cmd">df</span> <span class="c-flag">-hT</span>                         <span class="c-comment"># Disk usage + filesystem type</span>
<span class="c-cmd">du</span> <span class="c-flag">-sh</span> <span class="c-path">/var/log/*</span>             <span class="c-comment"># Size of each log dir</span>
<span class="c-cmd">fdisk</span> <span class="c-flag">-l</span>                        <span class="c-comment"># Partition table</span>
<span class="c-cmd">blkid</span>                           <span class="c-comment"># UUID + filesystem of devices</span>
</pre>
  </div>
</section>

<!-- ===== 7. SHELL SCRIPTING ===== -->

<section class="section" id="shell">
  <div class="section-header">
    <span class="section-num">07</span>
    <h2 class="section-title">Shell Scripting & Bash</h2>
    <span class="section-icon">📜</span>
  </div>

  <!-- Pipe flow -->

  <div style="margin-bottom:16px;">
    <p style="font-family:'JetBrains Mono',monospace; font-size:0.75rem; color:var(--text-muted); margin-bottom:10px;">PIPELINE FLOW</p>
    <div class="pipe-flow">
      <div class="pipe-col">
        <div class="pipe-box">cat file.log</div>
        <div class="pipe-label">source</div>
      </div>
      <div class="pipe-arrow">|</div>
      <div class="pipe-col">
        <div class="pipe-box">grep "ERROR"</div>
        <div class="pipe-label">filter</div>
      </div>
      <div class="pipe-arrow">|</div>
      <div class="pipe-col">
        <div class="pipe-box">awk '{print $5}'</div>
        <div class="pipe-label">extract field</div>
      </div>
      <div class="pipe-arrow">|</div>
      <div class="pipe-col">
        <div class="pipe-box">sort | uniq -c</div>
        <div class="pipe-label">count unique</div>
      </div>
      <div class="pipe-arrow">|</div>
      <div class="pipe-col">
        <div class="pipe-box">sort -rn | head -10</div>
        <div class="pipe-label">top 10</div>
      </div>
    </div>
  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Bash Script — User Lifecycle Automation</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-hi">#!/bin/bash</span>
<span class="c-comment"># User Lifecycle Manager — provision/deprovision from CSV</span>

<span class="c-var">CSV_FILE</span>=<span class="c-str">”/opt/scripts/users.csv”</span>
<span class="c-var">LOG</span>=<span class="c-str">”/var/log/user_lifecycle.log”</span>
<span class="c-var">ARCHIVE</span>=<span class="c-str">”/srv/user_archives”</span>

<span class="c-comment"># Helper: log with timestamp</span>
<span class="c-hi">log()</span> { <span class="c-cmd">echo</span> <span class="c-str">”[$(date ‘+%Y-%m-%d %H:%M:%S’)] $*”</span> | <span class="c-cmd">tee</span> <span class="c-flag">-a</span> <span class="c-str">”$LOG”</span>; }

<span class="c-comment"># Check root</span>
<span class="c-hi">[[ $EUID -ne 0 ]]</span> && { log <span class="c-str">“ERROR: must run as root”</span>; <span class="c-cmd">exit</span> 1; }

<span class="c-comment"># Read CSV: action,username,group</span>
<span class="c-hi">while</span> <span class="c-cmd">IFS=</span><span class="c-str">’,’</span> <span class="c-cmd">read</span> <span class="c-flag">-r</span> <span class="c-var">action user group</span>; <span class="c-hi">do</span>
<span class="c-hi">case “$action”</span> <span class="c-hi">in</span>
<span class="c-str">“add”</span>)
<span class="c-cmd">useradd</span> <span class="c-flag">-m -s</span> /bin/bash <span class="c-flag">-G</span> <span class="c-str">”$group”</span> <span class="c-str">”$user”</span>
<span class="c-cmd">passwd</span> <span class="c-flag">-e</span> <span class="c-str">”$user”</span>              <span class="c-comment"># Force pw change on first login</span>
log <span class="c-str">“ADDED: $user → $group”</span>
;;
<span class="c-str">“remove”</span>)
<span class="c-cmd">tar</span> <span class="c-flag">-czf</span> <span class="c-str">”$ARCHIVE/${user}_$(date +%F).tar.gz”</span> <span class="c-str">”/home/$user”</span>
<span class="c-cmd">userdel</span> <span class="c-flag">-r</span> <span class="c-str">”$user”</span> 2>/dev/null
log <span class="c-str">“REMOVED: $user (home archived)”</span>
;;
*) log <span class="c-str">“UNKNOWN action: $action”</span> ;;
<span class="c-hi">esac</span>
<span class="c-hi">done</span> < <span class="c-str">”$CSV_FILE”</span>

log <span class="c-str">“Done.”</span>
</pre>

  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Cron — Scheduling</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># Edit crontab</span>
<span class="c-cmd">crontab</span> <span class="c-flag">-e</span>                      <span class="c-comment"># Edit current user's crontab</span>
<span class="c-cmd">crontab</span> <span class="c-flag">-l</span>                      <span class="c-comment"># List current cron jobs</span>
<span class="c-cmd">crontab</span> <span class="c-flag">-u</span> <span class="c-var">nilay</span> <span class="c-flag">-l</span>          <span class="c-comment"># List another user's cron</span>

<span class="c-comment"># Cron syntax:  min  hr  day  mon  dow  command</span>
<span class="c-hi">0 2 * * *</span>     <span class="c-cmd">/opt/scripts/backup.sh</span>   <span class="c-comment"># Daily at 2:00 AM</span>
<span class="c-hi">*/15 * * * *</span>  <span class="c-cmd">/opt/scripts/healthcheck.sh</span>  <span class="c-comment"># Every 15 min</span>
<span class="c-hi">0 9 * * 1-5</span>  <span class="c-cmd">/opt/scripts/report.sh</span>   <span class="c-comment"># Weekdays 9AM</span>
<span class="c-hi">@reboot</span>       <span class="c-cmd">/opt/scripts/init.sh</span>     <span class="c-comment"># On every boot</span>

<span class="c-comment"># Systemd timer alternative (RHEL 9 recommended)</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">list-timers</span>           <span class="c-comment"># All active timers</span>
</pre>

  </div>

  <div class="hi-row">
    <span class="hi-chip green">$? — exit code</span>
    <span class="hi-chip cyan">$0 — script name</span>
    <span class="hi-chip yellow">$1..$9 — arguments</span>
    <span class="hi-chip orange">$# — arg count</span>
    <span class="hi-chip purple">$@ — all args</span>
    <span class="hi-chip green">$$ — current PID</span>
    <span class="hi-chip cyan">$! — last bg PID</span>
    <span class="hi-chip yellow">${VAR:-default}</span>
  </div>
</section>

<!-- ===== 8. SYSTEMD ===== -->

<section class="section" id="systemd">
  <div class="section-header">
    <span class="section-num">08</span>
    <h2 class="section-title">Systemd — Service Management</h2>
    <span class="section-icon">🔧</span>
  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">systemctl Cheatsheet</span><span class="code-lang">bash</span></div>
    <pre>
<span class="c-comment"># Service lifecycle</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">start</span>   <span class="c-var">nginx</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">stop</span>    <span class="c-var">nginx</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">restart</span> <span class="c-var">nginx</span>       <span class="c-comment"># Stop then start</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">reload</span>  <span class="c-var">nginx</span>       <span class="c-comment"># Reload config without restart</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">status</span>  <span class="c-var">nginx</span>       <span class="c-comment"># Status + last logs</span>

<span class="c-comment"># Enable/disable at boot</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">enable</span>  <span class="c-var">nginx</span>       <span class="c-comment"># Enable on boot</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">disable</span> <span class="c-var">nginx</span>       <span class="c-comment"># Disable on boot</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">enable –now</span> <span class="c-var">nginx</span>  <span class="c-comment"># Enable AND start immediately</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">is-enabled</span> <span class="c-var">nginx</span>   <span class="c-comment"># Check boot state</span>

<span class="c-comment"># System state</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">list-units –type=service</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">list-units –failed</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">get-default</span>         <span class="c-comment"># Current target (runlevel)</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">set-default</span> <span class="c-var">multi-user.target</span>
<span class="c-cmd">systemctl</span> <span class="c-flag">isolate</span> <span class="c-var">rescue.target</span>  <span class="c-comment"># Switch target live</span>

<span class="c-comment"># Logs with journalctl</span>
<span class="c-cmd">journalctl</span> <span class="c-flag">-u</span> <span class="c-var">nginx</span>            <span class="c-comment"># Logs for nginx unit</span>
<span class="c-cmd">journalctl</span> <span class="c-flag">-u</span> <span class="c-var">nginx</span> <span class="c-flag">-f</span>        <span class="c-comment"># Follow live</span>
<span class="c-cmd">journalctl</span> <span class="c-flag">-n 50 –since</span> <span class="c-str">“1 hour ago”</span>
<span class="c-cmd">journalctl</span> <span class="c-flag">-p err</span> <span class="c-flag">-b</span>          <span class="c-comment"># Errors since last boot</span>
<span class="c-cmd">journalctl</span> <span class="c-flag">–disk-usage</span>        <span class="c-comment"># Journal disk space</span>
</pre>

  </div>

  <div class="code-block">
    <div class="code-header"><span class="code-label">Custom Service Unit — /etc/systemd/system/myapp.service</span><span class="code-lang">ini</span></div>
    <pre>
<span class="c-hi">[Unit]</span>
<span class="c-var">Description</span>=<span class="c-str">My Application Server</span>
<span class="c-var">After</span>=<span class="c-str">network.target</span>
<span class="c-var">Wants</span>=<span class="c-str">network-online.target</span>

<span class="c-hi">[Service]</span>
<span class="c-var">Type</span>=<span class="c-str">simple</span>
<span class="c-var">User</span>=<span class="c-str">appuser</span>
<span class="c-var">WorkingDirectory</span>=<span class="c-path">/opt/myapp</span>
<span class="c-var">ExecStart</span>=<span class="c-path">/opt/myapp/bin/start.sh</span>
<span class="c-var">ExecStop</span>=<span class="c-path">/opt/myapp/bin/stop.sh</span>
<span class="c-var">Restart</span>=<span class="c-str">on-failure</span>
<span class="c-var">RestartSec</span>=<span class="c-hi">5s</span>
<span class="c-var">StandardOutput</span>=<span class="c-str">journal</span>
<span class="c-var">StandardError</span>=<span class="c-str">journal</span>

<span class="c-hi">[Install]</span>
<span class="c-var">WantedBy</span>=<span class="c-str">multi-user.target</span>
</pre>

  </div>

  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Systemd Target</th><th>Equivalent Runlevel</th><th>Description</th></tr></thead>
      <tbody>
        <tr><td><code>poweroff.target</code></td><td>0</td><td>Shutdown</td></tr>
        <tr><td><code>rescue.target</code></td><td>1</td><td>Single-user mode</td></tr>
        <tr><td><code>multi-user.target</code></td><td>3</td><td>Multi-user, no GUI (servers)</td></tr>
        <tr><td><code>graphical.target</code></td><td>5</td><td>Multi-user + GUI</td></tr>
        <tr><td><code>reboot.target</code></td><td>6</td><td>Reboot</td></tr>
        <tr><td><code>emergency.target</code></td><td>—</td><td>Emergency shell (minimal)</td></tr>
      </tbody>
    </table>
  </div>

  <div class="callout info">
    <span class="callout-icon">ℹ️</span>
    <p><strong>After editing a unit file:</strong> Always run <code>systemctl daemon-reload</code> to reload the systemd manager configuration before restarting the service.</p>
  </div>

  <!-- Quick Ref Summary -->

  <div style="margin-top:48px;">
    <div class="section-header" style="border-bottom:none; padding-bottom:0;">
      <h2 class="section-title" style="font-size:1.2rem;">⚡ Quick Reference Card</h2>
    </div>
    <div class="cards cols3" style="margin-top:16px;">
      <div class="card">
        <div class="card-label">Logs</div>
        <h3>Key Log Files</h3>
        <p><code>/var/log/messages</code> — general<br><code>/var/log/secure</code> — auth/sudo<br><code>/var/log/audit/audit.log</code> — SELinux<br><code>journalctl -xe</code> — systemd</p>
      </div>
      <div class="card">
        <div class="card-label">SELinux</div>
        <h3>Quick Commands</h3>
        <p><code>getenforce</code> — check mode<br><code>setenforce 0/1</code> — permissive/enforcing<br><code>restorecon -Rv /path</code> — fix context<br><code>ausearch -m AVC</code> — denials</p>
      </div>
      <div class="card">
        <div class="card-label">Performance</div>
        <h3>System Health</h3>
        <p><code>free -h</code> — memory<br><code>vmstat 1 5</code> — VM stats<br><code>iostat -xz 1</code> — disk I/O<br><code>sar -u 1 5</code> — CPU history</p>
      </div>
      <div class="card">
        <div class="card-label">Package Mgmt</div>
        <h3>DNF (RHEL/CentOS)</h3>
        <p><code>dnf install nginx</code><br><code>dnf update</code><br><code>dnf remove pkg</code><br><code>dnf search keyword</code><br><code>rpm -qa | grep ssh</code></p>
      </div>
      <div class="card">
        <div class="card-label">SSH</div>
        <h3>Remote Access</h3>
        <p><code>ssh-keygen -t ed25519</code><br><code>ssh-copy-id user@host</code><br><code>scp file user@host:/path</code><br><code>rsync -avz src/ user@host:dst/</code></p>
      </div>
      <div class="card">
        <div class="card-label">Text Processing</div>
        <h3>awk / sed / grep</h3>
        <p><code>awk -F: '{print $1}' /etc/passwd</code><br><code>sed -i 's/old/new/g' file</code><br><code>grep -E "err|warn" /var/log/messages</code></p>
      </div>
    </div>
  </div>
</section>

</main>

<footer>
  Crafted with <span>♥</span> for Linux Admins &nbsp;·&nbsp; RHCSA Reference &nbsp;·&nbsp; <span>$ man everything</span>
</footer>

<script>
  // Intersection Observer for fade-in animation
  const sections = document.querySelectorAll('.section');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.08 });
  sections.forEach(s => observer.observe(s));

  // Animate hero terminal typing
  const lines = document.querySelectorAll('.term-body > div');
  lines.forEach((line, i) => {
    line.style.opacity = '0';
    line.style.transition = 'opacity 0.3s';
    setTimeout(() => { line.style.opacity = '1'; }, 400 + i * 200);
  });
</script>

</body>
</html>
