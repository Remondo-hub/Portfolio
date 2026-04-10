<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Nabil Meziani | Ingénieur Automatisme & Instrumentation</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        :root {
            --bg-primary: #f5f7fc;
            --bg-card: #ffffff;
            --text-primary: #1a2c3e;
            --text-secondary: #334155;
            --border-light: #e2e8f0;
            --accent: #1f6e8c;
            --accent-light: #e6f7f5;
            --accent-glow: rgba(31,110,140,0.15);
            --header-bg: #ffffffdd;
            --tag-bg: #ffffff;
            --footer-bg: #f1f5f9;
            --shadow: 0 8px 20px rgba(0,0,0,0.02);
            --shadow-hover: 0 20px 30px -12px rgba(0,0,0,0.1);
            --modal-overlay: rgba(0,0,0,0.75);
        }
        body.dark {
            --bg-primary: #0f172a;
            --bg-card: #1e293b;
            --text-primary: #e2e8f0;
            --text-secondary: #cbd5e1;
            --border-light: #334155;
            --accent: #2c9bb8;
            --accent-light: #1e3a4a;
            --accent-glow: rgba(44,155,184,0.2);
            --header-bg: #0f172add;
            --tag-bg: #334155;
            --footer-bg: #0f172a;
            --shadow: 0 8px 20px rgba(0,0,0,0.2);
            --modal-overlay: rgba(0,0,0,0.85);
        }
        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.5;
            scroll-behavior: smooth;
            transition: background 0.3s ease, color 0.2s ease;
            overflow-x: hidden;
        }
        .container { max-width: 1400px; margin: 0 auto; padding: 0 2rem; }
        @media (max-width: 768px) { .container { padding: 0 1.2rem; } }
        
        .navbar {
            background: var(--header-bg);
            backdrop-filter: blur(12px);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid var(--border-light);
        }
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }
        .logo {
            font-weight: 800;
            font-size: 1.6rem;
            background: linear-gradient(135deg, #0f2b3d, var(--accent));
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            cursor: pointer;
        }
        .action-buttons { display: flex; gap: 0.8rem; align-items: center; }
        .lang-switch, .theme-toggle {
            background: none;
            border: 1px solid var(--border-light);
            padding: 0.4rem 0.9rem;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 500;
            color: var(--text-primary);
            transition: all 0.3s ease;
            font-size: 0.85rem;
        }
        .cv-quick-btn {
            background: var(--accent);
            border: 1px solid var(--accent);
            padding: 0.4rem 0.9rem;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 500;
            color: white;
            transition: all 0.3s ease;
            font-size: 0.85rem;
        }
        .cv-quick-btn:hover {
            background: #0f4b5e;
            transform: translateY(-2px);
        }
        .lang-switch:hover, .theme-toggle:hover {
            background: var(--accent);
            color: white;
            border-color: var(--accent);
        }
        .mobile-menu-btn {
            display: none;
            font-size: 1.6rem;
            cursor: pointer;
            background: none;
            border: none;
            color: var(--text-primary);
        }
        .mobile-dropdown {
            display: none;
            position: absolute;
            top: 70px;
            right: 1rem;
            background: var(--bg-card);
            border: 1px solid var(--border-light);
            border-radius: 1rem;
            padding: 1rem 1.5rem;
            flex-direction: column;
            gap: 1rem;
            z-index: 101;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            min-width: 200px;
        }
        .mobile-dropdown.active { display: flex; }
        .mobile-dropdown a {
            text-decoration: none;
            color: var(--text-primary);
            font-weight: 500;
            padding: 0.5rem 0;
            transition: all 0.3s ease;
        }
        .mobile-dropdown a:hover { color: var(--accent); padding-left: 0.5rem; }
        @media (max-width: 768px) { .mobile-menu-btn { display: block; } }
        
        section { padding: 5rem 0; border-bottom: 1px solid var(--border-light); }
        #certifications { border-bottom: none; padding-bottom: 0; }
        #stages { border-top: none; margin-top: 0; }
        
        .section-title {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 2.5rem;
            position: relative;
            display: inline-block;
            background: linear-gradient(120deg, var(--accent), #0f2b3d);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }
        .section-title:after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: var(--accent);
            border-radius: 4px;
            transition: width 0.4s ease;
        }
        .section-title:hover:after { width: 100px; }
        
        .hero {
            background: linear-gradient(145deg, var(--bg-primary) 0%, var(--bg-card) 100%);
            padding: 3rem 0;
        }
        .hero-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 2rem;
        }
        .hero-info { flex: 1; animation: fadeInUp 0.6s ease-out; }
        .hero-badge {
            background: var(--accent-light);
            color: var(--accent);
            display: inline-block;
            padding: 0.3rem 1.2rem;
            border-radius: 30px;
            font-size: 0.85rem;
            font-weight: 600;
        }
        .hero-info h1 { font-size: 3.2rem; font-weight: 800; margin-bottom: 0.5rem; }
        @media (max-width: 768px) { .hero-info h1 { font-size: 2rem; } }
        .hero-info .title { font-size: 1.5rem; color: var(--accent); font-weight: 600; margin-top: 0.5rem; }
        .hero-desc { color: var(--text-secondary); max-width: 550px; margin: 1.2rem 0; font-size: 1rem; }
        .avatar-icon {
            background: var(--accent-light);
            width: 200px;
            height: 200px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5rem;
            color: var(--accent);
            border: 6px solid var(--bg-card);
            box-shadow: 0 20px 30px -10px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        .avatar-icon:hover { transform: scale(1.03); }
        
        .btn-portfolio {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            background: linear-gradient(135deg, var(--accent), #0f4b5e);
            color: white;
            padding: 0.85rem 2rem;
            border-radius: 50px;
            font-weight: 700;
            text-decoration: none;
            transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            margin: 0.5rem 0 1.2rem;
            border: none;
            cursor: pointer;
            box-shadow: 0 6px 14px var(--accent-glow);
        }
        .btn-portfolio:hover { transform: translateY(-3px); box-shadow: 0 12px 22px var(--accent-glow); }
        
        .availability-banner {
            background: linear-gradient(135deg, var(--accent), #0f4b5e);
            border-radius: 2rem;
            padding: 1.8rem 2rem;
            text-align: center;
            box-shadow: 0 15px 30px var(--accent-glow);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .availability-banner:hover { transform: translateY(-5px); }
        .availability-banner h2 { color: white; font-size: 1.6rem; margin-bottom: 0.5rem; }
        .availability-banner p { color: rgba(255,255,255,0.9); margin-bottom: 1.2rem; }
        .roles-container { display: flex; flex-wrap: wrap; justify-content: center; gap: 1rem; }
        .role-badge {
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(4px);
            padding: 0.6rem 1.3rem;
            border-radius: 50px;
            font-weight: 600;
            color: white;
            display: inline-flex;
            align-items: center;
            gap: 0.6rem;
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.3);
        }
        .role-badge:hover { background: white; color: var(--accent); transform: scale(1.02); }
        .availability-note { margin-top: 1rem; font-size: 0.85rem; color: rgba(255,255,255,0.8); }
        
        /* Carrousel */
        .carousel-wrapper {
            position: relative;
            width: 100%;
            overflow: hidden;
            border-radius: 1.5rem;
            background: var(--bg-card);
            box-shadow: var(--shadow);
        }
        .carousel-track {
            display: flex;
            transition: transform 0.5s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            cursor: grab;
        }
        .carousel-track:active { cursor: grabbing; }
        .carousel-slide {
            flex: 0 0 100%;
            position: relative;
            aspect-ratio: 4 / 1.5;
            overflow: hidden;
            cursor: pointer;
        }
        .carousel-slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s ease;
        }
        .carousel-slide:hover img { transform: scale(1.03); }
        .slide-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0.3) 50%, transparent 100%);
            padding: 2rem;
            color: white;
        }
        .slide-overlay h3 { font-size: 1.8rem; font-weight: 700; margin-bottom: 0.5rem; }
        @media (max-width: 768px) {
            .slide-overlay h3 { font-size: 1.3rem; }
            .slide-overlay { padding: 1.2rem; }
        }
        .desc-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }
        .click-details-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(8px);
            padding: 0.5rem 1.2rem;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.85rem;
            color: white;
            border: 1px solid rgba(255,255,255,0.4);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .click-details-btn:hover { background: var(--accent); transform: translateY(-2px); }
        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(0,0,0,0.6);
            backdrop-filter: blur(4px);
            border: none;
            width: 48px;
            height: 48px;
            border-radius: 50%;
            cursor: pointer;
            color: white;
            font-size: 1.4rem;
            transition: all 0.3s ease;
            z-index: 20;
            opacity: 0;
            visibility: hidden;
        }
        .carousel-wrapper:hover .carousel-btn { opacity: 1; visibility: visible; }
        .carousel-btn:hover { background: var(--accent); transform: translateY(-50%) scale(1.05); }
        .btn-prev { left: 1.5rem; }
        .btn-next { right: 1.5rem; }
        .carousel-dots {
            display: flex;
            justify-content: center;
            gap: 0.75rem;
            margin-top: 1.5rem;
        }
        .dot {
            width: 10px;
            height: 10px;
            background: var(--border-light);
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .dot.active { background: var(--accent); width: 28px; border-radius: 12px; }
        
        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin: 1.5rem 0;
        }
        .skill-tag {
            background: var(--tag-bg);
            border-radius: 40px;
            padding: 0.5rem 1.3rem;
            border: 1px solid var(--border-light);
            transition: all 0.3s ease;
            font-weight: 500;
            cursor: pointer;
        }
        .skill-tag:hover { transform: translateY(-3px); border-color: var(--accent); background: var(--accent-light); }
        
        .horizontal-scroll {
            display: flex;
            overflow-x: auto;
            gap: 1.8rem;
            padding: 0.5rem 0.2rem 1.5rem;
            scrollbar-width: thin;
            scroll-snap-type: x mandatory;
        }
        .horizontal-scroll::-webkit-scrollbar { height: 6px; }
        .horizontal-scroll::-webkit-scrollbar-track { background: var(--border-light); border-radius: 10px; }
        .horizontal-scroll::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 10px; }
        .exp-card-h {
            flex: 0 0 380px;
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 1.5rem;
            border: 1px solid var(--border-light);
            transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            scroll-snap-align: start;
            box-shadow: var(--shadow);
        }
        .exp-card-h:hover { transform: translateY(-8px); box-shadow: var(--shadow-hover); border-color: var(--accent); }
        .exp-title-h { font-size: 1.3rem; font-weight: 700; color: var(--accent); }
        .exp-date {
            font-size: 0.75rem;
            background: var(--accent-light);
            display: inline-block;
            padding: 0.2rem 0.8rem;
            border-radius: 30px;
            margin: 0.5rem 0;
        }
        .exp-list { list-style: none; margin-top: 0.8rem; }
        .exp-list li { margin-bottom: 0.6rem; display: flex; gap: 0.7rem; align-items: baseline; font-size: 0.9rem; }
        .exp-list i { color: var(--accent); min-width: 18px; }
        
        .two-columns {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.8rem;
        }
        .formation-item {
            background: var(--bg-card);
            border-radius: 1.2rem;
            padding: 1.3rem;
            border-left: 5px solid var(--accent);
            transition: transform 0.2s;
        }
        .formation-item:hover { transform: translateX(5px); }
        
        .lang-cert-wrapper { display: flex; flex-wrap: wrap; gap: 2rem; }
        .lang-box {
            flex: 1;
            min-width: 280px;
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 1.8rem;
            border: 1px solid var(--border-light);
            transition: transform 0.3s;
        }
        .lang-box:hover { transform: translateY(-5px); }
        .level-indicator {
            margin: 0.8rem 0;
            display: flex;
            align-items: center;
            gap: 1rem;
            flex-wrap: wrap;
        }
        .stars { color: #f5b042; letter-spacing: 2px; font-size: 0.9rem; }
        
        /* Certifications */
        .certifications-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }
        .cert-card {
            background: var(--bg-card);
            border-radius: 1.5rem;
            overflow: hidden;
            transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            border: 1px solid var(--border-light);
            cursor: pointer;
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }
        .cert-card:nth-child(1) { animation-delay: 0.1s; }
        .cert-card:nth-child(2) { animation-delay: 0.2s; }
        .cert-card:nth-child(3) { animation-delay: 0.3s; }
        .cert-card:nth-child(4) { animation-delay: 0.4s; }
        .cert-card:hover { transform: translateY(-8px); box-shadow: var(--shadow-hover); border-color: var(--accent); }
        .cert-header {
            background: linear-gradient(135deg, var(--accent), #0f4b5e);
            padding: 1.2rem;
            position: relative;
        }
        .cert-header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 150px;
            height: 150px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: all 0.4s ease;
        }
        .cert-card:hover .cert-header::before { transform: scale(1.5); opacity: 0.5; }
        .cert-icon {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 2.5rem;
            color: white;
        }
        .cert-year {
            background: rgba(255,255,255,0.2);
            padding: 0.3rem 0.8rem;
            border-radius: 30px;
            font-size: 0.8rem;
            font-weight: 600;
            color: white;
        }
        .cert-body { padding: 1.5rem; }
        .cert-title { font-size: 1.2rem; font-weight: 700; margin-bottom: 0.5rem; }
        .cert-issuer {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--accent);
            font-size: 0.85rem;
            margin-bottom: 1rem;
            padding-bottom: 0.8rem;
            border-bottom: 1px dashed var(--border-light);
        }
        .cert-description { color: var(--text-secondary); font-size: 0.9rem; line-height: 1.5; margin-bottom: 1rem; }
        .cert-skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }
        .cert-skills span {
            font-size: 0.7rem;
            background: var(--accent-light);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            color: var(--accent);
            font-weight: 500;
            transition: all 0.3s ease;
        }
        .cert-card:hover .cert-skills span { background: var(--accent); color: white; transform: translateY(-2px); }
    
        .verified-badge {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: rgba(0,0,0,0.6);
            backdrop-filter: blur(4px);
            color: #4caf50;
            font-size: 0.7rem;
            font-weight: 600;
            padding: 0.5rem 0.7rem;
            border-radius: 20px;
            display: flex;
            align-items: center;
            gap: 0.3rem;
            z-index: 2;
        }
        
        /* Timeline formations */
        .trainings-timeline {
            position: relative;
            padding: 2rem 0;
        }
        .trainings-timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 3px;
            height: calc(100% - 4rem);
            background: linear-gradient(180deg, var(--accent), var(--accent-light));
            border-radius: 3px;
            top: 2rem;
        }
        .training-card {
            position: relative;
            width: calc(50% - 2rem);
            margin-bottom: 2.5rem;
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }
        .training-card:nth-child(1) { animation-delay: 0.1s; }
        .training-card:nth-child(2) { animation-delay: 0.2s; }
        .training-card:nth-child(3) { animation-delay: 0.3s; }
        .training-card:nth-child(4) { animation-delay: 0.4s; }
        .training-card.left { left: 0; }
        .training-card.right { left: 50%; margin-left: 2rem; }
        .training-card::before {
            content: '';
            position: absolute;
            right: -3rem;
            top: 1.5rem;
            width: 1.2rem;
            height: 1.2rem;
            background: var(--accent);
            border: 3px solid var(--bg-card);
            border-radius: 50%;
            z-index: 10;
            box-shadow: 0 0 0 4px var(--accent-light);
            transition: transform 0.3s ease;
        }
        .training-card.right::before { left: -3rem; right: auto; }
        .training-card:hover::before { transform: scale(1.3); background: #2c9bb8; }
        .training-content {
            background: var(--bg-card);
            border-radius: 1.2rem;
            padding: 1.5rem;
            border: 1px solid var(--border-light);
            transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        .training-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: linear-gradient(135deg, var(--accent-light), transparent);
            transition: width 0.4s ease;
            z-index: 0;
        }
        .training-content:hover { transform: translateY(-5px); box-shadow: var(--shadow-hover); border-color: var(--accent); }
        .training-content:hover::before { width: 100%; }
        .training-content > * { position: relative; z-index: 1; }
        .training-header { display: flex; align-items: flex-start; gap: 1rem; margin-bottom: 1rem; flex-wrap: wrap; }
        .training-icon {
            width: 55px;
            height: 55px;
            background: linear-gradient(135deg, var(--accent-light), var(--bg-card));
            border-radius: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.6rem;
            color: var(--accent);
            transition: all 0.3s ease;
            border: 1px solid var(--border-light);
        }
        .training-content:hover .training-icon { transform: scale(1.1) rotate(5deg); background: var(--accent); color: white; }
        .training-info { flex: 1; }
        .training-title { font-size: 1.2rem; font-weight: 700; margin-bottom: 0.3rem; display: flex; align-items: center; gap: 0.5rem; flex-wrap: wrap; }
        .training-date {
            font-size: 0.7rem;
            background: var(--accent-light);
            padding: 0.25rem 0.8rem;
            border-radius: 20px;
            color: var(--accent);
            font-weight: 600;
        }
        .training-org { font-size: 0.85rem; color: var(--text-secondary); display: flex; align-items: center; gap: 0.5rem; margin-top: 0.3rem; }
        .training-desc { margin-top: 1rem; padding-left: 0.5rem; border-left: 3px solid var(--accent); }
        .training-desc p { font-size: 0.9rem; color: var(--text-secondary); line-height: 1.5; }
        .training-skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px dashed var(--border-light);
        }
        .training-skills span {
            background: var(--accent-light);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.7rem;
            color: var(--accent);
        }
        
        .training-badge {
            position: absolute;
            top: 0;
            right: 0;
            background: linear-gradient(135deg, #e8a020 0%, #c97e0a 100%);
            color: white;
            font-size: 0.7rem;
            font-weight: 700;
            padding: 0.5rem 1.2rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            z-index: 10;
            box-shadow: 0 2px 8px rgba(0,0,0,0.2);
            border-radius: 0 1rem 0 1rem;
            pointer-events: none;
        }

        @media (max-width: 768px) {
            .trainings-timeline::before { left: 1.5rem; }
            .training-card { width: calc(100% - 3rem); margin-left: 3rem !important; left: 0 !important; }
            .training-card::before { left: -2.5rem !important; right: auto !important; }
            .training-badge { position: relative; top: auto; right: auto; margin-top: 0.5rem; display: inline-flex; width: fit-content; border-radius: 20px; transform: none; }
            .training-header { flex-direction: column; }
        }
        
        /* Stages */
        .stages-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }
        .stage-card {
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 1.8rem;
            transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            border: 1px solid var(--border-light);
            cursor: pointer;
            position: relative;
            overflow: hidden;
            opacity: 0;
            animation: fadeInUp 0.6s ease forwards;
        }
        .stage-card:nth-child(1) { animation-delay: 0.1s; }
        .stage-card:nth-child(2) { animation-delay: 0.2s; }
        .stage-card:nth-child(3) { animation-delay: 0.3s; }
        .stage-card:nth-child(4) { animation-delay: 0.4s; }
        .stage-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 0;
            background: linear-gradient(135deg, var(--accent-light), transparent);
            transition: height 0.4s ease;
            z-index: 0;
        }
        .stage-card:hover { transform: translateY(-8px); box-shadow: var(--shadow-hover); border-color: var(--accent); }
        .stage-card:hover::before { height: 100%; }
        .stage-card > * { position: relative; z-index: 1; }
        .stage-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 1.2rem; flex-wrap: wrap; }
        .stage-icon {
            width: 50px;
            height: 50px;
            background: var(--accent-light);
            border-radius: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--accent);
            transition: all 0.3s ease;
        }
        .stage-card:hover .stage-icon { transform: scale(1.1) rotate(5deg); background: var(--accent); color: white; }
        .stage-company h3 { font-size: 1.2rem; font-weight: 700; margin-bottom: 0.2rem; }
        .stage-date {
            font-size: 0.7rem;
            background: var(--accent-light);
            display: inline-block;
            padding: 0.2rem 0.7rem;
            border-radius: 20px;
            color: var(--accent);
            font-weight: 600;
        }
        .stage-title { font-size: 1rem; font-weight: 600; color: var(--accent); margin-bottom: 0.8rem; display: flex; align-items: center; gap: 0.5rem; }
        .stage-description { color: var(--text-secondary); font-size: 0.9rem; line-height: 1.5; margin-bottom: 1rem; }
        .stage-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px dashed var(--border-light);
        }
        .stage-tech span { font-size: 0.7rem; background: var(--bg-primary); padding: 0.3rem 0.8rem; border-radius: 20px; transition: all 0.3s ease; }
        .stage-card:hover .stage-tech span { background: var(--accent-light); color: var(--accent); }
        
        /* Footer moderne */
        footer {
            background: var(--footer-bg);
            padding: 3rem 0 2rem;
            border-top: 1px solid var(--border-light);
        }
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 2rem;
            margin-bottom: 2rem;
        }
        .footer-contact, .footer-social {
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 1.8rem;
            border: 1px solid var(--border-light);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            flex: 1;
            min-width: 250px;
        }
        .footer-contact:hover, .footer-social:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-hover);
            border-color: var(--accent);
        }
        .footer-contact h3, .footer-social h3 {
            font-size: 1.3rem;
            margin-bottom: 1.2rem;
            color: var(--accent);
            display: flex;
            align-items: center;
            gap: 0.6rem;
        }
        .animated-contact {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 0.7rem 0;
            transition: all 0.3s ease;
            border-bottom: 1px dashed var(--border-light);
        }
        .contact-item:last-child { border-bottom: none; }
        .contact-item:hover { transform: translateX(8px); color: var(--accent); }
        .contact-item i {
            width: 40px;
            height: 40px;
            background: var(--accent-light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--accent);
            transition: all 0.3s ease;
        }
        .contact-item:hover i {
            background: var(--accent);
            color: white;
            transform: scale(1.1);
        }
        .contact-item span { font-size: 0.95rem; word-break: break-word; }
        .social-links {
            display: flex;
            flex-direction: column;
            gap: 0.8rem;
        }
        .social-links a {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            background: var(--bg-primary);
            padding: 0.7rem 1.2rem;
            border-radius: 50px;
            text-decoration: none;
            color: var(--text-primary);
            border: 1px solid var(--border-light);
            transition: all 0.3s ease;
            font-weight: 500;
        }
        .social-links a:hover {
            background: var(--accent);
            color: white;
            transform: translateX(5px);
            border-color: var(--accent);
        }
        .social-links a i { font-size: 1.2rem; }
        .footer-note {
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px dashed var(--border-light);
            font-size: 0.85rem;
            color: var(--text-secondary);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .copyright {
            text-align: center;
            font-size: 0.8rem;
            padding-top: 1.5rem;
            border-top: 1px solid var(--border-light);
            color: var(--text-secondary);
        }
        
        /* MODALES MODERNES */
        .modal, .cert-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--modal-overlay);
            backdrop-filter: blur(8px);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .modal.show, .cert-modal.show { display: flex; opacity: 1; }
        .modal-content, .cert-modal-content {
            background: var(--bg-card);
            max-width: 550px;
            width: 90%;
            border-radius: 2rem;
            padding: 2rem;
            position: relative;
            transform: scale(0.95);
            transition: transform 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
            box-shadow: 0 30px 40px rgba(0,0,0,0.3);
            border: 1px solid var(--border-light);
            max-height: 85vh;
            overflow-y: auto;
        }
        .modal.show .modal-content, .cert-modal.show .cert-modal-content { transform: scale(1); }
        .modal-close, .cert-modal-close {
            position: absolute;
            top: 1.2rem;
            right: 1.5rem;
            font-size: 1.8rem;
            cursor: pointer;
            transition: 0.2s;
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            color: var(--text-secondary);
        }
        .modal-close:hover, .cert-modal-close:hover { color: var(--accent); background: var(--accent-light); transform: scale(1.1); }
        .modal-icon, .cert-modal-icon {
            font-size: 3rem;
            color: var(--accent);
            margin-bottom: 1rem;
            text-align: center;
        }
        .modal h3, .cert-modal h3 {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            text-align: center;
        }
        .modal-desc, .cert-modal-desc {
            margin: 1rem 0;
            line-height: 1.6;
            color: var(--text-secondary);
        }
        .modal-details {
            background: var(--accent-light);
            padding: 1rem 1.2rem;
            border-radius: 1rem;
            margin: 1rem 0;
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            font-size: 0.9rem;
            color: var(--accent);
            font-weight: 500;
        }
        hr { border-color: var(--border-light); margin: 1rem 0; }
        .modal-tech {
            margin-top: 0.5rem;
            font-size: 0.95rem;
        }
        .modal-tech strong { color: var(--accent); }
        .cert-modal-issuer {
            color: var(--accent);
            font-weight: 600;
            text-align: center;
            margin-bottom: 0.5rem;
        }
        .cert-modal-date {
            background: var(--accent-light);
            display: inline-block;
            padding: 0.3rem 1rem;
            border-radius: 30px;
            font-size: 0.8rem;
            margin-bottom: 1rem;
            text-align: center;
            width: auto;
        }
        .cert-modal-skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            justify-content: center;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px solid var(--border-light);
        }
        .cert-modal-skills span {
            background: var(--accent-light);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            color: var(--accent);
        }
        
        [data-lang="en"] .lang-fr { display: none; }
        [data-lang="fr"] .lang-en { display: none; }
        body:not([data-lang="en"]) .lang-en { display: none; }
        body[data-lang="en"] .lang-fr { display: none; }
        body[data-lang="fr"] .lang-fr { display: inline; }
        body[data-lang="en"] .lang-en { display: inline; }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body data-lang="fr">
<nav class="navbar">
    <div class="nav-container">
        <div class="logo" id="homeLogo">Nabil Meziani</div>
        <div class="action-buttons">
            <button class="cv-quick-btn"    id="cvQuickBtn">    <i class="fas fa-file-alt">     </i> CV     </button>
            <button class="lang-switch"     id="langSwitch">    🇬🇧 EN                                       </button>
            <button class="theme-toggle"    id="themeToggle">   <i class="fas fa-moon">                     </i></button>
            <button class="mobile-menu-btn" id="mobileMenuBtn"> <i class="fas fa-bars">                     </i></button>
        </div>
    </div>
    <div class="mobile-dropdown" id="mobileDropdown">
        <a href="#home" data-translate="home">Accueil</a>
        <a href="#disponibilite" data-translate="availability">Disponibilité</a>
        <a href="#expertise" data-translate="expertise">Expertise</a>
        <a href="#experience" data-translate="exp">Expériences</a>
        <a href="#competences" data-translate="skills">Compétences</a>
        <a href="#diplomes" data-translate="diplomas">Diplômes</a>
        <a href="#formations" data-translate="training">Formations</a>
        <a href="#langues" data-translate="lang">Langues</a>
        <a href="#certifications" data-translate="cert">Certifications</a>
        <a href="#stages" data-translate="stages">Stages</a>
    </div>
</nav>
<main>
    <section id="home" class="hero">
        <div class="container hero-grid">
            <div class="hero-info">
                <div class="hero-badge"><i class="fas fa-microchip"></i> <span class="lang-fr">Ingénieur automatisme & instrumentation</span><span class="lang-en">Automation & Instrumentation Engineer</span></div>
                <h1>Nabil MEZIANI</h1>
                <div class="title">Automatisation | DCS | PLC | SCADA | Commissioning</div>
                <p class="hero-desc"><span class="lang-fr">Ingénieur passionné par la mise en œuvre pratique des solutions d'automatisation, l'amélioration continue et les technologies industrielles modernes. Expérience terrain en construction, commissioning et exploitation.</span><span class="lang-en">Passionate engineer specialized in automation solutions, commissioning, and industrial process optimization with field experience.</span></p>
                <a href="CVs.html" class="btn-portfolio" id="portfolioBtn">
                    <i class="fas fa-folder-open"></i>
                    <span class="lang-fr"> Découvrir mon CV</span>
                    <span class="lang-en"> View my CV</span>
                    <i class="fas fa-arrow-right"></i>
                </a>
            </div>
            <div class="hero-image"><div class="avatar-icon"><i class="fas fa-robot"></i></div></div>
        </div>
    </section>
    
    <section id="disponibilite" data-aos="zoom-in" data-aos-duration="800">
        <div class="container">
            <div class="availability-banner">
                <h2><i class="fas fa-bullhorn"></i> <span class="lang-fr">📢 Disponible pour de nouvelles opportunités</span><span class="lang-en">📢 Available for new opportunities</span></h2>
                <p><span class="lang-fr">Ingénieur en automatisme & instrumentation – Mobilité nationale & internationale</span><span class="lang-en">Automation & Instrumentation Engineer – National & international mobility</span></p>
                <div class="roles-container">
                    <span class="role-badge"><i class="fas fa-microchip"></i> <span class="lang-fr">Ingénieur automatisme</span><span class="lang-en">Automation Engineer</span></span>
                    <span class="role-badge"><i class="fas fa-chart-line"></i> <span class="lang-fr">Ingénieur en instrumentation</span><span class="lang-en">Instrumentation Engineer</span></span>
                    <span class="role-badge"><i class="fas fa-chalkboard-user"></i> <span class="lang-fr">Formateur technique</span><span class="lang-en">Technical Trainer</span></span>
                    <span class="role-badge"><i class="fas fa-users"></i> <span class="lang-fr">Superviseur / Chef de projet</span><span class="lang-en">Supervisor / Project Lead</span></span>
                    <span class="role-badge"><i class="fas fa-tools"></i> <span class="lang-fr">Maintenancien spécialisé</span><span class="lang-en">Maintenance Specialist</span></span>
                    <span class="role-badge"><i class="fas fa-chart-simple"></i> <span class="lang-fr">Consultant instrumentation</span><span class="lang-en">Instrumentation Consultant</span></span>
                </div>
                <div class="availability-note">
                    <i class="fas fa-clock"></i> <span class="lang-fr">Disponible immédiatement – Tous types de contrats : CDI, CDD, Freelance, Mission de formation</span>
                    <span class="lang-en">Immediately available – All contract types: permanent, fixed-term, freelance, training missions</span>
                </div>
            </div>
        </div>
    </section>

    <section id="expertise" class="carousel-section" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title"><span class="lang-fr">🎯 Mes activités professionnelles</span><span class="lang-en">🎯 My professional activities</span></h2>
            <div class="carousel-wrapper">
                <div class="carousel-track" id="carouselTrack"></div>
                <button class="carousel-btn btn-prev" id="prevBtn"><i class="fas fa-chevron-left"></i></button>
                <button class="carousel-btn btn-next" id="nextBtn"><i class="fas fa-chevron-right"></i></button>
                <div class="carousel-dots" id="carouselDots"></div>
            </div>
        </div>
    </section>

    <section id="competences" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title"><span class="lang-fr">Compétences techniques</span><span class="lang-en">Technical skills</span></h2>
            <div class="skills-grid">
                <span class="skill-tag" data-skill="dcs">DCS</span>
                <span class="skill-tag" data-skill="plc">PLC</span>
                <span class="skill-tag" data-skill="scada">SCADA</span>
                <span class="skill-tag" data-skill="calibration">Calibration/HART</span>
                <span class="skill-tag" data-skill="tia">TIA Portal</span>
                <span class="skill-tag" data-skill="step7">STEP 7</span>
                <span class="skill-tag" data-skill="pcs7">PCS 7</span>
                <span class="skill-tag" data-skill="wincc">WinCC</span>
                <span class="skill-tag" data-skill="profibus">PROFIBUS/PROFINET</span>
                <span class="skill-tag" data-skill="office">Microsoft Office</span>
            </div>
        </div>
    </section>
    
    <section id="experience" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title"><span class="lang-fr">Expériences professionnelles</span><span class="lang-en">Work Experience</span></h2>
            <div class="horizontal-scroll">
                <div class="exp-card-h">
                    <div class="exp-title-h"><span class="lang-fr">Ingénieur automatisme & instrumentation</span><span class="lang-en">Automation & Instrumentation Engineer</span></div>
                    <div class="exp-date">Depuis mai 2023 - Présent / Since May 2023 - Present</div>
                    <div class="exp-company" style="font-weight:600; margin:0.5rem 0;"><span class="lang-fr">Raffinerie de sucre TAFADIS, Larbatache</span><span class="lang-en">TAFADIS Sugar Refinery, Larbatache</span></div>
                    <ul class="exp-list">
                        <li><i class="fas fa-clipboard-list"></i> <span class="lang-fr">Supervision et inspection des travaux sur site</span><span class="lang-en">Site supervision & inspection</span></li>
                        <li><i class="fas fa-drafting-compass"></i> <span class="lang-fr">Études et préparation technique</span><span class="lang-en">Technical studies & preparation</span></li>
                        <li><i class="fas fa-users-cog"></i> <span class="lang-fr">Gestion et coordination des sous-traitants</span><span class="lang-en">Subcontractor management & coordination</span></li>
                        <li><i class="fas fa-play-circle"></i> <span class="lang-fr">Mise en service et pré-commissioning</span><span class="lang-en">Commissioning & pre-commissioning</span></li>
                        <li><i class="fas fa-sliders-h"></i> <span class="lang-fr">Étalonnage et paramétrage des instruments</span><span class="lang-en">Instrument calibration & configuration</span></li>
                        <li><i class="fas fa-tools"></i> <span class="lang-fr">Maintenance et entretien des systèmes de contrôle-commande</span><span class="lang-en">Control system maintenance & troubleshooting</span></li>
                    </ul>
                </div>
                <div class="exp-card-h">
                    <div class="exp-title-h">Robotics Coach</div>
                    <div class="exp-date">Septembre 2022 - Juin 2023 / Sep 2022 - Jun 2023</div>
                    <div class="exp-company" style="font-weight:600;">SAKHRIA SCHOOL, Bab Ezzouar, Alger</div>
                    <ul class="exp-list">
                        <li><i class="fas fa-robot"></i> <span class="lang-fr">Enseignement programme MRT (Corée) : robotique, mécatronique</span><span class="lang-en">Teaching MRT program (Korea): robotics, mechatronics</span></li>
                        <li><i class="fas fa-lightbulb"></i> <span class="lang-fr">Conception de cours enrichissants & activités pratiques</span><span class="lang-en">Design of enriching courses & practical activities</span></li>
                        <li><i class="fas fa-trophy"></i> <span class="lang-fr">Organisation de compétitions robotiques</span><span class="lang-en">Organization of robotics competitions</span></li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
    
    <section id="diplomes" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title"><span class="lang-fr">Diplômes universitaires</span><span class="lang-en">Academic Degrees</span></h2>
            <div class="two-columns">
                <div class="formation-item"><i class="fas fa-graduation-cap"></i> <strong><span class="lang-fr">Master Automatisation Industrie et Process</span><span class="lang-en">Master in Industrial and Process Automation</span></strong><br>USTHB (2020-2022)</div>
                <div class="formation-item"><i class="fas fa-graduation-cap"></i> <strong><span class="lang-fr">Licence en automatique</span><span class="lang-en">Bachelor's Degree in Automation</span></strong><br>USTHB (2017-2020)</div>
                <div class="formation-item"><i class="fas fa-chalkboard"></i> <strong><span class="lang-fr">Baccalauréat mathématique</span><span class="lang-en">High School Diploma in Mathematics</span></strong><br><span class="lang-fr">Lycée Mohamed Boudiaf</span><span class="lang-en">Mohamed Boudiaf High School</span></div>
            </div>
        </div>
    </section>
    
    <section id="formations" class="trainings-modern" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title">
                <i class="fas fa-graduation-cap"></i> 
                <span class="lang-fr">Formations complémentaires</span>
                <span class="lang-en">Additional Training</span>
            </h2>
            <div class="trainings-timeline">
                <div class="training-card left">
                    <div class="training-content" data-training="pcs7">
                        <div class="training-badge"><i class="fas fa-certificate"></i> <span class="lang-fr">Certifié</span><span class="lang-en">Certified</span></div>
                        <div class="training-header">
                            <div class="training-icon"><i class="fas fa-microchip"></i></div>
                            <div class="training-info">
                                <div class="training-title">SIMATIC PCS7 Expert </div>
                                <div class="training-org"><i class="fas fa-building"></i> TECHNORD (Belgique / Belgium)<span class="training-date"><i class="far fa-calendar-alt"></i> Novembre 2025 / November 2025</span></div>
                            </div>
                        </div>
                        <div class="training-desc"><p><span class="lang-fr">Formation approfondie sur le système DCS Siemens SIMATIC PCS7.</span><span class="lang-en">Advanced training on Siemens SIMATIC PCS7 DCS system.</span></p></div>
                        <div class="training-skills"><span>Gestion de projets PCS7</span><span>Programmation CFC/SFC</span><span>Configuration PROFIBUS & PROFINET</span><span>Développement d'interfaces OS</span></div>
                    </div>
                </div>
                <div class="training-card right">
                    <div class="training-content" data-training="maintenance">
                        <div class="training-badge"><i class="fas fa-certificate"></i> <span class="lang-fr">Certifié</span><span class="lang-en">Certified</span></div>
                        <div class="training-header">
                            <div class="training-icon"><i class="fas fa-wrench"></i></div>
                            <div class="training-info">
                                <div class="training-title">SIMATIC Maintenance Niveau 1 </div>
                                <div class="training-org"><i class="fas fa-building"></i> CFIC GICA  <span class="training-date"><i class="far fa-calendar-alt"></i> Septembre 2025 / September 2025</span></div>
                            </div>
                        </div>
                        <div class="training-desc"><p><span class="lang-fr">Formation à la maintenance des systèmes SIMATIC S7.</span><span class="lang-en">Training on SIMATIC S7 systems maintenance.</span></p></div>
                        <div class="training-skills"><span>Diagnostic d'automates S7</span><span>Dépannage systèmes automatisés</span><span>Maintenance préventive et corrective</span><span>Lecture d'architectures industrielles</span></div>
                    </div>
                </div>
                <div class="training-card left">
                    <div class="training-content" data-training="seminar">
                        <div class="training-header">
                            <div class="training-icon"><i class="fas fa-chart-line"></i></div>
                            <div class="training-info">
                                <div class="training-title"><span class="lang-fr">Séminaire Maintenance industrielle</span><span class="lang-en">Industrial Maintenance Seminar</span></div>
                                <div class="training-org"><i class="fas fa-building"></i> INPED <span class="training-date"><i class="far fa-calendar-alt"></i> Octobre 2023 / October 2023</span></div>
                            </div>
                        </div>
                        <div class="training-desc"><p><span class="lang-fr">Séminaire sur les stratégies modernes de maintenance industrielle : préventive, corrective, conditionnelle. Couvre la gestion opérationnelle, la définition d'indicateurs de performance et la planification des interventions.</span><span class="lang-en">Seminar on modern industrial maintenance strategies: preventive, corrective, condition-based. Covers operational management, performance indicators definition, and intervention planning.</span></p></div>
                        <div class="training-skills"><span>Gestion de maintenance</span><span>Stratégie préventive et corrective</span><span>Maintenance conditionnelle</span><span>Planification d'interventions</span></div>
                    </div>
                </div>
                <div class="training-card right">
                    <div class="training-content" data-training="safety">
                        <div class="training-header">
                            <div class="training-icon"><i class="fas fa-shield-alt"></i></div>
                            <div class="training-info">
                                <div class="training-title"><span class="lang-fr">Sécurité industrielle</span><span class="lang-en">Industrial Safety</span></div>
                                <div class="training-org"><i class="fas fa-building"></i> IFACT <span class="training-date"><i class="far fa-calendar-alt"></i> Décembre 2020 / December 2020</span></div>
                            </div>
                        </div>
                        <div class="training-desc"><p><span class="lang-fr">Formation aux principes fondamentaux de la sécurité en milieu industriel. Couvre les principes de sécurité, la prévention des risques, la gestion des risques et les premiers secours.</span><span class="lang-en">Training on fundamental principles of industrial safety. Covers safety principles, risk prevention, risk management, and first aid.</span></p></div>
                        <div class="training-skills"><span>Analyse des risques industriels</span><span>Gestion des situations critiques</span><span>Intervention en zone dangereuse</span><span>Premiers secours</span></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="langues" data-aos="fade-up">
        <div class="container"><div class="lang-cert-wrapper"><div class="lang-box"><h3><i class="fas fa-language"></i> <span class="lang-fr">Langues</span><span class="lang-en">Languages</span></h3>
            <div class="level-indicator"><span class="lang-fr"><strong>Arabe</strong></span><span class="lang-en"><strong>Arabic</strong></span> <span class="stars">★★★★★</span> <span style="background:var(--accent-light); padding:0.2rem 0.6rem; border-radius:20px;"><span class="lang-fr">Maternel</span><span class="lang-en">Native</span></span></div>
            <div class="level-indicator"><span class="lang-fr"><strong>Français</strong></span><span class="lang-en"><strong>French</strong></span> <span class="stars">★★★★⯨</span>  <span style="background:var(--accent-light); padding:0.2rem 0.6rem; border-radius:20px;"><span class="lang-fr">Professionnel - Niveau avancé</span><span class="lang-en">Professional - Advanced Level</span></span></div>
            <div class="level-indicator"><span class="lang-fr"><strong>Anglais</strong></span><span class="lang-en"><strong>English</strong></span> <span class="stars">★★★★</span> <span style="background:var(--accent-light); padding:0.2rem 0.6rem; border-radius:20px;"><span class="lang-fr">Professionnel - Niveau intermédiaire supérieur</span><span class="lang-en">Professional - Upper Intermediate Level</span></span></div>
            <p style="margin-top:1rem;"><i class="fas fa-file-alt"></i> <span class="lang-fr">Capacité à communiquer efficacement en contexte technique et industriel.</span><span class="lang-en">Ability to communicate effectively in technical and industrial contexts.</span></p>
        </div></div></div>
    </section>

    <section id="certifications" class="certifications-modern" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title"><i class="fas fa-certificate"></i> <span class="lang-fr">Certifications industrielles</span><span class="lang-en">Industrial Certifications</span></h2>
            <div class="certifications-grid">
                <div class="cert-card" data-cert="pcs7">
                    <div class="cert-header"><div class="cert-icon"><i class="fas fa-microchip"></i><span class="cert-year">2025</span></div></div>
                    <div class="cert-body">
                        <div class="cert-title">SIMATIC PCS7 Expert</div>
                        <div class="cert-issuer"><i class="fas fa-building"></i> TECHNORD (Belgique / Belgium)</div>
                        <div class="cert-description"><span class="lang-fr">Certification avancée sur le système DCS Siemens SIMATIC PCS7.</span><span class="lang-en">Advanced certification on Siemens SIMATIC PCS7 DCS system.</span></div>
                        <div class="cert-skills"><span>Gestion de projets PCS7</span><span>Programmation CFC/SFC</span><span>Configuration PROFIBUS & PROFINET</span><span>Développement d'interfaces OS</span></div>
                    </div>
                </div>
                <div class="cert-card" data-cert="maintenance">
                    <div class="cert-header"><div class="cert-icon"><i class="fas fa-tools"></i><span class="cert-year">2025</span></div></div>
                    <div class="cert-body">
                        <div class="cert-title">SIMATIC Maintenance Niveau 1 / Level 1</div>
                        <div class="cert-issuer"><i class="fas fa-building"></i> CFIC GICA</div>
                        <div class="cert-description"><span class="lang-fr">Certification en maintenance des systèmes SIMATIC S7.</span><span class="lang-en">Certification in SIMATIC S7 systems maintenance.</span></div>
                        <div class="cert-skills"><span>Diagnostic d'automates S7</span><span>Dépannage systèmes automatisés</span><span>Maintenance préventive et corrective</span><span>Lecture d'architectures industrielles</span></div>
                    </div>
                </div>
                <div class="cert-card" data-cert="indmaintenance">
                    <div class="cert-header"><div class="cert-icon"><i class="fas fa-industry"></i><span class="cert-year">2023</span></div></div>
                    <div class="cert-body">
                        <div class="cert-title"><span class="lang-fr">Maintenance Industrielle</span><span class="lang-en">Industrial Maintenance</span></div>
                        <div class="cert-issuer"><i class="fas fa-building"></i> INPED</div>
                        <div class="cert-description"><span class="lang-fr">Certification en gestion et stratégies de maintenance industrielle.</span><span class="lang-en">Certification in industrial maintenance management and strategies.</span></div>
                        <div class="cert-skills"><span>Gestion de maintenance</span><span>Stratégie préventive et corrective</span><span>Maintenance conditionnelle</span><span>Planification d'interventions</span></div>
                    </div>
                </div>
                <div class="cert-card" data-cert="safety">
                    <div class="cert-header"><div class="cert-icon"><i class="fas fa-hard-hat"></i><span class="cert-year">2020</span></div></div>
                    <div class="cert-body">
                        <div class="cert-title"><span class="lang-fr">Sécurité Industrielle</span><span class="lang-en">Industrial Safety</span></div>
                        <div class="cert-issuer"><i class="fas fa-building"></i> IFACT</div>
                        <div class="cert-description"><span class="lang-fr">Certification aux principes fondamentaux de la sécurité industrielle.</span><span class="lang-en">Certification in fundamental industrial safety principles.</span></div>
                        <div class="cert-skills"><span>Analyse des risques industriels</span><span>Gestion des situations critiques</span><span>Intervention en zone dangereuse</span><span>Premiers secours</span></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <div id="certModal" class="cert-modal">
        <div class="cert-modal-content">
            <span class="cert-modal-close">&times;</span>
            <div class="cert-modal-icon" id="certModalIcon"></div>
            <h3 id="certModalTitle"></h3>
            <div class="cert-modal-issuer" id="certModalIssuer"></div>
            <div class="cert-modal-date" id="certModalDate"></div>
            <p class="cert-modal-desc" id="certModalDesc"></p>
            <div class="cert-modal-skills" id="certModalSkills"></div>
        </div>
    </div>
    
    <section id="stages" class="stages-modern" data-aos="fade-up">
        <div class="container">
            <h2 class="section-title"><i class="fas fa-briefcase"></i> <span class="lang-fr">Stages & projets terrain</span><span class="lang-en">Internships & Field Projects</span></h2>
            <div class="stages-grid">
                <div class="stage-card" data-stage="henkel">
                    <div class="stage-header">
                        <div class="stage-icon"><i class="fas fa-industry"></i></div>
                        <div class="stage-company"><h3>Henkel</h3><span class="stage-date">2022</span></div>
                    </div>
                    <div class="stage-title"><i class="fas fa-tint"></i> <span class="lang-fr">Automatisation station traitement des eaux</span><span class="lang-en">Water Treatment Plant Automation</span></div>
                    <div class="stage-description"><span class="lang-fr">Projet de fin d'étude - Conception et programmation d'un système d'automatisation pour la station de traitement des eaux.</span><span class="lang-en">Final year project - Design and programming of an automation system for the water treatment plant.</span></div>
                    <div class="stage-tech"><span>PLC Siemens</span><span>WinCC</span><span>PROFIBUS</span><span><span class="lang-fr">Instrumentation</span><span class="lang-en">Instrumentation</span></span></div>
                </div>
                <div class="stage-card" data-stage="lmelectric">
                    <div class="stage-header">
                        <div class="stage-icon"><i class="fas fa-microchip"></i></div>
                        <div class="stage-company"><h3>LM Electric Sarl</h3><span class="stage-date">2022</span></div>
                    </div>
                    <div class="stage-title"><i class="fas fa-cogs"></i> <span class="lang-fr">Station concassage pouzzolane</span><span class="lang-en">Pozzolana Crushing Station</span></div>
                    <div class="stage-description"><span class="lang-fr">Automaticien - Mise en service et programmation des automates pour une station de concassage.</span><span class="lang-en">Automation Engineer - Commissioning and programming of PLCs for a crushing station.</span></div>
                    <div class="stage-tech"><span><span class="lang-fr">Automates</span><span class="lang-en">PLCs</span></span><span>Schneider</span><span><span class="lang-fr">Variateur</span><span class="lang-en">Drive</span></span><span><span class="lang-fr">Supervision</span><span class="lang-en">Supervision</span></span></div>
                </div>
                <div class="stage-card" data-stage="bkfire">
                    <div class="stage-header">
                        <div class="stage-icon"><i class="fas fa-bolt"></i></div>
                        <div class="stage-company"><h3>BK FIRE</h3><span class="stage-date">2022</span></div>
                    </div>
                    <div class="stage-title"><i class="fas fa-plug"></i> <span class="lang-fr">Câblage armoires électriques</span><span class="lang-en">Electrical Cabinet Wiring</span></div>
                    <div class="stage-description"><span class="lang-fr">Électricien industriel - Réalisation de câblages d'armoires électriques et tableaux de commande.</span><span class="lang-en">Industrial Electrician - Electrical cabinet and control panel wiring.</span></div>
                    <div class="stage-tech"><span><span class="lang-fr">Schémas électriques</span><span class="lang-en">Electrical Diagrams</span></span><span><span class="lang-fr">Câblage</span><span class="lang-en">Wiring</span></span><span><span class="lang-fr">Borniers</span><span class="lang-en">Terminal Blocks</span></span><span><span class="lang-fr">Normes IEC</span><span class="lang-en">IEC Standards</span></span></div>
                </div>
                <div class="stage-card" data-stage="celia">
                    <div class="stage-header">
                        <div class="stage-icon"><i class="fas fa-wrench"></i></div>
                        <div class="stage-company"><h3>Celia Algérie</h3><span class="stage-date">2020</span></div>
                    </div>
                    <div class="stage-title"><i class="fas fa-stethoscope"></i> <span class="lang-fr">Diagnostic & maintenance préventive</span><span class="lang-en">Diagnostics & Preventive Maintenance</span></div>
                    <div class="stage-description"><span class="lang-fr">Maintenancier - Diagnostic de pannes et mise en place de maintenance préventive sur lignes de production.</span><span class="lang-en">Maintenance Technician - Fault diagnosis and preventive maintenance implementation on production lines.</span></div>
                    <div class="stage-tech"><span><span class="lang-fr">Maintenance</span><span class="lang-en">Maintenance</span></span><span><span class="lang-fr">Diagnostic</span><span class="lang-en">Diagnostics</span></span><span>GMP</span><span><span class="lang-fr">Analyse causes</span><span class="lang-en">Root Cause Analysis</span></span></div>
                </div>
            </div>
        </div>
    </section>
</main>

<footer>
    <div class="container">
        <div class="footer-content">
            <div class="footer-contact">
                <h3><i class="fas fa-address-card"></i> <span class="lang-fr">Coordonnées</span><span class="lang-en">Contact</span></h3>
                <div class="animated-contact">
                    <div class="contact-item"><i class="fas fa-envelope"></i><span>meziani.nabil.dz@gmail.com</span></div>
                    <div class="contact-item"><i class="fas fa-phone-alt"></i><span>+213 784 21 54 67</span></div>
                    <div class="contact-item"><i class="fas fa-map-marker-alt"></i><span class="lang-fr">Alger, Algérie</span><span class="lang-en">Algiers, Algeria</span></div>
                </div>
            </div>
            <div class="footer-social">
                <h3><i class="fas fa-users"></i> <span class="lang-fr">Professionnel</span><span class="lang-en">Professional</span></h3>
                <div class="social-links">
                    <a href="https://www.linkedin.com/in/nabilmeziani/" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin"></i> LinkedIn</a>
                    <a href="#" target="_blank"><i class="fab fa-github"></i> GitHub</a>
                </div>
                <div class="footer-note">
                    <i class="fas fa-briefcase"></i> 
                    <span class="lang-fr">Disponible pour opportunités</span>
                    <span class="lang-en">Open to opportunities</span>
                </div>
            </div>
        </div>
        <div class="copyright">
            <p>© 2025 Nabil Meziani - <span class="lang-fr">Ingénieur Automatisme & Instrumentation</span><span class="lang-en">Automation & Instrumentation Engineer</span></p>
        </div>
    </div>
</footer>

<div id="activityModal" class="modal">
    <div class="modal-content">
        <span class="modal-close">&times;</span>
        <div class="modal-icon" id="modalIcon"></div>
        <h3 id="modalTitle"></h3>
        <p class="modal-desc" id="modalDesc"></p>
        <div class="modal-details" id="modalDetails"></div>
        <hr>
        <div class="modal-tech" id="modalTech"></div>
        <div class="skills-list-modal" id="skillsListModal"></div>
    </div>
</div>

<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<script>
    AOS.init({ duration: 700, once: true, offset: 80 });
    
    const activitiesData = [
        { id: 0, imgUrl: "images/maintenance.png", icon: "fas fa-tools", title_fr: "MAINTENANCE", title_en: "MAINTENANCE", short_fr: "Dépannage, réparation, optimisation de systèmes informatiques", short_en: "Troubleshooting, repair, optimization of IT systems", desc_fr: "Intervention rapide sur pannes matérielles et logicielles, optimisation des performances, maintenance préventive et corrective pour infrastructures critiques.", desc_en: "Rapid intervention on hardware and software failures, performance optimization, preventive and corrective maintenance for critical infrastructures.", details_fr: "⏱️ Durée typique : 1 à 5 jours | 💰 Tarif : sur devis", details_en: "⏱️ Typical duration: 1-5 days | 💰 Price: on quote", tech: "PLC, SCADA, TIA Portal, Outils diagnostiques" },
        { id: 1, imgUrl: "https://picsum.photos/id/102/1200/700", icon: "fas fa-code", title_fr: "PROGRAMMATION", title_en: "PROGRAMMING", short_fr: "Développement web, applications, scripts sur mesure", short_en: "Web development, applications, custom scripts", desc_fr: "Création d'applications métier, scripts d'automatisation, interfaces web interactives.", desc_en: "Creation of business applications, automation scripts, interactive web interfaces.", details_fr: "⏱️ Délai moyen : 2 à 8 semaines | 💰 Devis personnalisé", details_en: "⏱️ Average lead time: 2-8 weeks | 💰 Custom quote", tech: "Python, JavaScript, React, Node.js, SQL" },
        { id: 2, imgUrl: "https://picsum.photos/id/103/1200/700", icon: "fas fa-chalkboard-user", title_fr: "FORMATEUR", title_en: "TRAINER", short_fr: "Formation en informatique, pédagogie, accompagnement", short_en: "IT training, pedagogy, coaching", desc_fr: "Sessions de formation sur mesure pour équipes ou particuliers : automatisme, programmation, instrumentation.", desc_en: "Tailored training sessions for teams or individuals: automation, programming, instrumentation.", details_fr: "📚 Modules : 1 à 3 jours | 🎯 Groupes jusqu'à 12 pers.", details_en: "📚 Modules: 1-3 days | 🎯 Groups up to 12 pers.", tech: "LMS, supports interactifs, ateliers pratiques" },
        { id: 3, imgUrl: "https://picsum.photos/id/104/1200/700", icon: "fas fa-newspaper", title_fr: "INFO TECHNIQUE", title_en: "TECH INFO", short_fr: "Veille technologique, documentation, conseil", short_en: "Technology watch, documentation, consulting", desc_fr: "Veille active sur les nouvelles technologies industrielles, rédaction de documentations techniques.", desc_en: "Active technology watch on new industrial technologies, technical documentation writing.", details_fr: "📅 Veille mensuelle | 📑 Rédaction technique", details_en: "📅 Monthly watch | 📑 Technical writing", tech: "Outils de veille, Rédaction technique, Gestion documentaire" },
        { id: 4, imgUrl: "https://picsum.photos/id/105/1200/700", icon: "fas fa-project-diagram", title_fr: "RÉALISATION PROJET", title_en: "PROJECT DELIVERY", short_fr: "Gestion de projet, livraison de solutions complètes", short_en: "Project management, end-to-end solution delivery", desc_fr: "Pilotage de projets techniques de la conception à la livraison.", desc_en: "Management of technical projects from design to delivery.", details_fr: "📆 Durée : selon complexité | 📊 Méthodologie agile", details_en: "📆 Duration: depending on complexity | 📊 Agile methodology", tech: "MS Project, Jira, Méthodes Agiles" }
    ];

    let currentLang = localStorage.getItem('lang') || 'fr';
    let currentIndex = 0;
    let autoPlayInterval;
    let track = document.getElementById('carouselTrack');
    let dotsContainer = document.getElementById('carouselDots');
    let isDragging = false;
    let startX = 0;
    let initialIndex = 0;

    function buildSlides() {
        if(!track) return;
        track.innerHTML = '';
        activitiesData.forEach((act, idx) => {
            let slide = document.createElement('div');
            slide.className = 'carousel-slide';
            slide.innerHTML = `<img src="${act.imgUrl}" alt="${act.title_fr}" loading="lazy"><div class="slide-overlay"><h3>${currentLang === 'fr' ? act.title_fr : act.title_en}</h3><div class="desc-row"><p>${currentLang === 'fr' ? act.short_fr : act.short_en}</p><div class="click-details-btn" data-index="${idx}"><i class="fas fa-info-circle"></i><span class="lang-fr">✨ Cliquez pour détails</span><span class="lang-en">✨ Click for details</span></div></div></div>`;
            let btn = slide.querySelector('.click-details-btn');
            btn.addEventListener('click', (e) => { e.stopPropagation(); openModal(idx); });
            slide.querySelector('img').addEventListener('click', () => openModal(idx));
            slide.querySelector('.slide-overlay').addEventListener('click', (e) => { if(!e.target.closest('.click-details-btn')) openModal(idx); });
            track.appendChild(slide);
        });
        updateDots();
        updateCarouselPosition();
    }

    function updateDots() {
        if(!dotsContainer) return;
        dotsContainer.innerHTML = '';
        activitiesData.forEach((_, idx) => {
            let dot = document.createElement('div');
            dot.classList.add('dot');
            if(idx === currentIndex) dot.classList.add('active');
            dot.addEventListener('click', () => { currentIndex = idx; updateCarouselPosition(); updateDots(); resetAutoPlay(); });
            dotsContainer.appendChild(dot);
        });
    }

    function updateCarouselPosition() {
        if(!track || !track.children.length) return;
        let slideWidth = track.children[0].offsetWidth;
        track.style.transform = `translateX(-${currentIndex * slideWidth}px)`;
        document.querySelectorAll('.dot').forEach((dot, i) => { dot.classList.toggle('active', i === currentIndex); });
    }

    function nextSlide() { currentIndex = (currentIndex + 1) % activitiesData.length; updateCarouselPosition(); resetAutoPlay(); }
    function prevSlide() { currentIndex = (currentIndex - 1 + activitiesData.length) % activitiesData.length; updateCarouselPosition(); resetAutoPlay(); }
    function startAutoPlay() { if(autoPlayInterval) clearInterval(autoPlayInterval); autoPlayInterval = setInterval(() => nextSlide(), 5000); }
    function stopAutoPlay() { if(autoPlayInterval) clearInterval(autoPlayInterval); }
    function resetAutoPlay() { stopAutoPlay(); startAutoPlay(); }

    function initDrag() {
        if(!track) return;
        track.addEventListener('mousedown', (e) => { if(e.button !== 0) return; stopAutoPlay(); startX = e.clientX; initialIndex = currentIndex; track.style.transition = 'none'; isDragging = true; track.style.cursor = 'grabbing'; e.preventDefault(); });
        window.addEventListener('mousemove', (e) => { if(!isDragging || !track.children.length) return; let diff = e.clientX - startX; let slideWidth = track.children[0]?.offsetWidth || 0; let newIndex = initialIndex - (diff / slideWidth); newIndex = Math.min(Math.max(newIndex, 0), activitiesData.length - 1); track.style.transform = `translateX(-${newIndex * slideWidth}px)`; });
        window.addEventListener('mouseup', () => { if(!isDragging) return; isDragging = false; if(!track.children.length) return; let slideWidth = track.children[0]?.offsetWidth || 0; let transform = track.style.transform; let match = transform.match(/translateX\(-([\d.]+)px\)/); let newIdx = match ? Math.round(parseFloat(match[1]) / slideWidth) : currentIndex; currentIndex = Math.min(Math.max(newIdx, 0), activitiesData.length - 1); track.style.transition = 'transform 0.5s cubic-bezier(0.2, 0.9, 0.4, 1.1)'; updateCarouselPosition(); startAutoPlay(); track.style.cursor = 'grab'; });
        track.addEventListener('touchstart', (e) => { stopAutoPlay(); startX = e.touches[0].clientX; initialIndex = currentIndex; track.style.transition = 'none'; isDragging = true; });
        window.addEventListener('touchmove', (e) => { if(!isDragging || !track.children.length) return; let diff = e.touches[0].clientX - startX; let slideWidth = track.children[0]?.offsetWidth || 0; let newIndex = initialIndex - (diff / slideWidth); newIndex = Math.min(Math.max(newIndex, 0), activitiesData.length - 1); track.style.transform = `translateX(-${newIndex * slideWidth}px)`; });
        window.addEventListener('touchend', () => { if(!isDragging) return; isDragging = false; if(!track.children.length) return; let slideWidth = track.children[0]?.offsetWidth || 0; let transform = track.style.transform; let match = transform.match(/translateX\(-([\d.]+)px\)/); let newIdx = match ? Math.round(parseFloat(match[1]) / slideWidth) : currentIndex; currentIndex = Math.min(Math.max(newIdx, 0), activitiesData.length - 1); track.style.transition = 'transform 0.5s cubic-bezier(0.2, 0.9, 0.4, 1.1)'; updateCarouselPosition(); startAutoPlay(); });
    }

    function openModal(index) {
        let act = activitiesData[index];
        document.getElementById('modalIcon').innerHTML = `<i class="${act.icon}"></i>`;
        document.getElementById('modalTitle').innerText = currentLang === 'fr' ? act.title_fr : act.title_en;
        document.getElementById('modalDesc').innerText = currentLang === 'fr' ? act.desc_fr : act.desc_en;
        document.getElementById('modalDetails').innerHTML = `<i class="fas fa-info-circle"></i> ${currentLang === 'fr' ? act.details_fr : act.details_en}`;
        document.getElementById('modalTech').innerHTML = `<strong>${currentLang === 'fr' ? 'Technologies clés :' : 'Key technologies:'}</strong> ${act.tech}`;
        document.getElementById('skillsListModal').innerHTML = '';
        document.getElementById('activityModal').classList.add('show');
        document.body.style.overflow = 'hidden';
    }
    
    function closeModal() { document.getElementById('activityModal').classList.remove('show'); document.body.style.overflow = ''; }

    buildSlides();
    startAutoPlay();
    initDrag();
    window.addEventListener('resize', () => updateCarouselPosition());
    document.getElementById('prevBtn')?.addEventListener('click', () => { prevSlide(); resetAutoPlay(); });
    document.getElementById('nextBtn')?.addEventListener('click', () => { nextSlide(); resetAutoPlay(); });
    document.querySelector('.carousel-wrapper')?.addEventListener('mouseenter', stopAutoPlay);
    document.querySelector('.carousel-wrapper')?.addEventListener('mouseleave', startAutoPlay);
    document.querySelector('.modal-close')?.addEventListener('click', closeModal);
    window.addEventListener('click', (e) => { if(e.target === document.getElementById('activityModal')) closeModal(); });

    // Navigation et thème
    document.getElementById('homeLogo')?.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));
    document.getElementById('mobileMenuBtn')?.addEventListener('click', (e) => { e.stopPropagation(); document.getElementById('mobileDropdown')?.classList.toggle('active'); });
    document.addEventListener('click', (e) => { let dd = document.getElementById('mobileDropdown'); if(dd && !dd.contains(e.target) && e.target !== document.getElementById('mobileMenuBtn')) dd.classList.remove('active'); });
    
    // CV Quick Button
    document.getElementById('cvQuickBtn')?.addEventListener('click', () => {
        window.location.href = 'CVs.html';
    });
    document.getElementById('portfolioBtn')?.addEventListener('click', (e) => {
        e.preventDefault();
        window.location.href = 'CVs.html';
    });
    
    let themeToggle = document.getElementById('themeToggle');
    if(localStorage.getItem('theme') === 'dark') document.body.classList.add('dark');
    themeToggle?.addEventListener('click', () => { document.body.classList.toggle('dark'); localStorage.setItem('theme', document.body.classList.contains('dark') ? 'dark' : 'light'); });
    
    let langSwitch = document.getElementById('langSwitch');
    document.body.setAttribute('data-lang', currentLang);
    langSwitch.textContent = currentLang === 'fr' ? '🇬🇧 EN' : '🇫🇷 FR';
    langSwitch?.addEventListener('click', () => {
        let newLang = document.body.getAttribute('data-lang') === 'fr' ? 'en' : 'fr';
        document.body.setAttribute('data-lang', newLang);
        localStorage.setItem('lang', newLang);
        currentLang = newLang;
        langSwitch.textContent = newLang === 'fr' ? '🇬🇧 EN' : '🇫🇷 FR';
        let trans = { home:{fr:'Accueil',en:'Home'}, availability:{fr:'Disponibilité',en:'Availability'}, expertise:{fr:'Expertise',en:'Expertise'}, exp:{fr:'Expériences',en:'Experience'}, skills:{fr:'Compétences',en:'Skills'}, diplomas:{fr:'Diplômes',en:'Degrees'}, training:{fr:'Formations',en:'Training'}, lang:{fr:'Langues',en:'Languages'}, cert:{fr:'Certifications',en:'Certifications'}, stages:{fr:'Stages',en:'Internships'} };
        document.querySelectorAll('[data-translate]').forEach(el => { let key = el.getAttribute('data-translate'); if(trans[key]) el.innerText = trans[key][newLang]; });
        buildSlides();
    });
    
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            e.preventDefault();
            let target = document.querySelector(this.getAttribute('href'));
            if(target) { target.scrollIntoView({ behavior: 'smooth' }); document.getElementById('mobileDropdown')?.classList.remove('active'); }
        });
    });

    // Skills modal data
    const skillsData = {
        dcs: { title_fr: "DCS (Distributed Control System)", title_en: "DCS (Distributed Control System)", desc_fr: "Systèmes de contrôle distribués pour la gestion de processus industriels complexes.", desc_en: "Distributed control systems for complex industrial process management.", skills: ["Configuration DCS", "Siemens PCS7", "Contrôle distribué", "Redondance"] },
        plc: { title_fr: "PLC (Programmable Logic Controller)", title_en: "PLC (Programmable Logic Controller)", desc_fr: "Programmation d'automates programmables industriels.", desc_en: "Programming of industrial programmable logic controllers.", skills: ["Siemens S7", "Schneider Modicon", "TIA Portal", "STEP 7"] },
        scada: { title_fr: "SCADA (Supervisory Control And Data Acquisition)", title_en: "SCADA", desc_fr: "Systèmes de supervision et d'acquisition de données.", desc_en: "Supervision and data acquisition systems.", skills: ["WinCC", "Citect", "Wonderware", "iFIX"] },
        calibration: { title_fr: "Calibration & HART", title_en: "Calibration & HART", desc_fr: "Étalonnage d'instruments industriels et protocole HART.", desc_en: "Industrial instrument calibration and HART protocol.", skills: ["Calibration pression/température", "HART communicator", "Boucles 4-20mA", "Transmetteurs"] },
        tia: { title_fr: "TIA Portal", title_en: "TIA Portal", desc_fr: "Environnement de développement Siemens Totally Integrated Automation.", desc_en: "Siemens Totally Integrated Automation development environment.", skills: ["Programmation S7-1200/1500", "WinCC intégré", "PROFINET", "Bibliothèques avancées"] },
        step7: { title_fr: "STEP 7", title_en: "STEP 7", desc_fr: "Logiciel de programmation Siemens pour automates S7-300/400.", desc_en: "Siemens programming software for S7-300/400 PLCs.", skills: ["Ladder", "STL", "FBD", "S7-Graph"] },
        pcs7: { title_fr: "SIMATIC PCS 7", title_en: "SIMATIC PCS 7", desc_fr: "Système DCS Siemens pour process industries.", desc_en: "Siemens DCS system for process industries.", skills: ["CFC/SFC", "OS clients/serveurs", "Redondance", "Batch"] },
        wincc: { title_fr: "WinCC", title_en: "WinCC", desc_fr: "Logiciel de supervision Siemens.", desc_en: "Siemens supervision software.", skills: ["Scripts VBS/C", "Archives", "Alarmes", "Tendances"] },
        profibus: { title_fr: "PROFIBUS & PROFINET", title_en: "PROFIBUS & PROFINET", desc_fr: "Réseaux industriels de terrain.", desc_en: "Industrial field networks.", skills: ["Configuration maître/esclave", "Topologies PROFINET", "Diagnostic réseau", "GSDML"] },
        office: { title_fr: "Microsoft Office", title_en: "Microsoft Office", desc_fr: "Suite bureautique complète.", desc_en: "Complete office suite.", skills: ["Excel avancé", "Word", "PowerPoint", "Outlook"] }
    };
    
    document.querySelectorAll('.skill-tag').forEach(tag => {
        tag.addEventListener('click', () => {
            let key = tag.getAttribute('data-skill');
            let s = skillsData[key];
            if(s) {
                let isFr = document.body.getAttribute('data-lang') === 'fr';
                document.getElementById('modalIcon').innerHTML = '<i class="fas fa-microchip"></i>';
                document.getElementById('modalTitle').innerText = isFr ? s.title_fr : s.title_en;
                document.getElementById('modalDesc').innerText = isFr ? s.desc_fr : s.desc_en;
                document.getElementById('modalDetails').innerHTML = '<i class="fas fa-info-circle"></i> ' + (isFr ? 'Compétences associées' : 'Associated skills');
                document.getElementById('modalTech').innerHTML = '';
                let skillsHtml = '<div class="skills-list-modal">' + s.skills.map(sk => `<span>${sk}</span>`).join('') + '</div>';
                document.getElementById('skillsListModal').innerHTML = skillsHtml;
                document.getElementById('activityModal').classList.add('show');
                document.body.style.overflow = 'hidden';
            }
        });
    });

    // Certifications modal
    const certDetails = {
        pcs7: { icon: '<i class="fas fa-microchip"></i>', title: 'SIMATIC PCS7 Expert', issuer: 'TECHNORD (Belgique / Belgium)', date: 'Novembre 2025 / November 2025', desc: 'Formation approfondie sur le système DCS Siemens SIMATIC PCS7. Maîtrise des projets CFC/SFC, création d\'OS graphiques, mise en place de redondance serveur/client.', desc_en: 'Advanced training on Siemens SIMATIC PCS7 DCS system. Mastery of CFC/SFC projects, graphic OS creation, server/client redundancy setup.', skills: ['Gestion de projets PCS7', 'Programmation CFC/SFC', 'Configuration PROFIBUS & PROFINET', 'Développement d\'interfaces OS'] },
        maintenance: { icon: '<i class="fas fa-tools"></i>', title: 'SIMATIC Maintenance Niveau 1 / Level 1', issuer: 'CFIC GICA', date: 'Septembre 2025 / September 2025', desc: 'Certification en maintenance des systèmes SIMATIC S7. Acquisition des compétences en diagnostic avancé, dépannage des automates S7.', desc_en: 'Certification in SIMATIC S7 systems maintenance. Skills acquired in advanced diagnostics, S7 PLC troubleshooting.', skills: ['Diagnostic d\'automates S7', 'Dépannage systèmes automatisés', 'Maintenance préventive et corrective', 'Lecture d\'architectures industrielles'] },
        indmaintenance: { icon: '<i class="fas fa-industry"></i>', title: 'Maintenance Industrielle / Industrial Maintenance', issuer: 'INPED', date: 'Octobre 2023 / October 2023', desc: 'Certification en gestion et stratégies de maintenance industrielle. Maîtrise des concepts TPM et GMAO.', desc_en: 'Certification in industrial maintenance management and strategies. Mastery of TPM and CMMS concepts.', skills: ['Gestion de maintenance', 'Stratégie préventive et corrective', 'Maintenance conditionnelle', 'Planification d\'interventions'] },
        safety: { icon: '<i class="fas fa-hard-hat"></i>', title: 'Sécurité Industrielle / Industrial Safety', issuer: 'IFACT', date: 'Décembre 2020 / December 2020', desc: 'Certification aux principes fondamentaux de la sécurité industrielle. Prévention des risques et conformité aux normes ISO 45001.', desc_en: 'Certification in fundamental industrial safety principles. Risk prevention and ISO 45001 standards compliance.', skills: ['Analyse des risques industriels', 'Gestion des situations critiques', 'Intervention en zone dangereuse', 'Premiers secours'] }
    };
    
    document.querySelectorAll('.cert-card').forEach(card => {
        card.addEventListener('click', () => {
            let key = card.getAttribute('data-cert');
            let cert = certDetails[key];
            if(cert && document.getElementById('certModal')) {
                document.getElementById('certModalIcon').innerHTML = cert.icon;
                document.getElementById('certModalTitle').innerText = cert.title;
                document.getElementById('certModalIssuer').innerHTML = `<i class="fas fa-building"></i> ${cert.issuer}`;
                document.getElementById('certModalDate').innerHTML = `<i class="far fa-calendar-alt"></i> ${cert.date}`;
                let descText = currentLang === 'fr' ? cert.desc : cert.desc_en;
                document.getElementById('certModalDesc').innerText = descText;
                document.getElementById('certModalSkills').innerHTML = cert.skills.map(s => `<span>${s}</span>`).join('');
                document.getElementById('certModal').classList.add('show');
                document.body.style.overflow = 'hidden';
            }
        });
    });
    document.querySelector('.cert-modal-close')?.addEventListener('click', () => { document.getElementById('certModal')?.classList.remove('show'); document.body.style.overflow = ''; });
    window.addEventListener('click', (e) => { if(e.target === document.getElementById('certModal')) { document.getElementById('certModal').classList.remove('show'); document.body.style.overflow = ''; } });

    // Training cards modal
    const trainingDetails = {
        pcs7: { icon: 'fas fa-microchip', title_fr: 'SIMATIC PCS7 Expert', title_en: 'SIMATIC PCS7 Expert', desc_fr: 'Formation approfondie sur le système DCS Siemens SIMATIC PCS7. Cette certification avancée couvre la création de projets CFC/SFC, la conception d\'OS graphiques, la mise en place de redondance serveur/client et la configuration avancée des systèmes distribués.', desc_en: 'Advanced training on Siemens SIMATIC PCS7 DCS system. This certification covers CFC/SFC project creation, graphic OS design, server/client redundancy setup, and advanced distributed system configuration.', details_fr: '📅 Novembre 2025 | 🏢 TECHNORD (Belgique) | ✅ Certifié', details_en: '📅 November 2025 | 🏢 TECHNORD (Belgium) | ✅ Certified', tech_fr: 'Gestion de projets PCS7, Programmation CFC/SFC, Configuration PROFIBUS & PROFINET, Développement d\'interfaces OS', tech_en: 'PCS7 Project Management, CFC/SFC Programming, PROFIBUS & PROFINET Configuration, OS Interface Development' },
        maintenance: { icon: 'fas fa-wrench', title_fr: 'SIMATIC Maintenance Niveau 1', title_en: 'SIMATIC Maintenance Level 1', desc_fr: 'Formation à la maintenance des systèmes SIMATIC S7. Acquisition des compétences en diagnostic avancé, dépannage des automates S7, compréhension des architectures industrielles et utilisation des outils de monitoring.', desc_en: 'Training on SIMATIC S7 systems maintenance. Skills acquired: advanced diagnostics, S7 PLC troubleshooting, industrial architectures understanding, and monitoring tools usage.', details_fr: '📅 Septembre 2025 | 🏢 CFIC GICA | ✅ Certifié', details_en: '📅 September 2025 | 🏢 CFIC GICA | ✅ Certified', tech_fr: 'Diagnostic d\'automates S7, Dépannage systèmes automatisés, Maintenance préventive et corrective, Lecture d\'architectures industrielles', tech_en: 'S7 PLC Diagnostics, Automated Systems Troubleshooting, Preventive & Corrective Maintenance, Industrial Architecture Reading' },
        seminar: { icon: 'fas fa-chart-line', title_fr: 'Séminaire Maintenance industrielle', title_en: 'Industrial Maintenance Seminar', desc_fr: 'Séminaire sur les stratégies modernes de maintenance industrielle. Couvre la gestion de maintenance, les stratégies TPM, la définition d\'indicateurs de performance et la planification des interventions.', desc_en: 'Seminar on modern industrial maintenance strategies. Covers maintenance management, TPM strategies, performance indicators definition, and intervention planning.', details_fr: '📅 Octobre 2023 | 🏢 INPED', details_en: '📅 October 2023 | 🏢 INPED', tech_fr: 'Gestion de maintenance, Stratégie préventive et corrective, Maintenance conditionnelle, Planification d\'interventions', tech_en: 'Maintenance Management, Preventive & Corrective Strategy, Condition-Based Maintenance, Intervention Planning' },
        safety: { icon: 'fas fa-shield-alt', title_fr: 'Sécurité industrielle', title_en: 'Industrial Safety', desc_fr: 'Formation aux principes fondamentaux de la sécurité en milieu industriel. Couvre les principes de sécurité, la prévention des risques, la gestion des risques et les premiers secours.', desc_en: 'Training on fundamental principles of industrial safety. Covers safety principles, risk prevention, risk management, and first aid.', details_fr: '📅 Décembre 2020 | 🏢 IFACT', details_en: '📅 December 2020 | 🏢 IFACT', tech_fr: 'Analyse des risques industriels, Gestion des situations critiques, Intervention en zone dangereuse, Premiers secours', tech_en: 'Industrial Risk Analysis, Critical Situation Management, Dangerous Zone Intervention, First Aid' }
    };
    
    document.querySelectorAll('.training-content').forEach(card => {
        card.addEventListener('click', () => {
            let key = card.getAttribute('data-training');
            let t = trainingDetails[key];
            if(t) {
                document.getElementById('modalIcon').innerHTML = `<i class="${t.icon}"></i>`;
                document.getElementById('modalTitle').innerText = currentLang === 'fr' ? t.title_fr : t.title_en;
                document.getElementById('modalDesc').innerText = currentLang === 'fr' ? t.desc_fr : t.desc_en;
                document.getElementById('modalDetails').innerHTML = `<i class="fas fa-info-circle"></i> ${currentLang === 'fr' ? t.details_fr : t.details_en}`;
                let techText = currentLang === 'fr' ? t.tech_fr : t.tech_en;
                document.getElementById('modalTech').innerHTML = `<strong>${currentLang === 'fr' ? 'Compétences acquises :' : 'Skills acquired:'}</strong> ${techText}`;
                document.getElementById('skillsListModal').innerHTML = '';
                document.getElementById('activityModal').classList.add('show');
                document.body.style.overflow = 'hidden';
            }
        });
    });

    // Stage cards modal
    const stageDetails = {
        henkel: { icon: 'fas fa-industry', title_fr: 'Henkel - Automatisation station traitement des eaux', title_en: 'Henkel - Water Treatment Plant Automation', desc_fr: 'Projet de fin d\'étude réalisé chez Henkel. Conception et programmation d\'un système d\'automatisation complet pour la station de traitement des eaux, incluant la programmation d\'automates Siemens, la supervision sous WinCC et la communication PROFIBUS.', desc_en: 'Final year project at Henkel. Design and programming of a complete automation system for the water treatment plant, including Siemens PLC programming, WinCC supervision, and PROFIBUS communication.', details_fr: '📅 2022 | 🏢 Henkel | 📍 Alger', details_en: '📅 2022 | 🏢 Henkel | 📍 Algiers', tech_fr: 'PLC Siemens, WinCC, PROFIBUS, Instrumentation', tech_en: 'Siemens PLC, WinCC, PROFIBUS, Instrumentation' },
        lmelectric: { icon: 'fas fa-microchip', title_fr: 'LM Electric - Station concassage pouzzolane', title_en: 'LM Electric - Pozzolana Crushing Station', desc_fr: 'Mission en tant qu\'automaticien pour la mise en service et la programmation des automates d\'une station de concassage de pouzzolane. Travail sur automates Schneider, variateurs de vitesse et supervision.', desc_en: 'Assignment as automation engineer for commissioning and programming of PLCs for a pozzolana crushing station. Work on Schneider PLCs, variable speed drives, and supervision.', details_fr: '📅 2022 | 🏢 LM Electric Sarl | 📍 Alger', details_en: '📅 2022 | 🏢 LM Electric Sarl | 📍 Algiers', tech_fr: 'Automates Schneider, Variateurs, Supervision', tech_en: 'Schneider PLCs, Drives, Supervision' },
        bkfire: { icon: 'fas fa-bolt', title_fr: 'BK FIRE - Câblage armoires électriques', title_en: 'BK FIRE - Electrical Cabinet Wiring', desc_fr: 'Expérience en tant qu\'électricien industriel. Réalisation de câblages d\'armoires électriques et tableaux de commande selon les schémas électriques et normes IEC.', desc_en: 'Experience as industrial electrician. Electrical cabinet and control panel wiring according to electrical diagrams and IEC standards.', details_fr: '📅 2022 | 🏢 BK FIRE | 📍 Alger', details_en: '📅 2022 | 🏢 BK FIRE | 📍 Algiers', tech_fr: 'Schémas électriques, Câblage, Borniers, Normes IEC', tech_en: 'Electrical Diagrams, Wiring, Terminal Blocks, IEC Standards' },
        celia: { icon: 'fas fa-wrench', title_fr: 'Celia Algérie - Diagnostic & maintenance préventive', title_en: 'Celia Algérie - Diagnostics & Preventive Maintenance', desc_fr: 'Mission en tant que maintenancier. Diagnostic de pannes et mise en place de maintenance préventive sur lignes de production. Analyse des causes racines et amélioration des processus.', desc_en: 'Assignment as maintenance technician. Fault diagnosis and preventive maintenance implementation on production lines. Root cause analysis and process improvement.', details_fr: '📅 2020 | 🏢 Celia Algérie | 📍 Alger', details_en: '📅 2020 | 🏢 Celia Algérie | 📍 Algiers', tech_fr: 'Maintenance, Diagnostic, GMP, Analyse causes', tech_en: 'Maintenance, Diagnostics, GMP, Root Cause Analysis' }
    };
    
    document.querySelectorAll('.stage-card').forEach(card => {
        card.addEventListener('click', () => {
            let key = card.getAttribute('data-stage');
            let s = stageDetails[key];
            if(s) {
                document.getElementById('modalIcon').innerHTML = `<i class="${s.icon}"></i>`;
                document.getElementById('modalTitle').innerText = currentLang === 'fr' ? s.title_fr : s.title_en;
                document.getElementById('modalDesc').innerText = currentLang === 'fr' ? s.desc_fr : s.desc_en;
                document.getElementById('modalDetails').innerHTML = `<i class="fas fa-info-circle"></i> ${currentLang === 'fr' ? s.details_fr : s.details_en}`;
                let techText = currentLang === 'fr' ? s.tech_fr : s.tech_en;
                document.getElementById('modalTech').innerHTML = `<strong>${currentLang === 'fr' ? 'Technologies & compétences :' : 'Technologies & skills:'}</strong> ${techText}`;
                document.getElementById('skillsListModal').innerHTML = '';
                document.getElementById('activityModal').classList.add('show');
                document.body.style.overflow = 'hidden';
            }
        });
    });
</script>
</body>
</html>
