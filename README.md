<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sekolah Star She — Hitam & Kuning</title>
  <img src="https://uploads.onecompiler.io/43vzhtmas/43xrddk5q/Gedung-Sekolah-3.jpg" alt="Sekolah" width="485">

  <style>
    :root{
      --bg:#0b0b0b; /* nearly black */
      --accent:#ffd400; /* yellow */
      --muted:#222;
      --card:#0f0f0f;
      --glass: rgba(255,255,255,0.03);
      --text:#f6f6f6;
      --shadow: 0 8px 24px rgba(0,0,0,0.6);
      font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,var(--bg) 0%, #050505 100%);color:var(--text)}
    a{color:var(--accent);text-decoration:none}

    /* Layout */
    .container{max-width:1100px;margin:28px auto;padding:24px}
    header{display:flex;align-items:center;justify-content:space-between;gap:16px}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:54px;height:54px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#ffc84d);display:flex;align-items:center;justify-content:center;color:#111;font-weight:700;box-shadow:var(--shadow)}
    nav{display:flex;gap:12px;align-items:center}
    .navlink{padding:8px 14px;border-radius:8px;color:var(--text)}
    .navlink:hover{background:var(--glass)}
    .hero{display:flex;gap:24px;align-items:center;margin-top:22px}

    /* left column */
    .left{flex:1}
    .card{background:linear-gradient(180deg,var(--card),#0b0b0b);border-radius:14px;padding:18px;box-shadow:var(--shadow);}
    .actions{display:flex;gap:10px;margin-top:12px}
    .btn{background:var(--accent);border:none;color:#111;padding:10px 14px;border-radius:10px;font-weight:600;cursor:pointer}
    .btn.ghost{background:transparent;border:1px solid rgba(255,212,0,0.12);color:var(--text)}

    /* right column */
    .right{width:320px}
    .profile-card{display:flex;gap:12px;align-items:center}
    .avatar{width:72px;height:72px;border-radius:12px;background:linear-gradient(180deg,#ffea7a,#ffd400);display:flex;align-items:center;justify-content:center;font-weight:800;color:#111}

    /* sections */
    section.content{margin-top:18px}
    h1,h2,h3{margin:0}
    h1{font-size:26px}
    .subtitle{color:#ddd;margin-top:6px}

    /* kejuruan grid */
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:12px;margin-top:14px}
    .prog{padding:14px;border-radius:12px;background:linear-gradient(180deg,rgba(255,212,0,0.06),rgba(255,212,0,0.03));border:1px solid rgba(255,212,0,0.06)}
    .prog h3{color:var(--accent);margin-bottom:8px}

    /* table */
    table{width:100%;border-collapse:collapse;margin-top:12px}
    th,td{padding:10px;border-bottom:1px solid rgba(255,255,255,0.03);text-align:left}
    th{color:var(--accent)}

    footer{margin-top:28px;color:#999;font-size:13px;text-align:center}

    /* responsive */
    @media (max-width:820px){
      .hero{flex-direction:column}
      .right{width:100%}
    }

    /* small animations */
    .appear{animation:fadeIn .6s ease both}
    @keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}

    /* simple modal for login */
    .modal{position:fixed;inset:0;display:flex;align-items:center;justify-content:center;background:rgba(0,0,0,0.6);backdrop-filter:blur(4px);opacity:0;pointer-events:none;transition:all .18s}
    .modal.active{opacity:1;pointer-events:auto}
    .modal-box{width:360px;background:#0d0d0d;padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.03)}
    .form-row{display:flex;flex-direction:column;gap:6px;margin-top:8px}
    input{background:#080808;border:1px solid rgba(255,255,255,0.03);padding:10px;border-radius:8px;color:var(--text)}

    .small{font-size:13px;color:#bbb}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">ST</div>
        <div>
          <div style="font-weight:700">Sekolah Star She</div>
          <div class="small">Laman resmi</div>
        </div>
      </div>
      <nav>
        <a class="navlink" href="#home" data-link>Home</a>
        <a class="navlink" href="#profile" data-link>Profile</a>
        <a class="navlink" href="#kejuruan" data-link>Kejuruan</a>
        <button class="btn" id="openLogin">Login</button>
      </nav>
    </header>

    <main class="hero">
      <div class="left">
        <div class="card appear" id="home">
          <h1>Selamat datang di Sekolah Star She</h1>
          <div class="subtitle">Website sederhana: profil sekolah, kejuruan, dan data siswa.</div>

          <div class="actions">
            <button class="btn" onclick="scrollToSection('#profile')">Lihat Profile</button>
            <button class="btn ghost" onclick="scrollToSection('#kejuruan')">Program Kejuruan</button>
          </div>

          <section class="content" aria-labelledby="data-siswa">
            <h2 id="data-siswa" style="margin-top:14px">Data Siswa </h2>
            <table>
              <thead>
                <tr><th>No</th><th>Nama</th><th>Kelas</th><th>Program</th></tr>
              </thead>
              <tbody id="siswaTable">
                <tr><td>1</td><td>Alya Lennisa</td><td>X RPL 1</td><td>Rekayasa Perangkat Lunak</td></tr>
                <tr><td>2</td><td>Risyah Indrinia</td><td>XI TKJ</td><td>Teknik Komputer Jaringan</td></tr>
                <tr><td>3</td><td>Dewi ernita</td><td>XII MM</td><td>Multimedia</td></tr>
                 <tr><td>4</td><td>Evita Virnissa</td><td>XII AN</td><td>Akuntansi</td></tr>
              </tbody>
            </table>

          </section>
        </div>

        <div class="card appear" id="profile" style="margin-top:14px">
          <h2>Profile Sekolah</h2>
          <p class="small">Alamat: Jl. Melati No. 10   Kota Asik. Telepon: (+62) 824-8532-3207</p>
          <p style="margin-top:10px">Sekolah kami fokus pada pembelajaran praktis dengan suasana kreatif. Visi: "Menjadi sekolah unggul berbasis keterampilan".</p>
        </div>

        <div class="card appear" id="kejuruan" style="margin-top:14px">
          <h2>Program Kejuruan</h2>
          <div class="grid" id="programGrid">
            <div class="prog">
              <h3>Rekayasa Perangkat Lunak</h3>
              <p class="small">Belajar pemrograman, basis data, dan pengembangan aplikasi.</p>
            </div>
            <div class="prog">
              <h3>Teknik Komputer & Jaringan</h3>
              <p class="small">Jaringan, konfigurasi server, dan troubleshooting.</p>
            </div>
            <div class="prog">
              <h3>Multimedia</h3>
              <p class="small">Desain grafis, editing video, animasi.</p>
            </div>
            <div class="prog">
              <h3>Akuntansi</h3>
              <p class="small">Pembukuan, laporan keuangan, penggunaan software akuntansi.</p>
            </div>
          </div>
        </div>

      </div>

      <aside class="right">
        <div class="card appear profile-card">
          <div class="avatar">ST</div>
          <div>
            <div style="font-weight:700">Kepala Sekolah</div>
            <div class="small"> Lidya Star.S.T</div>
            <div style="margin-top:8px">
              <button class="btn" onclick="alert('Kontak: (+62) 824-8532-3207')">Hubungi</button>
            </div>
          </div>
        </div>

        <div class="card appear" style="margin-top:12px">
          <h3>Info Singkat</h3>
          <p class="small">Penerimaan murid baru dibuka setiap tahun ajaran.Sekolah kami hanya menerima murid perempuan.</p>
        </div>

        <div class="card appear" style="margin-top:12px">
          <h3>Statistik</h3>
          <p class="small">Siswa: <strong id="statSiswa">4</strong> • Guru: <strong>1</strong></p>
        </div>
      </aside>
    </main>

    <footer>
      © Sekolah StarShe — Dibuat sederhana. 
    </footer>
  </div>

  <!-- Modal Login -->
  <div class="modal" id="loginModal" role="dialog" aria-modal="true">
    <div class="modal-box">
      <h3>Login Sederhana</h3>
      <div class="form-row">
        <label class="small">Username</label>
        <input id="username" placeholder="masukkan username" />
      </div>
      <div class="form-row">
        <label class="small">Password</label>
        <input id="password" type="password" placeholder="" />
      </div>
      <div style="display:flex;gap:8px;margin-top:12px;justify-content:flex-end">
        <button class="btn ghost" onclick="closeModal()">Batal</button>
        <button class="btn" onclick="doLogin()">Masuk</button>
      </div>
    </div>
  </div>

  <script>
    // navigation smooth scroll
    document.querySelectorAll('[data-link]').forEach(a=>{
      a.addEventListener('click', e=>{
        e.preventDefault();
        const id = a.getAttribute('href');
        scrollToSection(id);
      })
    })

    function scrollToSection(selector){
      const el = document.querySelector(selector);
      if(!el) return; el.scrollIntoView({behavior:'smooth',block:'start'});
    }

    // modal login
    const modal = document.getElementById('loginModal');
    document.getElementById('openLogin').addEventListener('click', ()=> modal.classList.add('active'));
    function closeModal(){ modal.classList.remove('active'); }
    function doLogin(){
      const u = document.getElementById('username').value.trim();
      const p = document.getElementById('password').value.trim();
      if(u==='admin'&&p==='admin123'){
        alert('Login berhasil — Anda masuk sebagai admin (mode demo).');
        closeModal();
      } else {
        alert('Login gagal — username: admin / password: admin123 (demo)');
      }
    }

    // small dynamic example: add student row function
    function addStudent(no,nama,kelas,prog){
      const tbody = document.getElementById('siswaTable');
      const tr = document.createElement('tr');
      tr.innerHTML = <td>${no}</td><td>${nama}</td><td>${kelas}</td><td>${prog}</td>;
      tbody.appendChild(tr);
      document.getElementById('statSiswa').textContent = parseInt(document.getElementById('statSiswa').textContent||0)+1;
    }

    // demo: add a new student after 2s (just to show dynamism)
    setTimeout(()=> addStudent(4,'Iqbal Hanif','XII RPL', 'Rekayasa Perangkat Lunak'),2000);
  </script>
</body>
</html>
