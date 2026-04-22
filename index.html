import { useState, useEffect, useRef } from "react";

const API_KEY_STORAGE = "wa_agent_api_key";

// ─── THEME ───────────────────────────────────────────────────────────────────
const css = `
  @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=IBM+Plex+Mono:wght@400;600;700&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080808;
    --s1: #0f0f0f;
    --s2: #161616;
    --s3: #1e1e1e;
    --border: #252525;
    --acc: #00e676;
    --acc2: #ff6d00;
    --acc3: #29b6f6;
    --txt: #e8e8e8;
    --muted: #555;
    --danger: #ff1744;
  }

  body { background: var(--bg); color: var(--txt); font-family: 'IBM Plex Mono', monospace; }

  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }

  .app { display: flex; height: 100vh; overflow: hidden; }

  /* SIDEBAR */
  .sidebar {
    width: 220px; min-width: 220px;
    background: var(--s1);
    border-right: 1px solid var(--border);
    display: flex; flex-direction: column;
    padding: 24px 0;
  }
  .sidebar-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 3px;
    color: var(--acc);
    padding: 0 20px 24px;
    border-bottom: 1px solid var(--border);
    line-height: 1;
  }
  .sidebar-logo span { color: var(--muted); font-size: 10px; display: block; letter-spacing: 2px; margin-top: 4px; font-family: 'IBM Plex Mono', monospace; }
  .nav { margin-top: 16px; flex: 1; }
  .nav-item {
    display: flex; align-items: center; gap: 10px;
    padding: 11px 20px;
    font-size: 11px; letter-spacing: 1px; text-transform: uppercase;
    color: var(--muted); cursor: pointer;
    border-left: 2px solid transparent;
    transition: all 0.15s;
  }
  .nav-item:hover { color: var(--txt); background: var(--s2); }
  .nav-item.active { color: var(--acc); border-left-color: var(--acc); background: rgba(0,230,118,0.04); }
  .nav-dot { width: 6px; height: 6px; border-radius: 50%; background: currentColor; flex-shrink: 0; }
  .nav-badge {
    margin-left: auto; background: var(--acc); color: #000;
    font-size: 9px; font-weight: 700; padding: 2px 6px; border-radius: 1px;
  }

  .api-section {
    padding: 16px 20px;
    border-top: 1px solid var(--border);
  }
  .api-label { font-size: 9px; color: var(--muted); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 6px; }
  .api-input {
    width: 100%; background: var(--s2); border: 1px solid var(--border);
    color: var(--txt); font-family: 'IBM Plex Mono', monospace;
    font-size: 10px; padding: 7px 10px; border-radius: 2px; outline: none;
  }
  .api-input:focus { border-color: var(--acc); }
  .api-status { font-size: 9px; margin-top: 4px; }
  .api-status.ok { color: var(--acc); }
  .api-status.no { color: var(--danger); }

  /* MAIN */
  .main { flex: 1; overflow-y: auto; display: flex; flex-direction: column; }
  .topbar {
    position: sticky; top: 0; z-index: 10;
    background: var(--bg); border-bottom: 1px solid var(--border);
    padding: 16px 32px; display: flex; align-items: center; justify-content: space-between;
  }
  .topbar-title { font-family: 'Bebas Neue', sans-serif; font-size: 20px; letter-spacing: 2px; }
  .topbar-sub { font-size: 10px; color: var(--muted); margin-top: 2px; }
  .page { padding: 32px; flex: 1; }

  /* CARDS */
  .card {
    background: var(--s1); border: 1px solid var(--border);
    border-radius: 2px; padding: 24px; margin-bottom: 20px;
  }
  .card-title { font-size: 11px; letter-spacing: 2px; text-transform: uppercase; color: var(--acc2); margin-bottom: 16px; }

  /* INPUTS */
  .field { margin-bottom: 16px; }
  .field label { display: block; font-size: 10px; color: var(--muted); letter-spacing: 1px; text-transform: uppercase; margin-bottom: 6px; }
  .field input, .field textarea, .field select {
    width: 100%; background: var(--s2); border: 1px solid var(--border);
    color: var(--txt); font-family: 'IBM Plex Mono', monospace;
    font-size: 12px; padding: 10px 14px; border-radius: 2px; outline: none;
    transition: border-color 0.15s;
  }
  .field input:focus, .field textarea:focus, .field select:focus { border-color: var(--acc); }
  .field textarea { resize: vertical; min-height: 80px; }
  .field select option { background: var(--s2); }

  /* BUTTONS */
  .btn {
    font-family: 'IBM Plex Mono', monospace; font-size: 11px; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase;
    padding: 11px 24px; border: none; border-radius: 2px; cursor: pointer;
    transition: all 0.15s; display: inline-flex; align-items: center; gap: 8px;
  }
  .btn-primary { background: var(--acc); color: #000; }
  .btn-primary:hover { background: #00ff88; }
  .btn-primary:disabled { background: var(--s3); color: var(--muted); cursor: not-allowed; }
  .btn-outline { background: transparent; color: var(--txt); border: 1px solid var(--border); }
  .btn-outline:hover { border-color: var(--acc); color: var(--acc); }
  .btn-danger { background: transparent; color: var(--danger); border: 1px solid var(--danger); }
  .btn-sm { padding: 7px 14px; font-size: 10px; }

  /* GRID */
  .grid2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
  .grid3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 20px; }

  /* STAT */
  .stat-card {
    background: var(--s1); border: 1px solid var(--border);
    padding: 20px; border-radius: 2px;
  }
  .stat-label { font-size: 9px; color: var(--muted); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 8px; }
  .stat-val { font-family: 'Bebas Neue', sans-serif; font-size: 36px; color: var(--acc); line-height: 1; }
  .stat-val.orange { color: var(--acc2); }
  .stat-val.blue { color: var(--acc3); }
  .stat-sub { font-size: 10px; color: var(--muted); margin-top: 4px; }

  /* LEAD TABLE */
  .table-wrap { overflow-x: auto; }
  table { width: 100%; border-collapse: collapse; font-size: 11px; }
  th { text-align: left; padding: 10px 14px; background: var(--s2); color: var(--muted); font-size: 9px; letter-spacing: 2px; text-transform: uppercase; border-bottom: 1px solid var(--border); }
  td { padding: 10px 14px; border-bottom: 1px solid var(--border); color: #aaa; vertical-align: middle; }
  tr:hover td { background: rgba(255,255,255,0.015); }
  .badge {
    font-size: 9px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase;
    padding: 3px 8px; border-radius: 1px; display: inline-block;
  }
  .badge-new { background: rgba(41,182,246,0.15); color: var(--acc3); }
  .badge-dm { background: rgba(255,109,0,0.15); color: var(--acc2); }
  .badge-replied { background: rgba(0,230,118,0.15); color: var(--acc); }
  .badge-converted { background: rgba(0,230,118,0.3); color: #00ff88; }
  .badge-onboarded { background: rgba(0,230,118,0.5); color: #000; }
  .badge-delivered { background: var(--acc); color: #000; }

  /* OUTPUT BOX */
  .output-box {
    background: #050505; border: 1px solid var(--border);
    padding: 20px; font-size: 12px; color: #aaa;
    line-height: 1.9; white-space: pre-wrap; border-radius: 2px;
    max-height: 400px; overflow-y: auto; margin-top: 16px;
    position: relative;
  }
  .output-box.streaming { border-color: var(--acc); }

  /* LOADING */
  .spinner {
    display: inline-block; width: 14px; height: 14px;
    border: 2px solid var(--border); border-top-color: var(--acc);
    border-radius: 50%; animation: spin 0.6s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .pulse { animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.4; } }

  /* FLOW CARDS */
  .flow-card {
    background: var(--s2); border: 1px solid var(--border);
    border-radius: 2px; padding: 16px; margin-bottom: 12px;
  }
  .flow-card-title { font-size: 11px; color: var(--acc2); font-weight: 700; margin-bottom: 8px; letter-spacing: 1px; }
  .flow-step { font-size: 11px; color: #888; padding: 4px 0; border-bottom: 1px solid var(--border); }
  .flow-step:last-child { border-bottom: none; }
  .flow-step strong { color: var(--txt); }

  /* ONBOARD FORM */
  .onboard-step {
    display: flex; align-items: flex-start; gap: 16px;
    padding: 16px 0; border-bottom: 1px solid var(--border);
  }
  .onboard-step:last-child { border-bottom: none; }
  .step-num {
    width: 28px; height: 28px; border-radius: 50%;
    background: var(--s3); color: var(--acc); font-size: 11px; font-weight: 700;
    display: flex; align-items: center; justify-content: center; flex-shrink: 0;
    border: 1px solid var(--acc);
  }
  .step-content { flex: 1; }
  .step-title { font-size: 12px; color: var(--txt); margin-bottom: 6px; }
  .step-desc { font-size: 10px; color: var(--muted); line-height: 1.7; }

  /* DM PREVIEW */
  .dm-bubble {
    background: var(--s2); border: 1px solid var(--border);
    border-radius: 2px 12px 12px 12px; padding: 14px 18px;
    font-size: 12px; color: #ccc; line-height: 1.8; max-width: 480px;
    margin-bottom: 12px; position: relative;
  }
  .dm-sender { font-size: 9px; color: var(--acc); letter-spacing: 1px; text-transform: uppercase; margin-bottom: 8px; }

  /* TABS */
  .tabs { display: flex; gap: 0; border-bottom: 1px solid var(--border); margin-bottom: 24px; }
  .tab {
    font-size: 10px; letter-spacing: 2px; text-transform: uppercase;
    padding: 10px 20px; cursor: pointer; color: var(--muted);
    border-bottom: 2px solid transparent; transition: all 0.15s;
  }
  .tab.active { color: var(--acc); border-bottom-color: var(--acc); }
  .tab:hover { color: var(--txt); }

  /* COPY BTN */
  .copy-btn {
    position: absolute; top: 10px; right: 10px;
    background: var(--s3); border: 1px solid var(--border);
    color: var(--muted); font-family: 'IBM Plex Mono', monospace;
    font-size: 9px; letter-spacing: 1px; padding: 4px 10px; cursor: pointer;
    border-radius: 2px; transition: all 0.15s;
  }
  .copy-btn:hover { border-color: var(--acc); color: var(--acc); }

  /* PIPELINE */
  .pipeline { display: flex; gap: 0; margin-bottom: 24px; }
  .pipe-stage {
    flex: 1; text-align: center; padding: 12px 8px;
    font-size: 9px; letter-spacing: 1px; text-transform: uppercase; color: var(--muted);
    border-bottom: 2px solid var(--border); position: relative;
  }
  .pipe-stage.active { color: var(--acc); border-bottom-color: var(--acc); }
  .pipe-count { font-family: 'Bebas Neue', sans-serif; font-size: 22px; display: block; margin-bottom: 2px; }

  /* ALERT */
  .alert { padding: 12px 16px; border-radius: 2px; font-size: 11px; margin-bottom: 16px; line-height: 1.6; }
  .alert-warn { background: rgba(255,109,0,0.08); border: 1px solid rgba(255,109,0,0.3); color: var(--acc2); }
  .alert-ok { background: rgba(0,230,118,0.08); border: 1px solid rgba(0,230,118,0.3); color: var(--acc); }
  .alert-info { background: rgba(41,182,246,0.08); border: 1px solid rgba(41,182,246,0.3); color: var(--acc3); }

  .divider { height: 1px; background: var(--border); margin: 20px 0; }
  .row { display: flex; gap: 12px; align-items: flex-start; }
  .row .field { flex: 1; }
`;

// ─── CLAUDE CALL ─────────────────────────────────────────────────────────────
async function callClaude(apiKey, systemPrompt, userPrompt, onChunk) {
  const res = await fetch("https://api.anthropic.com/v1/messages", {
    method: "POST",
    headers: { "Content-Type": "application/json", "x-api-key": apiKey, "anthropic-version": "2023-06-01" },
    body: JSON.stringify({
      model: "claude-sonnet-4-20250514",
      max_tokens: 1500,
      stream: true,
      system: systemPrompt,
      messages: [{ role: "user", content: userPrompt }]
    })
  });
  if (!res.ok) throw new Error(`API error ${res.status}`);
  const reader = res.body.getReader();
  const dec = new TextDecoder();
  let full = "";
  while (true) {
    const { done, value } = await reader.read();
    if (done) break;
    const chunk = dec.decode(value);
    const lines = chunk.split("\n").filter(l => l.startsWith("data: "));
    for (const line of lines) {
      try {
        const d = JSON.parse(line.slice(6));
        if (d.type === "content_block_delta" && d.delta?.text) {
          full += d.delta.text;
          onChunk(full);
        }
      } catch {}
    }
  }
  return full;
}

// ─── INITIAL DATA ────────────────────────────────────────────────────────────
const SAMPLE_LEADS = [
  { id: 1, name: "Rajesh Mehta", title: "Owner", biz: "Mehta Real Estate", city: "Pune", industry: "Real Estate", phone: "+91 98201 XXXXX", source: "LinkedIn", status: "new", dmSent: false, replied: false, converted: false, onboarded: false, delivered: false, notes: "" },
  { id: 2, name: "Priya Sharma", title: "Director", biz: "Shine Coaching Institute", city: "Ahmedabad", industry: "Coaching", phone: "+91 93741 XXXXX", source: "Facebook", status: "new", dmSent: false, replied: false, converted: false, onboarded: false, delivered: false, notes: "" },
  { id: 3, name: "Anil Gupta", title: "Proprietor", biz: "Gupta Diagnostics Clinic", city: "Jaipur", industry: "Clinic", phone: "+91 99282 XXXXX", source: "LinkedIn", status: "new", dmSent: false, replied: false, converted: false, onboarded: false, delivered: false, notes: "" },
];

const INDUSTRIES = ["Real Estate", "Coaching", "Clinic", "Salon", "Logistics", "Retail", "Restaurant", "Travel Agency", "Gym", "CA/Finance"];

// ─── MAIN APP ─────────────────────────────────────────────────────────────────
export default function App() {
  const [page, setPage] = useState("dashboard");
  const [apiKey, setApiKey] = useState(() => localStorage.getItem(API_KEY_STORAGE) || "");
  const [leads, setLeads] = useState(SAMPLE_LEADS);

  useEffect(() => { localStorage.setItem(API_KEY_STORAGE, apiKey); }, [apiKey]);

  const apiOk = apiKey.startsWith("sk-ant-");
  const stats = {
    total: leads.length,
    dmSent: leads.filter(l => l.dmSent).length,
    replied: leads.filter(l => l.replied).length,
    converted: leads.filter(l => l.converted).length,
    delivered: leads.filter(l => l.delivered).length,
    mrr: leads.filter(l => l.converted).length * 2000,
  };

  const updateLead = (id, patch) => setLeads(prev => prev.map(l => l.id === id ? { ...l, ...patch } : l));
  const addLead = (lead) => setLeads(prev => [...prev, { ...lead, id: Date.now() }]);

  const pages = {
    dashboard: <Dashboard stats={stats} leads={leads} setPage={setPage} />,
    leads: <Leads leads={leads} updateLead={updateLead} addLead={addLead} apiKey={apiKey} apiOk={apiOk} />,
    outreach: <Outreach leads={leads} updateLead={updateLead} apiKey={apiKey} apiOk={apiOk} />,
    onboarding: <Onboarding leads={leads} updateLead={updateLead} apiKey={apiKey} apiOk={apiOk} />,
    delivery: <Delivery leads={leads} updateLead={updateLead} apiKey={apiKey} apiOk={apiOk} />,
  };

  const navItems = [
    { id: "dashboard", label: "Dashboard" },
    { id: "leads", label: "Lead Gen", badge: stats.total },
    { id: "outreach", label: "Outreach", badge: stats.dmSent },
    { id: "onboarding", label: "Onboarding", badge: stats.converted },
    { id: "delivery", label: "Delivery", badge: stats.delivered },
  ];

  const pageTitles = { dashboard: "Command Center", leads: "Lead Generation", outreach: "Outreach Engine", onboarding: "Client Onboarding", delivery: "Bot Delivery" };
  const pageSubs = { dashboard: "Full pipeline overview", leads: "Find & manage prospects", outreach: "AI-generated DM scripts", onboarding: "Client intake & bot config", delivery: "Generate & hand off WhatsApp bots" };

  return (
    <>
      <style>{css}</style>
      <div className="app">
        <div className="sidebar">
          <div className="sidebar-logo">WABA<span>// whatsapp bot agency</span></div>
          <nav className="nav">
            {navItems.map(n => (
              <div key={n.id} className={`nav-item ${page === n.id ? "active" : ""}`} onClick={() => setPage(n.id)}>
                <div className="nav-dot" />
                {n.label}
                {n.badge > 0 && <span className="nav-badge">{n.badge}</span>}
              </div>
            ))}
          </nav>
          <div className="api-section">
            <div className="api-label">Claude API Key</div>
            <input className="api-input" type="password" placeholder="sk-ant-api03-..." value={apiKey} onChange={e => setApiKey(e.target.value)} />
            <div className={`api-status ${apiOk ? "ok" : "no"}`}>{apiOk ? "✓ connected" : "✗ add key to enable AI"}</div>
          </div>
        </div>
        <div className="main">
          <div className="topbar">
            <div>
              <div className="topbar-title">{pageTitles[page]}</div>
              <div className="topbar-sub">{pageSubs[page]}</div>
            </div>
            <div style={{ fontSize: 10, color: "var(--muted)" }}>MRR: <span style={{ color: "var(--acc)", fontWeight: 700 }}>₹{stats.mrr.toLocaleString()}</span></div>
          </div>
          <div className="page">{pages[page]}</div>
        </div>
      </div>
    </>
  );
}

// ─── DASHBOARD ────────────────────────────────────────────────────────────────
function Dashboard({ stats, leads, setPage }) {
  const recent = [...leads].reverse().slice(0, 5);
  return (
    <div>
      <div className="grid3" style={{ marginBottom: 20 }}>
        <div className="stat-card"><div className="stat-label">Total Leads</div><div className="stat-val blue">{stats.total}</div><div className="stat-sub">in pipeline</div></div>
        <div className="stat-card"><div className="stat-label">DMs Sent</div><div className="stat-val orange">{stats.dmSent}</div><div className="stat-sub">outreach active</div></div>
        <div className="stat-card"><div className="stat-label">Replies</div><div className="stat-val">{stats.replied}</div><div className="stat-sub">{stats.dmSent > 0 ? Math.round(stats.replied / stats.dmSent * 100) : 0}% reply rate</div></div>
        <div className="stat-card"><div className="stat-label">Converted</div><div className="stat-val orange">{stats.converted}</div><div className="stat-sub">paying clients</div></div>
        <div className="stat-card"><div className="stat-label">Bots Delivered</div><div className="stat-val">{stats.delivered}</div><div className="stat-sub">live in market</div></div>
        <div className="stat-card"><div className="stat-label">Monthly MRR</div><div className="stat-val" style={{ fontSize: 28 }}>₹{stats.mrr.toLocaleString()}</div><div className="stat-sub">₹{(stats.mrr * 12).toLocaleString()} ARR</div></div>
      </div>

      <div className="pipeline">
        {[
          { label: "Leads", count: stats.total, active: true },
          { label: "DM Sent", count: stats.dmSent, active: stats.dmSent > 0 },
          { label: "Replied", count: stats.replied, active: stats.replied > 0 },
          { label: "Converted", count: stats.converted, active: stats.converted > 0 },
          { label: "Delivered", count: stats.delivered, active: stats.delivered > 0 },
        ].map(s => (
          <div key={s.label} className={`pipe-stage ${s.active ? "active" : ""}`}>
            <span className="pipe-count">{s.count}</span>
            {s.label}
          </div>
        ))}
      </div>

      <div className="card">
        <div className="card-title">Recent Activity</div>
        <div className="table-wrap">
          <table>
            <thead><tr><th>Name</th><th>Business</th><th>Industry</th><th>Status</th></tr></thead>
            <tbody>
              {recent.map(l => (
                <tr key={l.id}>
                  <td>{l.name}</td>
                  <td style={{ color: "var(--txt)" }}>{l.biz}</td>
                  <td>{l.industry}</td>
                  <td><StatusBadge lead={l} /></td>
                </tr>
              ))}
            </tbody>
          </table>
        </div>
      </div>

      <div className="alert alert-info">
        💡 <strong>Today's target:</strong> Add 10 leads → Send 30 DMs → Follow up on all replies → Aim for 1 conversion. ₹2,000 closer to ₹10 CR.
      </div>
    </div>
  );
}

// ─── STATUS BADGE ─────────────────────────────────────────────────────────────
function StatusBadge({ lead }) {
  if (lead.delivered) return <span className="badge badge-delivered">Delivered</span>;
  if (lead.onboarded) return <span className="badge badge-onboarded">Onboarded</span>;
  if (lead.converted) return <span className="badge badge-converted">Converted</span>;
  if (lead.replied) return <span className="badge badge-replied">Replied</span>;
  if (lead.dmSent) return <span className="badge badge-dm">DM Sent</span>;
  return <span className="badge badge-new">New</span>;
}

// ─── LEADS ────────────────────────────────────────────────────────────────────
function Leads({ leads, updateLead, addLead, apiKey, apiOk }) {
  const [tab, setTab] = useState("list");
  const [genLoading, setGenLoading] = useState(false);
  const [genOutput, setGenOutput] = useState("");
  const [form, setForm] = useState({ name: "", title: "Owner", biz: "", city: "", industry: "Real Estate", phone: "", source: "LinkedIn", notes: "" });
  const [genConfig, setGenConfig] = useState({ industry: "Real Estate", city: "Mumbai", count: "10" });

  const handleAdd = () => {
    if (!form.name || !form.biz) return;
    addLead({ ...form, status: "new", dmSent: false, replied: false, converted: false, onboarded: false, delivered: false });
    setForm({ name: "", title: "Owner", biz: "", city: "", industry: "Real Estate", phone: "", source: "LinkedIn", notes: "" });
  };

  const generateLeads = async () => {
    if (!apiOk) return;
    setGenLoading(true); setGenOutput("");
    try {
      await callClaude(apiKey,
        "You are a B2B lead research expert for Indian SMB markets. Output ONLY raw text, no markdown formatting.",
        `Generate ${genConfig.count} realistic Indian SMB leads for WhatsApp bot automation service in ${genConfig.industry} sector, ${genConfig.city}.

For each lead output exactly this format (one per line, pipe-separated):
Name | Job Title | Business Name | City | Phone Pattern | Source | Pain Point

Make names, businesses, and details realistic and specific to Indian context. Phone as +91 XXXXX XXXXX format.`,
        (t) => setGenOutput(t)
      );
    } catch (e) { setGenOutput("Error: " + e.message); }
    setGenLoading(false);
  };

  return (
    <div>
      <div className="tabs">
        {["list", "add", "generate"].map(t => <div key={t} className={`tab ${tab === t ? "active" : ""}`} onClick={() => setTab(t)}>{t === "list" ? "Pipeline" : t === "add" ? "Add Lead" : "AI Generate"}</div>)}
      </div>

      {tab === "list" && (
        <div className="card">
          <div className="card-title">Lead Pipeline — {leads.length} prospects</div>
          <div className="table-wrap">
            <table>
              <thead><tr><th>Name</th><th>Business</th><th>City</th><th>Industry</th><th>Source</th><th>Status</th><th>Actions</th></tr></thead>
              <tbody>
                {leads.map(l => (
                  <tr key={l.id}>
                    <td style={{ color: "var(--txt)" }}>{l.name}</td>
                    <td>{l.biz}</td>
                    <td>{l.city}</td>
                    <td>{l.industry}</td>
                    <td>{l.source}</td>
                    <td><StatusBadge lead={l} /></td>
                    <td>
                      <div style={{ display: "flex", gap: 6 }}>
                        {!l.dmSent && <button className="btn btn-outline btn-sm" onClick={() => updateLead(l.id, { dmSent: true })}>Mark DM</button>}
                        {l.dmSent && !l.replied && <button className="btn btn-outline btn-sm" onClick={() => updateLead(l.id, { replied: true })}>Got Reply</button>}
                        {l.replied && !l.converted && <button className="btn btn-primary btn-sm" onClick={() => updateLead(l.id, { converted: true })}>Converted!</button>}
                      </div>
                    </td>
                  </tr>
                ))}
              </tbody>
            </table>
          </div>
        </div>
      )}

      {tab === "add" && (
        <div className="card">
          <div className="card-title">Add Lead Manually</div>
          <div className="grid2">
            <div className="field"><label>Full Name</label><input value={form.name} onChange={e => setForm({ ...form, name: e.target.value })} placeholder="Rajesh Mehta" /></div>
            <div className="field"><label>Job Title</label><input value={form.title} onChange={e => setForm({ ...form, title: e.target.value })} placeholder="Owner" /></div>
            <div className="field"><label>Business Name</label><input value={form.biz} onChange={e => setForm({ ...form, biz: e.target.value })} placeholder="Mehta Real Estate" /></div>
            <div className="field"><label>City</label><input value={form.city} onChange={e => setForm({ ...form, city: e.target.value })} placeholder="Pune" /></div>
            <div className="field"><label>Industry</label><select value={form.industry} onChange={e => setForm({ ...form, industry: e.target.value })}>{INDUSTRIES.map(i => <option key={i}>{i}</option>)}</select></div>
            <div className="field"><label>Source</label><select value={form.source} onChange={e => setForm({ ...form, source: e.target.value })}><option>LinkedIn</option><option>Facebook</option><option>IndiaMART</option><option>Referral</option><option>Other</option></select></div>
            <div className="field"><label>Phone</label><input value={form.phone} onChange={e => setForm({ ...form, phone: e.target.value })} placeholder="+91 98201 XXXXX" /></div>
          </div>
          <div className="field"><label>Notes</label><textarea value={form.notes} onChange={e => setForm({ ...form, notes: e.target.value })} placeholder="Any specific pain points noted..." /></div>
          <button className="btn btn-primary" onClick={handleAdd}>+ Add to Pipeline</button>
        </div>
      )}

      {tab === "generate" && (
        <div>
          {!apiOk && <div className="alert alert-warn">Add your Claude API key in the sidebar to use AI generation.</div>}
          <div className="card">
            <div className="card-title">AI Lead Research</div>
            <div className="grid3">
              <div className="field"><label>Industry</label><select value={genConfig.industry} onChange={e => setGenConfig({ ...genConfig, industry: e.target.value })}>{INDUSTRIES.map(i => <option key={i}>{i}</option>)}</select></div>
              <div className="field"><label>City</label><input value={genConfig.city} onChange={e => setGenConfig({ ...genConfig, city: e.target.value })} placeholder="Mumbai" /></div>
              <div className="field"><label>Count</label><select value={genConfig.count} onChange={e => setGenConfig({ ...genConfig, count: e.target.value })}><option>5</option><option>10</option><option>20</option></select></div>
            </div>
            <button className="btn btn-primary" disabled={!apiOk || genLoading} onClick={generateLeads}>
              {genLoading ? <><span className="spinner" /> Generating...</> : "Generate Leads with AI"}
            </button>
            {genOutput && (
              <div className="output-box" style={{ marginTop: 16 }}>
                <CopyBtn text={genOutput} />
                {genOutput}
              </div>
            )}
          </div>
        </div>
      )}
    </div>
  );
}

// ─── OUTREACH ────────────────────────────────────────────────────────────────
function Outreach({ leads, updateLead, apiKey, apiOk }) {
  const [selectedLead, setSelectedLead] = useState(null);
  const [dmOutput, setDmOutput] = useState("");
  const [emailOutput, setEmailOutput] = useState("");
  const [loading, setLoading] = useState(false);
  const [tab, setTab] = useState("dm");
  const [followUp, setFollowUp] = useState("");
  const [fuLoading, setFuLoading] = useState(false);

  const pending = leads.filter(l => !l.converted);

  const generateDM = async (lead) => {
    if (!apiOk) return;
    setLoading(true); setDmOutput(""); setEmailOutput("");
    setSelectedLead(lead);
    try {
      const sys = "You are an expert B2B cold outreach copywriter specializing in Indian SMB markets. Write punchy, direct, no-fluff messages. No emojis. No corporate speak. Sound human.";
      const dm = await callClaude(apiKey, sys,
        `Write a cold LinkedIn DM for selling a WhatsApp bot automation service.

Target:
- Name: ${lead.name}
- Title: ${lead.title} at ${lead.biz}
- Industry: ${lead.industry}
- City: ${lead.city}

Product: AI WhatsApp chatbot — qualifies leads 24/7, auto-replies, forwards hot leads. Setup 48hrs. ₹2,000/month.
Rule: Max 80 words. End with a live demo link placeholder [DEMO_LINK]. No call needed.`,
        (t) => setDmOutput(t));

      const email = await callClaude(apiKey, sys,
        `Write a cold email for the same prospect.

Target:
- Name: ${lead.name}
- Business: ${lead.biz}
- Industry: ${lead.industry}
- City: ${lead.city}

Product: AI WhatsApp chatbot. ₹2,000/month. 48-hour setup. Qualifies leads automatically.
Format: Subject line first, then body. Max 120 words total. End with [DEMO_LINK].`,
        (t) => setEmailOutput(t));
    } catch (e) { setDmOutput("Error: " + e.message); }
    setLoading(false);
  };

  const generateFollowUp = async () => {
    if (!apiOk || !selectedLead) return;
    setFuLoading(true); setFollowUp("");
    try {
      await callClaude(apiKey,
        "You write short, non-pushy follow-up messages for B2B sales. Max 50 words.",
        `Write a follow-up DM for ${selectedLead.name} at ${selectedLead.biz} (${selectedLead.industry}) who hasn't replied to a WhatsApp bot pitch in 3 days. Reference the live demo bot. Don't beg. Keep curiosity alive.`,
        (t) => setFollowUp(t));
    } catch (e) { setFollowUp("Error: " + e.message); }
    setFuLoading(false);
  };

  return (
    <div>
      <div className="grid2" style={{ gap: 20 }}>
        <div>
          <div className="card">
            <div className="card-title">Select Prospect</div>
            {pending.length === 0 && <div style={{ color: "var(--muted)", fontSize: 12 }}>All leads converted! Add more in Lead Gen.</div>}
            {pending.map(l => (
              <div key={l.id}
                style={{ padding: "10px 14px", cursor: "pointer", borderBottom: "1px solid var(--border)", background: selectedLead?.id === l.id ? "rgba(0,230,118,0.05)" : "transparent", borderLeft: selectedLead?.id === l.id ? "2px solid var(--acc)" : "2px solid transparent" }}
                onClick={() => { setSelectedLead(l); setDmOutput(""); setEmailOutput(""); setFollowUp(""); }}>
                <div style={{ fontSize: 12, color: "var(--txt)" }}>{l.name}</div>
                <div style={{ fontSize: 10, color: "var(--muted)" }}>{l.biz} · {l.industry} · {l.city}</div>
                <div style={{ marginTop: 4 }}><StatusBadge lead={l} /></div>
              </div>
            ))}
          </div>
        </div>

        <div>
          {!apiOk && <div className="alert alert-warn">Add Claude API key to generate AI scripts.</div>}
          {selectedLead && (
            <div className="card">
              <div className="card-title">Outreach for {selectedLead.name}</div>
              <button className="btn btn-primary" disabled={!apiOk || loading} onClick={() => generateDM(selectedLead)} style={{ marginBottom: 16 }}>
                {loading ? <><span className="spinner" /> Generating...</> : "Generate DM + Email with AI"}
              </button>

              {(dmOutput || emailOutput) && (
                <>
                  <div className="tabs" style={{ marginBottom: 16 }}>
                    <div className={`tab ${tab === "dm" ? "active" : ""}`} onClick={() => setTab("dm")}>LinkedIn DM</div>
                    <div className={`tab ${tab === "email" ? "active" : ""}`} onClick={() => setTab("email")}>Cold Email</div>
                    <div className={`tab ${tab === "followup" ? "active" : ""}`} onClick={() => setTab("followup")}>Follow-Up</div>
                  </div>

                  {tab === "dm" && dmOutput && (
                    <>
                      <div className="dm-bubble">
                        <div className="dm-sender">LinkedIn DM → {selectedLead.name}</div>
                        {dmOutput}
                      </div>
                      <CopyBtn text={dmOutput} inline />
                    </>
                  )}

                  {tab === "email" && emailOutput && (
                    <div className="output-box" style={{ marginTop: 0 }}>
                      <CopyBtn text={emailOutput} />
                      {emailOutput}
                    </div>
                  )}

                  {tab === "followup" && (
                    <>
                      <button className="btn btn-outline" disabled={!apiOk || fuLoading} onClick={generateFollowUp} style={{ marginBottom: 12 }}>
                        {fuLoading ? <><span className="spinner" /> Writing...</> : "Generate Follow-Up Message"}
                      </button>
                      {followUp && <div className="dm-bubble"><div className="dm-sender">Follow-Up (Day 3)</div>{followUp}</div>}
                    </>
                  )}

                  <div className="divider" />
                  <div style={{ display: "flex", gap: 10 }}>
                    {!selectedLead.dmSent && <button className="btn btn-outline btn-sm" onClick={() => updateLead(selectedLead.id, { dmSent: true })}>✓ Mark DM Sent</button>}
                    {selectedLead.dmSent && !selectedLead.replied && <button className="btn btn-outline btn-sm" onClick={() => updateLead(selectedLead.id, { replied: true })}>✓ Got Reply</button>}
                    {selectedLead.replied && !selectedLead.converted && <button className="btn btn-primary btn-sm" onClick={() => updateLead(selectedLead.id, { converted: true })}>🎉 Mark Converted</button>}
                  </div>
                </>
              )}
            </div>
          )}
          {!selectedLead && <div className="alert alert-info">← Select a prospect to generate personalized outreach scripts.</div>}
        </div>
      </div>
    </div>
  );
}

// ─── ONBOARDING ───────────────────────────────────────────────────────────────
function Onboarding({ leads, updateLead, apiKey, apiOk }) {
  const [selectedLead, setSelectedLead] = useState(null);
  const [intakeData, setIntakeData] = useState({ bizName: "", industry: "Real Estate", city: "", primaryPain: "", topFAQs: "", workingHours: "9am-7pm", priceRange: "", primaryCTA: "Book appointment", hotLeadCriteria: "" });
  const [flows, setFlows] = useState("");
  const [loading, setLoading] = useState(false);
  const [welcomeMsg, setWelcomeMsg] = useState("");

  const converted = leads.filter(l => l.converted && !l.onboarded);

  useEffect(() => {
    if (selectedLead) {
      setIntakeData(d => ({ ...d, bizName: selectedLead.biz, industry: selectedLead.industry, city: selectedLead.city }));
      setFlows(""); setWelcomeMsg("");
    }
  }, [selectedLead]);

  const generateFlows = async () => {
    if (!apiOk) return;
    setLoading(true); setFlows(""); setWelcomeMsg("");
    try {
      await callClaude(apiKey,
        "You are a WhatsApp chatbot architect. Generate precise, conversational bot flows for Indian SMBs. Be specific, practical, and ready-to-implement.",
        `Generate 5 complete WhatsApp chatbot conversation flows for:

Business: ${intakeData.bizName}
Industry: ${intakeData.industry}
City: ${intakeData.city}
Primary Pain: ${intakeData.primaryPain || "Missing inquiries outside working hours"}
Working Hours: ${intakeData.workingHours}
Common FAQs: ${intakeData.topFAQs || "pricing, availability, location, services"}
Primary CTA: ${intakeData.primaryCTA}
Hot Lead Criteria: ${intakeData.hotLeadCriteria || "budget confirmed + timeline this month"}

For each of these 5 flows, write:
FLOW NAME | TRIGGER KEYWORD | BOT MESSAGE (full text) | FOLLOW-UP IF NO REPLY

Flows to cover:
1. Price/Cost inquiry
2. Appointment/Booking request
3. Location/Address query
4. After-hours inquiry
5. Hot lead escalation (forward to owner)

Make messages sound natural and professional. Include the business name. End each flow with a clear CTA.`,
        (t) => setFlows(t));

      await callClaude(apiKey,
        "Write natural WhatsApp welcome messages for Indian businesses. Short, warm, professional.",
        `Write the perfect welcome message for ${intakeData.bizName} (${intakeData.industry} in ${intakeData.city}) WhatsApp bot. Max 3 lines. Show menu options numbered. Sound human not robotic.`,
        (t) => setWelcomeMsg(t));
    } catch (e) { setFlows("Error: " + e.message); }
    setLoading(false);
  };

  return (
    <div>
      <div className="grid2">
        <div>
          <div className="card">
            <div className="card-title">Converted Clients to Onboard</div>
            {converted.length === 0 && <div style={{ color: "var(--muted)", fontSize: 12 }}>No converted clients yet. Convert leads in Outreach.</div>}
            {converted.map(l => (
              <div key={l.id}
                style={{ padding: "10px 14px", cursor: "pointer", borderBottom: "1px solid var(--border)", background: selectedLead?.id === l.id ? "rgba(0,230,118,0.05)" : "transparent", borderLeft: selectedLead?.id === l.id ? "2px solid var(--acc)" : "2px solid transparent" }}
                onClick={() => setSelectedLead(l)}>
                <div style={{ fontSize: 12, color: "var(--txt)" }}>{l.name}</div>
                <div style={{ fontSize: 10, color: "var(--muted)" }}>{l.biz} · {l.industry}</div>
              </div>
            ))}
          </div>

          {selectedLead && (
            <div className="card">
              <div className="card-title">Client Intake Form</div>
              <div className="field"><label>Business Name</label><input value={intakeData.bizName} onChange={e => setIntakeData({ ...intakeData, bizName: e.target.value })} /></div>
              <div className="field"><label>Industry</label><select value={intakeData.industry} onChange={e => setIntakeData({ ...intakeData, industry: e.target.value })}>{INDUSTRIES.map(i => <option key={i}>{i}</option>)}</select></div>
              <div className="field"><label>City</label><input value={intakeData.city} onChange={e => setIntakeData({ ...intakeData, city: e.target.value })} /></div>
              <div className="field"><label>Primary Pain (what they hate most)</label><textarea value={intakeData.primaryPain} onChange={e => setIntakeData({ ...intakeData, primaryPain: e.target.value })} placeholder="Missing leads when busy / after hours" /></div>
              <div className="field"><label>Top 5 FAQs their customers ask</label><textarea value={intakeData.topFAQs} onChange={e => setIntakeData({ ...intakeData, topFAQs: e.target.value })} placeholder="What's the price? Do you visit location? What are timings?" /></div>
              <div className="field"><label>Working Hours</label><input value={intakeData.workingHours} onChange={e => setIntakeData({ ...intakeData, workingHours: e.target.value })} placeholder="9am-7pm Mon-Sat" /></div>
              <div className="field"><label>Primary CTA for Bot</label><input value={intakeData.primaryCTA} onChange={e => setIntakeData({ ...intakeData, primaryCTA: e.target.value })} placeholder="Book appointment / Get quote / Visit showroom" /></div>
              <div className="field"><label>Hot Lead Criteria (when to escalate)</label><input value={intakeData.hotLeadCriteria} onChange={e => setIntakeData({ ...intakeData, hotLeadCriteria: e.target.value })} placeholder="Budget > ₹50K and timeline this month" /></div>
              <button className="btn btn-primary" disabled={!apiOk || loading} onClick={generateFlows}>
                {loading ? <><span className="spinner" /> Building flows...</> : "Generate Bot Flows with AI"}
              </button>
            </div>
          )}
        </div>

        <div>
          {!apiOk && <div className="alert alert-warn">Add Claude API key to generate bot flows.</div>}
          {!selectedLead && <div className="alert alert-info">← Select a converted client to begin onboarding.</div>}

          {welcomeMsg && (
            <div className="card" style={{ marginBottom: 20 }}>
              <div className="card-title">Welcome Message</div>
              <div className="dm-bubble">
                <div className="dm-sender">Bot → Customer (first contact)</div>
                {welcomeMsg}
              </div>
              <CopyBtn text={welcomeMsg} inline />
            </div>
          )}

          {flows && (
            <div className="card">
              <div className="card-title">5 Conversation Flows</div>
              <div className="output-box" style={{ maxHeight: 500 }}>
                <CopyBtn text={flows} />
                {flows}
              </div>
              {selectedLead && !selectedLead.onboarded && (
                <button className="btn btn-primary" style={{ marginTop: 16 }} onClick={() => updateLead(selectedLead.id, { onboarded: true })}>
                  ✓ Mark Onboarding Complete
                </button>
              )}
            </div>
          )}
        </div>
      </div>
    </div>
  );
}

// ─── DELIVERY ────────────────────────────────────────────────────────────────
function Delivery({ leads, updateLead, apiKey, apiOk }) {
  const [selectedLead, setSelectedLead] = useState(null);
  const [handover, setHandover] = useState("");
  const [sop, setSop] = useState("");
  const [loading, setLoading] = useState(false);
  const [tab, setTab] = useState("handover");

  const onboarded = leads.filter(l => l.onboarded);

  const generateHandover = async () => {
    if (!apiOk || !selectedLead) return;
    setLoading(true); setHandover(""); setSop("");
    try {
      await callClaude(apiKey,
        "You write clear, professional client handover documents for WhatsApp bot services. Format for WhatsApp message delivery. No markdown. Use simple numbered steps.",
        `Write a WhatsApp handover message to send to the client after their bot is live.

Client: ${selectedLead.name}, ${selectedLead.biz} (${selectedLead.industry}, ${selectedLead.city})

Include:
1. Congratulations / bot is live message
2. How to test it (keywords to send)
3. What happens when hot lead is detected
4. How to request changes (contact you on WhatsApp)
5. What ₹2,000/month covers
6. Next billing date reminder
7. Upsell mention (brief): "When you're ready, we can add CRM integration and monthly analytics for ₹8,000/month"

Keep it warm, professional, under 250 words. Easy to understand for a non-tech business owner.`,
        (t) => setHandover(t));

      await callClaude(apiKey,
        "Write concise, practical SOPs for non-technical Indian business owners.",
        `Write a 1-page Operations Guide (plain text) for ${selectedLead.biz}'s new WhatsApp bot.

Include:
- What the bot does automatically
- What triggers a notification to the owner
- How to pause the bot if needed
- How to add a new FAQ (contact your service provider)
- Monthly maintenance: what we check each month
- Support contact: [YOUR_WHATSAPP_NUMBER]

Keep extremely simple. Owner has zero technical background.`,
        (t) => setSop(t));
    } catch (e) { setHandover("Error: " + e.message); }
    setLoading(false);
  };

  return (
    <div>
      <div className="grid2">
        <div>
          <div className="card">
            <div className="card-title">Ready for Delivery</div>
            {onboarded.length === 0 && <div style={{ color: "var(--muted)", fontSize: 12 }}>Complete onboarding first to deliver bots.</div>}
            {onboarded.map(l => (
              <div key={l.id}
                style={{ padding: "10px 14px", cursor: "pointer", borderBottom: "1px solid var(--border)", background: selectedLead?.id === l.id ? "rgba(0,230,118,0.05)" : "transparent", borderLeft: selectedLead?.id === l.id ? "2px solid var(--acc)" : "2px solid transparent" }}
                onClick={() => { setSelectedLead(l); setHandover(""); setSop(""); }}>
                <div style={{ fontSize: 12, color: "var(--txt)" }}>{l.name} — {l.biz}</div>
                <div style={{ fontSize: 10, color: "var(--muted)" }}>{l.industry} · {l.city}</div>
                <div style={{ marginTop: 4 }}><StatusBadge lead={l} /></div>
              </div>
            ))}
          </div>

          <div className="card">
            <div className="card-title">Delivery Checklist</div>
            {[
              "Bot flows built in Wati/AiSensy",
              "All 5 intents tested manually",
              "After-hours flow active",
              "Hot lead escalation tested (sends to your number)",
              "Client's number connected to API",
              "Welcome message set as greeting",
              "Loom walkthrough recorded",
              "Razorpay subscription activated",
            ].map((item, i) => (
              <div key={i} style={{ padding: "8px 0", borderBottom: "1px solid var(--border)", fontSize: 11, color: "#888", display: "flex", gap: 10 }}>
                <span style={{ color: "var(--acc)" }}>□</span> {item}
              </div>
            ))}
          </div>
        </div>

        <div>
          {!apiOk && <div className="alert alert-warn">Add Claude API key to generate delivery documents.</div>}
          {!selectedLead && <div className="alert alert-info">← Select an onboarded client to generate delivery package.</div>}

          {selectedLead && (
            <div className="card">
              <div className="card-title">Delivery Package — {selectedLead.biz}</div>
              <button className="btn btn-primary" disabled={!apiOk || loading} onClick={generateHandover} style={{ marginBottom: 16 }}>
                {loading ? <><span className="spinner" /> Generating...</> : "Generate Delivery Package"}
              </button>

              {(handover || sop) && (
                <>
                  <div className="tabs" style={{ marginBottom: 16 }}>
                    <div className={`tab ${tab === "handover" ? "active" : ""}`} onClick={() => setTab("handover")}>WhatsApp Handover</div>
                    <div className={`tab ${tab === "sop" ? "active" : ""}`} onClick={() => setTab("sop")}>Ops Guide (PDF)</div>
                  </div>

                  {tab === "handover" && handover && (
                    <div className="dm-bubble" style={{ maxWidth: "100%" }}>
                      <div className="dm-sender">You → {selectedLead.name} (WhatsApp)</div>
                      {handover}
                    </div>
                  )}

                  {tab === "sop" && sop && (
                    <div className="output-box" style={{ marginTop: 0 }}>
                      <CopyBtn text={sop} />
                      {sop}
                    </div>
                  )}

                  {!selectedLead.delivered && (
                    <button className="btn btn-primary" style={{ marginTop: 16 }} onClick={() => updateLead(selectedLead.id, { delivered: true })}>
                      🚀 Mark as Delivered — ₹2,000 MRR Locked
                    </button>
                  )}
                  {selectedLead.delivered && <div className="alert alert-ok" style={{ marginTop: 16 }}>✓ Delivered. ₹2,000/month recurring locked in.</div>}
                </>
              )}
            </div>
          )}
        </div>
      </div>
    </div>
  );
}

// ─── COPY BUTTON ──────────────────────────────────────────────────────────────
function CopyBtn({ text, inline }) {
  const [copied, setCopied] = useState(false);
  const copy = () => { navigator.clipboard.writeText(text); setCopied(true); setTimeout(() => setCopied(false), 1500); };
  if (inline) return <button className="btn btn-outline btn-sm" onClick={copy} style={{ marginTop: 8 }}>{copied ? "✓ Copied" : "Copy"}</button>;
  return <button className="copy-btn" onClick={copy}>{copied ? "✓ copied" : "copy"}</button>;
}
