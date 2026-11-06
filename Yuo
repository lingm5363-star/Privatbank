<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Trusted Bank</title>

<style>
:root {
  --bg:#eef2f4;
  --surface:#fff;
  --ink:#14272e;
  --muted:#5d727a;
  --line:#d5dee2;
  --accent:#075c65;
  --green:#16794a;
  --red:#b3392f;
}

* { box-sizing:border-box; }

body {
  margin:0;
  background:var(--bg);
  color:var(--ink);
  font:16px/1.5 Arial,sans-serif;
}

[hidden] { display:none !important; }

.banner {
  background:#fff3c4;
  color:#5a4300;
  text-align:center;
  padding:9px;
  font-size:13px;
  font-weight:bold;
}

.wrap {
  max-width:760px;
  margin:auto;
  padding:24px 16px;
}

.center {
  min-height:90vh;
  display:grid;
  place-items:center;
  padding:16px;
}

.card {
  width:100%;
  max-width:400px;
  background:var(--surface);
  border:1px solid var(--line);
  border-radius:12px;
  padding:26px;
}

h1 { margin:0 0 8px; }

.sub { color:var(--muted); }

label {
  display:block;
  margin:12px 0 5px;
  font-weight:bold;
  font-size:14px;
}

input,select {
  width:100%;
  padding:12px;
  border:1px solid var(--line);
  border-radius:6px;
  font-size:16px;
}

button {
  cursor:pointer;
  padding:11px 16px;
  border:0;
  border-radius:6px;
  background:var(--accent);
  color:white;
  font-weight:bold;
  font-size:15px;
}

button[type=submit] {
  width:100%;
  margin-top:18px;
}

.tabs {
  display:flex;
  gap:8px;
  margin:20px 0;
}

.tabs button {
  flex:1;
}

.tabs .on {
  background:#123b43;
}

.error {
  color:var(--red);
  font-size:13px;
}

header {
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  flex-wrap:wrap;
  margin-bottom:20px;
}

.balance {
  background:var(--accent);
  color:white;
  padding:25px;
  border-radius:12px;
  margin-bottom:20px;
}

.balance .num {
  display:block;
  font-size:32px;
  font-weight:bold;
}

section {
  background:white;
  border:1px solid var(--line);
  border-radius:10px;
  padding:18px;
  margin-bottom:20px;
}

dl {
  display:grid;
  grid-template-columns:max-content 1fr;
  gap:8px 15px;
}

dt { color:var(--muted); }
dd { margin:0; overflow-wrap:anywhere; }

.scroll { overflow-x:auto; }

table {
  width:100%;
  border-collapse:collapse;
  min-width:400px;
}

th,td {
  text-align:left;
  padding:11px 8px;
  border-bottom:1px solid var(--line);
}

th:last-child,td:last-child {
  text-align:right;
}

.in { color:var(--green); }
.out { color:var(--red); }

.row {
  display:grid;
  grid-template-columns:2fr 1fr 1fr auto;
  gap:10px;
  align-items:end;
}

.row label { margin-top:0; }

@media(max-width:560px) {
  .row { grid-template-columns:1fr 1fr; }
  .row button { grid-column:span 2; }
}
</style>
</head>

<body>

<div class="banner">
TRUSTED BANK SIMULATOR — INDEPENDENT PRACTICE PLATFORM.
ALL BALANCES ARE VIRTUAL AND HAVE NO CASH VALUE.
</div>

<main class="center" id="authView">

<div class="card">

<h1>TRUSTED BANK</h1>

<p class="sub">
Welcome to Trusted Bank Simulator.
Create an account or sign in.
</p>

<div class="tabs">
<button id="tabUp" class="on" type="button">
Register
</button>

<button id="tabIn" type="button">
Login
</button>
</div>

<form id="signupForm">

<label>Full Name</label>
<input id="sName" required maxlength="60">

<label>Email Address</label>
<input id="sEmail" type="email" required>

<label>Username</label>
<input id="sUser" required minlength="3"
maxlength="24" pattern="[A-Za-z0-9_]+">

<label>Password</label>
<input id="sPass" type="password"
required minlength="8">

<label>Confirm Password</label>
<input id="sPass2" type="password"
required minlength="8">

<p class="error" id="sErr"></p>

<button type="submit">Create Account</button>

</form>

<form id="loginForm" hidden>

<label>Username</label>
<input id="lUser" required>

<label>Password</label>
<input id="lPass" type="password" required>

<p class="error" id="lErr"></p>

<button type="submit">Login to Account</button>

</form>

</div>
</main>


<div class="wrap" id="dashView" hidden>

<header>
<h1>Trusted Bank</h1>
<button id="logout" type="button">Logout</button>
</header>

<div class="balance">

<small>VIRTUAL ACCOUNT BALANCE</small>

<span class="num" id="balance"></span>

<small>Simulator funds — not withdrawable</small>

</div>


<section>

<h2>Account Information</h2>

<dl>

<dt>Account Holder</dt>
<dd id="dName"></dd>

<dt>Email</dt>
<dd id="dEmail"></dd>

<dt>Username</dt>
<dd id="dUser"></dd>

<dt>Account Type</dt>
<dd>Virtual Checking</dd>

<dt>Account Number</dt>
<dd id="dAcct"></dd>

<dt>Date Opened</dt>
<dd id="dOpen"></dd>

</dl>

</section>


<section>

<h2>Transaction History</h2>

<div class="scroll">

<table>

<thead>
<tr>
<th>Date</th>
<th>Description</th>
<th>Amount</th>
</tr>
</thead>

<tbody id="tx"></tbody>

</table>

</div>

</section>


<section>

<h2>Add Virtual Transaction</h2>

<form id="txForm" class="row">

<div>
<label>Description</label>
<input id="desc" required maxlength="60">
</div>

<div>
<label>Amount</label>
<input id="amount" type="number"
step="0.01" min="0.01" required>
</div>

<div>
<label>Type</label>
<select id="type">
<option value="out">Money Out</option>
<option value="in">Money In</option>
</select>
</div>

<button type="submit">Add</button>

</form>

</section>

</div>


<script>

const START_BALANCE = 5000000;

const $ = id => document.getElementById(id);

const money = n =>
"$" + Math.abs(n).toLocaleString("en-US", {
minimumFractionDigits:2,
maximumFractionDigits:2
});

function load(key,fallback) {
try {
const v = localStorage.getItem(key);
return v ? JSON.parse(v) : fallback;
} catch(e) {
return fallback;
}
}

function save(key,value) {
try {
localStorage.setItem(key,JSON.stringify(value));
} catch(e) {}
}

async function hash(pass,salt) {
const data = new TextEncoder().encode(salt+":"+pass);
const buf = await crypto.subtle.digest("SHA-256",data);

return Array.from(new Uint8Array(buf))
.map(b=>b.toString(16).padStart(2,"0"))
.join("");
}

function randomHex(bytes) {
return Array.from(
crypto.getRandomValues(new Uint8Array(bytes))
).map(b=>b.toString(16).padStart(2,"0")).join("");
}

function fakeAccountNumber() {
let s="";
crypto.getRandomValues(new Uint8Array(10))
.forEach(b=>s+=(b%10));

return "SIM-"+s;
}

let users = load("trusted_sim_users",{});
let current = null;


/* SWITCH FORMS */

function tab(up) {
$("signupForm").hidden=!up;
$("loginForm").hidden=up;

$("tabUp").classList.toggle("on",up);
$("tabIn").classList.toggle("on",!up);
}

$("tabUp").onclick=()=>tab(true);
$("tabIn").onclick=()=>tab(false);


/* REGISTER ACCOUNT */

$("signupForm").addEventListener("submit",async e=>{

e.preventDefault();

const err=$("sErr");
err.textContent="";

const username=$("sUser").value.trim().toLowerCase();

if($("sPass").value!==$("sPass2").value) {
err.textContent="Passwords do not match.";
return;
}

if(users[username]) {
err.textContent="Username already exists.";
return;
}

try {

const salt=randomHex(16);

users[username]={
name:$("sName").value.trim(),
email:$("sEmail").value.trim(),
username,
salt,
hash:await hash($("sPass").value,salt),
account:fakeAccountNumber(),
opened:new Date().toISOString().slice(0,10),

transactions:[{
date:new Date().toISOString().slice(0,10),
desc:"Virtual Welcome Balance",
amt:START_BALANCE
}]

};

save("trusted_sim_users",users);

e.target.reset();

show(username);

} catch(ex) {

err.textContent="Unable to create account. Use HTTPS.";

}

});


/* LOGIN */

$("loginForm").addEventListener("submit",async e=>{

e.preventDefault();

const username=$("lUser").value.trim().toLowerCase();
const u=users[username];

if(u && await hash($("lPass").value,u.salt)===u.hash) {

$("lPass").value="";
show(username);

} else {

$("lErr").textContent="Incorrect username or password.";

}

});


/* DASHBOARD */

function show(username) {

current=username;

try {
sessionStorage.setItem("trusted_current",username);
} catch(e) {}

const u=users[username];

$("who").textContent=u.name;
$("dName").textContent=u.name;
$("dEmail").textContent=u.email;
$("dUser").textContent=u.username;
$("dAcct").textContent=u.account;
$("dOpen").textContent=u.opened;

$("authView").hidden=true;
$("dashView").hidden=false;

render();

}


/* DISPLAY TRANSACTIONS */

function render() {

const u=users[current];
const body=$("tx");

body.textContent="";

u.transactions.slice(0,20).forEach(t=>{

const tr=document.createElement("tr");

const date=document.createElement("td");
date.textContent=t.date;

const desc=document.createElement("td");
desc.textContent=t.desc;

const amount=document.createElement("td");

amount.className=t.amt<0?"out":"in";

amount.textContent=(t.amt>0?"+":"-")+money(t.amt);

tr.append(date,desc,amount);

body.appendChild(tr);

});

const total=u.transactions.reduce(
(s,t)=>s+t.amt,0
);

$("balance").textContent=money(total);

}


/* ADD VIRTUAL TRANSACTION */

$("txForm").addEventListener("submit",e=>{

e.preventDefault();

const amount=parseFloat($("amount").value);

if(!(amount>0)) return;

const isIn=$("type").value==="in";

users[current].transactions.unshift({

date:new Date().toISOString().slice(0,10),

desc:$("desc").value.trim(),

amt:isIn?amount:-amount

});

save("trusted_sim_users",users);

e.target.reset();

render();

});


/* LOGOUT */

$("logout").onclick=()=>{

current=null;

try {
sessionStorage.removeItem("trusted_current");
} catch(e) {}

$("dashView").hidden=true;
$("authView").hidden=false;

};


/* RESTORE SESSION */

(function init(){

let c=null;

try {
c=sessionStorage.getItem("trusted_current");
} catch(e) {}

if(c && users[c]) show(c);

})();

</script>

</body>
</html>
