<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seu Nome - Desenvolvedor React</title>
    <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg" type="image/svg+xml">

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Montserrat:wght@700&display=swap" rel="stylesheet">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        /* CSS será inserido aqui */
        body {
            font-family: 'Inter', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #0d1117; /* Fundo escuro do GitHub */
            color: #c9d1d9; /* Cor de texto padrão do GitHub */
            line-height: 1.6;
            overflow-x: hidden; /* Evita scroll horizontal */
        }

        .container {
            max-width: 960px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* --- Seção Hero / Avatar --- */
        .hero-section {
            text-align: center;
            padding: 4rem 0 2rem;
            position: relative;
            background: linear-gradient(135deg, #161b22, #0d1117); /* Gradiente sutil */
            animation: fadeIn 2s ease-out;
        }

        .avatar-wrapper {
            position: relative;
            display: inline-block;
            margin-bottom: 1.5rem;
        }

        .avatar-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #58a6ff; /* Borda azul clara */
            box-shadow: 0 0 15px rgba(88, 166, 255, 0.6); /* Sombra luminosa */
            transition: all 0.3s ease-in-out;
            animation: pulseBorder 2s infinite alternate; /* Animação de pulsar */
        }

        .avatar-img:hover {
            transform: scale(1.05) rotate(5deg);
            box-shadow: 0 0 25px rgba(88, 166, 255, 0.9);
        }

        .status-badge {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background-color: #2ea44f; /* Verde de "online" */
            color: white;
            padding: 0.3rem 0.6rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            animation: bounceIn 1s ease-out forwards;
            animation-delay: 1.5s;
            opacity: 0;
        }

        .hero-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 2.8rem;
            color: #58a6ff;
            margin-bottom: 0.5rem;
            letter-spacing: -1px;
            text-shadow: 0 0 10px rgba(88, 166, 255, 0.4);
            animation: slideInFromTop 1s ease-out;
            animation-delay: 0.5s;
        }

        .hero-subtitle {
            font-size: 1.4rem;
            color: #8b949e;
            margin-bottom: 1.5rem;
            animation: slideInFromBottom 1s ease-out;
            animation-delay: 0.7s;
        }

        .call-to-action a {
            display: inline-block;
            background-color: #2ea44f;
            color: white;
            padding: 0.8rem 1.8rem;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: background-color 0.3s ease, transform 0.3s ease;
            box-shadow: 0 5px 15px rgba(46, 164, 79, 0.3);
            animation: bounceIn 1s ease-out forwards;
            animation-delay: 2s;
            opacity: 0;
        }

        .call-to-action a:hover {
            background-color: #2c974b;
            transform: translateY(-3px) scale(1.02);
        }

        /* --- Seção de Habilidades --- */
        .skills-section {
            padding: 3rem 0;
            background-color: #161b22;
            text-align: center;
        }

        .skills-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 2.2rem;
            color: #58a6ff;
            margin-bottom: 2rem;
        }

        .skill-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .skill-item {
            background-color: #0d1117;
            padding: 1.5rem 1rem;
            border-radius: 8px;
            border: 1px solid #30363d;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeInFromBottom 0.8s ease-out forwards;
        }

        .skill-item:nth-child(1) { animation-delay: 0.2s; }
        .skill-item:nth-child(2) { animation-delay: 0.4s; }
        .skill-item:nth-child(3) { animation-delay: 0.6s; }
        .skill-item:nth-child(4) { animation-delay: 0.8s; }
        .skill-item:nth-child(5) { animation-delay: 1.0s; }
        .skill-item:nth-child(6) { animation-delay: 1.2s; }
        /* Adicione mais nth-child se tiver mais skills */

        .skill-item:hover {
            transform: translateY(-5px) scale(1.03);
            border-color: #58a6ff;
            box-shadow: 0 6px 15px rgba(88, 166, 255, 0.3);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 0.8rem;
            color: #58a6ff; /* Cor padrão para ícones */
        }

        /* Ícones específicos para dar um toque a mais */
        .skill-icon.react-icon { color: #61DAFB; text-shadow: 0 0 10px rgba(97, 218, 251, 0.5); }
        .skill-icon.js-icon { color: #F7DF1E; }
        .skill-icon.ts-icon { color: #3178C6; }
        .skill-icon.html-icon { color: #E34F26; }
        .skill-icon.css-icon { color: #1572B6; }
        .skill-icon.node-icon { color: #339933; }
        .skill-icon.git-icon { color: #F05032; }

        .skill-name {
            font-weight: 600;
            font-size: 1.1rem;
            color: #c9d1d9;
        }

        /* --- Seção de Projetos (Exemplo) --- */
        .projects-section {
            padding: 4rem 0;
            background-color: #0d1117;
            text-align: center;
        }

        .projects-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 2.2rem;
            color: #58a6ff;
            margin-bottom: 2rem;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background-color: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            overflow: hidden;
            text-align: left;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeInFromBottom 0.8s ease-out forwards;
            animation-delay: 1.5s; /* Atraso inicial para a seção */
        }

        .project-card:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 8px 20px rgba(88, 166, 255, 0.3);
        }

        .project-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-bottom: 1px solid #30363d;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-title {
            font-size: 1.5rem;
            color: #58a6ff;
            margin-bottom: 0.5rem;
        }

        .project-description {
            font-size: 0.95rem;
            color: #8b949e;
            margin-bottom: 1rem;
        }

        .project-links a {
            color: #58a6ff;
            text-decoration: none;
            margin-right: 1rem;
            transition: color 0.3s ease;
        }

        .project-links a:hover {
            color: #8b949e;
            text-decoration: underline;
        }

        /* --- Footer --- */
        .footer {
            text-align: center;
            padding: 2rem;
            background-color: #161b22;
            border-top: 1px solid #30363d;
            font-size: 0.9rem;
            color: #8b949e;
        }

        .footer-socials a {
            color: #c9d1d9;
            font-size: 1.5rem;
            margin: 0 0.8rem;
            transition: color 0.3s ease, transform 0.3s ease;
        }

        .footer-socials a:hover {
            color: #58a6ff;
            transform: translateY(-3px);
        }

        /* --- Animações --- */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes pulseBorder {
            0% { border-color: #58a6ff; box-shadow: 0 0 10px rgba(88, 166, 255, 0.4); }
            100% { border-color: #8b949e; box-shadow: 0 0 20px rgba(88, 166, 255, 0.8); }
        }

        @keyframes slideInFromTop {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes slideInFromBottom {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes bounceIn {
            0% { transform: scale(0.5); opacity: 0; }
            60% { transform: scale(1.2); opacity: 1; }
            100% { transform: scale(1); opacity: 1; }
        }

        @keyframes fadeInFromBottom {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        /* --- Responsividade Básica --- */
        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.2rem;
            }
            .hero-subtitle {
                font-size: 1.2rem;
            }
            .skills-title, .projects-title {
                font-size: 1.8rem;
            }
            .container {
                padding: 1rem;
            }
            .skill-grid, .project-grid {
                grid-template-columns: 1fr;
            }
            .project-card img {
                height: 150px;
            }
        }
    </style>
</head>
<body>

    <header class="hero-section">
        <div class="container">
            <div class="avatar-wrapper">
                <img src="https://avatars.githubusercontent.com/u/SEU_ID_GITHUB?v=4" alt="Seu Avatar" class="avatar-img">
                <span class="status-badge">Disponível para projetos</span>
            </div>
            <h1 class="hero-title">Olá, eu sou [Seu Nome Completo]</h1>
            <p class="hero-subtitle">Desenvolvedor Front-end com foco em <span style="color: #61DAFB; font-weight: bold;">React.js</span></p>
            <div class="call-to-action">
                <a href="https://github.com/SEU_USUARIO_GITHUB" target="_blank">
                    <i class="fab fa-github"></i> Ver meu GitHub
                </a>
            </div>
        </div>
    </header>

    <section class="skills-section">
        <div class="container">
            <h2 class="skills-title">Minhas Habilidades</h2>
            <div class="skill-grid">
                <div class="skill-item">
                    <i class="fab fa-react skill-icon react-icon"></i>
                    <p class="skill-name">React.js</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-js skill-icon js-icon"></i>
                    <p class="skill-name">JavaScript (ES6+)</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-node-js skill-icon node-icon"></i>
                    <p class="skill-name">Node.js (Básico)</p>
                </div>
                 <div class="skill-item">
                    <i class="fab fa-html5 skill-icon html-icon"></i>
                    <p class="skill-name">HTML5</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-css3-alt skill-icon css-icon"></i>
                    <p class="skill-name">CSS3 / Styled-Components</p>
                </div>
                <div class="skill-item">
                    <i class="fab fa-git-alt skill-icon git-icon"></i>
                    <p class="skill-name">Git & GitHub</p>
                </div>
                </div>
        </div>
    </section>

    <section class="projects-section">
        <div class="container">
            <h2 class="projects-title">Meus Projetos Recentes</h2>
            <div class="project-grid">
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x180/1e2329/c9d1d9?text=Projeto+React+1" alt="Projeto 1">
                    <div class="project-content">
                        <h3 class="project-title">E-commerce de Roupas</h3>
                        <p class="project-description">
                            Desenvolvimento de um e-commerce moderno com React, utilizando Context API e integrações com Stripe para pagamentos.
                        </p>
                        <div class="project-links">
                            <a href="https://github.com/SEU_USUARIO_GITHUB/nome-do-projeto-1" target="_blank"><i class="fab fa-github"></i> Código</a>
                            <a href="#" target="_blank"><i class="fas fa-external-link-alt"></i> Demo</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <img src="https://via.placeholder.com/400x180/1e2329/c9d1d9?text=Projeto+React+2" alt="Projeto 2">
                    <div class="project-content">
                        <h3 class="project-title">Dashboard de Análise</h3>
                        <p class="project-description">
                            Dashboard interativo para visualização de dados, construído com React e bibliotecas de gráficos como Chart.js.
                        </p>
                        <div class="project-links">
                            <a href="https://github.com/SEU_USUARIO_GITHUB/nome-do-projeto-2" target="_blank"><i class="fab fa-github"></i> Código</a>
                            <a href="#" target="_blank"><i class="fas fa-external-link-alt"></i> Demo</a>
                        </div>
                    </div>
                </div>

                </div>
        </div>
    </section>

    <footer class="footer">
        <div class="container">
            <div class="footer-socials">
                <a href="https://linkedin.com/in/SEU_LINKEDIN" target="_blank" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
                <a href="https://twitter.com/SEU_TWITTER" target="_blank" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
                <a href="mailto:SEU_EMAIL@example.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
            </div>
            <p>&copy; 2023 Seu Nome. Todos os direitos reservados.</p>
        </div>
    </footer>

</body>
</html>
