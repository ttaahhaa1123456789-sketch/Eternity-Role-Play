<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💎 Eternity | پیشرفته‌ترین سرور سمپ</title>
    <!-- فونت فارسی -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
    <!-- AOS Animation -->
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Vazirmatn', sans-serif;
            background: #0a0c0f;
            color: #fff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* کاستوم اسکرول بار */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #1a1e24;
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(180deg, #fbbf24, #dc2626);
            border-radius: 5px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(180deg, #f59e0b, #b91c1c);
        }

        /* انیمیشن پس‌زمینه */
        .cyber-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(251, 191, 36, 0.05) 0%, transparent 50%),
                        radial-gradient(circle at 80% 80%, rgba(220, 38, 38, 0.05) 0%, transparent 50%),
                        repeating-linear-gradient(45deg, rgba(255,255,255,0.01) 0px, rgba(255,255,255,0.01) 2px, transparent 2px, transparent 8px);
            z-index: -1;
            pointer-events: none;
        }

        /* ناوبری اصلی */
        .navbar {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 1300px;
            background: rgba(10, 15, 25, 0.8);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(251, 191, 36, 0.2);
            border-radius: 100px;
            padding: 0.8rem 1.5rem;
            z-index: 1000;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4), 0 0 20px rgba(251, 191, 36, 0.2);
            transition: all 0.3s;
        }

        .navbar.scrolled {
            background: rgba(5, 8, 15, 0.95);
            border-color: #fbbf24;
            box-shadow: 0 10px 30px rgba(251, 191, 36, 0.3);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* همبرگر منو در سمت چپ */
        .hamburger-menu {
            cursor: pointer;
            z-index: 1001;
        }

        .hamburger-icon {
            width: 30px;
            height: 20px;
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .hamburger-icon span {
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #fbbf24, #ef4444);
            border-radius: 3px;
            transition: all 0.3s;
        }

        .hamburger-icon.active span:nth-child(1) {
            transform: rotate(45deg) translate(5px, 5px);
        }

        .hamburger-icon.active span:nth-child(2) {
            opacity: 0;
        }

        .hamburger-icon.active span:nth-child(3) {
            transform: rotate(-45deg) translate(7px, -6px);
        }

        /* لوگو در وسط */
        .logo {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-icon {
            font-size: 2.2rem;
            filter: drop-shadow(0 0 15px #fbbf24);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .logo-text {
            font-size: 1.6rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fbbf24, #ef4444, #fbbf24);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 3s ease infinite;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* آیپی لوزی شکل در سمت راست */
        .ip-diamond {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #fbbf24, #dc2626);
            transform: rotate(45deg);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: 0.3s;
            box-shadow: 0 0 30px rgba(251, 191, 36, 0.5);
            position: relative;
        }

        .ip-diamond:hover {
            transform: rotate(45deg) scale(1.1);
            box-shadow: 0 0 50px #fbbf24;
        }

        .ip-diamond i {
            transform: rotate(-45deg);
            font-size: 1.8rem;
            color: #0a0c0f;
        }

        .ip-diamond .copy-notification {
            position: absolute;
            top: -40px;
            right: 50%;
            transform: translateX(50%);
            background: #fbbf24;
            color: #0a0c0f;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            white-space: nowrap;
            opacity: 0;
            transition: 0.3s;
            pointer-events: none;
        }

        .ip-diamond:hover .copy-notification {
            opacity: 1;
            top: -50px;
        }

        /* منوی موبایل */
        .mobile-menu {
            position: fixed;
            top: 0;
            right: -100%;
            width: 300px;
            height: 100vh;
            background: rgba(10, 15, 25, 0.95);
            backdrop-filter: blur(20px);
            border-left: 2px solid #fbbf24;
            z-index: 999;
            transition: 0.5s;
            padding: 100px 30px 30px;
            box-shadow: -10px 0 30px rgba(0,0,0,0.5);
        }

        .mobile-menu.active {
            right: 0;
        }

        .mobile-menu ul {
            list-style: none;
        }

        .mobile-menu li {
            margin-bottom: 20px;
        }

        .mobile-menu a {
            color: #fff;
            text-decoration: none;
            font-size: 1.2rem;
            font-weight: 600;
            display: block;
            padding: 10px;
            border-radius: 10px;
            transition: 0.3s;
        }

        .mobile-menu a:hover,
        .mobile-menu a.active {
            background: linear-gradient(135deg, #fbbf24, #dc2626);
            color: #0a0c0f;
            padding-right: 20px;
        }

        .menu-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            z-index: 998;
            opacity: 0;
            visibility: hidden;
            transition: 0.3s;
        }

        .menu-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        /* محتوای اصلی */
        .main {
            margin-top: 120px;
        }

        /* بخش‌ها */
        section {
            padding: 80px 5%;
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-subtitle {
            color: #fbbf24;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            margin-bottom: 10px;
        }

        .section-title {
            font-size: 3rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fff, #fbbf24);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 20px;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #fbbf24, #ef4444, #fbbf24);
            margin: 20px auto 0;
            border-radius: 2px;
        }

        /* بخش خانه */
        .hero {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 50px;
            min-height: 80vh;
        }

        .hero-content {
            flex: 1;
        }

        .hero-badge {
            display: inline-block;
            background: rgba(251, 191, 36, 0.2);
            border: 1px solid #fbbf24;
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            font-size: 0.9rem;
            margin-bottom: 20px;
            backdrop-filter: blur(5px);
        }

        .hero-title {
            font-size: 4.5rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .hero-title span {
            background: linear-gradient(135deg, #fbbf24, #ef4444);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
            animation: glow 3s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 20px #fbbf24); }
            50% { filter: drop-shadow(0 0 40px #ef4444); }
        }

        .hero-desc {
            font-size: 1.2rem;
            color: #a0a0a0;
            margin-bottom: 40px;
            max-width: 600px;
        }

        /* فقط تعداد پلیر در وسط */
        .hero-stats {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
        }

        .stat-item {
            text-align: center;
        }

        .stat-value {
            font-size: 3.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fbbf24, #fff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            font-size: 1.2rem;
            color: #fbbf24;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #fbbf24, #dc2626);
            border: none;
            color: #0a0c0f;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 10px 20px rgba(220, 38, 38, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(251, 191, 36, 0.4);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid #fbbf24;
            color: #fff;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn-outline:hover {
            background: #fbbf24;
            color: #0a0c0f;
            box-shadow: 0 0 30px #fbbf24;
        }

        .hero-image {
            flex: 1;
            position: relative;
        }

        .hero-image img {
            width: 100%;
            animation: float 6s ease-in-out infinite;
            filter: drop-shadow(0 0 50px rgba(251, 191, 36, 0.3));
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* گالری تصاویر */
        .gallery-section {
            background: linear-gradient(135deg, rgba(10, 15, 25, 0.9), rgba(20, 10, 20, 0.9));
            border-radius: 30px;
            padding: 40px;
            border: 1px solid rgba(251, 191, 36, 0.2);
            backdrop-filter: blur(10px);
            margin: 40px auto;
        }

        .gallery-container {
            position: relative;
            width: 100%;
            max-width: 1000px;
            margin: 0 auto;
            overflow: hidden;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.5);
        }

        .gallery-slider {
            display: flex;
            transition: transform 0.5s ease;
        }

        .gallery-slide {
            min-width: 100%;
            position: relative;
        }

        .gallery-slide img {
            width: 100%;
            height: 500px;
            object-fit: cover;
            display: block;
        }

        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.8));
            color: #fff;
            padding: 30px 20px 20px;
            text-align: center;
            font-size: 1.2rem;
            font-weight: 600;
        }

        .gallery-caption span {
            color: #fbbf24;
            font-size: 1rem;
            display: block;
            margin-top: 5px;
        }

        .gallery-dots {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 20px;
        }

        .gallery-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255,255,255,0.3);
            cursor: pointer;
            transition: 0.3s;
        }

        .gallery-dot.active {
            background: #fbbf24;
            transform: scale(1.2);
            box-shadow: 0 0 10px #fbbf24;
        }

        .gallery-nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 50px;
            height: 50px;
            background: rgba(251, 191, 36, 0.3);
            border: 1px solid #fbbf24;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: 0.3s;
            z-index: 10;
            backdrop-filter: blur(5px);
        }

        .gallery-nav:hover {
            background: #fbbf24;
            color: #0a0c0f;
        }

        .gallery-nav.prev {
            left: 20px;
        }

        .gallery-nav.next {
            right: 20px;
        }

        .gallery-nav i {
            font-size: 1.5rem;
        }

        /* بخش مدیریت */
        .management-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .management-card {
            background: rgba(20, 25, 40, 0.7);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(251, 191, 36, 0.2);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            transition: 0.3s;
            position: relative;
            overflow: hidden;
        }

        .management-card:hover {
            transform: translateY(-10px);
            border-color: #fbbf24;
            box-shadow: 0 20px 40px rgba(251, 191, 36, 0.3);
        }

        .management-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 50% 0%, rgba(251, 191, 36, 0.2), transparent 70%);
            opacity: 0;
            transition: 0.3s;
        }

        .management-card:hover::before {
            opacity: 1;
        }

        .management-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #fbbf24, #dc2626);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: #0a0c0f;
            margin: 0 auto 20px;
            position: relative;
            z-index: 1;
        }

        .management-role {
            font-size: 1.3rem;
            font-weight: 700;
            color: #fbbf24;
            margin-bottom: 10px;
        }

        .management-name {
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fff, #fbbf24);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
        }

        .management-badge {
            display: inline-block;
            background: rgba(251, 191, 36, 0.2);
            border: 1px solid #fbbf24;
            color: #fbbf24;
            padding: 0.3rem 1.5rem;
            border-radius: 50px;
            font-size: 0.9rem;
        }

        .double-scripters {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 15px;
        }

        .scripter-item {
            background: rgba(255,255,255,0.05);
            border-radius: 10px;
            padding: 10px;
            flex: 1;
        }

        .scripter-name {
            font-size: 1.2rem;
            font-weight: 700;
            color: #fbbf24;
        }

        .scripter-title {
            font-size: 0.8rem;
            color: #a0a0a0;
        }

        /* بخش درباره سرور (بیشتر بدانید) */
        .about-server {
            background: linear-gradient(135deg, rgba(10, 15, 25, 0.9), rgba(20, 10, 20, 0.9));
            border-radius: 30px;
            padding: 50px;
            border: 1px solid rgba(251, 191, 36, 0.2);
            backdrop-filter: blur(10px);
            margin: 40px auto;
        }

        /* انیمیشن شناور برای دایره عکس */
        @keyframes floatImage {
            0%, 100% { transform: translateY(0) scale(1); }
            50% { transform: translateY(-8px) scale(1.02); }
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .about-card {
            background: rgba(20, 25, 40, 0.5);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(251, 191, 36, 0.1);
            transition: 0.3s;
        }

        .about-card:hover {
            border-color: #fbbf24;
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(251, 191, 36, 0.2);
        }

        .about-card i {
            font-size: 2.5rem;
            color: #fbbf24;
            margin-bottom: 20px;
        }

        .about-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #fbbf24;
        }

        .about-card p {
            color: #a0a0a0;
            line-height: 1.8;
        }

        .about-stats {
            display: flex;
            justify-content: space-around;
            margin-top: 40px;
            padding-top: 40px;
            border-top: 1px solid rgba(251, 191, 36, 0.2);
        }

        .about-stat {
            text-align: center;
        }

        .about-stat .number {
            font-size: 2.5rem;
            font-weight: 900;
            color: #fbbf24;
        }

        .about-stat .label {
            color: #a0a0a0;
            font-size: 1rem;
        }

        /* فوتر */
        footer {
            background: rgba(5, 8, 15, 0.95);
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(251, 191, 36, 0.2);
            padding: 60px 5% 30px;
            margin-top: 80px;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .footer-col h4 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            color: #fbbf24;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #a0a0a0;
            text-decoration: none;
            transition: 0.3s;
        }

        .footer-links a:hover {
            color: #fbbf24;
            padding-right: 10px;
        }

        /* آیپی فوتر به صورت رنک */
        .footer-ip-card {
            background: rgba(20, 25, 40, 0.7);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(251, 191, 36, 0.2);
            border-radius: 20px;
            padding: 20px;
            text-align: center;
            transition: 0.3s;
            cursor: pointer;
            margin-bottom: 30px;
        }

        .footer-ip-card:hover {
            border-color: #fbbf24;
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(251, 191, 36, 0.2);
        }

        .footer-ip-card i {
            font-size: 2rem;
            color: #fbbf24;
            margin-bottom: 10px;
        }

        .footer-ip-text {
            font-family: 'Courier New', monospace;
            font-size: 1.3rem;
            font-weight: 700;
            color: #fbbf24;
            direction: ltr;
            margin: 10px 0;
        }

        .footer-ip-label {
            color: #a0a0a0;
            font-size: 0.9rem;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 40px;
            margin-top: 40px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #a0a0a0;
        }

        /* دکمه بازگشت به بالا */
        .go-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #fbbf24, #dc2626);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #0a0c0f;
            font-size: 1.5rem;
            cursor: pointer;
            transition: 0.3s;
            border: none;
            z-index: 999;
            opacity: 0;
            visibility: hidden;
        }

        .go-top.show {
            opacity: 1;
            visibility: visible;
        }

        .go-top:hover {
            transform: scale(1.1) translateY(-5px);
            box-shadow: 0 10px 30px #fbbf24;
        }

        /* ریسپانسیو */
        @media (max-width: 968px) {
            .navbar {
                width: 95%;
                border-radius: 20px;
            }
            
            .nav-container {
                flex-direction: row;
                gap: 15px;
            }
            
            .hero {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-buttons {
                justify-content: center;
            }
            
            .section-title {
                font-size: 2.5rem;
            }
            
            .logo-text {
                font-size: 1.2rem;
            }
            
            .gallery-slide img {
                height: 300px;
            }
            
            .about-stats {
                flex-direction: column;
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="cyber-bg"></div>

    <!-- ناوبری -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <!-- همبرگر منو در سمت چپ -->
            <div class="hamburger-menu" onclick="toggleMenu()">
                <div class="hamburger-icon" id="hamburgerIcon">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>

            <!-- لوگو در وسط -->
            <div class="logo">
                <i class="fas fa-crown logo-icon"></i>
                <span class="logo-text">ETERNITY</span>
            </div>

            <!-- آیپی لوزی شکل در سمت راست با کپی خودکار -->
            <div class="ip-diamond" onclick="copyIP()">
                <i class="fas fa-copy"></i>
                <span class="copy-notification">کپی آیپی</span>
            </div>
        </div>
    </nav>

    <!-- منوی موبایل (با آیتم قوانین اضافه شده) -->
    <div class="mobile-menu" id="mobileMenu">
        <ul>
            <li><a href="#home" onclick="toggleMenu()">خانه</a></li>
            <li><a href="#gallery" onclick="toggleMenu()">گالری</a></li>
            <li><a href="#features" onclick="toggleMenu()">ویژگی‌ها</a></li>
            <li><a href="#about" onclick="toggleMenu()">درباره سرور</a></li>
            <li><a href="#management" onclick="toggleMenu()">مدیریت</a></li>
            <!-- آیتم قوانین با لینک خارجی -->
            <li><a href="https://ttaahhaa1123456789-sketch.github.io/Gvanin-Eternity-/" target="_blank" onclick="toggleMenu()">📜 قوانین</a></li>
        </ul>
    </div>
    <div class="menu-overlay" id="menuOverlay" onclick="toggleMenu()"></div>

    <!-- محتوای اصلی -->
    <main class="main">
        <!-- خانه -->
        <section id="home">
            <div class="hero">
                <div class="hero-content" data-aos="fade-left">
                    <span class="hero-badge"><i class="fas fa-bolt"></i> برترین سرور سمپ 2025</span>
                    <h1 class="hero-title">
                        تجربه <span>جدید</span><br>
                        در Eternity
                    </h1>
                    <p class="hero-desc">به پیشرفته‌ترین سرور سمپ خوش آمدید. با بیش از 50 بازیکن فعال، ایونت‌های روزانه و مدیریت حرفه‌ای</p>
                    
                    <!-- فقط تعداد پلیر -->
                    <div class="hero-stats">
                        <div class="stat-item">
                            <span class="stat-value">۵۰+</span>
                            <span class="stat-label">بازیکن آنلاین</span>
                        </div>
                    </div>

                    <div class="hero-buttons">
                        <button class="btn-primary" onclick="copyIP()"><i class="fas fa-play"></i> هم‌اکنون وارد شو</button>
                        <button class="btn-outline" onclick="document.getElementById('about').scrollIntoView({behavior: 'smooth'})"><i class="fas fa-info-circle"></i> بیشتر بدانید</button>
                    </div>
                </div>
                <div class="hero-image" data-aos="fade-right">
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 200'%3E%3Cpath d='M100 0 L200 100 L100 200 L0 100 Z' fill='%23fbbf24' opacity='0.1'/%3E%3Ccircle cx='100' cy='100' r='80' fill='none' stroke='%23fbbf24' stroke-width='2' stroke-dasharray='10 10'/%3E%3C/svg%3E" alt="hero">
                </div>
            </div>
        </section>

        <!-- گالری تصاویر -->
        <section id="gallery">
            <div class="section-header" data-aos="fade-up">
                <div class="section-subtitle">تصاویر سرور</div>
                <h2 class="section-title">گالری Eternity</h2>
            </div>

            <div class="gallery-section" data-aos="fade-up">
                <div class="gallery-container">
                    <div class="gallery-slider" id="gallerySlider">
                        <!-- اسلاید 1 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/1a1e2a/fbbf24?text=Eternity+Server+1" alt="گالری 1">
                            <div class="gallery-caption">
                                نقشه اختصاصی لاس ونتوراس
                                <span>جدیدترین مپ 2025</span>
                            </div>
                        </div>
                        <!-- اسلاید 2 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/2a1e1a/fbbf24?text=Eternity+Server+2" alt="گالری 2">
                            <div class="gallery-caption">
                                ایونت شبانه ۵۰ نفره
                                <span>مسابقات جایزه دار</span>
                            </div>
                        </div>
                        <!-- اسلاید 3 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/1e2a1a/fbbf24?text=Eternity+Server+3" alt="گالری 3">
                            <div class="gallery-caption">
                                ساختمان دولت مرکزی
                                <span>سرور نقش بازی</span>
                            </div>
                        </div>
                        <!-- اسلاید 4 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/2a1a2a/fbbf24?text=Eternity+Server+4" alt="گالری 4">
                            <div class="gallery-caption">
                                کلن وار هفتگی
                                <span>جنگ کلن ها</span>
                            </div>
                        </div>
                        <!-- اسلاید 5 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/1a2a2a/fbbf24?text=Eternity+Server+5" alt="گالری 5">
                            <div class="gallery-caption">
                                ماشین های اختصاصی
                                <span>بیش از ۱۰۰ مدل</span>
                            </div>
                        </div>
                        <!-- اسلاید 6 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/2a2a1a/fbbf24?text=Eternity+Server+6" alt="گالری 6">
                            <div class="gallery-caption">
                                جزیره تفریحی
                                <span>منطقه ویژه VIP</span>
                            </div>
                        </div>
                        <!-- اسلاید 7 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/1a1a2a/fbbf24?text=Eternity+Server+7" alt="گالری 7">
                            <div class="gallery-caption">
                                سیستم مشاغل
                                <span>۱۵ شغل مختلف</span>
                            </div>
                        </div>
                        <!-- اسلاید 8 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/2a1a1a/fbbf24?text=Eternity+Server+8" alt="گالری 8">
                            <div class="gallery-caption">
                                کازینو و قمارخانه
                                <span>برنده جایزه میلیونی</span>
                            </div>
                        </div>
                        <!-- اسلاید 9 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/1a2a1a/fbbf24?text=Eternity+Server+9" alt="گالری 9">
                            <div class="gallery-caption">
                                فرودگاه بین المللی
                                <span>نقشه اختصاصی</span>
                            </div>
                        </div>
                        <!-- اسلاید 10 -->
                        <div class="gallery-slide">
                            <img src="https://via.placeholder.com/1000x500/2a2a2a/fbbf24?text=Eternity+Server+10" alt="گالری 10">
                            <div class="gallery-caption">
                                شب نشینی بازیکنان
                                <span>کامیونیتی فعال</span>
                            </div>
                        </div>
                    </div>
                    
                    <!-- دکمه‌های ناوبری -->
                    <div class="gallery-nav prev" onclick="prevSlide()">
                        <i class="fas fa-chevron-right"></i>
                    </div>
                    <div class="gallery-nav next" onclick="nextSlide()">
                        <i class="fas fa-chevron-left"></i>
                    </div>
                </div>
                
                <!-- دکمه‌های پایین اسلایدر -->
                <div class="gallery-dots" id="galleryDots">
                    <!-- با جاوااسکریپت ساخته می‌شود -->
                </div>
            </div>
        </section>

        <!-- ویژگی‌ها -->
        <section id="features">
            <div class="section-header" data-aos="fade-up">
                <div class="section-subtitle">چرا ما؟</div>
                <h2 class="section-title">ویژگی‌های منحصر به فرد</h2>
            </div>

            <div class="features-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;">
                <div class="feature-card" data-aos="flip-right" data-aos-delay="100">
                    <i class="fas fa-rocket" style="font-size: 3rem; color: #fbbf24; margin-bottom: 20px;"></i>
                    <h3>سرعت فوق‌العاده</h3>
                    <p>بهترین سخت‌افزار با پهنای باند ۱۰ گیگابایت برای تجربه بازی بدون لگ و تاخیر</p>
                </div>

                <div class="feature-card" data-aos="flip-right" data-aos-delay="200">
                    <i class="fas fa-shield-halved" style="font-size: 3rem; color: #fbbf24; margin-bottom: 20px;"></i>
                    <h3>آنتی‌چیت پیشرفته</h3>
                    <p>سیستم هوشمند تشخیص تقلب با دقت ۹۹.۹٪ و بن دائمی متقلبان</p>
                </div>

                <div class="feature-card" data-aos="flip-right" data-aos-delay="300">
                    <i class="fas fa-map" style="font-size: 3rem; color: #fbbf24; margin-bottom: 20px;"></i>
                    <h3>۲۰۰+ مپ اختصاصی</h3>
                    <p>تعداد بیشمار مپ جدید و انحصاری با آپدیت‌های هفتگی</p>
                </div>

                <div class="feature-card" data-aos="flip-right" data-aos-delay="400">
                    <i class="fas fa-gift" style="font-size: 3rem; color: #fbbf24; margin-bottom: 20px;"></i>
                    <h3>جایزه‌های میلیونی</h3>
                    <p>مسابقات روزانه با جوایز نقدی و آیتم‌های کمیاب</p>
                </div>

                <div class="feature-card" data-aos="flip-right" data-aos-delay="500">
                    <i class="fas fa-headset" style="font-size: 3rem; color: #fbbf24; margin-bottom: 20px;"></i>
                    <h3>پشتیبانی ۲۴/۷</h3>
                    <p>تیم پشتیبانی حرفه‌ای آماده پاسخگویی در تمام ساعات شبانه‌روز</p>
                </div>

                <div class="feature-card" data-aos="flip-right" data-aos-delay="600">
                    <i class="fas fa-robot" style="font-size: 3rem; color: #fbbf24; margin-bottom: 20px;"></i>
                    <h3>سیستم‌های هوشمند</h3>
                    <p>پیشرفته‌ترین سیستم‌های مینی‌گیم، مشاغل و کلن‌ها</p>
                </div>
            </div>
        </section>

        <!-- درباره سرور (بیشتر بدانید) -->
        <section id="about">
            <div class="section-header" data-aos="fade-up">
                <div class="section-subtitle">درباره سرور Eternity</div>
                <h2 class="section-title">بیشتر بدانید</h2>
            </div>

            <div class="about-server" data-aos="fade-up">
                <!-- دایره عکس اضافه شده -->
                <div style="
                    width: 120px;
                    height: 120px;
                    border-radius: 50%;
                    overflow: hidden;
                    border: 4px solid #fbbf24;
                    box-shadow: 0 0 30px rgba(251, 191, 36, 0.6);
                    margin: 0 auto 40px auto;
                    transition: transform 0.4s ease, box-shadow 0.4s ease;
                    cursor: pointer;
                    animation: floatImage 4s ease-in-out infinite;">
                    <img src="https://uploadkon.ir/uploads/46d126_26file-00000000853471fdb1b85cd2d888a071.png" alt="نماد سرور Eternity" style="width: 100%; height: 100%; object-fit: cover; display: block;">
                </div>

                <div class="about-grid">
                    <div class="about-card" data-aos="fade-up" data-aos-delay="100">
                        <i class="fas fa-history"></i>
                        <h3>تاریخچه سرور</h3>
                        <p>سرور Eternity از سال ۱۴۰۲ فعالیت خود را آغاز کرده و با تلاش تیم مدیریتی به یکی از پیشرفته‌ترین سرورهای سمپ تبدیل شده است.</p>
                    </div>
                    <div class="about-card" data-aos="fade-up" data-aos-delay="200">
                        <i class="fas fa-trophy"></i>
                        <h3>افتخارات</h3>
                        <p>برترین سرور نقش‌بازی سال ۱۴۰۳ - بهترین کامیونیتی فعال - بیش از ۱۰۰۰ عضو فعال در دیسکورد</p>
                    </div>
                    <div class="about-card" data-aos="fade-up" data-aos-delay="300">
                        <i class="fas fa-users"></i>
                        <h3>کامیونیتی</h3>
                        <p>با بیش از ۵۰ بازیکن آنلاین در ساعات پیک و ۲۰۰۰+ عضو در شبکه‌های اجتماعی</p>
                    </div>
                    <div class="about-card" data-aos="fade-up" data-aos-delay="400">
                        <i class="fas fa-code"></i>
                        <h3>توسعه و نوآوری</h3>
                        <p>تیم برنامه‌نویسی حرفه‌ای ما به صورت مداوم در حال توسعه سیستم‌های جدید و بهبود سرور است. هر ماه شاهد آپدیت‌های بزرگ با امکانات جدید و مپ‌های اختصاصی باشید.</p>
                    </div>
                </div>

                <div class="about-stats">
                    <div class="about-stat">
                        <div class="number">۲+</div>
                        <div class="label">سال سابقه</div>
                    </div>
                    <div class="about-stat">
                        <div class="number">۵۰+</div>
                        <div class="label">بازیکن آنلاین</div>
                    </div>
                    <div class="about-stat">
                        <div class="number">۱۰۰+</div>
                        <div class="label">ایونت برگزار شده</div>
                    </div>
                    <div class="about-stat">
                        <div class="number">۵۰+</div>
                        <div class="label">مپ اختصاصی</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- بخش مدیریت -->
        <section id="management">
            <div class="section-header" data-aos="fade-up">
                <div class="section-subtitle">تیم رهبری</div>
                <h2 class="section-title">مدیریت ارشد Eternity</h2>
            </div>

            <div class="management-grid">
                <!-- Owner -->
                <div class="management-card" data-aos="flip-right" data-aos-delay="100">
                    <div class="management-icon">
                        <i class="fas fa-crown"></i>
                    </div>
                    <div class="management-role">صاحب سرور (Owner)</div>
                    <div class="management-name">Taha</div>
                    <span class="management-badge">بنیان‌گذار</span>
                </div>

                <!-- Founder -->
                <div class="management-card" data-aos="flip-right" data-aos-delay="200">
                    <div class="management-icon">
                        <i class="fas fa-hand-fist"></i>
                    </div>
                    <div class="management-role">بنیان‌گذار (Founder)</div>
                    <div class="management-name">Daryl_Dixon</div>
                    <span class="management-badge">هم بنیان‌گذار</span>
                </div>

                <!-- Scripter (دو نفره) -->
                <div class="management-card" data-aos="flip-right" data-aos-delay="300">
                    <div class="management-icon">
                        <i class="fas fa-code"></i>
                    </div>
                    <div class="management-role">تیم اسکریپت (Scripter)</div>
                    <div class="double-scripters">
                        <div class="scripter-item">
                            <div class="scripter-name">Kurdx</div>
                            <div class="scripter-title">توسعه‌دهنده ارشد</div>
                        </div>
                        <div class="scripter-item">
                            <div class="scripter-name">BeNy</div>
                            <div class="scripter-title">توسعه‌دهنده سیستم</div>
                        </div>
                    </div>
                    <span class="management-badge">۲ نفره حرفه‌ای</span>
                </div>

                <!-- Head Ghetto -->
                <div class="management-card" data-aos="flip-right" data-aos-delay="400">
                    <div class="management-icon">
                        <i class="fas fa-street-view"></i>
                    </div>
                    <div class="management-role">هد گتو (Head Ghetto)</div>
                    <div class="management-name">Abolfazl_Ofog</div>
                    <span class="management-badge">مدیر گتوها</span>
                </div>

                <!-- Head Dolat -->
                <div class="management-card" data-aos="flip-right" data-aos-delay="500">
                    <div class="management-icon">
                        <i class="fas fa-building"></i>
                    </div>
                    <div class="management-role">هد دولت (Head Dolat)</div>
                    <div class="management-name">Amir_Viking</div>
                    <span class="management-badge">مدیر سیستم دولت</span>
                </div>

                <!-- روابط عمومی و تولید محتوا -->
                <div class="management-card" data-aos="flip-right" data-aos-delay="600">
                    <div class="management-icon">
                        <i class="fas fa-bullhorn"></i>
                    </div>
                    <div class="management-role">روابط عمومی و تولید محتوا</div>
                    <div class="management-name">AmirUx</div>
                    <span class="management-badge">مدیر رسانه</span>
                </div>
            </div>
        </section>
    </main>

    <!-- فوتر -->
    <footer>
        <div class="footer-content">
            <div class="footer-col">
                <h4>آیپی سرور</h4>
                <!-- آیپی به صورت رنک و با قابلیت کپی -->
                <div class="footer-ip-card" onclick="copyIP()">
                    <i class="fas fa-network-wired"></i>
                    <div class="footer-ip-text">5.57.34.6:7777</div>
                    <div class="footer-ip-label">برای کپی کلیک کنید</div>
                </div>
                
                <h4 style="margin-top: 30px;">درباره ما</h4>
                <p style="color: #a0a0a0; line-height: 1.8;">برترین سرور سمپ با نام Eternity، میزبان بیش از 50 بازیکن فعال روزانه</p>
                <div style="margin-top: 20px;">
                    <i class="fas fa-map-pin" style="color: #fbbf24;"></i>
                </div>
            </div>
            <div class="footer-col">
                <h4>لینک‌های سریع</h4>
                <ul class="footer-links">
                    <li><a href="#home">خانه</a></li>
                    <li><a href="#gallery">گالری</a></li>
                    <li><a href="#features">ویژگی‌ها</a></li>
                    <li><a href="#about">درباره سرور</a></li>
                    <li><a href="#management">مدیریت</a></li>
                    <!-- لینک قوانین در فوتر -->
                    <li><a href="https://ttaahhaa1123456789-sketch.github.io/Gvanin-Eternity-/" target="_blank">📜 قوانین</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>ارتباط با ما</h4>
                <ul class="footer-links">
                    <li><a href="#"><i 
                    <li><a href="https://t.me/Eternity_Role_Play" target="_blank"><i class="fab fa-telegram"></i> تلگرام</a></li>
                    <li><a href="#"><i> 
                    <li><a href="https://rubika.ir/@DraGon_RolePlay" target="_blank"><i class="fas fa-paper-plane"></i> روبیکا</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>تمامی حقوق برای سرور Eternity محفوظ است © 2025</p>
        </div>
    </footer>

    <!-- دکمه بازگشت به بالا -->
    <div class="go-top" onclick="scrollToTop()">
        <i class="fas fa-arrow-up"></i>
    </div>

    <!-- اسکریپت‌ها -->
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        // راه‌اندازی AOS
        AOS.init({
            duration: 1000,
            once: true
        });

        // کپی آیپی
        function copyIP() {
            const ip = "185.14.30.50:7777";
            navigator.clipboard.writeText(ip).then(() => {
                // ایجاد نوتیفیکیشن
                const notification = document.createElement('div');
                notification.style.cssText = `
                    position: fixed;
                    top: 100px;
                    left: 50%;
                    transform: translateX(-50%);
                    background: linear-gradient(135deg, #fbbf24, #dc2626);
                    color: #0a0c0f;
                    padding: 15px 30px;
                    border-radius: 50px;
                    font-weight: 700;
                    z-index: 9999;
                    animation: slideDown 0.3s ease;
                    box-shadow: 0 10px 30px rgba(251, 191, 36, 0.5);
                `;
                notification.textContent = '✅ آیپی با موفقیت کپی شد!';
                document.body.appendChild(notification);
                
                setTimeout(() => {
                    notification.remove();
                }, 2000);
            });
        }

        // اسکرول به بالا
        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        // نمایش/مخفی کردن دکمه بازگشت به بالا
        window.addEventListener('scroll', () => {
            const goTop = document.querySelector('.go-top');
            if (window.scrollY > 500) {
                goTop.classList.add('show');
            } else {
                goTop.classList.remove('show');
            }

            // تغییر استایل نوار ناوبری هنگام اسکرول
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // هایلایت لینک فعال
        const sections = document.querySelectorAll('section');
        const mobileLinks = document.querySelectorAll('.mobile-menu a');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop - 150;
                const sectionHeight = section.clientHeight;
                if (scrollY >= sectionTop) {
                    current = section.getAttribute('id');
                }
            });

            mobileLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === '#' + current) {
                    link.classList.add('active');
                }
            });
        });

        // منوی همبرگری
        function toggleMenu() {
            const mobileMenu = document.getElementById('mobileMenu');
            const menuOverlay = document.getElementById('menuOverlay');
            const hamburgerIcon = document.getElementById('hamburgerIcon');
            
            mobileMenu.classList.toggle('active');
            menuOverlay.classList.toggle('active');
            hamburgerIcon.classList.toggle('active');
        }

        // بستن منو با کلیک روی لینک
        document.querySelectorAll('.mobile-menu a').forEach(link => {
            link.addEventListener('click', () => {
                toggleMenu();
            });
        });

        // گالری تصاویر
        let currentSlide = 0;
        const slides = document.querySelectorAll('.gallery-slide');
        const slider = document.getElementById('gallerySlider');
        const dotsContainer = document.getElementById('galleryDots');
        let autoSlideInterval;

        // ایجاد دکمه‌های پایین اسلایدر
        slides.forEach((_, index) => {
            const dot = document.createElement('div');
            dot.classList.add('gallery-dot');
            dot.onclick = () => goToSlide(index);
            dotsContainer.appendChild(dot);
        });

        const dots = document.querySelectorAll('.gallery-dot
