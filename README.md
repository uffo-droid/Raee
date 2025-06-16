<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Red de Apoyo Emocional Eunoia - RAEE</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #2c3e50;
            background: linear-gradient(135deg, #f0f8ff 0%, #e6f3f7 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header y navegación */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
            font-size: 1.8rem;
            font-weight: bold;
            color: #6db4c4;
            text-decoration: none;
        }

        .logo-img {
            width: 50px;
            height: 50px;
            background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 400"><defs><linearGradient id="purpleGrad" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" style="stop-color:%23a855f7;stop-opacity:1" /><stop offset="100%" style="stop-color:%236b46c1;stop-opacity:1" /></linearGradient><linearGradient id="tealGrad" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" style="stop-color:%2314b8a6;stop-opacity:1" /><stop offset="100%" style="stop-color:%236db4c4;stop-opacity:1" /></linearGradient></defs><circle cx="200" cy="150" r="25" fill="url(%23purpleGrad)"/><circle cx="200" cy="200" r="40" fill="url(%23purpleGrad)"/><path d="M 160 120 Q 170 80 200 90 Q 230 100 240 140 Q 250 180 220 220 Q 190 260 160 220 Q 130 180 140 140 Q 150 100 160 120" fill="url(%23tealGrad)" opacity="0.8"/><text x="80" y="320" font-family="Arial, sans-serif" font-size="80" font-weight="bold" fill="%236b7280">R</text><text x="280" y="320" font-family="Arial, sans-serif" font-size="80" font-weight="bold" fill="%236b7280">EE</text><text x="350" y="320" font-family="Arial, sans-serif" font-size="80" font-weight="bold" fill="%23ea580c">E</text></svg>');
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #34495e;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #6db4c4;
        }

        /* Hero Section */
        .hero {
            margin-top: 80px;
            padding: 4rem 0;
            text-align: center;
            background: linear-gradient(135deg, #6db4c4 0%, #a855f7 50%, #6b46c1 100%);
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 320"><path fill="rgba(255,255,255,0.1)" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,149.3C960,160,1056,160,1152,138.7C1248,117,1344,75,1392,53.3L1440,32L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>') no-repeat bottom;
            background-size: cover;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .hero-subtitle {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(135deg, #ea580c, #f97316);
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(234, 88, 12, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(234, 88, 12, 0.4);
        }

        /* Sections */
        .section {
            padding: 4rem 0;
            margin: 2rem 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, #6db4c4, #a855f7);
            border-radius: 2px;
        }

        .card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            margin-bottom: 2rem;
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .principles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .principle-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .principle-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .principle-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .objectives-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .objective-item {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            border-left: 4px solid #6db4c4;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .objective-item:hover {
            border-left-color: #ea580c;
            transform: translateX(5px);
        }

        .objective-item h3 {
            color: #a855f7;
            margin-bottom: 0.5rem;
        }

        /* Contact Section */
        .contact-section {
            background: linear-gradient(135deg, #6db4c4 0%, #14b8a6 100%);
            color: white;
            text-align: center;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .form-group {
            margin-bottom: 1.5rem;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #2c3e50;
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #6db4c4;
        }

        .submit-btn {
            background: linear-gradient(135deg, #ea580c, #f97316);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            background: linear-gradient(135deg, #dc2626, #ea580c);
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero-subtitle {
                font-size: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .principles-grid {
                grid-template-columns: 1fr;
            }

            .objectives-list {
                grid-template-columns: 1fr;
            }
        }

        /* Animaciones */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate-on-scroll {
            animation: fadeInUp 0.8s ease-out;
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav class="container">
            <a href="#inicio" class="logo">RAEE</a>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#quienes-somos">Quiénes Somos</a></li>
                <li><a href="#nuestra-esencia">Nuestra Esencia</a></li>
                <li><a href="#objetivos">Objetivos</a></li>
                <li><a href="#unirse">Únete</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="inicio" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Red de Apoyo Emocional Eunoia</h1>
                <p class="hero-subtitle">Creando espacios seguros para el bienestar emocional y la salud mental en la comunidad universitaria</p>
                <a href="#quienes-somos" class="cta-button">Conoce Más</a>
            </div>
        </div>
    </section>

    <!-- Quiénes Somos -->
    <section id="quienes-somos" class="section">
        <div class="container">
            <h2 class="section-title">Quiénes Somos</h2>
            <div class="card">
                <p style="font-size: 1.1rem; text-align: center; margin-bottom: 2rem;">
                    Somos un <strong>grupo organizado estudiantil sin ánimo de lucro</strong>, de carácter permanente, adscrito al Departamento de Orientación de la Dirección de Desarrollo Estudiantil de la Universidad Centroccidental Lisandro Alvarado (UCLA).
                </p>
                <p style="font-size: 1.1rem; text-align: center; margin-bottom: 2rem;">
                    Nos dedicamos a la <strong>prevención y promoción del bienestar emocional y la salud mental</strong>, actuando como Promotores de la Salud Mental bajo el marco de la Ley de Salud Mental Comunitaria del Estado Lara.
                </p>
                <p style="font-size: 1.1rem; text-align: center; margin-bottom: 2rem;">
                    Buscamos crear un <strong>espacio seguro y de apoyo</strong> para la comunidad universitaria, nacidos de la necesidad de apoyar al estudiantado frente a los desafíos de la salud mental.
                </p>
            </div>
        </div>
    </section>

    <!-- Nuestra Esencia -->
    <section id="nuestra-esencia" class="section" style="background: rgba(255, 255, 255, 0.8);">
        <div class="container">
            <h2 class="section-title">Nuestra Esencia</h2>
            
            <!-- Principios Fundamentales -->
            <h3 style="text-align: center; font-size: 2rem; margin-bottom: 2rem; color: #a855f7;">Principios Fundamentales</h3>
            <div class="principles-grid">
                <div class="principle-card">
                    <div class="principle-icon">🤝</div>
                    <h4>Confianza y Respeto</h4>
                    <p>Valoramos a cada miembro sin juicios, escuchando y respetando a todos.</p>
                </div>
                <div class="principle-card">
                    <div class="principle-icon">💙</div>
                    <h4>Empatía</h4>
                    <p>Prestamos atención activa, sin interrupciones ni juicios.</p>
                </div>
                <div class="principle-card">
                    <div class="principle-icon">🌟</div>
                    <h4>Apoyo Mutuo</h4>
                    <p>Ofrecemos consuelo, aliento y orientación en momentos difíciles.</p>
                </div>
                <div class="principle-card">
                    <div class="principle-icon">🤲</div>
                    <h4>Colaboración</h4>
                    <p>Trabajamos juntos para alcanzar objetivos comunes.</p>
                </div>
                <div class="principle-card">
                    <div class="principle-icon">💬</div>
                    <h4>Comunicación Abierta</h4>
                    <p>Creamos ambientes donde todos se sienten cómodos expresándose.</p>
                </div>
                <div class="principle-card">
                    <div class="principle-icon">🔒</div>
                    <h4>Confidencialidad</h4>
                    <p>Mantenemos la información compartida de manera confidencial.</p>
                </div>
            </div>

            <!-- Visión -->
            <div class="card" style="margin-top: 3rem; background: linear-gradient(135deg, #a855f7 0%, #6b46c1 100%); color: white;">
                <h3 style="text-align: center; font-size: 2rem; margin-bottom: 1rem;">Nuestra Visión</h3>
                <p style="text-align: center; font-size: 1.1rem;">
                    Visualizamos una comunidad donde cada individuo florezca y alcance su máximo potencial emocional. 
                    A través del apoyo incondicional y herramientas personalizadas, transformaremos vidas, fortaleciendo 
                    la resiliencia y promoviendo el bienestar integral. Seremos el faro de esperanza y crecimiento para 
                    quienes buscan un espacio seguro para sanar y evolucionar.
                </p>
            </div>

            <!-- Misión -->
            <div class="card" style="background: linear-gradient(135deg, #6db4c4 0%, #14b8a6 100%); color: white;">
                <h3 style="text-align: center; font-size: 2rem; margin-bottom: 1rem;">Nuestra Misión</h3>
                <p style="text-align: center; font-size: 1.1rem;">
                    Construir una comunidad inclusiva y solidaria donde cada persona se sienta valorada, comprendida y 
                    empoderada para enfrentar los desafíos de la vida. A través de espacios seguros para compartir experiencias, 
                    ofrecemos apoyo emocional, herramientas prácticas y recursos que promueven el crecimiento personal y el bienestar.
                </p>
            </div>
        </div>
    </section>

    <!-- Objetivos -->
    <section id="objetivos" class="section">
        <div class="container">
            <h2 class="section-title">Nuestros Objetivos</h2>
            <div class="objectives-list">
                <div class="objective-item">
                    <h3>Formación de Promotores</h3>
                    <p>Formamos promotores de salud mental entre los estudiantes de la UCLA a través de actividades que promuevan el bienestar psicológico.</p>
                </div>
                <div class="objective-item">
                    <h3>Visibilizar Servicios</h3>
                    <p>Damos a conocer los servicios de orientación que brindan acompañamiento individualizado.</p>
                </div>
                <div class="objective-item">
                    <h3>Sensibilización</h3>
                    <p>Sensibilizamos a la comunidad universitaria sobre la salud mental, abordando estigmas para fomentar la inclusión.</p>
                </div>
                <div class="objective-item">
                    <h3>Colaboraciones</h3>
                    <p>Establecemos colaboraciones con otros grupos e instituciones en pro de la salud mental.</p>
                </div>
                <div class="objective-item">
                    <h3>Enlace con Especialistas</h3>
                    <p>Servimos como enlace entre el grupo organizado y los especialistas en salud mental del Departamento de Orientación.</p>
                </div>
                <div class="objective-item">
                    <h3>Primeros Auxilios Psicológicos</h3>
                    <p>Capacitamos para brindar primeros auxilios psicológicos en emergencias, orientando a servicios especializados.</p>
                </div>
                <div class="objective-item">
                    <h3>Espacios de Diálogo</h3>
                    <p>Generamos espacios guiados por especialistas para hablar abiertamente sobre problemas de salud mental.</p>
                </div>
                <div class="objective-item">
                    <h3>Actividades Variadas</h3>
                    <p>Planificamos talleres, seminarios, conferencias y actividades recreativas que fomenten la salud emocional.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Únete -->
    <section id="unirse" class="section" style="background: linear-gradient(135deg, #ea580c 0%, #f97316 100%); color: white;">
        <div class="container">
            <h2 class="section-title" style="color: white;">¿Cómo Unirte?</h2>
            <div class="card" style="background: rgba(255, 255, 255, 0.95); color: #2c3e50;">
                <h3 style="text-align: center; margin-bottom: 2rem; color: #a855f7;">Forma Parte de Nuestra Comunidad</h3>
                <p style="text-align: center; font-size: 1.1rem; margin-bottom: 2rem;">
                    Si eres estudiante de la UCLA y quieres ser parte de esta red de apoyo, contribuyendo al bienestar 
                    emocional de nuestra comunidad universitaria, ¡te invitamos a unirte!
                </p>
                <div style="text-align: center;">
                    <p style="font-size: 1.1rem; margin-bottom: 1rem;"><strong>Requisitos:</strong></p>
                    <ul style="text-align: left; max-width: 600px; margin: 0 auto;">
                        <li>Ser estudiante activo de la UCLA</li>
                        <li>Compromiso con los principios de la red</li>
                        <li>Disposición para aprender y compartir</li>
                        <li>Respeto por la confidencialidad</li>
                        <li>Actitud empática y solidaria</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Contacto -->
    <section id="contacto" class="contact-section">
        <div class="container">
            <h2 class="section-title" style="color: white;">Contacto
