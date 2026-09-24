<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <meta name="theme-color" content="#1a3a6b">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="apple-mobile-web-app-title" content="F & Triple D">
    <title>F AND TRIPLE D ACADEMY</title>
    <meta name="description" content="F AND TRIPLE D ACADEMY - Daycare, Nursery, Primary, and JSS. Quality education.">
    
    <link rel="manifest" href="manifest.json">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-color: #f0f2f5;
            --card-bg: #ffffff;
            --text-main: #050505;
            --text-muted: #52565c;
            --accent-color: #1a3a6b;
            --accent-hover: #0f2547;
            --accent-soft: rgba(26, 58, 107, 0.1);
            --border-color: #ced0d4;
            --nav-bg: #ffffff;
            --input-bg: #f0f2f5;
            --shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
            --radius: 14px;
            --nav-icon-inactive: rgba(0, 0, 0, 0.55);
            --skeleton-base: #e4e6eb;
            --skeleton-shine: #f0f2f5;
            --wa: #25D366;
            --success: #2e7d32;
            --danger: #c62828;
        }

        [data-theme="dark"] {
            --bg-color: #18191a;
            --card-bg: #242526;
            --text-main: #e4e6eb;
            --text-muted: #c4c7cc;
            --accent-color: #7aa3e0;
            --accent-hover: #9bbce8;
            --accent-soft: rgba(122, 163, 224, 0.15);
            --border-color: #3e4042;
            --nav-bg: #242526;
            --input-bg: #3a3b3c;
            --shadow: 0 1px 2px rgba(255, 255, 255, 0.05);
            --nav-icon-inactive: rgba(255, 255, 255, 0.6);
            --skeleton-base: #2f3033;
            --skeleton-shine: #3a3b3e;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            padding-bottom: 80px;
            overflow-x: hidden;
            transition: background-color 0.3s, color 0.3s;
            overscroll-behavior-y: contain;
        }

        .app-container {
            max-width: 600px;
            margin: 0 auto;
            min-height: 100vh;
            background-color: var(--bg-color);
            position: relative;
        }

        header {
            background-color: var(--card-bg);
            padding: 10px 14px;
            position: sticky;
            top: 0;
            z-index: 100;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-color);
            transition: background-color 0.3s;
        }

        .header-brand {
            display: flex;
            align-items: center;
            gap: 10px;
            flex: 1;
            min-width: 0;
        }

        .header-logo {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--accent-color);
            cursor: pointer;
            flex-shrink: 0;
        }

        .logo-text {
            font-size: 0.9rem;
            font-weight: 800;
            color: var(--accent-color);
            text-transform: uppercase;
            letter-spacing: 0.4px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .header-actions {
            display: flex;
            gap: 6px;
            align-items: center;
        }

        .icon-btn {
            background: var(--input-bg);
            border: none;
            color: var(--text-main);
            font-size: 1rem;
            cursor: pointer;
            padding: 8px 10px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background-color 0.2s;
            font-family: inherit;
        }

        .icon-btn:hover { background-color: var(--border-color); }
        .icon-btn:active { transform: scale(0.94); }

        main {
            padding: 14px;
        }

        .view { display: none; }
        .view.active { display: block; animation: fadeIn 0.3s ease; }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideInRight {
            from { opacity: 0; transform: translateX(20px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes slideInLeft {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .view.active.slide-right { animation: slideInRight 0.25s ease; }
        .view.active.slide-left { animation: slideInLeft 0.25s ease; }

        /* --- SEARCH --- */
        .search-wrap {
            position: relative;
            margin-bottom: 14px;
        }

        .search-wrap input {
            width: 100%;
            padding: 12px 40px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            background-color: var(--input-bg);
            color: var(--text-main);
            font-size: 0.92rem;
            font-family: inherit;
            outline: none;
        }

        .search-wrap input:focus { border-color: var(--accent-color); }

        .search-wrap .search-icon {
            position: absolute;
            left: 14px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
            pointer-events: none;
            font-size: 0.95rem;
        }

        .search-wrap .clear-btn {
            position: absolute;
            right: 12px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--text-muted);
            cursor: pointer;
            font-size: 1.1rem;
            display: none;
            padding: 4px 6px;
        }

        .search-wrap.has-value .clear-btn { display: block; }

        /* --- PULL TO REFRESH --- */
        .ptr-indicator {
            text-align: center;
            height: 0;
            overflow: hidden;
            transition: height 0.25s ease;
            color: var(--text-muted);
            font-size: 0.8rem;
        }

        .ptr-indicator.visible { height: 36px; }

        .ptr-spinner {
            display: inline-block;
            width: 16px;
            height: 16px;
            border: 2px solid var(--border-color);
            border-top-color: var(--accent-color);
            border-radius: 50%;
            animation: spin 0.7s linear infinite;
            vertical-align: middle;
            margin-right: 6px;
        }

        @keyframes spin { to { transform: rotate(360deg); } }

        /* --- SKELETON --- */
        .skeleton-card {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 16px;
            margin-bottom: 14px;
            border: 1px solid var(--border-color);
        }

        .skeleton-line {
            height: 12px;
            border-radius: 6px;
            background: linear-gradient(90deg, var(--skeleton-base) 25%, var(--skeleton-shine) 50%, var(--skeleton-base) 75%);
            background-size: 200% 100%;
            animation: shimmer 1.4s infinite;
            margin-bottom: 8px;
        }

        .skeleton-line.short { width: 40%; }
        .skeleton-line.medium { width: 70%; }
        .skeleton-line.full { width: 100%; }
        .skeleton-line.avatar { width: 40px; height: 40px; border-radius: 50%; margin-bottom: 12px; }
        .skeleton-line.image { width: 100%; height: 180px; border-radius: 10px; margin-top: 8px; }

        @keyframes shimmer {
            0% { background-position: 200% 0; }
            100% { background-position: -200% 0; }
        }

        /* --- POST CARDS --- */
        .post-card {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            margin-bottom: 14px;
            overflow: hidden;
            border: 1px solid var(--border-color);
        }

        .post-header {
            padding: 12px 14px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .avatar {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--accent-color);
            background-color: var(--accent-color);
            cursor: pointer;
        }

        .avatar-ring {
            position: relative;
            width: 42px;
            height: 42px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            flex-shrink: 0;
        }

        .avatar-ring::after {
            content: '';
            position: absolute;
            inset: -3px;
            border-radius: 50%;
            border: 2px solid var(--accent-color);
            opacity: 0.3;
            pointer-events: none;
        }

        .post-info h4 { font-size: 0.88rem; font-weight: 600; }
        .post-info span { font-size: 0.7rem; color: var(--text-muted); }

        .post-content {
            padding: 0 14px 12px;
            font-size: 0.9rem;
            line-height: 1.5;
            word-break: break-word;
        }

        .carousel {
            display: flex;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            scroll-behavior: smooth;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: none;
            gap: 8px;
            padding: 0 14px 8px;
        }

        .carousel::-webkit-scrollbar { display: none; }

        .carousel img {
            width: 85%;
            flex-shrink: 0;
            scroll-snap-align: center;
            border-radius: var(--radius);
            height: 240px;
            object-fit: cover;
            cursor: pointer;
        }

        .carousel-dots {
            display: flex;
            justify-content: center;
            gap: 6px;
            padding: 4px 0 8px;
        }

        .carousel-dots span {
            width: 7px;
            height: 7px;
            border-radius: 50%;
            background-color: var(--border-color);
            transition: background-color 0.3s, transform 0.3s;
        }

        .carousel-dots span.active {
            background-color: var(--accent-color);
            transform: scale(1.2);
        }

        .post-image {
            width: 100%;
            max-height: 400px;
            object-fit: cover;
            display: block;
            cursor: pointer;
        }

        .post-actions {
            padding: 6px 14px;
            border-top: 1px solid var(--border-color);
            display: flex;
            justify-content: space-around;
            color: var(--text-muted);
            font-size: 0.8rem;
            font-weight: 600;
        }

        .post-actions button {
            display: flex;
            align-items: center;
            gap: 6px;
            cursor: pointer;
            padding: 8px 10px;
            border-radius: 8px;
            transition: background-color 0.2s, color 0.2s;
            border: none;
            background: none;
            color: inherit;
            font-family: inherit;
            font-size: inherit;
            font-weight: inherit;
        }

        .post-actions button:hover {
            color: var(--accent-color);
            background-color: var(--accent-soft);
        }

        .post-actions button.liked { color: var(--accent-color); }

        /* --- CARDS --- */
        .card {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 18px;
            box-shadow: var(--shadow);
            border: 1px solid var(--border-color);
            margin-bottom: 14px;
        }

        .card h3 {
            font-size: 1rem;
            margin-bottom: 12px;
            color: var(--accent-color);
            border-bottom: 2px solid var(--accent-color);
            display: inline-block;
            padding-bottom: 3px;
        }

        .card p { font-size: 0.9rem; line-height: 1.6; margin-bottom: 10px; }

        .divider {
            height: 1px;
            background-color: var(--border-color);
            margin: 14px 0;
        }

        /* --- POST FORM --- */
        .post-form {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 18px;
            box-shadow: var(--shadow);
            border: 1px solid var(--border-color);
            margin-bottom: 14px;
        }

        .post-form h3 {
            font-size: 0.95rem;
            margin-bottom: 12px;
            color: var(--accent-color);
        }

        .post-form label {
            display: block;
            font-size: 0.82rem;
            font-weight: 600;
            margin-bottom: 4px;
            color: var(--text-main);
        }

        .post-form input,
        .post-form textarea {
            width: 100%;
            padding: 10px 12px;
            border-radius: 10px;
            border: 1px solid var(--border-color);
            background-color: var(--input-bg);
            color: var(--text-main);
            font-size: 0.88rem;
            font-family: inherit;
            margin-bottom: 12px;
            outline: none;
        }

        .post-form input:focus,
        .post-form textarea:focus {
            border-color: var(--accent-color);
        }

        .post-form textarea {
            resize: vertical;
            min-height: 80px;
        }

        .post-form button {
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 10px;
            font-weight: 600;
            font-family: inherit;
            font-size: 0.9rem;
            cursor: pointer;
            width: 100%;
            transition: background-color 0.2s;
        }

        .post-form button:hover { background-color: var(--accent-hover); }
        .post-form button:active { transform: scale(0.98); }
        .post-form button:disabled {
            opacity: 0.6;
            cursor: not-allowed;
        }

        .form-status {
            margin-top: 10px;
            font-size: 0.82rem;
            padding: 8px 12px;
            border-radius: 8px;
            display: none;
        }

        .form-status.success {
            background-color: rgba(46, 125, 50, 0.1);
            color: var(--success);
            border: 1px solid var(--success);
            display: block;
        }

        .form-status.error {
            background-color: rgba(198, 40, 40, 0.1);
            color: var(--danger);
            border: 1px solid var(--danger);
            display: block;
        }

        /* --- PAYMENT STYLES --- */
        .bank-box {
            background-color: var(--input-bg);
            border-radius: var(--radius);
            padding: 16px;
            margin-top: 12px;
            border-left: 4px solid var(--accent-color);
        }

        .bank-box p { margin-bottom: 6px; font-size: 0.9rem; }
        .bank-box strong { color: var(--text-main); }

        .copy-btn {
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 10px 16px;
            border-radius: 10px;
            font-weight: 600;
            font-family: inherit;
            cursor: pointer;
            margin-top: 10px;
            width: 100%;
            transition: background-color 0.2s;
        }

        .copy-btn:active { transform: scale(0.97); }
        .copy-btn.copied { background-color: var(--success); }

        .fee-list { display: flex; flex-direction: column; gap: 10px; margin-top: 10px; }

        .fee-item {
            display: flex;
            justify-content: space-between;
            padding: 12px;
            background-color: var(--input-bg);
            border-radius: 10px;
            font-weight: 600;
            font-size: 0.9rem;
        }

        /* --- EVENTS --- */
        .event-item {
            display: flex;
            gap: 12px;
            padding: 12px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .event-item:last-child { border-bottom: none; }

        .event-date {
            background-color: var(--accent-soft);
            color: var(--accent-color);
            border-radius: 10px;
            padding: 8px 10px;
            text-align: center;
            min-width: 56px;
            flex-shrink: 0;
        }

        .event-date .day { font-size: 1.2rem; font-weight: 700; line-height: 1; }
        .event-date .month { font-size: 0.68rem; font-weight: 600; text-transform: uppercase; margin-top: 2px; }

        .event-details { flex: 1; min-width: 0; }
        .event-details h4 { font-size: 0.92rem; font-weight: 600; margin-bottom: 4px; }
        .event-details p { font-size: 0.82rem; color: var(--text-muted); margin: 0; line-height: 1.4; }

        /* --- STAFF --- */
        .staff-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 10px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .staff-item:last-child { border-bottom: none; }

        .staff-avatar {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background-color: var(--accent-soft);
            color: var(--accent-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 1rem;
            flex-shrink: 0;
        }

        .staff-info h4 { font-size: 0.9rem; font-weight: 600; }
        .staff-info p { font-size: 0.78rem; color: var(--text-muted); margin: 0; }

        /* --- CONTACT --- */
        .contact-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            background-color: var(--input-bg);
            color: var(--text-main);
            padding: 12px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            margin-top: 10px;
            border: 1px solid var(--border-color);
            transition: background-color 0.2s, transform 0.1s;
        }

        .contact-btn:hover { background-color: var(--border-color); }
        .contact-btn:active { transform: scale(0.98); }

        .contact-btn.whatsapp {
            background-color: var(--wa);
            color: white;
            border: none;
        }

        .contact-btn.whatsapp:hover { background-color: #1ebe57; }

        /* --- FAB --- */
        .fab {
            position: fixed;
            bottom: 84px;
            right: 18px;
            width: 52px;
            height: 52px;
            background-color: var(--wa);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 12px rgba(37, 211, 102, 0.4);
            z-index: 999;
            text-decoration: none;
            border: none;
            cursor: pointer;
        }

        .fab svg { width: 26px; height: 26px; fill: white; }
        .fab:active { transform: scale(0.94); }

        /* --- BACK TO TOP --- */
        .back-to-top {
            position: fixed;
            bottom: 84px;
            left: 18px;
            width: 42px;
            height: 42px;
            background-color: var(--accent-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
            z-index: 998;
            cursor: pointer;
            border: none;
            opacity: 0;
            visibility: hidden;
            transform: translateY(10px);
            transition: opacity 0.3s, visibility 0.3s, transform 0.3s;
        }

        .back-to-top.visible { opacity: 1; visibility: visible; transform: translateY(0); }

        /* --- BOTTOM NAV --- */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: var(--nav-bg);
            border-top: 1px solid var(--border-color);
            display: flex;
            justify-content: space-around;
            align-items: center;
            padding: 6px 0 max(8px, env(safe-area-inset-bottom));
            z-index: 1000;
        }

        @media (min-width: 600px) {
            .bottom-nav {
                max-width: 600px;
                left: 50%;
                transform: translateX(-50%);
                border-left: 1px solid var(--border-color);
                border-right: 1px solid var(--border-color);
                border-radius: 0 0 var(--radius) var(--radius);
            }
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--nav-icon-inactive);
            font-size: 0.62rem;
            font-weight: 500;
            cursor: pointer;
            flex: 1;
            padding: 6px 0;
            border: none;
            background: none;
            position: relative;
            font-family: inherit;
            transition: color 0.2s;
        }

        .nav-item .icon {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 2px;
            position: relative;
        }

        .nav-item .icon svg {
            width: 21px;
            height: 21px;
            stroke: currentColor;
            fill: none;
            stroke-width: 2;
            stroke-linecap: round;
            stroke-linejoin: round;
        }

        .nav-item.active { color: var(--accent-color); font-weight: 600; }
        .nav-item.active .icon svg { stroke-width: 2.4; }
        .nav-item:active { transform: scale(0.94); }

        .nav-item .badge {
            position: absolute;
            top: -2px;
            right: -6px;
            width: 9px;
            height: 9px;
            background-color: #e53935;
            border-radius: 50%;
            border: 2px solid var(--nav-bg);
        }

        /* --- ERROR / EMPTY --- */
        .error-feed {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-muted);
        }

        .error-feed button {
            margin-top: 12px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 10px 24px;
            border-radius: 10px;
            font-weight: 600;
            font-family: inherit;
            cursor: pointer;
        }

        .text-muted { color: var(--text-muted); font-size: 0.85rem; }

        /* --- LIGHTBOX --- */
        .lightbox {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.95);
            z-index: 9999;
            align-items: center;
            justify-content: center;
            padding: 20px;
            cursor: zoom-out;
            opacity: 0;
            transition: opacity 0.25s;
        }

        .lightbox.active { display: flex; opacity: 1; }

        .lightbox-img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
            border-radius: 8px;
            cursor: default;
        }

        .lightbox-close {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.15);
            color: white;
            border: none;
            width: 42px;
            height: 42px;
            border-radius: 50%;
            font-size: 26px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: inherit;
        }

        .lightbox-caption {
            position: absolute;
            bottom: 24px;
            left: 50%;
            transform: translateX(-50%);
            color: rgba(255, 255, 255, 0.9);
            font-size: 0.85rem;
            background: rgba(0, 0, 0, 0.5);
            padding: 8px 16px;
            border-radius: 20px;
            max-width: 90%;
            text-align: center;
        }

        button:focus-visible,
        a:focus-visible,
        input:focus-visible,
        textarea:focus-visible {
            outline: 2px solid var(--accent-color);
            outline-offset: 2px;
        }

        @media (prefers-reduced-motion: reduce) {
            *, *::before, *::after {
                animation-duration: 0.01ms !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body>

<div class="app-container">
    <header>
        <div class="header-brand">
            <img src="https://dl.dropboxusercontent.com/scl/fi/1ob0p5n7l6hyh4td3r0im/grok_1789571969699.jpg?rlkey=lquykzm9jj1czznynun4tfu15&dl=1" 
                 alt="F AND TRIPLE D ACADEMY Logo" 
                 class="header-logo"
                 onclick="openLightbox(this.src, 'F AND TRIPLE D ACADEMY')"
                 onerror="this.style.display='none';">
            <span class="logo-text" data-i18n="schoolName">F & TRIPLE D ACADEMY</span>
        </div>
        <div class="header-actions">
            <button class="icon-btn" onclick="toggleLang()" id="langBtn" aria-label="Change language">EN</button>
            <button class="icon-btn" id="themeToggle" onclick="toggleTheme()" aria-label="Toggle dark mode">
                <span id="themeIcon">🌙</span>
            </button>
        </div>
    </header>

    <main>
        <!-- UPDATES -->
        <section id="updates" class="view active">
            <div class="search-wrap" id="searchWrap">
                <span class="search-icon">🔍</span>
                <input type="search" 
                       id="searchInput" 
                       placeholder="Search updates..." 
                       oninput="onSearchInput(this.value)"
                       aria-label="Search updates">
                <button class="clear-btn" onclick="clearSearch()" aria-label="Clear search">&times;</button>
            </div>

            <div class="ptr-indicator" id="ptrIndicator">
                <span class="ptr-spinner"></span>Release to refresh
            </div>

            <div id="feedContainer"></div>
        </section>

        <!-- PAYMENTS -->
        <section id="payments" class="view">
            <div class="card">
                <h3 data-i18n="paymentsTitle">💳 School Fees Payment</h3>
                <p data-i18n="paymentsIntro">Make payments to the school bank account below:</p>
                
                <div class="bank-box">
                    <p><strong>Bank Name:</strong> [Insert Bank Name]</p>
                    <p><strong>Account Name:</strong> F AND TRIPLE D ACADEMY</p>
                    <p><strong>Account Number:</strong> <span id="accountNumber">2036010145</span></p>
                    <button class="copy-btn" id="copyBtn" onclick="copyAccountNumber()" data-i18n="copyAccount">📋 Copy Account Number</button>
                </div>

                <div class="divider"></div>

                <p><strong data-i18n="feesSchedule">Fees Schedule:</strong></p>
                <div class="fee-list">
                    <div class="fee-item"><span data-i18n="feeDayCare">Day Care</span> <span>₦13,500</span></div>
                    <div class="fee-item"><span data-i18n="feeNursery">Nursery 1 - 2</span> <span>₦13,500</span></div>
                    <div class="fee-item"><span data-i18n="feePrimary">Primary 1 - 5</span> <span>₦14,500</span></div>
                    <div class="fee-item"><span data-i18n="feeJss">JSS 1 - 3</span> <span>₦16,000</span></div>
                </div>

                <div class="divider"></div>

                <p class="text-muted" data-i18n="paymentNote">⚠️ Important: Use your child's full name and class as the payment reference. After payment, send proof via WhatsApp or Email.</p>
            </div>
        </section>

        <!-- EVENTS -->
        <section id="events" class="view">
            <div class="card">
                <h3 data-i18n="eventsTitle">📅 School Events</h3>
                <p class="text-muted" data-i18n="eventsIntro">Upcoming events, term dates, and important dates for parents.</p>
                <div class="divider"></div>
                <div id="eventsContainer"></div>
            </div>
        </section>

        <!-- ABOUT -->
        <section id="about" class="view">
            <div class="card">
                <img src="https://dl.dropboxusercontent.com/scl/fi/1ob0p5n7l6hyh4td3r0im/grok_1789571969699.jpg?rlkey=lquykzm9jj1czznynun4tfu15&dl=1" 
                     alt="School Logo" 
                     class="avatar"
                     style="width:120px;height:120px;display:block;margin:0 auto 16px;"
                     onclick="openLightbox(this.src, 'F AND TRIPLE D ACADEMY')"
                     onerror="this.style.display='none';">
                <h3 data-i18n="aboutTitle">🏫 About Our School</h3>
                <p data-i18n="aboutText1">Welcome to F AND TRIPLE D ACADEMY. We are committed to providing a safe, nurturing, and stimulating environment where children can learn, grow, and thrive.</p>
                <p data-i18n="aboutText2">Our school caters to children from Daycare through Junior Secondary School (JSS 1-3).</p>
                <div class="divider"></div>
                <h3 data-i18n="programmesTitle">📚 Our Programmes</h3>
                <p>• Day Care</p>
                <p>• Nursery 1 - 2</p>
                <p>• Primary 1 - 5</p>
                <p>• JSS 1 - 3</p>
                <div class="divider"></div>
                <h3 data-i18n="staffTitle">👩‍🏫 Our Staff</h3>
                <div id="staffContainer"></div>
            </div>
        </section>

        <!-- CONTACT -->
        <section id="contact" class="view">
            <div class="card">
                <h3 data-i18n="contactTitle">📞 Contact Admissions</h3>
                <p data-i18n="contactIntro">Admission is currently open for all classes. Reach out to us:</p>
                <a href="https://wa.me/2348027093798?text=Hello%20F%20AND%20TRIPLE%20D%20ACADEMY,%20I%20would%20like%20to%20make%20an%20enquiry%20about%20admission." 
                   target="_blank" class="contact-btn whatsapp" rel="noopener">
                    💬 Chat on WhatsApp
                </a>
                <a href="tel:08027093798" class="contact-btn">📞 Call: 0802 709 3798</a>
                <a href="mailto:patience_agbor@yahoo.com" class="contact-btn">✉️ Email Us</a>
                <div class="divider"></div>
                <p class="text-muted" style="text-align:center;" data-i18n="contactFooter">
                    We look forward to welcoming you and your child to the F AND TRIPLE D ACADEMY family!
                </p>
            </div>
        </section>
    </main>

    <a href="https://wa.me/2348027093798?text=Hello%20F%20AND%20TRIPLE%20D%20ACADEMY" 
       target="_blank" class="fab" aria-label="Chat on WhatsApp" rel="noopener">
        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
        </svg>
    </a>

    <button class="back-to-top" id="backToTop" onclick="scrollToTop()" aria-label="Back to top">⬆️</button>

    <nav class="bottom-nav" role="navigation">
        <button class="nav-item active" onclick="switchTab('updates', this)" aria-label="Updates">
            <span class="icon">
                <svg viewBox="0 0 24 24"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
                <span class="badge" id="updatesBadge" style="display:none;"></span>
            </span>
            <span data-i18n="navUpdates">Updates</span>
        </button>
        <button class="nav-item" onclick="switchTab('payments', this)" aria-label="Payments">
            <span class="icon">
                <svg viewBox="0 0 24 24"><rect x="1" y="4" width="22" height="16" rx="2" ry="2"/><line x1="1" y1="10" x2="23" y2="10"/></svg>
            </span>
            <span data-i18n="navPayments">Payments</span>
        </button>
        <button class="nav-item" onclick="switchTab('events', this)" aria-label="Events">
            <span class="icon">
                <svg viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
            </span>
            <span data-i18n="navEvents">Events</span>
        </button>
        <button class="nav-item" onclick="switchTab('about', this)" aria-label="About">
            <span class="icon">
                <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><line x1="12" y1="16" x2="12" y2="12"/><line x1="12" y1="8" x2="12.01" y2="8"/></svg>
            </span>
            <span data-i18n="navAbout">About</span>
        </button>
        <button class="nav-item" onclick="switchTab('contact', this)" aria-label="Contact">
            <span class="icon">
                <svg viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
            </span>
            <span data-i18n="navContact">Contact</span>
        </button>
    </nav>
</div>

<div class="lightbox" id="lightbox" onclick="closeLightbox()">
    <button class="lightbox-close" onclick="closeLightbox(event)" aria-label="Close">&times;</button>
    <img src="" alt="Enlarged view" class="lightbox-img" id="lightboxImg" onclick="event.stopPropagation()">
    <div class="lightbox-caption" id="lightboxCaption"></div>
</div>

<script>
/* ============================================================
   CONFIG — YOUR SETTINGS
   ============================================================ */
const CONFIG = {
    schoolName: 'F AND TRIPLE D ACADEMY',
    whatsappNumber: '2348027093798',
    schoolLogo: 'https://dl.dropboxusercontent.com/scl/fi/1ob0p5n7l6hyh4td3r0im/grok_1789571969699.jpg?rlkey=lquykzm9jj1czznynun4tfu15&dl=1',
    
    // 🎯 YOUR GOOGLE APPS SCRIPT URL
    apiUrl: 'https://script.google.com/macros/s/AKfycbyKT3hPqkX-A0VSs7UMehi5wwAXyUtH3GvC-A4fe5Z8Dn8XVfd8Ra7fH3I9QcdE8YUoEw/exec',
    
    events: [
        { date: '2026-10-15', title: 'PTA Meeting', desc: 'All parents are invited. 10:00 AM in the main hall.' },
        { date: '2026-10-24', title: 'Mid-term Break Begins', desc: 'School closes for one week.' },
        { date: '2026-11-05', title: 'Cultural Day', desc: 'Students come dressed in traditional attire.' },
        { date: '2026-12-12', title: 'End of Term & Carol Night', desc: 'End-of-term reports and carol service.' }
    ],
    
    staff: [
        { name: 'Mrs. Patience Agbor', role: 'Head Teacher / Administrator' },
        { name: 'Class Teachers', role: 'One dedicated teacher per class' },
        { name: 'Support Staff', role: 'Cleaning and facility care' }
    ],
    
    enablePullToRefresh: true,
    enablePushNotifications: true,
    enablePostForm: true  // Set to false to hide the "Post Update" form
};

/* ============================================================
   TRANSLATIONS
   ============================================================ */
const TRANSLATIONS = {
    en: {
        schoolName: 'F & TRIPLE D ACADEMY',
        navUpdates: 'Updates', navPayments: 'Payments', navEvents: 'Events', navAbout: 'About', navContact: 'Contact',
        searchPlaceholder: 'Search updates...',
        paymentsTitle: '💳 School Fees Payment',
        paymentsIntro: 'Make payments to the school bank account below:',
        copyAccount: '📋 Copy Account Number',
        feesSchedule: 'Fees Schedule:',
        feeDayCare: 'Day Care',
        feeNursery: 'Nursery 1 - 2',
        feePrimary: 'Primary 1 - 5',
        feeJss: 'JSS 1 - 3',
        paymentNote: '⚠️ Important: Use your child\'s full name and class as the payment reference. After payment, send proof via WhatsApp or Email.',
        eventsTitle: '📅 School Events',
        eventsIntro: 'Upcoming events, term dates, and important dates.',
        aboutTitle: '🏫 About Our School',
        aboutText1: 'Welcome to F AND TRIPLE D ACADEMY. We are committed to providing a safe, nurturing environment where children can learn, grow, and thrive.',
        aboutText2: 'Our school caters to children from Daycare through Junior Secondary School (JSS 1-3).',
        programmesTitle: '📚 Our Programmes',
        staffTitle: '👩‍🏫 Our Staff',
        contactTitle: '📞 Contact Admissions',
        contactIntro: 'Admission is currently open for all classes. Reach out to us:',
        contactFooter: 'We look forward to welcoming you and your child to the F AND TRIPLE D ACADEMY family!',
        like: 'Like', liked: 'Liked', comment: 'Comment', share: 'Share',
        noUpdates: 'No updates yet. Check back soon!',
        noResults: 'No updates match your search.',
        errorLoad: 'Could not load updates.',
        retry: 'Retry'
    },
    pcm: {
        schoolName: 'F & TRIPLE D ACADEMY',
        navUpdates: 'Updates', navPayments: 'Payments', navEvents: 'Events', navAbout: 'About Us', navContact: 'Contact Us',
        searchPlaceholder: 'Find update...',
        paymentsTitle: '💳 School Fees',
        paymentsIntro: 'Pay to the school bank account:',
        copyAccount: '📋 Copy Account Number',
        feesSchedule: 'How Much:',
        feeDayCare: 'Day Care',
        feeNursery: 'Nursery 1 - 2',
        feePrimary: 'Primary 1 - 5',
        feeJss: 'JSS 1 - 3',
        paymentNote: '⚠️ Use your pikin full name and class as reference. After paying, send proof via WhatsApp or Email.',
        eventsTitle: '📅 School Events',
        eventsIntro: 'Things wey dey happen for school.',
        aboutTitle: '🏫 About Our School',
        aboutText1: 'Welcome to F AND TRIPLE D ACADEMY. We dey give pikin safe place to learn and grow.',
        aboutText2: 'We dey take pikin from Daycare reach JSS 3.',
        programmesTitle: '📚 Wetin We Dey Teach',
        staffTitle: '👩‍🏫 Our Teachers',
        contactTitle: '📞 Contact Us',
        contactIntro: 'Admission still open. Reach out to us:',
        contactFooter: 'We dey wait to welcome you and your pikin!',
        like: 'Like', liked: 'You Like Am', comment: 'Comment', share: 'Share',
        noUpdates: 'No update for now.',
        noResults: 'We no see wetin you find.',
        errorLoad: 'We no fit load updates.',
        retry: 'Try Again'
    }
};

let currentLang = localStorage.getItem('lang') || 'en';
let allPosts = [];
let filteredPosts = [];
let searchTerm = '';

/* ============================================================
   THEME
   ============================================================ */
const root = document.documentElement;
const savedTheme = localStorage.getItem('theme');
if (savedTheme) {
    root.setAttribute('data-theme', savedTheme);
} else {
    const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
    root.setAttribute('data-theme', prefersDark ? 'dark' : 'light');
}
updateThemeIcon();

function toggleTheme() {
    const current = root.getAttribute('data-theme');
    const next = current === 'light' ? 'dark' : 'light';
    root.setAttribute('data-theme', next);
    localStorage.setItem('theme', next);
    updateThemeIcon();
}

function updateThemeIcon() {
    const icon = document.getElementById('themeIcon');
    if (icon) icon.innerText = root.getAttribute('data-theme') === 'dark' ? '☀️' : '🌙';
    const meta = document.querySelector('meta[name="theme-color"]');
    if (meta) meta.setAttribute('content', root.getAttribute('data-theme') === 'dark' ? '#18191a' : '#1a3a6b');
}

/* ============================================================
   LANGUAGE
   ============================================================ */
function t(key) {
    return (TRANSLATIONS[currentLang] && TRANSLATIONS[currentLang][key]) || TRANSLATIONS.en[key] || key;
}

function applyLanguage() {
    document.querySelectorAll('[data-i18n]').forEach(el => {
        const key = el.getAttribute('data-i18n');
        const translated = t(key);
        if (translated) el.textContent = translated;
    });
    const searchInput = document.getElementById('searchInput');
    if (searchInput) searchInput.placeholder = t('searchPlaceholder');
    const langBtn = document.getElementById('langBtn');
    if (langBtn) langBtn.textContent = currentLang === 'en' ? 'EN' : 'PCM';
    if (allPosts.length > 0) renderPosts(filteredPosts);
}

function toggleLang() {
    currentLang = currentLang === 'en' ? 'pcm' : 'en';
    localStorage.setItem('lang', currentLang);
    applyLanguage();
}

/* ============================================================
   TABS
   ============================================================ */
let currentTab = 'updates';

function switchTab(tabId, element) {
    if (tabId === currentTab) return;
    const views = document.querySelectorAll('.view');
    views.forEach(v => v.classList.remove('active', 'slide-right', 'slide-left'));
    const selected = document.getElementById(tabId);
    if (selected) {
        const order = ['updates', 'payments', 'events', 'about', 'contact'];
        const curIdx = order.indexOf(currentTab);
        const newIdx = order.indexOf(tabId);
        selected.classList.add('active');
        selected.classList.add(newIdx > curIdx ? 'slide-right' : 'slide-left');
    }
    document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
    element.classList.add('active');
    currentTab = tabId;
    if (tabId === 'updates') {
        const badge = document.getElementById('updatesBadge');
        if (badge) badge.style.display = 'none';
    }
    window.scrollTo({ top: 0, behavior: 'smooth' });
}

/* ============================================================
   COPY ACCOUNT
   ============================================================ */
function copyAccountNumber() {
    const acc = document.getElementById('accountNumber').innerText;
    const btn = document.getElementById('copyBtn');
    navigator.clipboard.writeText(acc).then(() => {
        btn.textContent = '✅ Copied!';
        btn.classList.add('copied');
        setTimeout(() => {
            btn.textContent = t('copyAccount');
            btn.classList.remove('copied');
        }, 2000);
    }).catch(() => {
        const ta = document.createElement('textarea');
        ta.value = acc;
        document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        document.body.removeChild(ta);
        btn.textContent = '✅ Copied!';
        btn.classList.add('copied');
        setTimeout(() => {
            btn.textContent = t('copyAccount');
            btn.classList.remove('copied');
        }, 2000);
    });
}

/* ============================================================
   LIGHTBOX
   ============================================================ */
const lightbox = document.getElementById('lightbox');
const lightboxImg = document.getElementById('lightboxImg');
const lightboxCaption = document.getElementById('lightboxCaption');

function openLightbox(src, caption) {
    lightboxImg.src = src;
    lightboxCaption.textContent = caption || '';
    lightboxCaption.style.display = caption ? 'block' : 'none';
    lightbox.classList.add('active');
    document.body.style.overflow = 'hidden';
}

function closeLightbox(e) {
    if (e) e.stopPropagation();
    lightbox.classList.remove('active');
    document.body.style.overflow = '';
    setTimeout(() => { lightboxImg.src = ''; }, 300);
}

document.addEventListener('keydown', e => {
    if (e.key === 'Escape' && lightbox.classList.contains('active')) closeLightbox();
});

/* ============================================================
   SEARCH
   ============================================================ */
function onSearchInput(value) {
    searchTerm = value.trim().toLowerCase();
    const wrap = document.getElementById('searchWrap');
    wrap.classList.toggle('has-value', searchTerm.length > 0);
    filteredPosts = !searchTerm 
        ? allPosts 
        : allPosts.filter(p => (p.text || '').toLowerCase().includes(searchTerm));
    renderPosts(filteredPosts);
}

function clearSearch() {
    const input = document.getElementById('searchInput');
    input.value = '';
    onSearchInput('');
    input.focus();
}

/* ============================================================
   BACK TO TOP
   ============================================================ */
const backToTopBtn = document.getElementById('backToTop');
window.addEventListener('scroll', () => {
    backToTopBtn.classList.toggle('visible', window.scrollY > 300);
}, { passive: true });

function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
}

/* ============================================================
   SKELETON
   ============================================================ */
function showSkeletons(count = 3) {
    const container = document.getElementById('feedContainer');
    let html = '';
    for (let i = 0; i < count; i++) {
        html += `
            <div class="skeleton-card">
                <div style="display:flex;gap:10px;align-items:center;">
                    <div class="skeleton-line avatar"></div>
                    <div style="flex:1;">
                        <div class="skeleton-line short"></div>
                        <div class="skeleton-line" style="width:30%;"></div>
                    </div>
                </div>
                <div class="skeleton-line full"></div>
                <div class="skeleton-line medium"></div>
                <div class="skeleton-line image"></div>
            </div>
        `;
    }
    container.innerHTML = html;
}

/* ============================================================
   LOAD FEED FROM GOOGLE APPS SCRIPT
   ============================================================ */
async function loadFeed(silent = false) {
    if (!silent) showSkeletons();
    const container = document.getElementById('feedContainer');
    
    try {
        const response = await fetch(CONFIG.apiUrl + '?t=' + Date.now(), {
            method: 'GET',
            cache: 'no-cache'
        });
        
        if (!response.ok) throw new Error('HTTP ' + response.status);
        
        const data = await response.json();
        
        if (!Array.isArray(data)) {
            throw new Error('Invalid response format');
        }
        
        allPosts = data.map((row, i) => ({
            id: 'post-' + i,
            text: row.PostText || row.posttext || '',
            images: [row.ImageURL1, row.ImageURL2].filter(Boolean)
        })).filter(p => p.text || p.images.length > 0);
        
        filteredPosts = allPosts;
        renderPosts(filteredPosts);
        
        // Add post form to the top of the feed if enabled
        if (CONFIG.enablePostForm && !document.getElementById('postFormContainer')) {
            const formHtml = `
                <div class="post-form" id="postFormContainer">
                    <h3>✍️ Post a New Update</h3>
                    <form onsubmit="submitPost(event)">
                        <label for="postText">Message *</label>
                        <textarea id="postText" placeholder="What's happening at school?" required></textarea>
                        
                        <label for="postImage1">Image URL 1 (optional)</label>
                        <input type="url" id="postImage1" placeholder="https://...">
                        
                        <label for="postImage2">Image URL 2 (optional)</label>
                        <input type="url" id="postImage2" placeholder="https://...">
                        
                        <button type="submit" id="postSubmitBtn">📤 Publish Update</button>
                        <div class="form-status" id="formStatus"></div>
                    </form>
                </div>
            `;
            container.insertAdjacentHTML('afterbegin', formHtml);
        }
        
    } catch (err) {
        console.error('Feed error:', err);
        container.innerHTML = `
            <div class="error-feed">
                <p>⚠️ ${t('errorLoad')}</p>
                <button onclick="loadFeed()">${t('retry')}</button>
            </div>
        `;
    }
}

/* ============================================================
   SUBMIT NEW POST
   ============================================================ */
async function submitPost(event) {
    event.preventDefault();
    const btn = document.getElementById('postSubmitBtn');
    const status = document.getElementById('formStatus');
    
    const text = document.getElementById('postText').value.trim();
    const img1 = document.getElementById('postImage1').value.trim();
    const img2 = document.getElementById('postImage2').value.trim();
    
    if (!text) return;
    
    btn.disabled = true;
    btn.textContent = '⏳ Publishing...';
    status.className = 'form-status';
    status.style.display = 'none';
    
    try {
        const response = await fetch(CONFIG.apiUrl, {
            method: 'POST',
            headers: { 'Content-Type': 'text/plain;charset=utf-8' },
            body: JSON.stringify({
                PostText: text,
                ImageURL1: img1,
                ImageURL2: img2
            })
        });
        
        const result = await response.json();
        
        if (result.status === 'success') {
            status.className = 'form-status success';
            status.textContent = '✅ Update published!';
            document.getElementById('postText').value = '';
            document.getElementById('postImage1').value = '';
            document.getElementById('postImage2').value = '';
            
            // Reload feed to show the new post
            setTimeout(() => loadFeed(true), 800);
        } else {
            throw new Error(result.message || 'Unknown error');
        }
        
    } catch (err) {
        console.error('Submit error:', err);
        status.className = 'form-status error';
        status.textContent = '❌ Failed to publish. Please try again.';
    } finally {
        btn.disabled = false;
        btn.textContent = '📤 Publish Update';
    }
}

/* ============================================================
   RENDER POSTS
   ============================================================ */
function renderPosts(posts) {
    const container = document.getElementById('feedContainer');
    
    // Preserve the form if it exists
    const form = document.getElementById('postFormContainer');
    const formHtml = form ? form.outerHTML : '';
    
    if (posts.length === 0) {
        container.innerHTML = formHtml + `<div class="error-feed"><p>${searchTerm ? t('noResults') : t('noUpdates')}</p></div>`;
        return;
    }
    
    let html = '';
    posts.forEach((post, idx) => {
        const text = post.text || '';
        const imgs = post.images || [];
        const shortCaption = text.substring(0, 60);
        
        let media = '';
        if (imgs.length > 1) {
            media = `
                <div class="carousel" id="car-${idx}">
                    ${imgs.map(img => `<img src="${img}" alt="School update" loading="lazy" onclick="openLightbox('${escapeAttr(img)}', '${escapeAttr(shortCaption)}')">`).join('')}
                </div>
                <div class="carousel-dots" id="dots-${idx}">
                    ${imgs.map((_, i) => `<span class="${i === 0 ? 'active' : ''}"></span>`).join('')}
                </div>
            `;
        } else if (imgs.length === 1) {
            media = `<img src="${imgs[0]}" alt="School update" class="post-image" loading="lazy" onclick="openLightbox('${escapeAttr(imgs[0])}', '${escapeAttr(shortCaption)}')">`;
        }
        
        const waText = encodeURIComponent(`Hello, I'd like to comment on this update:\n\n"${text.substring(0, 100)}"\n\n`);
        const waLink = `https://wa.me/${CONFIG.whatsappNumber}?text=${waText}`;
        
        html += `
            <article class="post-card">
                <div class="post-header">
                    <div class="avatar-ring" onclick="openLightbox('${escapeAttr(CONFIG.schoolLogo)}', '${escapeAttr(CONFIG.schoolName)}')">
                        <img src="${CONFIG.schoolLogo}" alt="School Logo" class="avatar"
                             onerror="this.outerHTML='<div class=\\'avatar\\' style=\\'display:flex;align-items:center;justify-content:center;color:white;font-weight:bold;\\'>F</div>';">
                    </div>
                    <div class="post-info">
                        <h4>${escapeHtml(CONFIG.schoolName)}</h4>
                        <span>📢 Update</span>
                    </div>
                </div>
                <div class="post-content">${escapeHtml(text)}</div>
                ${media}
                <div class="post-actions">
                    <button onclick="toggleLike(this)" aria-label="Like">
                        <span class="like-icon">👍</span><span class="like-label">${t('like')}</span>
                    </button>
                    <a href="${waLink}" target="_blank" rel="noopener" style="text-decoration:none;color:inherit;">
                        <button aria-label="Comment via WhatsApp">💬 ${t('comment')}</button>
                    </a>
                    <button onclick="sharePost('${escapeAttr(text)}')" aria-label="Share">↗️ ${t('share')}</button>
                </div>
            </article>
        `;
    });
    
    container.innerHTML = formHtml + html;
    
    // Re-attach form submit listener
    const newForm = document.querySelector('#postFormContainer form');
    if (newForm) {
        newForm.onsubmit = submitPost;
    }
    
    posts.forEach((post, idx) => {
        if (post.images && post.images.length > 1) initCarouselDots(idx);
    });
}

function initCarouselDots(idx) {
    const car = document.getElementById(`car-${idx}`);
    const dots = document.getElementById(`dots-${idx}`);
    if (!car || !dots) return;
    car.addEventListener('scroll', () => {
        const i = Math.round(car.scrollLeft / car.clientWidth);
        dots.querySelectorAll('span').forEach((d, k) => d.classList.toggle('active', k === i));
    }, { passive: true });
}

function toggleLike(btn) {
    btn.classList.toggle('liked');
    const label = btn.querySelector('.like-label');
    label.textContent = btn.classList.contains('liked') ? t('liked') : t('like');
    if (navigator.vibrate) navigator.vibrate(10);
}

function sharePost(text) {
    const data = { title: CONFIG.schoolName, text: text, url: window.location.href };
    if (navigator.share) {
        navigator.share(data).catch(() => {});
    } else {
        navigator.clipboard.writeText(text + ' - ' + window.location.href)
            .then(() => alert('Copied!'))
            .catch(() => {});
    }
}

function escapeHtml(str) {
    const div = document.createElement('div');
    div.textContent = str;
    return div.innerHTML;
}

function escapeAttr(str) {
    return String(str).replace(/\\/g, '\\\\').replace(/'/g, "\\'").replace(/"/g, '&quot;');
}

/* ============================================================
   EVENTS / STAFF
   ============================================================ */
function renderEvents() {
    const container = document.getElementById('eventsContainer');
    if (!container) return;
    const sorted = [...CONFIG.events].sort((a, b) => new Date(a.date) - new Date(b.date));
    if (sorted.length === 0) {
        container.innerHTML = '<p class="text-muted">No events scheduled.</p>';
        return;
    }
    container.innerHTML = sorted.map(ev => {
        const d = new Date(ev.date);
        return `
            <div class="event-item">
                <div class="event-date">
                    <div class="day">${d.getDate()}</div>
                    <div class="month">${d.toLocaleString('en', { month: 'short' })}</div>
                </div>
                <div class="event-details">
                    <h4>${escapeHtml(ev.title)}</h4>
                    <p>${escapeHtml(ev.desc)}</p>
                </div>
            </div>
        `;
    }).join('');
}

function renderStaff() {
    const container = document.getElementById('staffContainer');
    if (!container) return;
    container.innerHTML = CONFIG.staff.map(s => {
        const initials = s.name.split(' ').map(w => w[0]).slice(0, 2).join('').toUpperCase();
        return `
            <div class="staff-item">
                <div class="staff-avatar">${initials}</div>
                <div class="staff-info">
                    <h4>${escapeHtml(s.name)}</h4>
                    <p>${escapeHtml(s.role)}</p>
                </div>
            </div>
        `;
    }).join('');
}

/* ============================================================
   PULL TO REFRESH
   ============================================================ */
if (CONFIG.enablePullToRefresh) {
    let startY = 0;
    let pulling = false;
    const indicator = document.getElementById('ptrIndicator');
    
    document.addEventListener('touchstart', e => {
        if (window.scrollY === 0 && currentTab === 'updates') {
            startY = e.touches[0].clientY;
            pulling = true;
        }
    }, { passive: true });
    
    document.addEventListener('touchmove', e => {
        if (!pulling) return;
        const dy = e.touches[0].clientY - startY;
        indicator.classList.toggle('visible', dy > 60 && window.scrollY === 0);
    }, { passive: true });
    
    document.addEventListener('touchend', () => {
        if (pulling && indicator.classList.contains('visible')) {
            indicator.innerHTML = '<span class="ptr-spinner"></span>Refreshing...';
            loadFeed(true).then(() => {
                setTimeout(() => {
                    indicator.classList.remove('visible');
                    indicator.innerHTML = '<span class="ptr-spinner"></span>Release to refresh';
                }, 800);
            });
        }
        pulling = false;
    });
}

/* ============================================================
   PUSH NOTIFICATION STUB
   ============================================================ */
if (CONFIG.enablePushNotifications) {
    window.requestNotificationPermission = function() {
        if (window.OneSignal && typeof window.OneSignal.showSlidedownPrompt === 'function') {
            window.OneSignal.showSlidedownPrompt();
        } else if ('Notification' in window && Notification.permission === 'default') {
            Notification.requestPermission();
        }
    };
}

/* ============================================================
   INIT
   ============================================================ */
document.addEventListener('DOMContentLoaded', () => {
    applyLanguage();
    renderEvents();
    renderStaff();
    loadFeed();
    
    if ('serviceWorker' in navigator) {
        navigator.serviceWorker.register('sw.js').catch(err => {
            console.log('SW skipped:', err.message);
        });
    }
});
</script>

</body>
</html>
