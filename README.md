<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<title>TourTrack — Field Sales Workspace</title>
<style>
:root{--blue:#2563eb;--navy:#101828;--muted:#667085;--bg:#f5f7fb;--border:#e5eaf1;--white:#fff;--green:#16a34a;--red:#dc2626}
*{box-sizing:border-box}body{margin:0;font-family:Inter,system-ui,Arial,sans-serif;background:var(--bg);color:var(--navy)}button,input,select{font:inherit}button{cursor:pointer}
#login{min-height:100vh;display:grid;place-items:center;padding:24px;background:linear-gradient(135deg,#eff6ff,#f8fafc)}
.login-card{width:min(420px,100%);background:white;border:1px solid var(--border);border-radius:20px;padding:32px;box-shadow:0 20px 60px #0f172a12}.brand{font-weight:900;font-size:25px;letter-spacing:-1px}.brand span{color:var(--blue)}.login-card h1{font-size:25px;margin:24px 0 5px}.sub{color:var(--muted);font-size:14px}.field{margin-top:16px}.field label{display:block;font-size:13px;font-weight:700;margin-bottom:7px}.field input,.field select{width:100%;padding:11px 12px;border:1px solid #d0d5dd;border-radius:9px}.primary{background:var(--blue);color:white;border:0;padding:11px 16px;border-radius:9px;font-weight:700}.primary:hover{background:#1d4ed8}.wide{width:100%;margin-top:20px}.hint{font-size:12px;color:var(--muted);margin-top:15px}
#app{display:none}.layout{min-height:100vh;display:grid;grid-template-columns:250px 1fr}.sidebar{background:#111827;color:white;padding:24px 16px;display:flex;flex-direction:column;gap:20px}.sidebar .brand span{color:#60a5fa}.side-label{color:#94a3b8;font-size:11px;text-transform:uppercase;letter-spacing:1px;margin:10px 10px 0}.nav{display:flex;flex-direction:column;gap:5px}.nav button{color:#cbd5e1;background:transparent;border:0;text-align:left;padding:12px;border-radius:10px}.nav button.active,.nav button:hover{background:#263449;color:white}.nav button span{display:inline-block;width:28px}.sidebar-bottom{margin-top:auto;color:#94a3b8;font-size:12px}.main{min-width:0}.topbar{height:70px;background:white;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;padding:0 28px}.topbar h2{font-size:18px;margin:0}.user-chip{display:flex;gap:10px;align-items:center;font-size:13px}.avatar{width:36px;height:36px;background:#dbeafe;color:#1d4ed8;border-radius:50%;display:grid;place-items:center;font-weight:800}.content{padding:28px;max-width:1500px;margin:auto}.welcome{display:flex;justify-content:space-between;align-items:flex-start;gap:12px;margin-bottom:22px}.welcome h1{margin:0;font-size:26px}.welcome p{color:var(--muted);margin:6px 0}.cards{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}.card,.panel{background:white;border:1px solid var(--border);border-radius:14px;padding:18px}.metric-label{color:var(--muted);font-size:13px}.metric{font-size:26px;font-weight:800;margin:8px 0}.metric-foot{font-size:12px;color:var(--green)}.dashboard-grid{display:grid;grid-template-columns:1.4fr 1fr;gap:16px;margin-top:18px}.panel h3{margin:0 0 15px;font-size:16px}.table-wrap{overflow:auto}table{border-collapse:collapse;width:100%;min-width:550px}th,td{text-align:left;padding:12px 10px;border-bottom:1px solid var(--border);font-size:13px}th{font-size:11px;color:var(--muted);text-transform:uppercase;letter-spacing:.4px}.status{display:inline-block;padding:4px 9px;border-radius:99px;font-size:11px;background:#dcfce7;color:#166534}.status.pending{background:#fef3c7;color:#92400e}.status.low{background:#fee2e2;color:#991b1b}.activity{display:flex;gap:12px;padding:12px 0;border-bottom:1px solid var(--border);font-size:13px}.activity:last-child{border:none}.dot{width:10px;height:10px;border-radius:50%;background:#60a5fa;margin-top:5px}.toolbar{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:18px}.toolbar input,.toolbar select{padding:10px;border:1px solid #d0d5dd;border-radius:9px;background:white}.toolbar input{flex:1;min-width:160px}.secondary{background:white;border:1px solid var(--border);padding:10px 14px;border-radius:9px;font-weight:600}.section-title{margin:0 0 18px}.empty{padding:35px;text-align:center;color:var(--muted)}.modal-backdrop{position:fixed;inset:0;background:#10182870;display:none;align-items:center;justify-content:center;padding:20px;z-index:10}.modal{background:white;width:min(520px,100%);border-radius:16px;padding:24px;max-height:90vh;overflow:auto}.modal-head{display:flex;justify-content:space-between;align-items:center}.modal-head h3{margin:0}.close{border:0;background:transparent;font-size:24px}.modal .field{margin-top:13px}.modal-actions{display:flex;justify-content:flex-end;gap:10px;margin-top:20px}.toast{position:fixed;bottom:22px;right:22px;background:#166534;color:white;padding:13px 18px;border-radius:10px;display:none;z-index:20;box-shadow:0 10px 30px #0002}.mobile-menu{display:none}
@media(max-width:1000px){.cards{grid-template-columns:repeat(2,1fr)}.dashboard-grid{grid-template-columns:1fr}}
@media(max-width:700px){.layout{grid-template-columns:1fr}.sidebar{display:none}.sidebar.mobile-open{display:flex;position:fixed;z-index:5;top:0;bottom:0;width:250px}.topbar{padding:0 16px}.mobile-menu{display:inline-block;border:0;background:white;font-size:22px;margin-right:12px}.topbar-left{display:flex;align-items:center}.content{padding:18px}.cards{grid-template-columns:1fr 1fr}.welcome{flex-direction:column}.welcome h1{font-size:23px}}
@media(max-width:430px){.cards{grid-template-columns:1fr}.topbar h2{font-size:16px}}
</style>
</head>
<body>
<section id="login">
 <div class="login-card">
  <div class="brand">Tour<span>Track</span></div>
  <h1>Welcome back</h1><p class="sub">Sign in to manage your field sales team.</p>
  <form id="loginForm">
   <div class="field"><label>Email</label><input id="loginEmail" type="email" value="admin@tourtrack.demo" required></div>
   <div class="field"><label>Password</label><input id="loginPassword" type="password" value="demo1234" minlength="4" required></div>
   <button class="primary wide" type="submit">Sign in</button>
  </form>
  <div class="hint">Demo login: admin@tourtrack.demo / demo1234. This prototype uses a simulated login.</div>
 </div>
</section>
<section id="app">
<div class="layout">
 <aside class="sidebar" id="sidebar">
  <div class="brand">Tour<span>Track</span></div>
  <div class="side-label">Workspace</div>
  <nav class="nav" id="nav">
   <button data-view="dashboard" class="active"><span>▦</span>Dashboard</button>
   <button data-view="salesmen"><span>♙</span>Salesmen</button>
   <button data-view="tours"><span>⌖</span>Tour Planner</button>
   <button data-view="stock"><span>▤</span>Stock</button>
   <button data-view="sales"><span>₹</span>Sales</button>
   <button data-view="purchases"><span>⇧</span>Purchases</button>
  </nav>
  <div class="sidebar-bottom">TourTrack Demo Workspace<br>Local prototype • No backend</div>
 </aside>
 <main class="main">
  <header class="topbar"><div class="topbar-left"><button class="mobile-menu" id="mobileMenu">☰</button><h2 id="pageTitle">Dashboard</h2></div><div class="user-chip"><div class="avatar">A</div><div><b>Admin</b><br><span class="sub">Workspace owner</span></div><button class="secondary" id="logout" style="margin-left:8px">Logout</button></div></header>
  <div class="content" id="view"></div>
 </main>
</div>
</section>
<div class="modal-backdrop" id="modalBackdrop"><div class="modal"><div class="modal-head"><h3 id="modalTitle">Add record</h3><button class="close" id="modalClose" aria-label="Close">×</button></div><form id="modalForm"></form></div></div>
<div class="toast" id="toast"></div>
<script>
const state={
 salesmen:[{id:1,name:"Amit Sharma",phone:"9876543210",area:"Varanasi",status:"Active"},{id:2,name:"Neha Singh",phone:"9876543211",area:"Lucknow",status:"Active"},{id:3,name:"Rahul Verma",phone:"9876543212",area:"Jaunpur",status:"Active"}],
 tours:[{id:1,salesman:"Amit Sharma",date:"2026-11-21",customer:"Sharma General Store",area:"Varanasi",status:"Planned"},{id:2,salesman:"Neha Singh",date:"2026-11-21",customer:"City Wholesale",area:"Lucknow",status:"Completed"},{id:3,salesman:"Rahul Verma",date:"2026-11-22",customer:"Gupta Traders",area:"Jaunpur",status:"Planned"}],
 stock:[{id:1,product:"Premium Tea (1kg)",sku:"TT-001",qty:42,price:380},{id:2,product:"Biscuits Pack",sku:"TT-002",qty:12,price:60},{id:3,product:"Cooking Oil (5L)",sku:"TT-003",qty:7,price:720}],
 sales:[{id:1,date:"2026-11-21",customer:"Sharma General Store",salesman:"Amit Sharma",amount:5400},{id:2,date:"2026-11-20",customer:"City Wholesale",salesman:"Neha Singh",amount:8200}],
 purchases:[{id:1,date:"2026-11-20",supplier:"Sunrise Distributors",product:"Premium Tea (1kg)",qty:20,total:7600},{id:2,date:"2026-11-19",supplier:"Metro Supplies",product:"Biscuits Pack",qty:100,total:6000}]
};
const views={dashboard:"Dashboard",salesmen:"Salesmen",tours:"Tour Planner",stock:"Stock",sales:"Sales",purchases:"Purchases"};
let current="dashboard";
const view=document.getElementById("view");
function money(n){return "₹"+Number(n).toLocaleString("en-IN")}
function save(){localStorage.setItem("tourtrackData",JSON.stringify(state))}
function load(){try{let d=JSON.parse(localStorage.getItem("tourtrackData"));if(d)Object.assign(state,d)}catch(e){}}
load();
function showToast(msg){let t=document.getElementById("toast");t.textContent=msg;t.style.display="block";setTimeout(()=>t.style.display="none",2500)}
function table(headers,rows){return `<div class="table-wrap"><table><thead><tr>${headers.map(x=>`<th>${x}</th>`).join("")}</tr></thead><tbody>${rows.length?rows.join(""):`<tr><td colspan="${headers.length}" class="empty">No records yet.</td></tr>`}</tbody></table></div>`}
function dashboard(){let total=state.sales.reduce((a,x)=>a+x.amount,0), visits=state.tours.length, stockItems=state.stock.length;return `<div class="welcome"><div><h1>Good morning, Admin 👋</h1><p>Here's what's happening across your field sales operation.</p></div><button class="primary" onclick="openModal('tour')">+ Plan a Tour</button></div><div class="cards"><div class="card"><div class="metric-label">Recorded sales</div><div class="metric">${money(total)}</div><div class="metric-foot">Across saved transactions</div></div><div class="card"><div class="metric-label">Salesmen</div><div class="metric">${state.salesmen.length}</div><div class="metric-foot">Team members</div></div><div class="card"><div class="metric-label">Tour activities</div><div class="metric">${visits}</div><div class="metric-foot">Planned and completed</div></div><div class="card"><div class="metric-label">Stock products</div><div class="metric">${stockItems}</div><div class="metric-foot">${state.stock.filter(x=>x.qty<10).length} low stock items</div></div></div><div class="dashboard-grid"><div class="panel"><h3>Recent Sales</h3>${table(["Date","Customer","Salesman","Amount"],state.sales.slice().sort((a,b)=>b.date.localeCompare(a.date)).slice(0,5).map(x=>`<tr><td>${x.date}</td><td>${x.customer}</td><td>${x.salesman}</td><td><b>${money(x.amount)}</b></td></tr>`))}</div><div class="panel"><h3>Today's tour activity</h3>${state.tours.filter(x=>x.date==="2026-11-21").map(x=>`<div class="activity"><div class="dot"></div><div><b>${x.customer}</b><br><span class="sub">${x.salesman} • ${x.area}</span><br><span class="status ${x.status==="Planned"?"pending":""}">${x.status}</span></div></div>`).join("")||'<div class="empty">No tours scheduled today.</div>'}</div></div>`}
function listView(key){let data=state[key],headers,rows,add;
if(key==="salesmen"){headers=["Name","Phone","Area","Status",""];rows=data.map(x=>`<tr><td><b>${x.name}</b></td><td>${x.phone}</td><td>${x.area}</td><td><span class="status">${x.status}</span></td><td><button class="secondary" onclick="removeRecord('salesmen',${x.id})">Delete</button></td></tr>`);add="salesman"}
if(key==="tours"){headers=["Date","Salesman","Customer","Area","Status",""];rows=data.map(x=>`<tr><td>${x.date}</td><td>${x.salesman}</td><td><b>${x.customer}</b></td><td>${x.area}</td><td><span class="status ${x.status==="Planned"?"pending":""}">${x.status}</span></td><td><button class="secondary" onclick="toggleTour(${x.id})">${x.status==="Planned"?"Complete":"Reopen"}</button> <button class="secondary" onclick="removeRecord('tours',${x.id})">Delete</button></td></tr>`);add="tour"}
if(key==="stock"){headers=["Product","SKU","Quantity","Unit price","Status",""];rows=data.map(x=>`<tr><td><b>${x.product}</b></td><td>${x.sku}</td><td>${x.qty}</td><td>${money(x.price)}</td><td><span class="status ${x.qty<10?"low":""}">${x.qty<10?"Low stock":"In stock"}</span></td><td><button class="secondary" onclick="removeRecord('stock',${x.id})">Delete</button></td></tr>`);add="stock"}
if(key==="sales"){headers=["Date","Customer","Salesman","Amount",""];rows=data.map(x=>`<tr><td>${x.date}</td><td><b>${x.customer}</b></td><td>${x.salesman}</td><td><b>${money(x.amount)}</b></td><td><button class="secondary" onclick="removeRecord('sales',${x.id})">Delete</button></td></tr>`);add="sale"}
if(key==="purchases"){headers=["Date","Supplier","Product","Quantity","Total",""];rows=data.map(x=>`<tr><td>${x.date}</td><td><b>${x.supplier}</b></td><td>${x.product}</td><td>${x.qty}</td><td>${money(x.total)}</td><td><button class="secondary" onclick="removeRecord('purchases',${x.id})">Delete</button></td></tr>`);add="purchase"}
return `<div class="welcome"><div><h1>${views[key]}</h1><p>Manage and review your ${views[key].toLowerCase()} records.</p></div><button class="primary" onclick="openModal('${add}')">+ Add ${key==="tours"?"Tour":key==="sales"?"Sale":key==="purchases"?"Purchase":key==="stock"?"Product":"Salesman"}</button></div><div class="panel">${table(headers,rows)}</div>`}
function render(){document.getElementById("pageTitle").textContent=views[current];view.innerHTML=current==="dashboard"?dashboard():listView(current);document.querySelectorAll("#nav button").forEach(b=>b.classList.toggle("active",b.dataset.view===current))}
document.getElementById("nav").addEventListener("click",e=>{let b=e.target.closest("button[data-view]");if(!b)return;current=b.dataset.view;render();document.getElementById("sidebar").classList.remove("mobile-open")});
document.getElementById("loginForm").addEventListener("submit",e=>{e.preventDefault();const email=document.getElementById("loginEmail").value.trim().toLowerCase();const password=document.getElementById("loginPassword").value;const btn=e.submitter;try{if(email!=="admin@tourtrack.demo"||password!=="demo1234"){showToast("Incorrect demo email or password");return;}load();current="dashboard";render();document.getElementById("login").style.display="none";document.getElementById("app").style.display="block";}catch(err){console.error("TourTrack sign-in error:",err);showToast("Dashboard error. Refresh the page and try again.");}});
document.getElementById("logout").onclick=()=>{document.getElementById("app").style.display="none";document.getElementById("login").style.display="grid"};
document.getElementById("mobileMenu").onclick=()=>document.getElementById("sidebar").classList.toggle("mobile-open");
document.getElementById("modalClose").onclick=closeModal;document.getElementById("modalBackdrop").onclick=e=>{if(e.target.id==="modalBackdrop")closeModal()};
function closeModal(){document.getElementById("modalBackdrop").style.display="none"}
function removeRecord(key,id){if(confirm("Delete this record?")){state[key]=state[key].filter(x=>x.id!==id);save();render();showToast("Record deleted")}}
function toggleTour(id){let x=state.tours.find(x=>x.id===id);if(x){x.status=x.status==="Planned"?"Completed":"Planned";save();render();showToast("Tour status updated")}}
function openModal(type){let title,fields;
const salesmanOpts=state.salesmen.map(x=>`<option>${x.name}</option>`).join("");
const productOpts=state.stock.map(x=>`<option>${x.product}</option>`).join("");
if(type==="salesman"){title="Add salesman";fields=[["name","Full name","text"],["phone","Phone","tel"],["area","Territory / area","text"]]}
if(type==="tour"){title="Plan a tour";fields=[["date","Date","date"],["salesman","Salesman","select",state.salesmen.map(x=>x.name)],["customer","Customer / retailer","text"],["area","Area","text"]]}
if(type==="stock"){title="Add product";fields=[["product","Product name","text"],["sku","SKU","text"],["qty","Quantity","number"],["price","Unit price (₹)","number"]]}
if(type==="sale"){title="Record sale";fields=[["date","Date","date"],["customer","Customer","text"],["salesman","Salesman","select",state.salesmen.map(x=>x.name)],["amount","Amount (₹)","number"]]}
if(type==="purchase"){title="Record purchase";fields=[["date","Date","date"],["supplier","Supplier","text"],["product","Product","select",state.stock.map(x=>x.product)],["qty","Quantity","number"],["total","Total (₹)","number"]]}
document.getElementById("modalTitle").textContent=title;
let form=document.getElementById("modalForm");
form.innerHTML=fields.map(f=>{let control;if(f[2]==="select"){control='<select name="'+f[0]+'" required><option value="">Choose…</option>'+f[3].map(v=>'<option>'+v+'</option>').join('')+'</select>';}else{control='<input name="'+f[0]+'" type="'+f[2]+'" '+(f[2]==="number"?'min="0"':'')+' required>';}return '<div class="field"><label>'+f[1]+'</label>'+control+'</div>';}).join('')+'<div class="modal-actions"><button type="button" class="secondary" onclick="closeModal()">Cancel</button><button class="primary" type="submit">Save</button></div>';
form.onsubmit=e=>{e.preventDefault();let fd=new FormData(form),o=Object.fromEntries(fd.entries());o.id=Date.now();
if(type==="salesman"){o.status="Active";state.salesmen.push(o)}
if(type==="tour"){o.status="Planned";state.tours.push(o)}
if(type==="stock"){o.qty=Number(o.qty);o.price=Number(o.price);state.stock.push(o)}
if(type==="sale"){o.amount=Number(o.amount);state.sales.push(o)}
if(type==="purchase"){o.qty=Number(o.qty);o.total=Number(o.total);state.purchases.push(o);let p=state.stock.find(x=>x.product===o.product);if(p)p.qty+=o.qty}
save();closeModal();render();showToast(title.replace("Add ","").replace("Record ","").replace("Plan ","")+" saved successfully")};
document.getElementById("modalBackdrop").style.display="flex"}
</script>
</body>
</html>
