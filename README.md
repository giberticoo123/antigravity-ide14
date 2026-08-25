# antigravity-ide14
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Plataforma institucional y centro enciclopédico de investigación sobre ciencias de la familia, psicología sistémica, estilos de crianza y desarrollo humano intergeneracional.">
    <meta name="author" content="Instituto Internacional de Estudios sobre la Familia">
    <title>Portal Internacional de Estudios sobre la Familia y Desarrollo Humano</title>

    <!-- Google Fonts Import -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,300;0,400;0,700;1,400&family=Merriweather:ital,wght@0,300;0,400;0,700;1,300;1,400&display=swap" rel="stylesheet">

    <style>
        :root {
            --color-bg-primary: #FAF8F5;
            --color-bg-secondary: #EFECE6;
            --color-text-main: #2D2A26;
            --color-accent: #C27D58;
            --color-accent-hover: #A66442;
            --color-secondary-accent: #5B7065;
            --color-secondary-hover: #485A50;
            --color-dark-marble: #1F1C1A;
            --color-border: #D8D2C9;
            --color-terracotta-soft: rgba(194, 125, 88, 0.12);
            --color-salvia-soft: rgba(91, 112, 101, 0.12);

            --font-heading: 'Merriweather', Georgia, serif;
            --font-body: 'Lato', system-ui, -apple-system, sans-serif;

            --transition-smooth: all 0.35s cubic-bezier(0.16, 1, 0.3, 1);
            --max-width-container: 1280px;
            --border-radius-sm: 4px;
            --border-radius-md: 8px;
        }

        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
            font-size: 16px;
        }

        body {
            background-color: var(--color-bg-primary);
            color: var(--color-text-main);
            font-family: var(--font-body);
            line-height: 1.8;
            -webkit-font-smoothing: antialiased;
            overflow-x: hidden;
        }

        :focus-visible {
            outline: 2px solid var(--color-accent);
            outline-offset: 4px;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: var(--font-heading);
            color: var(--color-dark-marble);
            line-height: 1.35;
            font-weight: 700;
        }

        p {
            margin-bottom: 1.25rem;
            font-size: 1.05rem;
            color: #3D3935;
        }

        a {
            color: var(--color-accent);
            text-decoration: none;
            transition: var(--transition-smooth);
        }

        a:hover {
            color: var(--color-accent-hover);
        }

        .header {
            background-color: var(--color-dark-marble);
            color: #FAF8F5;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 3px solid var(--color-accent);
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
        }

        .header__container {
            max-width: var(--max-width-container);
            margin: 0 auto;
            padding: 1rem 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .header__brand {
            display: flex;
            align-items: center;
            gap: 0.85rem;
            cursor: pointer;
        }

        .header__logo-mark {
            width: 42px;
            height: 42px;
            border: 2px solid var(--color-accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: var(--font-heading);
            color: var(--color-accent);
            font-size: 1.4rem;
            font-weight: 700;
            border-radius: var(--border-radius-sm);
            background-color: rgba(194, 125, 88, 0.08);
        }

        .header__title {
            font-size: 1.1rem;
            letter-spacing: 1.2px;
            text-transform: uppercase;
            color: #FAF8F5;
            font-weight: 700;
            display: block;
        }

        .header__subtitle {
            font-size: 0.72rem;
            letter-spacing: 1.8px;
            color: var(--color-accent);
            text-transform: uppercase;
            display: block;
        }

        .nav__list {
            display: flex;
            list-style: none;
            gap: 0.8rem;
            align-items: center;
            flex-wrap: wrap;
        }

        .nav__link {
            color: #EFECE6;
            font-size: 0.82rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            padding: 0.45rem 0.65rem;
            border-radius: var(--border-radius-sm);
            border-bottom: 2px solid transparent;
            transition: var(--transition-smooth);
            font-weight: 700;
        }

        .nav__link:hover, .nav__link--active {
            color: var(--color-accent);
            border-bottom-color: var(--color-accent);
            background-color: rgba(255, 255, 255, 0.04);
        }

        .nav__mobile-toggle {
            display: none;
            background: none;
            border: 1px solid var(--color-accent);
            color: var(--color-accent);
            padding: 0.5rem 0.75rem;
            cursor: pointer;
            border-radius: var(--border-radius-sm);
            font-size: 1.2rem;
        }

        .main-container {
            max-width: var(--max-width-container);
            margin: 0 auto;
            padding: 2.5rem 1.5rem 5rem 1.5rem;
            min-height: 80vh;
        }

        .page-view {
            display: none;
            animation: fadeIn 0.45s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .page-view--active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(14px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-header {
            margin-bottom: 3rem;
            text-align: center;
            border-bottom: 1px solid var(--color-border);
            padding-bottom: 2rem;
            position: relative;
        }

        .section-header::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 50%;
            transform: translateX(-50%);
            width: 90px;
            height: 3px;
            background-color: var(--color-accent);
        }

        .section-header__tag {
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 2.5px;
            color: var(--color-secondary-accent);
            font-weight: 700;
            margin-bottom: 0.5rem;
            display: block;
        }

        .section-header__title {
            font-size: 2.3rem;
            margin-bottom: 0.75rem;
            color: var(--color-dark-marble);
        }

        .section-header__lead {
            font-size: 1.15rem;
            color: #5A544F;
            max-width: 820px;
            margin: 0 auto;
            font-style: italic;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.85rem 1.8rem;
            font-family: var(--font-body);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1.2px;
            font-weight: 700;
            border-radius: var(--border-radius-sm);
            cursor: pointer;
            transition: var(--transition-smooth);
            border: 1px solid var(--color-accent);
            background: transparent;
            color: var(--color-dark-marble);
        }

        .btn--primary {
            background-color: var(--color-accent);
            color: #FFFFFF;
        }

        .btn--primary:hover {
            background-color: var(--color-accent-hover);
            border-color: var(--color-accent-hover);
            color: #FFFFFF;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(194, 125, 88, 0.3);
        }

        .btn--secondary {
            background-color: var(--color-secondary-accent);
            color: #FFFFFF;
            border-color: var(--color-secondary-accent);
        }

        .btn--secondary:hover {
            background-color: var(--color-secondary-hover);
            border-color: var(--color-secondary-hover);
            color: #FFFFFF;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(91, 112, 101, 0.3);
        }

        .hero {
            background: linear-gradient(135deg, rgba(31,28,26,0.88) 0%, rgba(45,42,38,0.82) 100%),
                        url('https://images.unsplash.com/photo-1511895426328-dc8714191300?auto=format&fit=crop&w=1600&q=80') center/cover no-repeat;
            color: #FAF8F5;
            padding: 5rem 2.5rem;
            border-radius: var(--border-radius-md);
            margin-bottom: 4rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.12);
            position: relative;
            border-left: 6px solid var(--color-accent);
        }

        .hero__content {
            max-width: 820px;
        }

        .hero__subtitle {
            color: var(--color-accent);
            font-size: 0.88rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .hero__title {
            color: #FAF8F5;
            font-size: 3rem;
            line-height: 1.2;
            margin-bottom: 1.5rem;
        }

        .hero__text {
            font-size: 1.2rem;
            color: #EFECE6;
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .hero__actions {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .card {
            background-color: #FFFFFF;
            border: 1px solid var(--color-border);
            padding: 2rem;
            border-radius: var(--border-radius-md);
            transition: var(--transition-smooth);
            position: relative;
            display: flex;
            flex-direction: column;
            box-shadow: 0 2px 8px rgba(0,0,0,0.03);
        }

        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 28px rgba(0,0,0,0.08);
            border-color: var(--color-accent);
        }

        .card__badge {
            align-self: flex-start;
            background-color: var(--color-terracotta-soft);
            color: var(--color-accent);
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            font-weight: 700;
            padding: 0.3rem 0.7rem;
            margin-bottom: 1rem;
            border-radius: var(--border-radius-sm);
        }

        .card__badge--salvia {
            background-color: var(--color-salvia-soft);
            color: var(--color-secondary-accent);
        }

        .card__title {
            font-size: 1.4rem;
            margin-bottom: 0.85rem;
            color: var(--color-dark-marble);
        }

        .card__text {
            color: #4A4540;
            font-size: 1rem;
            flex-grow: 1;
        }

        .timeline {
            position: relative;
            padding: 2rem 0;
            margin: 2rem 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            top: 0;
            bottom: 0;
            left: 50%;
            width: 2px;
            background-color: var(--color-accent);
            transform: translateX(-50%);
        }

        .timeline__item {
            position: relative;
            width: 50%;
            padding: 0 2.5rem 2.5rem 2.5rem;
            box-sizing: border-box;
        }

        .timeline__item--left {
            left: 0;
            text-align: right;
        }

        .timeline__item--right {
            left: 50%;
            text-align: left;
        }

        .timeline__node {
            position: absolute;
            top: 0;
            width: 18px;
            height: 18px;
            background-color: var(--color-accent);
            border: 4px solid var(--color-bg-primary);
            border-radius: 50%;
            z-index: 2;
        }

        .timeline__item--left .timeline__node {
            right: -9px;
        }

        .timeline__item--right .timeline__node {
            left: -9px;
        }

        .timeline__content {
            background: #FFFFFF;
            padding: 1.75rem;
            border: 1px solid var(--color-border);
            border-radius: var(--border-radius-md);
            box-shadow: 0 4px 14px rgba(0,0,0,0.03);
        }

        .timeline__era {
            font-family: var(--font-heading);
            font-size: 1.25rem;
            color: var(--color-accent);
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .table-responsive {
            width: 100%;
            overflow-x: auto;
            margin: 2rem 0;
            border: 1px solid var(--color-border);
            border-radius: var(--border-radius-md);
            background-color: #FFFFFF;
        }

        .family-table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
        }

        .family-table th {
            background-color: var(--color-dark-marble);
            color: #FAF8F5;
            font-family: var(--font-heading);
            padding: 1.1rem;
            font-size: 0.95rem;
            letter-spacing: 1px;
            border-bottom: 3px solid var(--color-accent);
        }

        .family-table td {
            padding: 1.1rem;
            border-bottom: 1px solid var(--color-bg-secondary);
            font-size: 0.98rem;
            color: var(--color-text-main);
        }

        .family-table tr:nth-child(even) {
            background-color: var(--color-bg-primary);
        }

        .family-table tr:hover {
            background-color: var(--color-terracotta-soft);
        }

        .filter-bar {
            display: flex;
            justify-content: center;
            gap: 0.6rem;
            flex-wrap: wrap;
            margin-bottom: 2.5rem;
        }

        .filter-btn {
            background-color: var(--color-bg-secondary);
            border: 1px solid var(--color-border);
            color: var(--color-text-main);
            padding: 0.65rem 1.25rem;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 700;
            cursor: pointer;
            border-radius: var(--border-radius-sm);
            transition: var(--transition-smooth);
        }

        .filter-btn:hover, .filter-btn--active {
            background-color: var(--color-accent);
            color: #FFFFFF;
            border-color: var(--color-accent);
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }

        .resource-card {
            background: #FFFFFF;
            border: 1px solid var(--color-border);
            border-radius: var(--border-radius-md);
            overflow: hidden;
            cursor: pointer;
            transition: var(--transition-smooth);
            box-shadow: 0 2px 8px rgba(0,0,0,0.03);
            display: flex;
            flex-direction: column;
        }

        .resource-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.09);
            border-color: var(--color-accent);
        }

        .resource-card__img-wrapper {
            width: 100%;
            height: 210px;
            overflow: hidden;
            background-color: var(--color-bg-secondary);
            position: relative;
        }

        .resource-card__img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition-smooth);
        }

        .resource-card:hover .resource-card__img {
            transform: scale(1.05);
        }

        .resource-card__body {
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .resource-card__category {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            color: var(--color-accent);
            font-weight: 700;
            display: block;
            margin-bottom: 0.35rem;
        }

        .resource-card__title {
            font-size: 1.3rem;
            margin-bottom: 0.6rem;
        }

        .resource-card__desc {
            font-size: 0.95rem;
            color: #55504A;
            line-height: 1.6;
            margin-bottom: 1rem;
            flex-grow: 1;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(31, 28, 26, 0.85);
            backdrop-filter: blur(4px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 1.5rem;
            animation: fadeIn 0.3s ease-out;
        }

        .modal--active {
            display: flex;
        }

        .modal__content {
            background-color: #FFFFFF;
            border: 2px solid var(--color-accent);
            border-radius: var(--border-radius-md);
            max-width: 720px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            padding: 2.5rem;
            position: relative;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .modal__close {
            position: absolute;
            top: 1rem;
            right: 1.5rem;
            background: none;
            border: none;
            font-size: 2.2rem;
            color: var(--color-dark-marble);
            cursor: pointer;
            line-height: 1;
        }

        .modal__close:hover {
            color: var(--color-accent);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            font-weight: 700;
            font-size: 0.88rem;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--color-dark-marble);
        }

        .form-input, .form-textarea, .form-select {
            width: 100%;
            padding: 0.85rem 1rem;
            border: 1px solid var(--color-border);
            border-radius: var(--border-radius-sm);
            font-family: var(--font-body);
            font-size: 1rem;
            background-color: #FFFFFF;
            color: var(--color-text-main);
            transition: var(--transition-smooth);
        }

        .form-input:focus, .form-textarea:focus, .form-select:focus {
            border-color: var(--color-accent);
            outline: none;
            box-shadow: 0 0 0 3px var(--color-terracotta-soft);
        }

        .form-error {
            color: #C0392B;
            font-size: 0.85rem;
            margin-top: 0.35rem;
            display: none;
        }

        .toast {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background-color: var(--color-dark-marble);
            color: #FAF8F5;
            border-left: 5px solid var(--color-accent);
            padding: 1.2rem 1.8rem;
            border-radius: var(--border-radius-sm);
            box-shadow: 0 10px 25px rgba(0,0,0,0.25);
            display: none;
            z-index: 3000;
            animation: fadeIn 0.3s ease-out;
            font-weight: 700;
        }

        .footer {
            background-color: var(--color-dark-marble);
            color: #EFECE6;
            border-top: 3px solid var(--color-accent);
            padding: 4.5rem 1.5rem 2.5rem 1.5rem;
            margin-top: 5rem;
        }

        .footer__container {
            max-width: var(--max-width-container);
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 2.5rem;
            margin-bottom: 3rem;
        }

        .footer__col-title {
            font-family: var(--font-heading);
            color: #FAF8F5;
            font-size: 1.2rem;
            margin-bottom: 1.2rem;
            border-bottom: 1px solid rgba(194, 125, 88, 0.3);
            padding-bottom: 0.5rem;
        }

        .footer__list {
            list-style: none;
        }

        .footer__list-item {
            margin-bottom: 0.6rem;
        }

        .footer__link {
            color: #C2BBB2;
            font-size: 0.92rem;
            cursor: pointer;
        }

        .footer__link:hover {
            color: var(--color-accent);
        }

        .footer__bottom {
            max-width: var(--max-width-container);
            margin: 0 auto;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 2rem;
            text-align: center;
            font-size: 0.88rem;
            color: #9A9288;
        }

        @media (max-width: 900px) {
            .hero__title { font-size: 2.3rem; }
            .section-header__title { font-size: 2rem; }
            .timeline::before { left: 20px; }
            .timeline__item { width: 100%; padding-left: 3.2rem; padding-right: 0; text-align: left !important; }
            .timeline__item--right { left: 0; }
            .timeline__node { left: 11px !important; }
        }

        @media (max-width: 768px) {
            .nav__list {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: var(--color-dark-marble);
                padding: 1.5rem;
                border-bottom: 3px solid var(--color-accent);
            }

            .nav__list--open {
                display: flex;
            }

            .nav__mobile-toggle {
                display: block;
            }
        }
    </style>
</head>
<body>

    <header class="header">
        <div class="header__container">
            <div class="header__brand" onclick="navigateTo('index')" role="button" tabindex="0">
                <div class="header__logo-mark">F</div>
                <div>
                    <span class="header__title">Instituto de la Familia</span>
                    <span class="header__subtitle">Desarrollo Humano & Dinámicas Sociales</span>
                </div>
            </div>

            <button class="nav__mobile-toggle" id="mobile-toggle" aria-label="Abrir menú de navegación">
                ☰
            </button>

            <nav class="nav" id="main-nav">
                <ul class="nav__list">
                    <li><a href="#index" class="nav__link nav__link--active" onclick="navigateTo('index')">Inicio</a></li>
                    <li><a href="#historia" class="nav__link" onclick="navigateTo('historia')">Historia</a></li>
                    <li><a href="#etapas" class="nav__link" onclick="navigateTo('etapas')">Ciclo Vital</a></li>
                    <li><a href="#crianza" class="nav__link" onclick="navigateTo('crianza')">Crianza</a></li>
                    <li><a href="#comunicacion" class="nav__link" onclick="navigateTo('comunicacion')">Convivencia</a></li>
                    <li><a href="#genealogia" class="nav__link" onclick="navigateTo('genealogia')">Genealogía</a></li>
                    <li><a href="#diversidad" class="nav__link" onclick="navigateTo('diversidad')">Diversidad</a></li>
                    <li><a href="#salud_emocional" class="nav__link" onclick="navigateTo('salud_emocional')">Salud Mental</a></li>
                    <li><a href="#galeria" class="nav__link" onclick="navigateTo('galeria')">Biblioteca</a></li>
                    <li><a href="#contacto" class="nav__link" onclick="navigateTo('contacto')">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main class="main-container">

        <section id="page-index" class="page-view page-view--active">
            <div class="hero">
                <div class="hero__content">
                    <span class="hero__subtitle">Centro de Investigación y Ciencias Sociales</span>
                    <h1 class="hero__title">La Familia como Núcleo Afectivo y Cultural del Ser Humano</h1>
                    <p class="hero__text">
                        Un espacio enciclopédico e institucional consagrado a la investigación rigurosa de las dinámicas familiares, los modelos de crianza, la cohesión intergeneracional y el desarrollo psicoemocional a lo largo del ciclo vital.
                    </p>
                    <div class="hero__actions">
                        <button class="btn btn--primary" onclick="navigateTo('galeria')">Explorar Biblioteca de Recursos</button>
                        <button class="btn btn--secondary" onclick="navigateTo('etapas')">Ciclo Vital Familiar</button>
                    </div>
                </div>
            </div>

            <div class="section-header">
                <span class="section-header__tag">Fundamentos Sistémicos</span>
                <h2 class="section-header__title">Los 4 Pilares del Bienestar Familiar</h2>
                <p class="section-header__lead">Principios clave respaldados por la psicología evolutiva, la sociología y la terapia familiar sistémica.</p>
            </div>

            <div class="grid">
                <article class="card">
                    <span class="card__badge">Pilar I</span>
                    <h3 class="card__title">Afecto incondicional y Seguridad</h3>
                    <p class="card__text">
                        La construcción de un apego seguro durante las primeras etapas de la infancia constituye la matriz neural y emocional sobre la cual el individuo desarrollará su autoestima, resiliencia y capacidad de vinculación en la vida adulta.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge card__badge--salvia">Pilar II</span>
                    <h3 class="card__title">Comunicación Asertiva</h3>
                    <p class="card__text">
                        El diálogo abierto, la escucha activa y la validación emocional reducen la reactividad del sistema familiar, transformando los desacuerdos inevitables en oportunidades de crecimiento y aprendizaje mutuo.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge">Pilar III</span>
                    <h3 class="card__title">Cohesión y Pertenencia</h3>
                    <p class="card__text">
                        La presencia de rituales familiares, tradiciones compartidas y normas claras crea una estructura protectora que brinda estabilidad psíquica ante las transiciones vitales y las crisis sociocontextuales.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge card__badge--salvia">Pilar IV</span>
                    <h3 class="card__title">Autonomía e Individualización</h3>
                    <p class="card__text">
                        Un sistema familiar saludable fomenta el sentido de pertenencia sin asfixiar la identidad individual, permitiendo que cada miembro desarrolle sus metas particulares en un clima de respeto y diferenciación.
                    </p>
                </article>
            </div>
        </section>

        <section id="page-historia" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Perspectiva Antropológica</span>
                <h2 class="section-header__title">Evolución Histórica de la Estructura Familiar</h2>
                <p class="section-header__lead">Un recorrido cronológico por la transformación del grupo familiar desde las bandas ancestrales hasta la era contemporánea.</p>
            </div>

            <div class="timeline">
                <div class="timeline__item timeline__item--left">
                    <div class="timeline__node"></div>
                    <div class="timeline__content">
                        <div class="timeline__era">Prehistoria - El Clan Clan y la Horda Ancestral</div>
                        <h4>Cooperación Aliancista y Crianza Compartida</h4>
                        <p>En las comunidades de cazadores-recolectores, la familia no se limitaba a la unidad biológica. La sobrevivencia dependía de la "alocrianza" (crianza comunitaria), donde todo el clan compartía el cuidado y la protección de la infancia.</p>
                    </div>
                </div>

                <div class="timeline__item timeline__item--right">
                    <div class="timeline__node"></div>
                    <div class="timeline__content">
                        <div class="timeline__era">Antigüedad y Edad Media - La Familia Extensa Patriarcal</div>
                        <h4>Unidad de Producción y Linaje Patrimonial</h4>
                        <p>Con el desarrollo de la agricultura y la propiedad privada, la familia se estructuró de forma jerárquica y patriarcal. Múltiples generaciones convivían bajo el mismo techo, funcionando como una unidad económica de trabajo agrícola.</p>
                    </div>
                </div>

                <div class="timeline__item timeline__item--left">
                    <div class="timeline__node"></div>
                    <div class="timeline__content">
                        <div class="timeline__era">Siglos XIX y XX - La Revolución Industrial y la Familia Nuclear</div>
                        <h4>Urbanización y Especialización de Roles</h4>
                        <p>La migración a las ciudades industriales fragmentó la gran familia extensa. Emergió el modelo de familia nuclear (padre, madre e hijos) con una delimitación marcada entre la esfera laboral del hogar y el trabajo fabril.</p>
                    </div>
                </div>

                <div class="timeline__item timeline__item--right">
                    <div class="timeline__node"></div>
                    <div class="timeline__content">
                        <div class="timeline__era">Siglo XXI - Pluralidad y Redes Afectivas</div>
                        <h4>Diversidad de Estructuras y Co-Responsabilidad</h4>
                        <p>La democratización del hogar, la incorporación de la mujer al mercado laboral formal y los cambios socioculturales dan paso a la coexistencia legitima de múltiples tipologías familiares unidas por el vínculo afectivo.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="page-etapas" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Psicología Evolutiva</span>
                <h2 class="section-header__title">El Ciclo de Vida Familiar</h2>
                <p class="section-header__lead">Análisis de las transiciones normativas y los desafíos sistémicos en las seis etapas fundamentales.</p>
            </div>

            <div class="grid">
                <article class="card">
                    <span class="card__badge">Etapa 1</span>
                    <h3 class="card__title">Formación de la Pareja</h3>
                    <p class="card__text">
                        Consiste en la negociación de fronteras, fusión de hábitos individuales y creación de una nueva identidad compartida sin perder la autonomía de origen.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge card__badge--salvia">Etapa 2</span>
                    <h3 class="card__title">Crianza Inicial y Primera Infancia</h3>
                    <p class="card__text">
                        Apertura del sistema dinámico para dar entrada a los hijos. Reorganización de las tareas domésticas, renegociación del tiempo de pareja y establecimiento de apegos primarios.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge">Etapa 3</span>
                    <h3 class="card__title">Familia con Hijos Escolares y Adolescentes</h3>
                    <p class="card__text">
                        Flexibilización de los límites familiares para permitir el ingreso a las instituciones educativas y acompañar el proceso de emancipación e identidad de la adolescencia.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge card__badge--salvia">Etapa 4</span>
                    <h3 class="card__title">Plataforma de Lanzamiento (Nido Vacío)</h3>
                    <p class="card__text">
                        Salida de los hijos del hogar para iniciar vidas independientes. La pareja se reencuentra en una nueva fase de convivencia y redefinición de objetivos compartidos.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge">Etapa 5</span>
                    <h3 class="card__title">Etapa de la Abuelidad y Senectud</h3>
                    <p class="card__text">
                        Aceptación del relevo generacional, transmisión de la sabiduría histórica acumulada, afrontamiento del retiro laboral y mantenimiento de la dignidad afectiva.
                    </p>
                </article>
            </div>
        </section>

        <section id="page-crianza" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Parentalidad Consciente</span>
                <h2 class="section-header__title">Estilos de Crianza y Desarrollo Infantil</h2>
                <p class="section-header__lead">Cuadro comparativo científico según la tipología de Diana Baumrind y la psicología del desarrollo.</p>
            </div>

            <div class="table-responsive">
                <table class="family-table">
                    <thead>
                        <tr>
                            <th>Estilo Parental</th>
                            <th>Nivel de Afecto / Sensibilidad</th>
                            <th>Nivel de Exigencia / Control</th>
                            <th>Impacto Psicoemocional en el Hijo</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>Democrático / Respetuoso</strong></td>
                            <td>Alto (Cálido y receptivo)</td>
                            <td>Alto (Límites claros e explicados)</td>
                            <td>Alta autoestima, autorregulación emocional, habilidades sociales sobresalientes e independencia.</td>
                        </tr>
                        <tr>
                            <td><strong>Autoritario</strong></td>
                            <td>Bajo (Frío y punitivo)</td>
                            <td>Muy Alto (Normas rígidas sin diálogo)</td>
                            <td>Tendencia a la ansiedad, obediencia por temor, baja autoestima y posibles estallidos agresivos.</td>
                        </tr>
                        <tr>
                            <td><strong>Permisivo</strong></td>
                            <td>Muy Alto (Afectivo pero sin estructura)</td>
                            <td>Bajo (Ausencia de normas)</td>
                            <td>Dificultad para tolerar la frustración, baja autorregulación y egocentrismo social.</td>
                        </tr>
                        <tr>
                            <td><strong>Indiferente / Negligente</strong></td>
                            <td>Bajo (Ausente emocionalmente)</td>
                            <td>Bajo (Ausente operativamente)</td>
                            <td>Inseguridad profunda, vulnerabilidad a conductas de riesgo e inestabilidad afectiva.</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <section id="page-comunicacion" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Dinámicas de Convivencia</span>
                <h2 class="section-header__title">Resolución de Conflictos y Convivencia Saludable</h2>
                <p class="section-header__lead">Estrategias operativas para fortalecer la inteligencia emocional colectiva en el hogar.</p>
            </div>

            <div class="grid">
                <article class="card">
                    <h3 class="card__title">Escucha Activa y Validación</h3>
                    <p class="card__text">
                        Aprender a escuchar sin interrumpir y validar el estado emocional del otro antes de proponer soluciones. Reconocer que la experiencia del hijo o de la pareja es legítima reduce inmediatamente la escalada del conflicto.
                    </p>
                </article>

                <article class="card">
                    <h3 class="card__title">Límites Claros y Consistentes</h3>
                    <p class="card__text">
                        Los límites no son castigos, sino marcos de seguridad que permiten a los niños comprender las consecuencias de sus acciones. Deben ser acordados previamente entre los adultos responsables y aplicarse con serenidad y firmeza.
                    </p>
                </article>

                <article class="card">
                    <h3 class="card__title">Gestión de la Reactividad Afectiva</h3>
                    <p class="card__text">
                        Implementar la "pausa consciente" durante momentos de alta tensión intrafamiliar evita que el enojo derive en agresiones verbales. Las conversaciones complejas deben postergarse hasta que el sistema nervioso recupere la calma.
                    </p>
                </article>
            </div>
        </section>

        <section id="page-genealogia" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Transgeneracionalidad</span>
                <h2 class="section-header__title">Genealogía, Memoria e Identidad Familiar</h2>
                <p class="section-header__lead">La reconstrucción de la historia familiar como herramienta de autoconocimiento y sentido de pertenencia.</p>
            </div>

            <div class="grid">
                <article class="card">
                    <span class="card__badge">Herramienta Clínica</span>
                    <h3 class="card__title">El Genograma Familiar</h3>
                    <p class="card__text">
                        Representación gráfica multiterrenal (mínimo 3 generaciones) que registra la estructura de la familia, sus eventos vitales significativos y los patrones de relación o lealtades invisibles a través de las décadas.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge card__badge--salvia">Patrimonio Oral</span>
                    <h3 class="card__title">Los Relatos Transgeneracionales</h3>
                    <p class="card__text">
                        Las historias narradas sobre los antepasados —sus migraciones, resiliencias y superaciones— otorgan a las nuevas generaciones un marco narrativo que fortalece la identidad personal y la resiliencia ante la adversidad.
                    </p>
                </article>
            </div>
        </section>

        <section id="page-diversidad" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Sociología Contemporánea</span>
                <h2 class="section-header__title">Diversidad y Estructuras Familiares Modernas</h2>
                <p class="section-header__lead">Composiciones familiares contemporáneas fundamentadas en el compromiso, el afecto y el respeto mutuo.</p>
            </div>

            <div class="grid">
                <article class="card">
                    <h3 class="card__title">Familia Monoparental</h3>
                    <p class="card__text">
                        Encabezada por un único progenitor (madre o padre) debido a elección personal, divorcio o viudez. Requiere redes de apoyo comunitarias sólidas para equilibrar la crianza y la vida laboral.
                    </p>
                </article>

                <article class="card">
                    <h3 class="card__title">Familia Reconstituida / Ensamblada</h3>
                    <p class="card__text">
                        Formada por una pareja donde uno o ambos miembros aportan hijos de relaciones previas. Su principal reto es la integración gradual y respetuosa de las nuevas figuras parentales.
                    </p>
                </article>

                <article class="card">
                    <h3 class="card__title">Familia Homoparental</h3>
                    <p class="card__text">
                        Integrada por una pareja del mismo sexo con hijos biológicos, adoptivos o por reproducción asistida. Estudios longitudinales confirman que el bienestar infantil depende de la calidad afectiva y no de la orientación sexual de los progenitores.
                    </p>
                </article>

                <article class="card">
                    <h3 class="card__title">Familia Adoptiva</h3>
                    <p class="card__text">
                        Unida por un vínculo jurídico y afectivo consciente. Se caracteriza por la integración abierta de la historia de origen del hijo, brindando un entorno incondicional de seguridad.
                    </p>
                </article>
            </div>
        </section>

        <section id="page-salud_emocional" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Bienestar Psicológico</span>
                <h2 class="section-header__title">Salud Mental y Prevención del Desgaste Parental</h2>
                <p class="section-header__lead">Orientación clínica para proteger el equilibrio emocional del hogar y conciliar las demandas cotidianas.</p>
            </div>

            <div class="grid">
                <article class="card">
                    <span class="card__badge">Prevención Clínica</span>
                    <h3 class="card__title">El Burnout Parental</h3>
                    <p class="card__text">
                        Síndrome de agotamiento físico y emocional extremo derivado de las exigencias continuas de la crianza. Se manifiesta con distanciamiento emocional hacia los hijos y sensación de ineficacia parental.
                    </p>
                </article>

                <article class="card">
                    <span class="card__badge card__badge--salvia">Conciliación</span>
                    <h3 class="card__title">Equilibrio Trabajo - Hogar</h3>
                    <p class="card__text">
                        Establecimiento de fronteras claras entre las jornadas laborales y el tiempo compartido en familia. La calidad de la presencia afectiva es más significativa para el niño que la mera cantidad de horas acumuladas.
                    </p>
                </article>
            </div>
        </section>

        <section id="page-galeria" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Catálogo Interactivo</span>
                <h2 class="section-header__title">Biblioteca de Recursos y Guías Familiares</h2>
                <p class="section-header__lead">Seleccione cualquier material académico para desplegar su ficha temática explicativa.</p>
            </div>

            <div class="filter-bar">
                <button class="filter-btn filter-btn--active" onclick="filterGallery('all')">Todos los Recursos</button>
                <button class="filter-btn" onclick="filterGallery('infancia')">Infancia</button>
                <button class="filter-btn" onclick="filterGallery('adolescencia')">Adolescencia</button>
                <button class="filter-btn" onclick="filterGallery('pareja')">Pareja</button>
                <button class="filter-btn" onclick="filterGallery('mayores')">Adultos Mayores</button>
                <button class="filter-btn" onclick="filterGallery('convivencia')">Convivencia</button>
            </div>

            <div class="gallery-grid" id="gallery-container">
                <!-- Contenido dinámico renderizado por JS -->
            </div>
        </section>

        <section id="page-contacto" class="page-view">
            <div class="section-header">
                <span class="section-header__tag">Orientación e Información</span>
                <h2 class="section-header__title">Contacto y Suscripción Institucional</h2>
                <p class="section-header__lead">Suscríbase al Boletín de Orientación Familiar y reciba guías de investigación actualizadas.</p>
            </div>

            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 3rem;">
                <div>
                    <h3 style="margin-bottom: 1.5rem;">Formulario de Registro</h3>
                    <form id="contact-form" onsubmit="handleFormSubmit(event)">
                        <div class="form-group">
                            <label class="form-label" for="fullname">Nombre y Apellidos</label>
                            <input type="text" id="fullname" class="form-input" placeholder="Ej. María García López" required>
                            <span class="form-error" id="error-fullname">Por favor, introduzca su nombre completo.</span>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="email">Correo Electrónico</label>
                            <input type="email" id="email" class="form-input" placeholder="correo@ejemplo.com" required>
                            <span class="form-error" id="error-email">Introduzca un correo electrónico válido.</span>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="topic">Área de Interés Principal</label>
                            <select id="topic" class="form-select">
                                <option value="crianza">Crianza Respetuosa e Infancia</option>
                                <option value="adolescencia">Acompañamiento en la Adolescencia</option>
                                <option value="pareja">Terapia y Vínculo de Pareja</option>
                                <option value="gerontologia">Acompañamiento a Adultos Mayores</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="message">Consulta o Comentario</label>
                            <textarea id="message" class="form-textarea" rows="4" placeholder="Escriba su consulta institucional..." required></textarea>
                            <span class="form-error" id="error-message">El mensaje debe tener al menos 10 caracteres.</span>
                        </div>

                        <button type="submit" class="btn btn--primary" style="width: 100%;">Registrar Suscripción</button>
                    </form>
                </div>

                <div>
                    <h3 style="margin-bottom: 1.5rem;">Sede del Instituto</h3>
                    <div class="card" style="margin-bottom: 1.5rem;">
                        <p><strong>Dirección:</strong> Av. de las Ciencias Sociales 204, Pabellón Humanístico.</p>
                        <p><strong>Atención Docente:</strong> Lunes a Viernes: 08:30 - 17:30 hrs.</p>
                        <p><strong>Correo Institucional:</strong> contacto@institutofamilia.org</p>
                    </div>

                    <div style="width: 100%; height: 230px; background-color: var(--color-dark-marble); border: 1px solid var(--color-accent); display: flex; align-items: center; justify-content: center; color: var(--color-accent); text-align: center; padding: 1.5rem; border-radius: var(--border-radius-md);">
                        <div>
                            <span style="font-size: 2.2rem; display: block; margin-bottom: 0.5rem;">🏡</span>
                            <p style="margin: 0; font-family: var(--font-heading); color: #FAF8F5; font-size: 1.1rem;">Centro de Documentación Abierto</p>
                            <span style="font-size: 0.85rem; color: #A69D94;">Acceso a Investigadores y Familias</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <div class="modal" id="resource-modal" role="dialog" aria-modal="true">
        <div class="modal__content">
            <button class="modal__close" onclick="closeModal()" aria-label="Cerrar ventana modal">&times;</button>
            <div id="modal-body-content">
                <!-- Carga dinámica del recurso -->
            </div>
        </div>
    </div>

    <div class="toast" id="toast-message">Registro completado con éxito.</div>

    <footer class="footer">
        <div class="footer__container">
            <div>
                <h4 class="footer__col-title">Instituto de la Familia</h4>
                <p style="font-size: 0.92rem; color: #B3AAA0;">
                    Centro de estudios e investigación dedicado a la divulgación académica sobre la evolución de la familia, el desarrollo humano y la resiliencia comunitaria.
                </p>
            </div>

            <div>
                <h4 class="footer__col-title">Secciones Educativas</h4>
                <ul class="footer__list">
                    <li class="footer__list-item"><a href="#historia" class="footer__link" onclick="navigateTo('historia')">Evolución Histórica</a></li>
                    <li class="footer__list-item"><a href="#etapas" class="footer__link" onclick="navigateTo('etapas')">Ciclo Vital Familiar</a></li>
                    <li class="footer__list-item"><a href="#crianza" class="footer__link" onclick="navigateTo('crianza')">Estilos de Crianza</a></li>
                    <li class="footer__list-item"><a href="#galeria" class="footer__link" onclick="navigateTo('galeria')">Biblioteca Virtual</a></li>
                </ul>
            </div>

            <div>
                <h4 class="footer__col-title">Lineamientos Éticos</h4>
                <ul class="footer__list">
                    <li class="footer__list-item"><span class="footer__link">Código de Protección a la Infancia</span></li>
                    <li class="footer__list-item"><span class="footer__link">Inclusión y Diversidad Afectiva</span></li>
                    <li class="footer__list-item"><span class="footer__link">Estándares Internacionales WCAG 2.1</span></li>
                </ul>
            </div>
        </div>

        <div class="footer__bottom">
            <p>&copy; 2026 Instituto Internacional de Estudios sobre la Familia y Desarrollo Humano. Todos los derechos reservados.</p>
        </div>
    </footer>

    <script>
        const RESOURCE_DATABASE = [
            {
                id: 'guia-apego',
                title: 'Guía de Apego Seguro en la Infancia Temprana',
                category: 'infancia',
                categoryLabel: 'Infancia',
                img: 'https://images.unsplash.com/photo-1542037104857-ffbb0b9155fb?auto=format&fit=crop&w=600&q=80',
                desc: 'Manual práctico para fortalecer la sintonía afectiva en los primeros años de vida.',
                fullText: 'El apego seguro no exige perfección en los progenitores, sino disponibilidad emocional constante y sensibilidad ante las señales de estrés del bebé. Esta guía explora la regulación del sistema nervioso infantil a través del contacto físico y la contención sincrónica.',
                autor: 'Dra. Elena Benítez (Psicóloga Evolutiva)'
            },
            {
                id: 'dialogo-adolescente',
                title: 'Comunicación y Puentes en la Adolescencia',
                category: 'adolescencia',
                categoryLabel: 'Adolescencia',
                img: 'https://images.unsplash.com/photo-1529156069898-49953e39b3ac?auto=format&fit=crop&w=600&q=80',
                desc: 'Estrategias para negociar la autonomía sin perder la cercanía afectiva.',
                fullText: 'Durante la adolescencia, el cerebro atraviesa una importante reestructuración en la corteza prefrontal. La labor parental consiste en pasar del control directo al acompañamiento consultivo, manteniendo límites firmes en aspectos de seguridad pero respetando la privacidad del joven.',
                autor: 'Prof. Carlos Mendoza (Sociólogo Familiar)'
            },
            {
                id: 'acuerdos-pareja',
                title: 'Construcción de Acuerdos en la Pareja',
                category: 'pareja',
                categoryLabel: 'Pareja',
                img: 'https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?auto=format&fit=crop&w=600&q=80',
                desc: 'Protocolos de diálogo constructivo para resolver diferencias de convivencia.',
                fullText: 'Las crisis de pareja suelen surgir cuando los modelos implícitos aprendidos en las familias de origen chocan de forma silenciosa. Este recurso ofrece metodologías de negociación abierta sobre la distribución del trabajo del hogar y el tiempo de ocio.',
                autor: 'Instituto de Terapia Sistémica'
            },
            {
                id: 'abuelidad-activa',
                title: 'El Rol Transgeneracional de los Abuelos',
                category: 'mayores',
                categoryLabel: 'Adultos Mayores',
                img: 'https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80',
                desc: 'El valor de la ancianidad en el traspaso de la memoria e identidad familiar.',
                fullText: 'Los abuelos aportan una dimensión de afecto incondicional y estabilidad histórica insustituible. Analizamos cómo establecer fronteras saludables para evitar el sobreagotamiento del adulto mayor en el cuidado diario sin perder el vínculo afectivo enriquecedor.',
                autor: 'Dra. Sofia Alarcón (Gerontóloga)'
            },
            {
                id: 'resolucion-conflictos',
                title: 'Técnicas de Mediación Intrafamiliar',
                category: 'convivencia',
                categoryLabel: 'Convivencia',
                img: 'https://images.unsplash.com/photo-1491438590914-bc09fcaaf77a?auto=format&fit=crop&w=600&q=80',
                desc: 'Mecanismos para desescalar el enojo y llegar a consensos respetuosos.',
                fullText: 'Un conflicto no resuelto adecuadamente tiende a repetirse en patrones cada vez más rígidos. Mediante la técnica de los enunciados en primera persona ("Yo me siento...") en lugar de recriminaciones ("Tú siempre..."), los miembros aprenden a expresar necesidades sin atacar al otro.',
                autor: 'Gabinete de Mediación Familiar'
            }
        ];

        function navigateTo(pageId) {
            const pages = document.querySelectorAll('.page-view');
            pages.forEach(p => p.classList.remove('page-view--active'));

            const navLinks = document.querySelectorAll('.nav__link');
            navLinks.forEach(link => link.classList.remove('nav__link--active'));

            const targetPage = document.getElementById(`page-${pageId}`);
            if (targetPage) {
                targetPage.classList.add('page-view--active');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }

            const activeLink = document.querySelector(`.nav__link[href="#${pageId}"]`);
            if (activeLink) {
                activeLink.classList.add('nav__link--active');
            }

            const mainNav = document.getElementById('main-nav');
            if (mainNav.classList.contains('nav__list--open')) {
                mainNav.classList.remove('nav__list--open');
            }
        }

        function renderGallery(items) {
            const container = document.getElementById('gallery-container');
            if (!container) return;

            container.innerHTML = items.map(item => `
                <article class="resource-card" onclick="openResourceModal('${item.id}')">
                    <div class="resource-card__img-wrapper">
                        <img src="${item.img}" alt="${item.title}" class="resource-card__img" loading="lazy">
                    </div>
                    <div class="resource-card__body">
                        <span class="resource-card__category">${item.categoryLabel}</span>
                        <h3 class="resource-card__title">${item.title}</h3>
                        <p class="resource-card__desc">${item.desc}</p>
                        <span style="font-size: 0.8rem; color: var(--color-accent); font-weight: 700;">Leer Ficha Académica &rarr;</span>
                    </div>
                </article>
            `).join('');
        }

        function filterGallery(category) {
            const buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(btn => btn.classList.remove('filter-btn--active'));

            if (event && event.target) {
                event.target.classList.add('filter-btn--active');
            }

            if (category === 'all') {
                renderGallery(RESOURCE_DATABASE);
            } else {
                const filtered = RESOURCE_DATABASE.filter(r => r.category === category);
                renderGallery(filtered);
            }
        }

        function openResourceModal(resourceId) {
            const item = RESOURCE_DATABASE.find(r => r.id === resourceId);
            if (!item) return;

            const modalContent = document.getElementById('modal-body-content');
            modalContent.innerHTML = `
                <span style="color: var(--color-accent); text-transform: uppercase; letter-spacing: 2px; font-size: 0.8rem; font-weight: 700;">${item.categoryLabel}</span>
                <h2 style="font-size: 1.8rem; margin-top: 0.25rem; margin-bottom: 1rem; color: var(--color-dark-marble);">${item.title}</h2>
                <img src="${item.img}" alt="${item.title}" style="width: 100%; height: 250px; object-fit: cover; border-radius: var(--border-radius-sm); margin-bottom: 1.5rem;">
                
                <h4 style="margin-bottom: 0.5rem;">Resumen de la Investigación</h4>
                <p style="color: #444; margin-bottom: 1.5rem; line-height: 1.7;">${item.fullText}</p>
                
                <div style="background-color: var(--color-bg-secondary); padding: 1.2rem; border-left: 4px solid var(--color-accent); border-radius: var(--border-radius-sm);">
                    <p style="margin: 0; font-size: 0.9rem;"><strong>Autoría / Fuente:</strong> ${item.autor}</p>
                </div>
            `;

            document.getElementById('resource-modal').classList.add('modal--active');
        }

        function closeModal() {
            document.getElementById('resource-modal').classList.remove('modal--active');
        }

        function handleFormSubmit(event) {
            event.preventDefault();

            const name = document.getElementById('fullname').value.trim();
            const email = document.getElementById('email').value.trim();
            const message = document.getElementById('message').value.trim();

            let isValid = true;

            if (name.length < 3) {
                document.getElementById('error-fullname').style.display = 'block';
                isValid = false;
            } else {
                document.getElementById('error-fullname').style.display = 'none';
            }

            if (!email.includes('@') || !email.includes('.')) {
                document.getElementById('error-email').style.display = 'block';
                isValid = false;
            } else {
                document.getElementById('error-email').style.display = 'none';
            }

            if (message.length < 10) {
                document.getElementById('error-message').style.display = 'block';
                isValid = false;
            } else {
                document.getElementById('error-message').style.display = 'none';
            }

            if (isValid) {
                showToast("Su registro ha sido procesado exitosamente por la Secretaría Institucional.");
                document.getElementById('contact-form').reset();
            }
        }

        function showToast(msg) {
            const toast = document.getElementById('toast-message');
            toast.innerText = msg;
            toast.style.display = 'block';
            setTimeout(() => {
                toast.style.display = 'none';
            }, 4000);
        }

        window.addEventListener('DOMContentLoaded', () => {
            renderGallery(RESOURCE_DATABASE);

            const mobileBtn = document.getElementById('mobile-toggle');
            const mainNav = document.querySelector('.nav__list');
            if (mobileBtn && mainNav) {
                mobileBtn.addEventListener('click', () => {
                    mainNav.classList.toggle('nav__list--open');
                });
            }

            const currentHash = window.location.hash.replace('#', '');
            if (currentHash && document.getElementById(`page-${currentHash}`)) {
                navigateTo(currentHash);
            } else {
                navigateTo('index');
            }

            const modal = document.getElementById('resource-modal');
            window.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeModal();
                }
            });
        });
    </script>
</body>
</html>
