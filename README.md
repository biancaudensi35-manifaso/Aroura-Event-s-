# Aroura-Event-s-
luxury event planning website

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aurora Events — Luxury Event Planner</title>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700;800&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
    
    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />
    
    <style>
        /* ========== RESET & BASE ========== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            background: #1A1A1A;
            color: #FDF8F0;
        }

        /* ========== NAVIGATION ========== */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: transparent;
            transition: all 0.4s ease;
        }

        .navbar.scrolled {
            background: rgba(26, 26, 26, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.3);
            padding: 0.75rem 2rem;
        }

        .nav-logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            font-weight: 700;
            color: #C9A96E;
            text-decoration: none;
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
            align-items: center;
        }

        .nav-links a {
            color: #FDF8F0;
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: #C9A96E;
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: #C9A96E;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            background: none;
            border: none;
        }

        .hamburger span {
            width: 25px;
            height: 2px;
            background: #FDF8F0;
            transition: all 0.3s ease;
        }

        /* ========== HERO SECTION ========== */
        .hero {
            position: relative;
            height: 100vh;
            width: 100%;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #1A1A1A;
        }

        .hero-video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: 1;
        }

        .overlay {
            position: absolute;
            inset: 0;
            background: rgba(107, 29, 47, 0.7);
            z-index: 2;
        }

        .hero-content {
            position: relative;
            z-index: 3;
            text-align: center;
            padding: 0 1.5rem;
            max-width: 64rem;
            margin: 0 auto;
        }

        .brand-tag {
            font-family: 'Playfair Display', serif;
            font-size: 0.9rem;
            font-weight: 400;
            letter-spacing: 4px;
            color: #C9A96E;
            text-transform: uppercase;
            margin-bottom: 0.5rem;
            opacity: 0.8;
        }

        @media (min-width: 640px) {
            .brand-tag {
                font-size: 1rem;
                letter-spacing: 6px;
            }
        }

        .hero-content h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            font-weight: 700;
            color: #C9A96E;
            line-height: 1.15;
            letter-spacing: -0.02em;
        }

        @media (min-width: 640px) {
            .hero-content h1 {
                font-size: 3.5rem;
            }
        }

        @media (min-width: 1024px) {
            .hero-content h1 {
                font-size: 5rem;
            }
        }

        .hero-subheadline {
            font-family: 'Inter', sans-serif;
            font-size: 1.125rem;
            font-weight: 300;
            color: #FDF8F0;
            margin-top: 1.5rem;
            max-width: 48rem;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.7;
        }

        @media (min-width: 640px) {
            .hero-subheadline {
                font-size: 1.25rem;
            }
        }

        @media (min-width: 1024px) {
            .hero-subheadline {
                font-size: 1.5rem;
            }
        }

        .hero-buttons {
            margin-top: 2.5rem;
            display: flex;
            flex-direction: column;
            gap: 1rem;
            align-items: center;
            justify-content: center;
        }

        @media (min-width: 640px) {
            .hero-buttons {
                flex-direction: row;
                gap: 1.25rem;
            }
        }

        .btn-primary,
        .btn-secondary {
            display: inline-block;
            padding: 1rem 2.5rem;
            font-family: 'Inter', sans-serif;
            font-weight: 600;
            font-size: 1rem;
            border-radius: 9999px;
            text-decoration: none;
            transition: all 0.3s ease;
            width: 100%;
            text-align: center;
            cursor: pointer;
        }

        @media (min-width: 640px) {
            .btn-primary,
            .btn-secondary {
                width: auto;
                min-width: 200px;
            }
        }

        .btn-primary {
            background: #C9A96E;
            color: #1A1A1A;
            border: 2px solid #C9A96E;
        }

        .btn-primary:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 40px rgba(201, 169, 110, 0.3);
            background: #d4b87a;
            border-color: #d4b87a;
        }

        .btn-secondary {
            background: transparent;
            color: #FDF8F0;
            border: 2px solid #FDF8F0;
        }

        .btn-secondary:hover {
            background: rgba(253, 248, 240, 0.1);
            transform: scale(1.05);
            border-color: #C9A96E;
            color: #C9A96E;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            z-index: 3;
            animation: bounce 2s ease-in-out infinite;
        }

        .scroll-indicator a {
            color: rgba(253, 248, 240, 0.6);
            text-decoration: none;
            font-size: 2rem;
            transition: color 0.3s ease;
            display: block;
        }

        .scroll-indicator a:hover {
            color: #C9A96E;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            50% {
                transform: translateX(-50%) translateY(-12px);
            }
        }

        .divider {
            width: 60px;
            height: 2px;
            background: #C9A96E;
            margin: 1.5rem auto 0;
            border-radius: 2px;
        }

        @media (min-width: 640px) {
            .divider {
                width: 80px;
            }
        }

        /* ========== SERVICES SECTION ========== */
        .services {
            padding: 5rem 2rem;
            background: #1A1A1A;
        }

        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-header h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            color: #C9A96E;
            margin-bottom: 0.5rem;
        }

        .section-header p {
            color: #B0A8A0;
            font-size: 1.1rem;
        }

        .services-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        @media (min-width: 768px) {
            .services-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        .service-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 16px;
            padding: 2.5rem 2rem;
            text-align: center;
            border: 1px solid rgba(201, 169, 110, 0.2);
            transition: all 0.4s ease;
            backdrop-filter: blur(10px);
        }

        .service-card:hover {
            transform: translateY(-10px);
            border-color: #C9A96E;
            box-shadow: 0 20px 40px rgba(201, 169, 110, 0.1);
            background: rgba(255, 255, 255, 0.08);
        }

        .service-card i {
            font-size: 3rem;
            color: #C9A96E;
            margin-bottom: 1.5rem;
        }

        .service-card h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            color: #FDF8F0;
            margin-bottom: 0.75rem;
        }

        .service-card p {
            color: #B0A8A0;
            line-height: 1.7;
            font-size: 0.95rem;
        }

        /* ========== PORTFOLIO SECTION ========== */
        .portfolio {
            padding: 5rem 2rem;
            background: #121212;
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        @media (min-width: 768px) {
            .portfolio-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        .portfolio-item {
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            aspect-ratio: 1;
            background: #2A2A2A;
            cursor: pointer;
            transition: all 0.4s ease;
        }

        .portfolio-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .portfolio-item:hover img {
            transform: scale(1.1);
        }

        .portfolio-overlay {
            position: absolute;
            inset: 0;
            background: rgba(107, 29, 47, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.4s ease;
            padding: 1.5rem;
            text-align: center;
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-overlay h4 {
            font-family: 'Playfair Display', serif;
            color: #C9A96E;
            font-size: 1.2rem;
            margin-bottom: 0.25rem;
        }

        .portfolio-overlay p {
            color: #FDF8F0;
            font-size: 0.85rem;
        }

        /* ========== BUDGET ESTIMATOR ========== */
        .estimator {
            padding: 5rem 2rem;
            background: #1A1A1A;
        }

        .estimator-box {
            max-width: 700px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 3rem 2rem;
            border: 1px solid rgba(201, 169, 110, 0.2);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            color: #FDF8F0;
            font-weight: 500;
            margin-bottom: 0.5rem;
            font-size: 0.95rem;
        }

        .form-group select {
            width: 100%;
            padding: 0.9rem 1.2rem;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            background: rgba(255, 255, 255, 0.05);
            color: #FDF8F0;
            font-size: 1rem;
            font-family: 'Inter', sans-serif;
            transition: border-color 0.3s ease;
            appearance: none;
        }

        .form-group select:focus {
            outline: none;
            border-color: #C9A96E;
        }

        .form-group select option {
            background: #1A1A1A;
            color: #FDF8F0;
        }

        .estimate-result {
            margin-top: 2rem;
            padding: 1.5rem;
            background: rgba(201, 169, 110, 0.1);
            border-radius: 12px;
            border: 1px solid rgba(201, 169, 110, 0.3);
            text-align: center;
        }

        .estimate-result .price {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            color: #C9A96E;
            font-weight: 700;
        }

        .estimate-result .label {
            color: #B0A8A0;
            font-size: 0.9rem;
            margin-top: 0.25rem;
        }

        .btn-calculate {
            width: 100%;
            padding: 1rem;
            background: #C9A96E;
            color: #1A1A1A;
            border: none;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            font-family: 'Inter', sans-serif;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-calculate:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 30px rgba(201, 169, 110, 0.2);
        }

        /* ========== WHATSAPP FLOATING BUTTON ========== */
        .whatsapp-float {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 999;
            background: #25D366;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            text-decoration: none;
            box-shadow: 0 8px 30px rgba(37, 211, 102, 0.4);
            transition: all 0.3s ease;
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
            box-shadow: 0 12px 40px rgba(37, 211, 102, 0.6);
        }

        /* ========== FOOTER ========== */
        .footer {
            padding: 3rem 2rem;
            background: #0D0D0D;
            text-align: center;
            border-top: 1px solid rgba(201, 169, 110, 0.1);
        }

        .footer .footer-logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            color: #C9A96E;
            margin-bottom: 0.5rem;
        }

        .footer p {
            color: #B0A8A0;
            font-size: 0.9rem;
            margin-bottom: 0.25rem;
        }

        .footer-socials {
            margin-top: 1.5rem;
            display: flex;
            justify-content: center;
            gap: 1.5rem;
        }

        .footer-socials a {
            color: #B0A8A0;
            font-size: 1.5rem;
            transition: color 0.3s ease;
        }

        .footer-socials a:hover {
            color: #C9A96E;
        }

        .footer .copyright {
            margin-top: 1.5rem;
            font-size: 0.8rem;
            color: #666;
        }

        /* ========== RESPONSIVE ========== */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: rgba(26, 26, 26, 0.98);
                padding: 2rem;
                gap: 1.5rem;
                backdrop-filter: blur(10px);
            }

            .nav-links.active {
                display: flex;
            }

            .hamburger {
                display: flex;
            }

            .hamburger.active span:nth-child(1) {
                transform: rotate(45deg) translate(5px, 5px);
            }

            .hamburger.active span:nth-child(2) {
                opacity: 0;
            }

            .hamburger.active span:nth-child(3) {
                transform: rotate(-45deg) translate(5px, -5px);
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .portfolio-grid {
                grid-template-columns: 1fr 1fr;
            }

            .estimator-box {
                padding: 2rem 1.5rem;
            }

            .estimate-result .price {
                font-size: 2rem;
            }
        }

        @media (max-width: 480px) {
            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .hero-content h1 {
                font-size: 2rem;
            }

            .section-header h2 {
                font-size: 2rem;
            }

            .whatsapp-float {
                width: 50px;
                height: 50px;
                font-size: 1.5rem;
                bottom: 1.5rem;
                right: 1.5rem;
            }
        }
    </style>
</head>
<body>

    <!-- ========== NAVIGATION ========== -->
    <nav class="navbar" id="navbar">
        <a href="#home" class="nav-logo">Aurora Events</a>
        <ul class="nav-links" id="navLinks">
            <li><a href="#home">Home</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#portfolio">Portfolio</a></li>
            <li><a href="#estimator">Pricing</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <button class="hamburger" id="hamburger" aria-label="Toggle menu">
            <span></span>
            <span></span>
            <span></span>
        </button>
    </nav>

    <!-- ========== HERO SECTION ========== -->
    <section class="hero" id="home">
        <video class="hero-video" autoplay muted loop playsinline>
            <source src="https://res.cloudinary.com/b50fjuew/video/upload/v1784848875/8967912-hd_1080_1920_25fps_rmynf1.mp4" type="video/mp4" />
        </video>
        <div class="overlay"></div>
        <div class="hero-content">
            <p class="brand-tag">✦ Aurora Events ✦</p>
            <h1>Where Dreams Become Celebrations</h1>
            <p class="hero-subheadline">
                Luxury weddings, corporate galas, and private parties across Nigeria
            </p>
            <div class="divider"></div>
            <div class="hero-buttons">
                <a href="#estimator" class="btn-primary">Let's Plan Your Event</a>
                <a href="#portfolio" class="btn-secondary">View Our Portfolio</a>
            </div>
        </div>
        <div class="scroll-indicator">
            <a href="#services" aria-label="Scroll down">↓</a>
        </div>
    </section>

    <!-- ========== SERVICES SECTION ========== -->
    <section class="services" id="services">
        <div class="section-header">
            <h2>Our Services</h2>
            <p>Creating unforgettable moments, tailored just for you</p>
        </div>
        <div class="services-grid">
            <div class="service-card">
                <i class="fas fa-ring"></i>
                <h3>Wedding Planning</h3>
                <p>From intimate ceremonies to grand celebrations — 
