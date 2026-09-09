<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Dua Orang</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Inter', sans-serif;
            background: #f8f6f4;
            color: #1e1e1e;
            scroll-behavior: smooth;
            line-height: 1.6;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* NAVBAR */
        nav {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(248, 246, 244, 0.92);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(0,0,0,0.04);
            padding: 14px 0;
        }
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        .logo {
            font-weight: 700;
            font-size: 1.4rem;
            letter-spacing: -0.5px;
            color: #1e1e1e;
        }
        .logo span { color: #a0847a; }
        .nav-links {
            display: flex;
            gap: 28px;
            list-style: none;
            flex-wrap: wrap;
        }
        .nav-links a {
            text-decoration: none;
            color: #2c2c2c;
            font-weight: 500;
            font-size: 0.95rem;
            transition: 0.2s;
            position: relative;
        }
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: #a0847a;
            transition: 0.25s;
        }
        .nav-links a:hover::after,
        .nav-links a.active::after { width: 100%; }
        .nav-links a.active { color: #a0847a; }
        .hamburger {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            background: none;
            border: none;
            color: #2c2c2c;
        }
        @media (max-width: 820px) {
            .nav-links {
                display: none;
                flex-direction: column;
                width: 100%;
                gap: 12px;
                padding: 16px 0 8px;
                border-top: 1px solid #e8e0da;
                margin-top: 10px;
            }
            .nav-links.open { display: flex; }
            .hamburger { display: block; }
        }

        /* SECTIONS */
        section {
            padding: 80px 0;
            animation: fadeUp 0.8s ease both;
        }
        .section-title {
            font-size: 2rem;
            font-weight: 600;
            letter-spacing: -0.5px;
            margin-bottom: 8px;
            color: #1e1e1e;
        }
        .section-sub {
            color: #7a6a62;
            font-weight: 400;
            margin-bottom: 40px;
            border-left: 3px solid #d4c5bc;
            padding-left: 18px;
        }
        @keyframes fadeUp {
            0% { opacity: 0; transform: translateY(24px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        /* HERO */
        .hero {
            min-height: 80vh;
            display: flex;
            align-items: center;
        }
        .hero-content {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            gap: 50px;
            text-align: center;
        }
        .hero-text h1 {
            font-size: 2.8rem;
            font-weight: 700;
            letter-spacing: -1px;
        }
        .hero-text h1 span { color: #a0847a; }
        .hero-text .subhead {
            font-size: 1.1rem;
            color: #7a6a62;
            font-weight: 400;
            margin: 6px 0 20px;
        }
        .hero-text p {
            max-width: 560px;
            margin: 0 auto 28px;
            color: #3d3d3d;
            font-weight: 300;
        }
        .btn-group {
            display: flex;
            gap: 16px;
            justify-content: center;
            flex-wrap: wrap;
        }
        .btn {
            display: inline-block;
            padding: 12px 32px;
            border-radius: 40px;
            text-decoration: none;
            font-weight: 500;
            transition: 0.25s;
            background: #1e1e1e;
            color: #fff;
            border: 1px solid #1e1e1e;
        }
        .btn-outline {
            background: transparent;
            color: #1e1e1e;
            border: 1px solid #cbc1b8;
        }
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.06);
            background: #2c2c2c;
            color: #fff;
        }
        .btn-outline:hover {
            background: #1e1e1e;
            color: #fff;
            border-color: #1e1e1e;
        }

        .hero-profiles {
            display: flex;
            gap: 40px;
            flex-wrap: wrap;
            justify-content: center;
        }
        .hero-profile-item {
            text-align: center;
        }
        .hero-profile-item .frame {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            overflow: hidden;
            background: #e8e0da;
            margin: 0 auto 10px;
            box-shadow: 0 12px 28px rgba(0,0,0,0.04);
        }
        .hero-profile-item .frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .hero-profile-item .name {
            font-weight: 600;
            font-size: 1.1rem;
        }

        /* TENTANG KAMI (2 card) */
        .profile-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 32px;
        }
        @media (max-width: 700px) {
            .profile-grid { grid-template-columns: 1fr; }
        }
        .profile-card {
            background: #fffdfc;
            border-radius: 24px;
            padding: 30px 24px;
            box-shadow: 0 4px 16px rgba(0,0,0,0.02);
            border: 1px solid #ede7e2;
            transition: 0.2s;
        }
        .profile-card:hover {
            box-shadow: 0 12px 32px rgba(0,0,0,0.04);
            transform: translateY(-4px);
        }
        .profile-card .avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            overflow: hidden;
            background: #ddd2ca;
            margin-bottom: 16px;
        }
        .profile-card .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .profile-card h3 {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 2px;
        }
        .profile-card .bio-item {
            display: flex;
            align-items: baseline;
            gap: 10px;
            font-size: 0.95rem;
            margin: 6px 0;
            color: #3d3d3d;
        }
        .profile-card .bio-item i {
            width: 20px;
            color: #a0847a;
        }
        .profile-card .desc {
            margin-top: 16px;
            padding-top: 16px;
            border-top: 1px solid #ede7e2;
            color: #4a4a4a;
            font-weight: 300;
        }

        /* CV TABS */
        .cv-tabs {
            display: flex;
            gap: 12px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        .cv-tab {
            padding: 8px 24px;
            border-radius: 40px;
            background: #ede7e2;
            border: none;
            font-weight: 500;
            cursor: pointer;
            transition: 0.2s;
            font-family: 'Inter', sans-serif;
        }
        .cv-tab.active {
            background: #1e1e1e;
            color: #fff;
        }
        .cv-tab:hover:not(.active) { background: #d4c5bc; }
        .cv-panel { display: none; }
        .cv-panel.active { display: block; }

        .cv-section {
            background: #fffdfc;
            border-radius: 28px;
            padding: 32px 28px;
            border: 1px solid #ede7e2;
        }
        .cv-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 28px 40px;
        }
        @media (max-width: 700px) { .cv-grid { grid-template-columns: 1fr; } }
        .cv-block h4 {
            font-weight: 600;
            font-size: 1.1rem;
            margin-bottom: 16px;
            border-bottom: 2px solid #ede7e2;
            padding-bottom: 6px;
        }
        .cv-item { margin-bottom: 20px; }
        .cv-item .year { font-weight: 600; color: #a0847a; font-size: 0.9rem; }
        .cv-item .title { font-weight: 600; margin: 2px 0 2px; }
        .cv-item .desc { font-weight: 300; color: #4a4a4a; font-size: 0.95rem; }
        .btn-download {
            margin-top: 28px;
            background: #1e1e1e;
            color: #fff;
            border: none;
            padding: 12px 36px;
            border-radius: 40px;
            font-weight: 500;
            cursor: pointer;
            transition: 0.25s;
            font-family: 'Inter', sans-serif;
        }
        .btn-download:hover {
            background: #2c2c2c;
            transform: translateY(-2px);
        }

        /* KARYA & ARTIKEL FILTER */
        .filter-group {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }
        .filter-btn {
            padding: 6px 20px;
            border-radius: 40px;
            background: #ede7e2;
            border: none;
            font-weight: 500;
            cursor: pointer;
            transition: 0.2s;
            font-family: 'Inter', sans-serif;
        }
        .filter-btn.active {
            background: #1e1e1e;
            color: #fff;
        }
        .filter-btn:hover:not(.active) { background: #d4c5bc; }

        .work-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 28px;
        }
        .work-card, .article-card {
            background: #fffdfc;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid #ede7e2;
            transition: 0.25s;
        }
        .work-card:hover, .article-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 16px 32px rgba(0,0,0,0.04);
        }
        .work-card img, .article-card img {
            width: 100%;
            height: 160px;
            object-fit: cover;
            background: #ddd2ca;
        }
        .work-card .info, .article-card .content {
            padding: 16px 18px 20px;
        }
        .work-card .info h4, .article-card .content h4 {
            font-weight: 600;
            font-size: 1.05rem;
        }
        .work-card .info .cat {
            font-size: 0.8rem;
            color: #a0847a;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 0.3px;
        }
        .work-card .info p, .article-card .content p {
            font-weight: 300;
            font-size: 0.9rem;
            color: #4a4a4a;
            margin: 6px 0 12px;
        }
        .btn-small {
            background: transparent;
            border: 1px solid #cbc1b8;
            padding: 6px 18px;
            border-radius: 30px;
            font-size: 0.8rem;
            font-weight: 500;
            color: #1e1e1e;
            cursor: pointer;
            transition: 0.2s;
            font-family: 'Inter', sans-serif;
        }
        .btn-small:hover {
            background: #1e1e1e;
            color: #fff;
            border-color: #1e1e1e;
        }

        /* GALERI */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            gap: 20px;
        }
        .gallery-item {
            border-radius: 18px;
            overflow: hidden;
            background: #ddd2ca;
            aspect-ratio: 1/1;
            cursor: pointer;
            transition: 0.2s;
        }
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: 0.25s;
        }
        .gallery-item:hover img { transform: scale(1.04); }

        /* MODAL GALERI */
        .modal {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.6);
            backdrop-filter: blur(6px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 2000;
        }
        .modal.open { display: flex; }
        .modal img {
            max-width: 80%;
            max-height: 80%;
            border-radius: 16px;
            box-shadow: 0 24px 48px rgba(0,0,0,0.3);
        }
        .modal .close-modal {
            position: absolute;
            top: 30px;
            right: 40px;
            font-size: 2.4rem;
            color: #fff;
            cursor: pointer;
            background: none;
            border: none;
        }

        /* SOCIAL */
        .social-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
        }
        .social-btn {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 12px 28px;
            border-radius: 60px;
            background: #fffdfc;
            border: 1px solid #ede7e2;
            text-decoration: none;
            color: #1e1e1e;
            font-weight: 500;
            transition: 0.2s;
        }
        .social-btn i {
            font-size: 1.2rem;
            width: 24px;
            color: #a0847a;
        }
        .social-btn:hover {
            background: #1e1e1e;
            color: #fff;
            border-color: #1e1e1e;
            transform: translateY(-3px);
        }
        .social-btn:hover i { color: #fff; }

        /* TESTIMONI */
        .testimoni-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 28px;
        }
        .testimoni-card {
            background: #fffdfc;
            border-radius: 24px;
            padding: 24px 22px;
            border: 1px solid #ede7e2;
            transition: 0.2s;
        }
        .testimoni-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 28px rgba(0,0,0,0.04);
        }
        .testimoni-card .avatar {
            width: 56px;
            height: 56px;
            border-radius: 50%;
            overflow: hidden;
            background: #ddd2ca;
            margin-bottom: 12px;
        }
        .testimoni-card .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .testimoni-card .name { font-weight: 600; }
        .testimoni-card .role { font-size: 0.8rem; color: #a0847a; }
        .testimoni-card .quote {
            margin-top: 12px;
            font-weight: 300;
            color: #3d3d3d;
            font-style: italic;
        }

        /* BACK TO TOP */
        .back-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #1e1e1e;
            color: #fff;
            border: none;
            border-radius: 50%;
            width: 48px;
            height: 48px;
            font-size: 1.3rem;
            cursor: pointer;
            box-shadow: 0 6px 16px rgba(0,0,0,0.08);
            transition: 0.25s;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
        }
        .back-top.visible { opacity: 1; pointer-events: auto; }
        .back-top:hover {
            background: #2c2c2c;
            transform: scale(1.05);
        }

        footer {
            background: #fffdfc;
            border-top: 1px solid #ede7e2;
            padding: 28px 0;
            text-align: center;
            color: #7a6a62;
            font-weight: 300;
            margin-top: 20px;
        }
        .placeholder-img {
            background: #e0d6ce;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #a0847a;
            font-weight: 300;
        }
    </style>
</head>
<body>

<!-- NAVBAR -->
<nav>
    <div class="container nav-container">
        <div class="logo">Portfolio<span>.</span></div>
        <button class="hamburger" id="hamburger" aria-label="Menu"><i class="fas fa-bars"></i></button>
        <ul class="nav-links" id="navLinks">
            <li><a href="#beranda" class="active">Beranda</a></li>
            <li><a href="#tentang">Tentang Kami</a></li>
            <li><a href="#cv">CV</a></li>
            <li><a href="#karya">Hasil Karya</a></li>
            <li><a href="#galeri">Galeri</a></li>
            <li><a href="#artikel">Artikel</a></li>
            <li><a href="#media">Link Media</a></li>
            <li><a href="#testimoni">Testimoni</a></li>
        </ul>
    </div>
</nav>

<!-- BERANDA -->
<section id="beranda" class="hero">
    <div class="container hero-content">
        <div class="hero-text">
            <h1>Halo, SYASYA AMILIA PURNAMA <span>[Orang 1]</span> & <span>[Orang 2]</span></h1>
            <div class="10 BR 2">Two People, Two Stories, One Website</div>
            <p>Selamat datang di portfolio kami. Kami adalah dua orang dengan cerita dan karya masing-masing, namun dalam satu ruang digital.</p>
            <div class="btn-group">
                <a href="#tentang" class="btn">Kenal Kami</a>
                <a href="#karya" class="btn btn-outline">Lihat Hasil Karya</a>
            </div>
        </div>
        <div class="hero-profiles">
            <div class="hero-profile-item">
                <div class="frame"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3Ccircle cx='38' cy='32' r='5' fill='%23f9f7f5'/%3E%3Ccircle cx='62' cy='32' r='5' fill='%23f9f7f5'/%3E%3Cpath d='M35 54 Q50 68 65 54' stroke='%23f9f7f5' stroke-width='4' fill='none' stroke-linecap='round'/%3E%3C/svg%3E" alt="Foto Orang 1"></div>
                <div class="name">[Orang 1]</div>
            </div>
            <div class="hero-profile-item">
                <div class="frame"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3Ccircle cx='38' cy='32' r='5' fill='%23f9f7f5'/%3E%3Ccircle cx='62' cy='32' r='5' fill='%23f9f7f5'/%3E%3Cpath d='M35 54 Q50 68 65 54' stroke='%23f9f7f5' stroke-width='4' fill='none' stroke-linecap='round'/%3E%3C/svg%3E" alt="Foto Orang 2"></div>
                <div class="name">[Orang 2]</div>
            </div>
        </div>
    </div>
</section>

<!-- TENTANG KAMI -->
<section id="tentang">
    <div class="container">
        <h2 class="section-title">Tentang Kami</h2>
        <div class="section-sub">dua profil dalam satu halaman</div>
        <div class="profile-grid">
            <!-- Profil Orang 1 -->
            <div class="profile-card">
                <div class="avatar"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3Ccircle cx='38' cy='32' r='5' fill='%23f9f7f5'/%3E%3Ccircle cx='62' cy='32' r='5' fill='%23f9f7f5'/%3E%3Cpath d='M35 54 Q50 68 65 54' stroke='%23f9f7f5' stroke-width='4' fill='none' stroke-linecap='round'/%3E%3C/svg%3E" alt="avatar"></div>
                <h3>[Nama Lengkap 1]</h3>
                <div class="bio-item"><i class="fas fa-user-tag"></i> Panggilan: [Nama Panggilan 1]</div>
                <div class="bio-item"><i class="fas fa-graduation-cap"></i> Kelas: [Kelas 1]</div>
                <div class="bio-item"><i class="fas fa-calendar-alt"></i> TTL: [Tempat, 1 Jan 2000]</div>
                <div class="bio-item"><i class="fas fa-heart"></i> Hobi: [Hobi 1]</div>
                <div class="bio-item"><i class="fas fa-star"></i> Minat: [Minat 1]</div>
                <div class="bio-item"><i class="fas fa-bullseye"></i> Cita-cita: [Cita-cita 1]</div>
                <div class="desc">Deskripsi singkat tentang [Orang 1]. Saya adalah orang yang [sifat] dan senang [kegiatan].</div>
            </div>
            <!-- Profil Orang 2 -->
            <div class="profile-card">
                <div class="avatar"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3Ccircle cx='38' cy='32' r='5' fill='%23f9f7f5'/%3E%3Ccircle cx='62' cy='32' r='5' fill='%23f9f7f5'/%3E%3Cpath d='M35 54 Q50 68 65 54' stroke='%23f9f7f5' stroke-width='4' fill='none' stroke-linecap='round'/%3E%3C/svg%3E" alt="avatar"></div>
                <h3>[Nama Lengkap 2]</h3>
                <div class="bio-item"><i class="fas fa-user-tag"></i> Panggilan: [Nama Panggilan 2]</div>
                <div class="bio-item"><i class="fas fa-graduation-cap"></i> Kelas: [Kelas 2]</div>
                <div class="bio-item"><i class="fas fa-calendar-alt"></i> TTL: [Tempat, 2 Feb 2000]</div>
                <div class="bio-item"><i class="fas fa-heart"></i> Hobi: [Hobi 2]</div>
                <div class="bio-item"><i class="fas fa-star"></i> Minat: [Minat 2]</div>
                <div class="bio-item"><i class="fas fa-bullseye"></i> Cita-cita: [Cita-cita 2]</div>
                <div class="desc">Deskripsi singkat tentang [Orang 2]. Saya suka [kegiatan] dan selalu bersemangat.</div>
            </div>
        </div>
    </div>
</section>

<!-- CV -->
<section id="cv" style="background: #f8f6f4;">
    <div class="container">
        <h2 class="section-title">CV</h2>
        <div class="section-sub">riwayat & keahlian</div>
        <div class="cv-tabs">
            <button class="cv-tab active" data-cv="cv1">CV Orang 1</button>
            <button class="cv-tab" data-cv="cv2">CV Orang 2</button>
        </div>
        <!-- CV Orang 1 -->
        <div class="cv-panel active" id="cv1">
            <div class="cv-section">
                <div class="cv-grid">
                    <div class="cv-block"><h4>Pendidikan</h4><div class="cv-item"><span class="year">2020-2024</span><div class="title">SMA [Nama]</div><div class="desc">Jurusan [IPA/IPS]</div></div></div>
                    <div class="cv-block"><h4>Pengalaman & Organisasi</h4><div class="cv-item"><span class="year">2023</span><div class="title">Staff [Org 1]</div><div class="desc">Bertanggung jawab atas [tugas]</div></div></div>
                    <div class="cv-block"><h4>Keahlian</h4><div class="cv-item"><div class="title">• [Keahlian 1]</div><div class="desc">Tingkat menengah</div></div></div>
                    <div class="cv-block"><h4>Prestasi & Sertifikat</h4><div class="cv-item"><div class="title">🏆 [Prestasi 1]</div><div class="desc">Tahun 2023</div></div></div>
                </div>
                <button class="btn-download"><i class="fas fa-download"></i> Download CV Orang 1</button>
            </div>
        </div>
        <!-- CV Orang 2 -->
        <div class="cv-panel" id="cv2">
            <div class="cv-section">
                <div class="cv-grid">
                    <div class="cv-block"><h4>Pendidikan</h4><div class="cv-item"><span class="year">2020-2024</span><div class="title">SMA [Nama]</div><div class="desc">Jurusan [IPA/IPS]</div></div></div>
                    <div class="cv-block"><h4>Pengalaman & Organisasi</h4><div class="cv-item"><span class="year">2023</span><div class="title">Staff [Org 2]</div><div class="desc">Bertanggung jawab atas [tugas]</div></div></div>
                    <div class="cv-block"><h4>Keahlian</h4><div class="cv-item"><div class="title">• [Keahlian 2]</div><div class="desc">Tingkat menengah</div></div></div>
                    <div class="cv-block"><h4>Prestasi & Sertifikat</h4><div class="cv-item"><div class="title">🏆 [Prestasi 2]</div><div class="desc">Tahun 2023</div></div></div>
                </div>
                <button class="btn-download"><i class="fas fa-download"></i> Download CV Orang 2</button>
            </div>
        </div>
    </div>
</section>

<!-- HASIL KARYA -->
<section id="karya">
    <div class="container">
        <h2 class="section-title">Hasil Karya</h2>
        <div class="section-sub">portfolio karya kami</div>
        <div class="filter-group">
            <button class="filter-btn active" data-filter="all">Semua</button>
            <button class="filter-btn" data-filter="orang1">Karya Orang 1</button>
            <button class="filter-btn" data-filter="orang2">Karya Orang 2</button>
        </div>
        <div class="work-grid" id="workGrid">
            <div class="work-card" data-owner="orang1"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='160' viewBox='0 0 300 160'%3E%3Crect width='300' height='160' fill='%23ddd2ca'/%3E%3Ctext x='30' y='80' fill='%23997b6e' font-family='Inter' font-size='16'%3EKarya 1%3C/text%3E%3C/svg%3E" alt="karya"><div class="info"><span class="cat">Kategori A</span><h4>[Nama Karya 1]</h4><p>Deskripsi singkat karya.</p><button class="btn-small">Lihat Detail</button></div></div>
            <div class="work-card" data-owner="orang2"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='160' viewBox='0 0 300 160'%3E%3Crect width='300' height='160' fill='%23ddd2ca'/%3E%3Ctext x='30' y='80' fill='%23997b6e' font-family='Inter' font-size='16'%3EKarya 2%3C/text%3E%3C/svg%3E" alt="karya"><div class="info"><span class="cat">Kategori B</span><h4>[Nama Karya 2]</h4><p>Deskripsi singkat karya.</p><button class="btn-small">Lihat Detail</button></div></div>
            <div class="work-card" data-owner="orang1"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='160' viewBox='0 0 300 160'%3E%3Crect width='300' height='160' fill='%23ddd2ca'/%3E%3Ctext x='30' y='80' fill='%23997b6e' font-family='Inter' font-size='16'%3EKarya 3%3C/text%3E%3C/svg%3E" alt="karya"><div class="info"><span class="cat">Kategori C</span><h4>[Nama Karya 3]</h4><p>Deskripsi singkat karya.</p><button class="btn-small">Lihat Detail</button></div></div>
        </div>
    </div>
</section>

<!-- GALERI -->
<section id="galeri" style="background: #f8f6f4;">
    <div class="container">
        <h2 class="section-title">Galeri</h2>
        <div class="section-sub">momen dan kenangan</div>
        <div class="filter-group">
            <button class="filter-btn active" data-filter="all">Semua</button>
            <button class="filter-btn" data-filter="foto1">Foto Orang 1</button>
            <button class="filter-btn" data-filter="foto2">Foto Orang 2</button>
            <button class="filter-btn" data-filter="bersama">Foto Bersama</button>
        </div>
        <div class="gallery-grid" id="galleryGrid">
            <div class="gallery-item" data-category="foto1"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200' viewBox='0 0 200 200'%3E%3Crect width='200' height='200' fill='%23ddd2ca'/%3E%3Ctext x='30' y='100' fill='%23997b6e' font-family='Inter' font-size='16'%3E1%3C/text%3E%3C/svg%3E" alt="foto 1"></div>
            <div class="gallery-item" data-category="foto2"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200' viewBox='0 0 200 200'%3E%3Crect width='200' height='200' fill='%23ddd2ca'/%3E%3Ctext x='30' y='100' fill='%23997b6e' font-family='Inter' font-size='16'%3E2%3C/text%3E%3C/svg%3E" alt="foto 2"></div>
            <div class="gallery-item" data-category="bersama"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200' viewBox='0 0 200 200'%3E%3Crect width='200' height='200' fill='%23ddd2ca'/%3E%3Ctext x='30' y='100' fill='%23997b6e' font-family='Inter' font-size='16'%3E3%3C/text%3E%3C/svg%3E" alt="foto 3"></div>
        </div>
    </div>
</section>

<!-- MODAL GALERI -->
<div class="modal" id="galleryModal">
    <button class="close-modal" id="closeModal">&times;</button>
    <img id="modalImage" src="" alt="preview">
</div>

<!-- ARTIKEL -->
<section id="artikel">
    <div class="container">
        <h2 class="section-title">Artikel</h2>
        <div class="section-sub">tulisan dari kami</div>
        <div class="filter-group">
            <button class="filter-btn active" data-filter="all">Semua</button>
            <button class="filter-btn" data-filter="artikel1">Artikel Orang 1</button>
            <button class="filter-btn" data-filter="artikel2">Artikel Orang 2</button>
        </div>
        <div class="work-grid" id="articleGrid">
            <div class="article-card" data-owner="artikel1"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='160' viewBox='0 0 300 160'%3E%3Crect width='300' height='160' fill='%23ddd2ca'/%3E%3Ctext x='30' y='80' fill='%23997b6e' font-family='Inter' font-size='16'%3EArtikel 1%3C/text%3E%3C/svg%3E" alt="artikel"><div class="content"><span class="meta">[Kategori] · [Tanggal]</span><h4>[Judul Artikel 1]</h4><p>Ringkasan artikel singkat.</p><button class="btn-small">Baca Selengkapnya</button></div></div>
            <div class="article-card" data-owner="artikel2"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='160' viewBox='0 0 300 160'%3E%3Crect width='300' height='160' fill='%23ddd2ca'/%3E%3Ctext x='30' y='80' fill='%23997b6e' font-family='Inter' font-size='16'%3EArtikel 2%3C/text%3E%3C/svg%3E" alt="artikel"><div class="content"><span class="meta">[Kategori] · [Tanggal]</span><h4>[Judul Artikel 2]</h4><p>Ringkasan artikel singkat.</p><button class="btn-small">Baca Selengkapnya</button></div></div>
        </div>
    </div>
</section>

<!-- LINK MEDIA -->
<section id="media" style="background: #f8f6f4;">
    <div class="container">
        <h2 class="section-title">Link Media</h2>
        <div class="section-sub">temukan kami di sosial media</div>
        <div style="display:grid; grid-template-columns: 1fr 1fr; gap: 32px; margin-bottom: 20px;">
            <div><h4 style="margin-bottom:12px;">Orang 1</h4><div class="social-grid">
                <a href="#" class="social-btn"><i class="fab fa-instagram"></i> [Link IG 1]</a>
                <a href="#" class="social-btn"><i class="fab fa-tiktok"></i> [Link TikTok 1]</a>
                <a href="#" class="social-btn"><i class="fab fa-youtube"></i> [Link YT 1]</a>
                <a href="#" class="social-btn"><i class="fab fa-whatsapp"></i> [WA 1]</a>
                <a href="#" class="social-btn"><i class="fas fa-envelope"></i> [Email 1]</a>
                <a href="#" class="social-btn"><i class="fab fa-linkedin"></i> [LinkedIn 1]</a>
            </div></div>
            <div><h4 style="margin-bottom:12px;">Orang 2</h4><div class="social-grid">
                <a href="#" class="social-btn"><i class="fab fa-instagram"></i> [Link IG 2]</a>
                <a href="#" class="social-btn"><i class="fab fa-tiktok"></i> [Link TikTok 2]</a>
                <a href="#" class="social-btn"><i class="fab fa-youtube"></i> [Link YT 2]</a>
                <a href="#" class="social-btn"><i class="fab fa-whatsapp"></i> [WA 2]</a>
                <a href="#" class="social-btn"><i class="fas fa-envelope"></i> [Email 2]</a>
                <a href="#" class="social-btn"><i class="fab fa-linkedin"></i> [LinkedIn 2]</a>
            </div></div>
        </div>
    </div>
</section>

<!-- TESTIMONI -->
<section id="testimoni">
    <div class="container">
        <h2 class="section-title">Testimoni</h2>
        <div class="section-sub">pendapat tentang kami</div>
        <div class="filter-group">
            <button class="filter-btn active" data-filter="all">Semua</button>
            <button class="filter-btn" data-filter="testi1">Testimoni Orang 1</button>
            <button class="filter-btn" data-filter="testi2">Testimoni Orang 2</button>
            <button class="filter-btn" data-filter="testi-bersama">Testimoni Bersama</button>
        </div>
        <div class="testimoni-grid" id="testimoniGrid">
            <div class="testimoni-card" data-category="testi1"><div class="avatar"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='56' height='56' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3C/svg%3E" alt=""></div><div class="name">[Nama 1]</div><div class="role">[Keterangan]</div><div class="quote">"Testimoni untuk Orang 1."</div></div>
            <div class="testimoni-card" data-category="testi2"><div class="avatar"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='56' height='56' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3C/svg%3E" alt=""></div><div class="name">[Nama 2]</div><div class="role">[Keterangan]</div><div class="quote">"Testimoni untuk Orang 2."</div></div>
            <div class="testimoni-card" data-category="testi-bersama"><div class="avatar"><img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='56' height='56' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%23d4c5bc'/%3E%3Ccircle cx='50' cy='38' r='20' fill='%23b8a89c'/%3E%3C/svg%3E" alt=""></div><div class="name">[Nama 3]</div><div class="role">[Keterangan]</div><div class="quote">"Testimoni untuk bersama."</div></div>
        </div>
    </div>
</section>

<!-- FOOTER -->
<footer>
    <div class="container">
        <p style="margin-bottom:6px;">© 2026 · Portfolio Dua Orang</p>
        <p style="font-size:0.9rem;">Dibuat dengan <i class="fas fa-heart" style="color:#a0847a;"></i></p>
    </div>
</footer>

<!-- BACK TO TOP -->
<button class="back-top" id="backTop"><i class="fas fa-arrow-up"></i></button>

<script>
    // HAMBURGER
    document.getElementById('hamburger').addEventListener('click', function() {
        document.getElementById('navLinks').classList.toggle('open');
    });

    // ACTIVE NAV
    const navLinks = document.querySelectorAll('.nav-links a');
    const sections = document.querySelectorAll('section[id]');
    function setActive() {
        let current = '';
        sections.forEach(s => {
            const top = s.offsetTop - 140;
            if (window.scrollY >= top) current = s.getAttribute('id');
        });
        navLinks.forEach(link => {
            link.classList.remove('active');
            if (link.getAttribute('href') === '#' + current) link.classList.add('active');
        });
    }
    window.addEventListener('scroll', setActive);
    window.addEventListener('load', setActive);

    // SMOOTH SCROLL NAV
    navLinks.forEach(link => {
        link.addEventListener('click', function(e) {
            e.preventDefault();
            const target = document.getElementById(this.getAttribute('href').substring(1));
            if (target) target.scrollIntoView({ behavior: 'smooth' });
        });
    });

    // CV TABS
    document.querySelectorAll('.cv-tab').forEach(tab => {
        tab.addEventListener('click', function() {
            document.querySelectorAll('.cv-tab').forEach(t => t.classList.remove('active'));
            this.classList.add('active');
            document.querySelectorAll('.cv-panel').forEach(p => p.classList.remove('active'));
            document.getElementById(this.dataset.cv).classList.add('active');
        });
    });

    // FILTER FUNGSI
    function filterGrid(containerId, filterAttr, filterClass) {
        const container = document.getElementById(containerId);
        const items = container.querySelectorAll('.work-card, .article-card, .gallery-item, .testimoni-card');
        const btns = container.parentElement.querySelectorAll('.filter-btn');
        btns.forEach(btn => {
            btn.addEventListener('click', function() {
                btns.forEach(b => b.classList.remove('active'));
                this.classList.add('active');
                const val = this.dataset.filter;
                items.forEach(item => {
                    const owner = item.dataset.owner || item.dataset.category || '';
                    if (val === 'all' || owner === val) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });
    }

    filterGrid('workGrid', 'data-owner', 'filter-btn');
    filterGrid('galleryGrid', 'data-category', 'filter-btn');
    filterGrid('articleGrid', 'data-owner', 'filter-btn');
    filterGrid('testimoniGrid', 'data-category', 'filter-btn');

    // GALERI MODAL
    const modal = document.getElementById('galleryModal');
    const modalImg = document.getElementById('modalImage');
    document.querySelectorAll('.gallery-item img').forEach(img => {
        img.addEventListener('click', function() {
            modalImg.src = this.src;
            modal.classList.add('open');
        });
    });
    document.getElementById('closeModal').addEventListener('click', () => modal.classList.remove('open'));
    modal.addEventListener('click', (e) => { if (e.target === modal) modal.classList.remove('open'); });

    // BACK TO TOP
    const backBtn = document.getElementById('backTop');
    window.addEventListener('scroll', () => {
        if (window.scrollY > 400) backBtn.classList.add('visible');
        else backBtn.classList.remove('visible');
    });
    backBtn.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));
</script>
</body>
</html>
