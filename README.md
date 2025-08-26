# Proyecto-XICOTENCATL-
Web XICOTENCATL 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WEB IA /JORGE XICOTENCATL -Estrategias Dinámicas para Redes Sociales</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
        href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&family=Playfair+Display:wght@400;700&display=swap"
        rel="stylesheet">
    <style>
        :root {
            --primary-color: #0A192F;   /* Azul Marino */
            --accent-color: #FFD700;    /* Oro de acento */
            --dark-color: #000F21;      /* Azul muy oscuro */
            --medium-dark-color: #10213D; /* Azul medio oscuro */
            --light-color: #F5F5DC;     /* Blanco roto */
            --title-color: #40E0D0;     /* Aguamarina para el título */
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--dark-color);
            color: var(--light-color);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }

        /* --- Estilos del Header --- */
        .main-header {
            background-color: var(--dark-color);
            position: fixed;
            width: 100%;
            z-index: 1000;
            top: 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
            transition: background-color 0.3s ease, padding 0.3s ease;
        }

        /* Estilos del header al hacer scroll */
        .main-header.scrolled {
            background-color: rgba(0, 15, 33, 0.95);
            padding: 0.5rem 0;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.6);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
            transition: padding 0.3s ease;
        }

        .logo a {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            text-decoration: none;
            color: var(--accent-color);
            transition: color 0.3s ease, font-size 0.3s ease;
        }

        .main-header.scrolled .logo a {
            font-size: 1.5rem;
        }

        .logo a:hover {
            color: var(--title-color);
        }

        .main-nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            gap: 1.5rem;
        }

        .main-nav a {
            text-decoration: none;
            color: var(--light-color);
            font-weight: 600;
            position: relative;
            transition: color 0.3s ease;
        }

        .main-nav a:hover {
            color: var(--accent-color);
        }

        /* --- Sección Hero --- */
        .hero-section {
            height: 100vh;
            background: linear-gradient(rgba(0, 15, 33, 0.8), rgba(0, 15, 33, 0.8)),
                url('https://images.unsplash.com/photo-1517048676732-d65bc937f952?q=80&w=2070&auto=format&fit=crop') no-repeat center center/cover;
            display: flex;
            align-items: center;
            text-align: center;
            position: relative;
            overflow: hidden; /* Asegura que las partículas no se desborden */
        }

        /* Estilos para el canvas de las partículas */
        #particles-js {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1; /* Asegura que las partículas estén detrás del contenido */
        }

        .hero-content {
            position: relative;
            z-index: 2;
            width: 100%;
            opacity: 0;
            transform: translateY(20px);
            animation: slideUp 0.8s ease-out forwards 0.3s;
        }

        .hero-content h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--title-color);
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2.5rem;
            color: var(--light-color);
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* --- Botón de Llamada a la Acción --- */
        .cta-button {
            background-color: var(--accent-color);
            color: var(--primary-color);
            padding: 1rem 3rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: inline-block;
            box-shadow: 0 4px 0px 0 var(--dark-color);
            transform: translateY(0);
            transition: all 0.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            cursor: pointer;
        }

        .cta-button:hover {
            background-color: var(--title-color);
            transform: translateY(-2px) scale(1.02);
            box-shadow: 0 6px 0px 0 var(--dark-color);
        }

        .cta-button:active {
            transform: translateY(2px) scale(0.98);
            box-shadow: 0 2px 0px 0 var(--dark-color);
        }

        /* --- Estilos Generales de Secciones --- */
        section {
            padding: 6rem 0;
            text-align: center;
            transition: background-color 0.5s ease;
            opacity: 0;
            transform: translateY(30px);
        }

        section.active {
            opacity: 1;
            transform: translateY(0);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        .section-dark {
            background-color: var(--dark-color);
        }

        .section-medium-dark {
            background-color: var(--medium-dark-color);
        }

        section h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 4rem;
            color: var(--accent-color);
            opacity: 0;
            transform: translateY(-10px);
            transition: opacity 0.6s ease-out 0.2s, transform 0.6s ease-out 0.2s;
        }

        section.active h2 {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- Sección de Estadísticas --- */
        .stats-section .container {
            padding-top: 2rem;
            padding-bottom: 2rem;
        }

        .stats-grid {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 2rem;
        }

        .stat-item {
            flex-basis: 30%;
            text-align: center;
            padding: 1.5rem;
            border-radius: 8px;
            background-color: var(--dark-color);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        .stat-number {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 800;
            color: var(--accent-color);
            margin: 0 0 0.5rem;
        }

        .stat-item p {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--light-color);
            opacity: 0.9;
        }

        /* --- Sección de Servicios --- */
        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            opacity: 0;
            transition: opacity 0.6s ease-out 0.4s;
        }

        section.active .service-grid {
            opacity: 1;
        }

        .service-card {
            background-color: var(--dark-color);
            padding: 2.5rem;
            border-radius: 10px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
            border-bottom: 4px solid var(--primary-color);
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s ease;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.4s ease-out, transform 0.4s ease-out;
        }

        section.active .service-grid .service-card:nth-child(1) {
            opacity: 1;
            transform: translateY(0);
            transition-delay: 0.5s;
        }

        section.active .service-grid .service-card:nth-child(2) {
            opacity: 1;
            transform: translateY(0);
            transition-delay: 0.6s;
        }

        section.active .service-grid .service-card:nth-child(3) {
            opacity: 1;
            transform: translateY(0);
            transition-delay: 0.7s;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.6);
            border-color: var(--accent-color);
        }

        .service-card img {
            width: 120px;
            height: 120px;
            margin-bottom: 1.5rem;
            transition: transform 0.4s ease-in-out;
        }

        .service-card:hover img {
            transform: scale(1.1);
        }

        .service-card h3 {
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--title-color);
            transition: color 0.3s ease;
        }

        .service-card:hover h3 {
            color: var(--accent-color);
        }

        /* --- Sección de Testimonios y Contacto --- */
        .testimonial-card,
        .contact-form {
            background-color: var(--dark-color);
            padding: 3rem;
            border-radius: 10px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
            border-left: 4px solid var(--accent-color);
            opacity: 0;
            transform: translateX(-30px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        section.active .testimonial-card,
        section.active .contact-form {
            opacity: 1;
            transform: translateX(0);
            transition-delay: 0.5s;
        }

        .testimonial-card {
            max-width: 800px;
            margin: 0 auto;
        }

        .testimonial-text {
            font-style: italic;
            font-size: 1.25rem;
            margin-bottom: 1.5rem;
            opacity: 0.8;
        }

        .testimonial-author {
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--title-color);
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            text-align: left;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--light-color);
            opacity: 0.9;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            background: var(--medium-dark-color);
            border: 1px solid var(--primary-color);
            border-radius: 5px;
            box-sizing: border-box;
            font-size: 1rem;
            color: var(--light-color);
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            border-color: var(--accent-color);
            outline: none;
        }

        .submit-button {
            width: 100%;
            padding: 1.2rem;
            border: none;
            background-color: var(--accent-color);
            color: var(--primary-color);
            font-size: 1.2rem;
            font-weight: 700;
            border-radius: 5px;
            box-shadow: 0 4px 0px 0 var(--dark-color);
            transform: translateY(0);
            transition: all 0.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            cursor: pointer;
        }

        .submit-button:hover {
            background-color: var(--title-color);
            transform: translateY(-2px) scale(1.02);
            box-shadow: 0 6px 0px 0 var(--dark-color);
        }

        .submit-button:active {
            transform: translateY(2px) scale(0.98);
            box-shadow: 0 2px 0px 0 var(--dark-color);
        }

        /* --- Sección de FAQ (Acordeón) --- */
        .faq-accordion {
            max-width: 800px;
            margin: 0 auto;
        }

        .faq-item {
            background-color: var(--medium-dark-color);
            margin-bottom: 1rem;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .faq-question {
            padding: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .faq-question:hover {
            background-color: var(--dark-color);
        }

        .faq-icon {
            font-size: 1.5rem;
            font-weight: 700;
            transition: transform 0.3s ease;
        }

        .faq-answer {
            padding: 0 1.5rem;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s ease-out, padding 0.4s ease-out;
        }

        .faq-answer p {
            padding-bottom: 1.5rem;
            margin: 0;
            font-size: 1rem;
            opacity: 0.8;
        }

        .faq-item.active .faq-question {
            color: var(--accent-color);
        }

        .faq-item.active .faq-icon {
            transform: rotate(45deg);
        }

        .faq-item.active .faq-answer {
            max-height: 200px; /* Ajusta según el contenido de la respuesta */
            padding: 1.5rem;
        }

        /* --- Estilos de la Ventana Emergente (Pop-up) --- */
        #popup-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            display: none; /* Se oculta por defecto */
            justify-content: center;
            align-items: center;
            z-index: 2000;
        }

        #popup-container {
            background-color: var(--medium-dark-color);
            padding: 3rem;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            max-width: 450px;
            text-align: center;
            position: relative;
            transform: scale(0.9);
            opacity: 0;
            animation: popup-enter 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
        }

        #popup-close-button {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 2rem;
            line-height: 1;
            background: none;
            border: none;
            color: var(--light-color);
            cursor: pointer;
            opacity: 0.7;
            transition: opacity 0.3s ease;
        }

        #popup-close-button:hover {
            opacity: 1;
        }

        #popup-content h3 {
            font-size: 2rem;
            font-family: 'Playfair Display', serif;
            color: var(--accent-color);
            margin-bottom: 1rem;
        }

        #popup-content p {
            font-size: 1rem;
            margin-bottom: 2rem;
            opacity: 0.8;
        }

        #popup-content input {
            width: 100%;
            padding: 1rem;
            margin-bottom: 1rem;
            border: 1px solid var(--primary-color);
            background-color: var(--dark-color);
            color: var(--light-color);
            border-radius: 5px;
        }

        #popup-content button {
            width: 100%;
            padding: 1rem;
            border: none;
            background-color: var(--accent-color);
            color: var(--primary-color);
            font-weight: 700;
            text-transform: uppercase;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        #popup-content button:hover {
            background-color: var(--title-color);
        }

        @keyframes popup-enter {
            from {
                transform: scale(0.9);
                opacity: 0;
            }
            to {
                transform: scale(1);
                opacity: 1;
            }
        }

        /* --- Footer --- */
        .main-footer {
            background-color: var(--medium-dark-color);
            color: var(--light-color);
            padding: 2rem 0;
            text-align: center;
            opacity: 0.9;
            transition: opacity 0.3s ease;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .social-links a {
            color: var(--light-color);
            margin: 0 0.8rem;
            font-size: 1.5rem;
            transition: color 0.3s ease, transform 0.3s ease-in-out;
            display: inline-block;
        }

        .social-links a:hover {
            color: var(--accent-color);
            transform: scale(1.2);
        }

        /* --- Estilos del Formulario 3D de Tarjeta --- */
        .payment-section .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
        }

        .card-container {
            perspective: 1000px;
            width: 350px;
            height: 220px;
        }

        .credit-card {
            position: relative;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: transform 0.8s;
        }

        .credit-card.flipped {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            padding: 2rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            background: linear-gradient(135deg, var(--primary-color), var(--dark-color));
        }

        .card-back {
            transform: rotateY(180deg);
            background: linear-gradient(135deg, var(--dark-color), var(--primary-color));
        }

        .card-chip {
            width: 50px;
            height: 40px;
            background-color: gold;
            border-radius: 5px;
        }

        .card-logo {
            font-size: 3rem;
            font-weight: 700;
            text-align: right;
            color: #FFD700;
        }

        .card-number {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            letter-spacing: 2px;
            margin-top: 1rem;
            color: var(--light-color);
        }

        .card-holder, .card-expiry {
            font-size: 0.9rem;
            text-transform: uppercase;
            opacity: 0.8;
        }

        .card-back .black-strip {
            width: 100%;
            height: 40px;
            background-color: black;
            margin-top: 2rem;
        }

        .card-back .cvv-strip {
            background-color: var(--light-color);
            color: var(--dark-color);
            padding: 0.5rem;
            text-align: right;
            margin-top: 0.5rem;
            border-radius: 3px;
        }

        .card-back .cvv-text {
            font-size: 0.8rem;
            margin-top: 0.5rem;
            text-align: right;
        }

        .payment-form {
            width: 100%;
            max-width: 400px;
            text-align: left;
        }

        /* --- Estilos de la sección Portafolio --- */
        .portfolio-section h2 {
            margin-bottom: 2rem;
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            padding-top: 2rem;
        }

        .portfolio-item {
            background-color: var(--dark-color);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .portfolio-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.5);
        }

        .portfolio-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: transform 0.4s ease;
        }

        .portfolio-item:hover img {
            transform: scale(1.05);
        }

        .portfolio-info {
            padding: 1.5rem;
        }

        .portfolio-info h3 {
            font-size: 1.5rem;
            margin-top: 0;
            color: var(--accent-color);
        }

        .portfolio-info p {
            font-size: 0.9rem;
            color: var(--light-color);
            opacity: 0.8;
        }

        /* --- Responsive Design --- */
        @media (max-width: 768px) {
            .header-content,
            .footer-content {
                flex-direction: column;
                gap: 1.5rem;
                text-align: center;
            }

            .main-nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.1rem;
            }

            .testimonial-card,
            .contact-form {
                transform: translateX(0);
            }
        }
    </style>
</head>

<body>

    <header class="main-header">
        <div class="container header-content">
            <div class="logo">
                <a href="#">JORGE XICOTENCATL</a>
            </div>
            <nav class="main-nav">
                <ul>
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#servicios">Servicios</a></li>
                    <li><a href="#portafolio">Portafolio</a></li>
                    <li><a href="#testimonios">Testimonios</a></li>
                    <li><a href="#contacto">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="inicio" class="hero-section active">
            <div id="particles-js"></div>
            <div class="container hero-content">
                <h1>Convierte tus Redes Sociales en una Máquina de Ventas</h1>
                <p>Diseñamos estrategias de contenido, publicidad y crecimiento que realmente funcionan.</p>
                <a href="#contacto" class="cta-button">¡Empezar Ahora!</a>
            </div>
        </section>

        <section id="servicios" class="services-section section-medium-dark">
            <div class="container">
                <h2>Nuestros Servicios de Éxito en Redes Sociales</h2>
                <div class="service-grid">
                    <div class="service-card">
                        <div id="lottie-animation-1" style="width: 120px; height: 120px; margin: 0 auto 1.5rem;"></div>
                        <h3>Creación de Contenido Viral</h3>
                        <p>Desarrollamos contenido que no solo atrae, sino que genera engagement y se comparte de forma masiva.</p>
                    </div>
                    <div class="service-card">
                        <img src="https://via.placeholder.com/120" alt="Automatización AI">
                        <h3>Gestión de Publicidad Efectiva</h3>
                        <p>Segmentamos a tu audiencia ideal para maximizar el retorno de inversión de tus campañas publicitarias.</p>
                    </div>
                    <div class="service-card">
                        <img src="https://via.placeholder.com/120" alt="Generación de Contenido AI">
                        <h3>Análisis de Audiencia Detallado</h3>
                        <p>Utilizamos IA para entender a tus seguidores, sus gustos y hábitos, optimizando cada una de tus
                            acciones.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="stats-section section-dark">
            <div class="container">
                <h2>Nuestros Números Hablan por Sí Mismos</h2>
                <div class="stats-grid">
                    <div class="stat-item">
                        <h3 class="stat-number" data-target="39756">0</h3>
                        <p> SUSCRITOS</p>
                    </div>
                    <div class="stat-item">
                        <h3 class="stat-number" data-target="13543">0</h3>
                        <p>CLIENTES REGISTRADOS</p>
                    </div>
                    <div class="stat-item">
                        <h3 class="stat-number" data-target="7389">0</h3>
                        <p>VISITAS WEB </p>
                    </div>
                </div>
            </div>
        </section>

        <section id="portafolio" class="portfolio-section section-medium-dark">
            <div class="container">
                <h2>Portafolio de Proyectos</h2>
                <div class="portfolio-grid">
                    <div class="portfolio-item">
                        <img src="https://via.placeholder.com/600x400" alt="Campaña de Instagram">
                        <div class="portfolio-info">
                            <h3>Campaña de Instagram para Marca de Ropa</h3>
                            <p>Estrategia de contenido visual, influencers y publicidad que generó un aumento del 150% en las ventas en 3 meses.</p>
                        </div>
                    </div>
                    <div class="portfolio-item">
                        <img src="https://via.placeholder.com/600x400" alt="Estrategia de TikTok">
                        <div class="portfolio-info">
                            <h3>Estrategia de TikTok para Startup Tecnológica</h3>
                            <p>Creación de contenido viral que llevó la cuenta de 0 a 100,000 seguidores en un mes, superando a la competencia.</p>
                        </div>
                    </div>
                    <div class="portfolio-item">
                        <img src="https://via.placeholder.com/600x400" alt="Optimización de Anuncios">
                        <div class="portfolio-info">
                            <h3>Optimización de Anuncios en Facebook Ads</h3>
                            <p>Auditoría y optimización de campañas que redujo el costo por adquisición en un 40%.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>


        <section id="testimonios" class="testimonials-section section-medium-dark">
            <div class="container">
                <h2>Lo que dicen nuestros clientes</h2>
                <div class="testimonial-card">
                    <p class="testimonial-text">"Gracias a su estrategia, triplicamos nuestras interacciones y vimos un aumento
                        del 200% en ventas desde Instagram. ¡Un cambio total!"</p>
                    <p class="testimonial-author">— Ana Gómez, Emprendedora Digital</p>
                </div>
            </div>
        </section>

        <section id="pago" class="payment-section section-dark">
            <div class="container">
                <h2>Completa tu Pago con Tarjeta</h2>
                <div class="card-container">
                    <div class="credit-card" id="credit-card">
                        <div class="card-front">
                            <div class="card-chip"></div>
                            <div class="card-logo">VISA</div>
                            <div class="card-number">#### #### #### ####</div>
                            <div class="card-details">
                                <div class="card-holder">NOMBRE COMPLETO</div>
                                <div class="card-expiry">MM/AA</div>
                            </div>
                        </div>
                        <div class="card-back">
                            <div class="black-strip"></div>
                            <div class="cvv-strip">###</div>
                            <div class="cvv-text">CVV</div>
                        </div>
                    </div>
                </div>

                <form action="#" method="post" class="payment-form">
                    <div class="form-group">
                        <label for="card-number">Número de Tarjeta</label>
                        <input type="text" id="card-number" required>
                    </div>
                    <div class="form-group">
                        <label for="card-holder">Nombre Completo</label>
                        <input type="text" id="card-holder" required>
                    </div>
                    <div class="form-group" style="display: flex; gap: 1.5rem;">
                        <div style="flex-grow: 1;">
                            <label for="card-expiry">Vencimiento (MM/AA)</label>
                            <input type="text" id="card-expiry" required>
                        </div>
                        <div style="flex-grow: 1;">
                            <label for="card-cvv">CVV</label>
                            <input type="text" id="card-cvv" required>
                        </div>
                    </div>
                    <button type="submit" class="cta-button" style="width: 100%; margin-top: 1rem;">Pagar Ahora</button>
                </form>
            </div>
        </section>

        <section id="faq" class="faq-section section-medium-dark">
            <div class="container">
                <h2>Preguntas Frecuentes</h2>
                <div class="faq-accordion">
                    <div class="faq-item">
                        <div class="faq-question">
                            <h3>¿Cuánto tiempo tarda en verse resultados?</h3>
                            <span class="faq-icon">+</span>
                        </div>
                        <div class="faq-answer">
                            <p>Los resultados iniciales en términos de crecimiento de audiencia e interacciones suelen ser visibles en las primeras 4 a 6 semanas. Un aumento significativo en ventas se consolida a partir del tercer mes, una vez que la estrategia está optimizada.</p>
                        </div>
                    </div>
                    <div class="faq-item">
                        <div class="faq-question">
                            <h3>¿Manejan todas las plataformas de redes sociales?</h3>
                            <span class="faq-icon">+</span>
                        </div>
                        <div class="faq-answer">
                            <p>Nos especializamos en las plataformas más relevantes para el crecimiento de tu marca, incluyendo Instagram, Facebook, TikTok y LinkedIn. Realizamos un análisis para determinar cuáles son las más adecuadas para tu negocio.</p>
                        </div>
                    </div>
                    <div class="faq-item">
                        <div class="faq-question">
                            <h3>¿Puedo ver ejemplos de campañas que han realizado?</h3>
                            <span class="faq-icon">+</span>
                        </div>
                        <div class="faq-answer">
                            <p>¡Claro! Contamos con un portafolio de casos de éxito que podemos compartir en nuestra primera consulta. Verás cómo hemos transformado la presencia de otras marcas en el mundo digital.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contacto" class="contact-section section-dark">
            <div class="container">
                <h2>¿Listo para Domar tus Redes Sociales?</h2>
                <p>Déjanos tus datos y un especialista te contactará para llevar tu marca al siguiente nivel en el mundo
                    digital.</p>
                <form action="https://formsubmit.co/TU_CORREO@EJEMPLO.COM" method="POST" class="contact-form">
                    <input type="hidden" name="_captcha" value="false">
                    <input type="hidden" name="_next" value="https://TU-SITIO.COM/gracias.html">
                    <div class="form-group">
                        <label for="name">Nombre:</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email:</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Mensaje:</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="submit-button">Enviar Mensaje</button>
                </form>
            </div>
        </section>
    </main>

    <footer class="main-footer">
        <div class="container footer-content">
            <p>&copy; 2025 World IA XICOTENCATL. Todos los derechos reservados.</p>
            <div class="social-links">
                <a href="#">FB</a>
                <a href="#">TW</a>
                <a href="#">IN</a>
            </div>
        </div>
    </footer>

    <div id="popup-overlay">
        <div id="popup-container">
            <button id="popup-close-button">&times;</button>
            <div id="popup-content">
                <h3>¡No te pierdas de nada!</h3>
                <p>Nuestra IA te suscribe para recibir las últimas estrategias y descuentos exclusivos.</p>
                <form action="#">
                    <input type="email" placeholder="Introduce tu email" required>
                    <button type="submit">Suscribirme</button>
                </form>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/lottie-web/5.10.2/lottie.min.js" defer></script>
    <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js" defer></script>
    <script defer>
        // JS para el encabezado dinámico
        window.addEventListener('scroll', () => {
            const header = document.querySelector('.main-header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // JS para la sección de FAQ (Acordeón)
        document.querySelectorAll('.faq-question').forEach(item => {
            item.addEventListener('click', () => {
                const parent = item.parentElement;
                parent.classList.toggle('active');
                const answer = parent.querySelector('.faq-answer');
                if (parent.classList.contains('active')) {
                    answer.style.maxHeight = answer.scrollHeight + 'px';
                } else {
                    answer.style.maxHeight = '0';
                }
            });
        });

        // JS para los contadores de métricas animados
        const statNumbers = document.querySelectorAll('.stat-number');
        const animateNumbers = (entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const numbers = entry.target.querySelectorAll('.stat-number');
                    numbers.forEach(number => {
                        const target = parseInt(number.getAttribute('data-target'));
                        let current = 0;
                        const increment = Math.ceil(target / 100);
                        const timer = setInterval(() => {
                            current += increment;
                            if (current >= target) {
                                current = target;
                                clearInterval(timer);
                            }
                            number.textContent = current.toLocaleString();
                        }, 10);
                    });
                    observer.unobserve(entry.target);
                }
            });
        };

        const options = {
            threshold: 0.5
        };

        const observer = new IntersectionObserver(animateNumbers, options);
        document.querySelectorAll('.stats-section').forEach(section => {
            observer.observe(section);
        });

        // JS para animar las secciones al hacer scroll
        const sections = document.querySelectorAll('section');
        function checkVisibility() {
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.offsetHeight;
                const windowHeight = window.innerHeight;
                const scrollPosition = window.scrollY;

                if (scrollPosition + windowHeight > sectionTop + sectionHeight / 3 && scrollPosition < sectionTop + sectionHeight) {
                    section.classList.add('active');
                } else {
                    section.classList.remove('active');
                }
            });
        }
        window.addEventListener('scroll', checkVisibility);
        checkVisibility();

        // JS para la ventana emergente
        const popupOverlay = document.getElementById('popup-overlay');
        const popupCloseButton = document.getElementById('popup-close-button');

        // Muestra la ventana emergente después de 3 segundos
        setTimeout(() => {
            popupOverlay.style.display = 'flex';
        }, 3000);

        // Cierra la ventana cuando se hace clic en el botón
        popupCloseButton.addEventListener('click', () => {
            popupOverlay.style.display = 'none';
        });

        // Cierra la ventana si se hace clic fuera de ella
        popupOverlay.addEventListener('click', (event) => {
            if (event.target === popupOverlay) {
                popupOverlay.style.display = 'none';
            }
        });

        // JS para cargar y reproducir la animación Lottie
        lottie.loadAnimation({
            container: document.getElementById('lottie-animation-1'), // El ID del contenedor
            renderer: 'svg',
            loop: true,
            autoplay: true,
            path: 'https://assets5.lottiefiles.com/packages/lf20_tuf40kfm.json' // URL de la animación
        });

        // JS para el efecto 3D de la tarjeta
        const card = document.getElementById('credit-card');
        const cvvInput = document.getElementById('card-cvv');

        cvvInput.addEventListener('focus', () => {
            card.classList.add('flipped');
        });

        cvvInput.addEventListener('blur', () => {
            card.classList.remove('flipped');
        });

        // Llenar la información de la tarjeta
        const cardNumberInput = document.getElementById('card-number');
        const cardHolderInput = document.getElementById('card-holder');
        const cardExpiryInput = document.getElementById('card-expiry');
        const cardCvvInput = document.getElementById('card-cvv');

        cardNumberInput.addEventListener('input', (e) => {
            card.querySelector('.card-number').textContent = e.target.value.replace(/\s?/g, '').replace(/(\d{4})/g, '$1 ').trim();
        });

        cardHolderInput.addEventListener('input', (e) => {
            card.querySelector('.card-holder').textContent = e.target.value.toUpperCase();
        });

        cardExpiryInput.addEventListener('input', (e) => {
            card.querySelector('.card-expiry').textContent = e.target.value;
        });

        cardCvvInput.addEventListener('input', (e) => {
            card.querySelector('.cvv-strip').textContent = e.target.value;
        });

        // JS para inicializar Particles.js
        particlesJS('particles-js', {
            "particles": {
                "number": {
                    "value": 80,
                    "density": {
                        "enable": true,
                        "value_area": 800
                    }
                },
                "color": {
                    "value": ["#FFD700", "#40E0D0", "#F5F5DC"]
                },
                "shape": {
                    "type": "circle",
                    "stroke": {
                        "width": 0,
                        "color": "#000000"
                    },
                    "polygon": {
                        "nb_sides": 5
                    }
                },
                "opacity": {
                    "value": 0.5,
                    "random": false,
                    "anim": {
                        "enable": false,
                        "speed": 1,
                        "opacity_min": 0.1,
                        "sync": false
                    }
                },
                "size": {
                    "value": 3,
                    "random": true,
                    "anim": {
                        "enable": false,
                        "speed": 40,
                        "size_min": 0.1,
                        "sync": false
                    }
                },
                "line_linked": {
                    "enable": true,
                    "distance": 150,
                    "color": "#ffffff",
                    "opacity": 0.4,
                    "width": 1
                },
                "move": {
                    "enable": true,
                    "speed": 3,
                    "direction": "none",
                    "random": false,
                    "straight": false,
                    "out_mode": "out",
                    "bounce": false,
                    "attract": {
                        "enable": false,
                        "rotateX": 600,
                        "rotateY": 1200
                    }
                }
            },
            "interactivity": {
                "detect_on": "canvas",
                "events": {
                    "onhover": {
                        "enable": true,
                        "mode": "grab"
                    },
                    "onclick": {
                        "enable": true,
                        "mode": "push"
                    },
                    "resize": true
                },
                "modes": {
                    "grab": {
                        "distance": 140,
                        "line_linked": {
                            "opacity": 1
                        }
                    },
                    "bubble": {
                        "distance": 400,
                        "size": 40,
                        "duration": 2,
                        "opacity": 8,
                        "speed": 3
                    },
                    "repulse": {
                        "distance": 200,
                        "duration": 0.4
                    },
                    "push": {
                        "particles_nb": 4
                    },
                    "remove": {
                        "particles_nb": 2
                    }
                }
            },
            "retina_detect": true
        });
    </script>

</body>

</html>
