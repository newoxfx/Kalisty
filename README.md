<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VANGUARD EVOLUTION - Notícias & Postagens | Admin</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Montserrat:wght@800&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        /* CSS CONSOLIDADO DO SITE E ADMIN */

        /* Variáveis de Cores (Tema Vibrante e Chamativo) */
        :root {
            --primary-bg: #0A1128;   /* Azul Marinho Profundo */
            --secondary-bg: #1B2A41; /* Azul Escuro um Pouco Mais Claro */
            --text-color: #E0E0E0;   /* Cinza Claro (quase branco) */
            --accent-color: #00C9A7; /* Verde Água Vibrante */
            --gold-color: #FFD700;   /* Dourado Suave */
            --light-accent: #00E0BD; /* Verde Água mais claro para hover */
            --error-color: #e74c3c;  /* Vermelho para erros */

            /* Cores do Admin - ajustadas para contraste com tema principal */
            --admin-bg-light: #f4f4f4;
            --admin-bg-dark: #333333; /* Cinza escuro */
            --admin-text-dark: #222222;
            --admin-text-light: #ffffff;
            --admin-border-light: #dddddd;
            --admin-hover-light: #e8e8e8;
            --admin-status-active-bg: #d4edda; /* Verde claro */
            --admin-status-active-text: #155724; /* Verde escuro */
            --admin-status-inactive-bg: #f8d7da; /* Vermelho claro */
            --admin-status-inactive-text: #721c24; /* Vermelho escuro */
        }

        /* Reset Básico */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--primary-bg);
            overflow-x: hidden; /* Evita scroll horizontal */
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Cabeçalho do Site */
        header.site-header {
            background-color: var(--secondary-bg);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        header.site-header .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .logo h1 {
            font-family: 'Montserrat', sans-serif;
            font-size: 2.2em;
            color: var(--text-color);
            letter-spacing: 1px;
        }

        .logo .evolution-text {
            color: var(--accent-color);
        }

        /* Ícone de Hambúrguer */
        .menu-toggle {
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 1.8em;
            cursor: pointer;
            padding: 10px;
            transition: color 0.3s ease;
        }
        .menu-toggle:hover {
            color: var(--gold-color);
        }

        /* Sidebar de Navegação */
        .sidebar {
            height: 100%;
            width: 0; /* Começa fechada */
            position: fixed;
            z-index: 1100; /* Acima do header */
            top: 0;
            right: 0; /* Desliza da direita */
            background-color: var(--secondary-bg);
            overflow-x: hidden;
            transition: 0.5s;
            padding-top: 60px;
            box-shadow: -5px 0 15px rgba(0,0,0,0.3);
            display: flex;
            flex-direction: column;
        }

        .sidebar.open {
            width: 250px; /* Largura aberta */
        }

        .sidebar a {
            padding: 15px 25px;
            text-decoration: none;
            font-size: 1.2em;
            color: var(--text-color);
            display: block;
            transition: 0.3s;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        .sidebar a:hover, .sidebar a.active {
            color: var(--gold-color);
            background-color: var(--primary-bg);
        }

        .sidebar .closebtn {
            position: absolute;
            top: 0;
            right: 25px;
            font-size: 3em;
            margin-left: 50px;
            color: var(--text-color);
        }
        .sidebar .closebtn:hover {
            color: var(--gold-color);
        }

        /* Botões dentro da sidebar */
        .sidebar .sidebar-btn {
            background-color: var(--accent-color); /* Usando a cor de destaque */
            color: var(--primary-bg); /* Texto escuro sobre destaque */
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.1em;
            font-weight: 600;
            margin: 15px 25px; /* Ajustado para espaço */
            transition: background-color 0.3s ease, transform 0.2s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            justify-content: center;
            text-decoration: none; /* Para parecer um link também */
        }
        .sidebar .sidebar-btn.login {
            background-color: var(--gold-color); /* Dourado para Login */
        }
        .sidebar .sidebar-btn.profile-btn { /* Estilo para o botão de perfil logado */
            background-color: var(--accent-color);
            color: var(--primary-bg);
        }
        .sidebar .sidebar-btn:hover {
            background-color: var(--light-accent);
            color: var(--primary-bg); /* Mantém escuro para contraste */
            transform: translateY(-2px);
        }
        .sidebar .sidebar-btn.login:hover {
            background-color: var(--gold-color);
            filter: brightness(0.9); /* Escurece um pouco ao passar o mouse */
        }
        /* Botão Criar Postagem para usuário logado */
        .sidebar .sidebar-btn.create-post-btn {
            background-color: var(--gold-color); /* Dourado para Criar Postagem */
            color: var(--primary-bg);
        }
        .sidebar .sidebar-btn.create-post-btn:hover {
            background-color: var(--gold-color);
            filter: brightness(0.9);
        }


        /* Botões Gerais */
        .btn {
            display: inline-block;
            padding: 12px 25px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.05em;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            display: flex;
            align-items: center;
            gap: 8px;
            justify-content: center;
        }

        .primary-btn {
            background-color: var(--accent-color);
            color: var(--primary-bg); /* Texto escuro */
        }

        .primary-btn:hover {
            background-color: var(--light-accent);
            transform: translateY(-2px);
        }

        .secondary-btn {
            background-color: transparent;
            color: var(--accent-color);
            border: 2px solid var(--accent-color);
        }

        .secondary-btn:hover {
            background-color: var(--accent-color);
            color: var(--primary-bg); /* Texto escuro */
            transform: translateY(-2px);
        }

        /* Seção Hero (Tela Inicial) */
        .hero-section {
            position: relative;
            height: 75vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            /* Usando um fundo que combine com a nova paleta */
            background: url('https://via.placeholder.com/1920x1080/0A1128/FFFFFF?text=Vanguard+Evolution+Site') no-repeat center center/cover;
            background-size: cover;
            background-position: center;
            overflow: hidden;
        }

        .hero-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(10, 17, 40, 0.85) 0%, rgba(27, 42, 65, 0.85) 100%);
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            padding: 20px;
            max-width: 800px;
        }

        .hero-content h2 {
            font-family: 'Montserrat', sans-serif;
            font-size: 4.5em;
            margin-bottom: 20px;
            line-height: 1.1;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.5);
            color: var(--text-color);
        }

        .founder-info {
            margin-top: 30px;
            margin-bottom: 0;
            position: relative;
        }

        .founder-info h3 {
            font-size: 1.4em;
            font-weight: 400;
            color: var(--gold-color);
            margin-bottom: 0;
        }

        .founder-name {
            color: var(--gold-color);
            font-weight: 600;
        }

        .big-v {
            font-family: 'Montserrat', sans-serif;
            font-size: 12em;
            color: var(--gold-color);
            opacity: 0.1;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            line-height: 0.8;
            z-index: -1;
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.3);
        }

        /* Animações Hero Section */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate-fade-in-up {
            animation: fadeInUp 0.8s ease-out forwards;
            opacity: 0;
        }
        .animate-fade-in-up.delay-1 { animation-delay: 0.3s; }
        .animate-fade-in-up.delay-2 { animation-delay: 0.6s; }


        /* Seções Gerais */
        .section-padding {
            padding: 80px 0;
        }

        .bg-darker {
            background-color: var(--secondary-bg);
        }

        .section-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 3em;
            text-align: center;
            margin-bottom: 60px;
            color: var(--accent-color);
            position: relative;
            padding-bottom: 10px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            left: 50%;
            bottom: 0;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--gold-color);
            border-radius: 2px;
        }

        .section-title i {
            color: var(--gold-color);
            margin-left: 15px;
        }

        .text-center {
            text-align: center;
        }

        .mt-4 {
            margin-top: 40px;
        }

        /* Cards de Notícias/Postagens */
        .news-grid, .posts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .news-card, .post-card {
            background-color: var(--secondary-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .news-card:hover, .post-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
        }

        .news-card img, .post-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .news-card:hover img, .post-card:hover img {
            transform: scale(1.05);
        }

        .card-content {
            padding: 25px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .card-content h3, .card-content h4 {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.6em;
            color: var(--accent-color);
            margin-bottom: 15px;
            line-height: 1.3;
        }
        .card-content h4 {
            font-size: 1.4em;
            color: var(--gold-color);
        }

        .card-content p {
            font-size: 0.95em;
            color: var(--text-color);
            margin-bottom: 20px;
        }

        .post-meta {
            font-size: 0.85em;
            color: var(--text-color);
            opacity: 0.7;
            margin-bottom: 10px;
        }

        .read-more {
            color: var(--gold-color);
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 5px;
            margin-top: auto;
            transition: color 0.3s ease;
        }

        .read-more:hover {
            color: var(--light-accent);
        }

        /* Animações de Revelação de Seção */
        .reveal {
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Animações para Cards */
        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }
        .animate-scale-in {
            animation: scaleIn 0.6s ease-out forwards;
            opacity: 0;
        }
        .animate-scale-in.delay-05 { animation-delay: 0.2s; }
        .animate-scale-in.delay-1 { animation-delay: 0.4s; }


        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        .animate-slide-in-left {
            animation: slideInLeft 0.6s ease-out forwards;
            opacity: 0;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        .animate-slide-in-right {
            animation: slideInRight 0.6s ease-out forwards;
            opacity: 0;
        }
        .animate-slide-in-right.delay-05 { animation-delay: 0.2s; }

        /* Sobre Nós */
        .about-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .about-content p {
            max-width: 800px;
            margin-bottom: 20px;
            font-size: 1.1em;
        }

        .about-content .about-image {
            width: 100%;
            max-width: 900px;
            border-radius: 10px;
            margin-top: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .animate-fade-in {
            animation: fadeIn 0.8s ease-out forwards;
            opacity: 0;
        }

        /* Contato */
        .contact-form {
            max-width: 700px;
            margin: 0 auto;
            background-color: var(--primary-bg);
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.4);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--gold-color);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            background-color: var(--secondary-bg);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            color: var(--text-color);
            font-size: 1em;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent-color);
            box-shadow: 0 0 0 3px rgba(0, 201, 167, 0.3);
        }

        .form-group textarea {
            resize: vertical;
        }

        /* Rodapé do Site */
        footer.site-footer {
            background-color: var(--secondary-bg);
            color: var(--text-color);
            padding: 60px 0 30px;
            font-size: 0.95em;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        footer.site-footer .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        footer.site-footer .footer-col h3, footer.site-footer .footer-col h4 {
            font-family: 'Montserrat', sans-serif;
            color: var(--accent-color);
            margin-bottom: 20px;
            font-size: 1.3em;
        }

        footer.site-footer .footer-col ul {
            list-style: none;
        }

        footer.site-footer .footer-col ul li {
            margin-bottom: 10px;
        }

        footer.site-footer .footer-col ul li a {
            color: var(--text-color);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        footer.site-footer .footer-col ul li a:hover {
            color: var(--gold-color);
        }

        .social-links a {
            color: var(--text-color);
            font-size: 1.5em;
            margin-right: 15px;
            transition: color 0.3s ease, transform 0.3s ease;
        }

        .social-links a:hover {
            color: var(--gold-color);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 30px;
            margin-top: 30px;
            color: rgba(255, 255, 255, 0.6);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        /* Botão de Acesso Admin no rodapé */
        .footer-bottom .admin-link-btn {
            background-color: var(--accent-color);
            color: var(--primary-bg);
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9em;
            font-weight: 600;
            text-decoration: none;
            transition: background-color 0.3s ease, transform 0.2s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        .footer-bottom .admin-link-btn:hover {
            background-color: var(--light-accent);
            transform: translateY(-2px);
        }
        .footer-bottom .admin-link-btn i {
            font-size: 1.1em;
        }


        /* Modais (Login e Registro) */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.7);
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }

        .modal.open {
            display: flex;
            opacity: 1;
        }

        .modal-content {
            background-color: var(--primary-bg);
            margin: auto;
            padding: 30px 40px;
            border-radius: 10px;
            width: 90%;
            max-width: 450px;
            position: relative;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
            transform: translateY(-50px);
            transition: transform 0.3s ease-in-out;
        }

        .modal.open .modal-content {
            transform: translateY(0);
        }


        .modal-content h2 {
            color: var(--accent-color);
            text-align: center;
            margin-bottom: 25px;
            font-size: 2.2em;
        }

        .close-button {
            color: var(--text-color);
            font-size: 2.2em;
            position: absolute;
            right: 20px;
            top: 10px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-button:hover,
        .close-button:focus {
            color: var(--gold-color);
            text-decoration: none;
        }

        .modal-content .form-group label {
            color: var(--text-color);
        }
        .modal-content .form-group input,
        .modal-content .form-group textarea {
            background-color: var(--secondary-bg);
            border-color: rgba(255, 255, 255, 0.1);
        }

        .modal-content .primary-btn {
            width: 100%;
            margin-top: 20px;
        }

        .error-message {
            color: var(--error-color);
            text-align: center;
            margin-top: 15px;
            font-weight: 600;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .error-message.show {
            opacity: 1;
        }

        /* --- User Profile Section Styles --- */
        #user-profile-section {
            display: none; /* Escondido por padrão */
            background-color: var(--primary-bg);
            min-height: calc(100vh - 100px); /* Ajuste para não sobrepor header/footer */
            padding: 60px 0;
            color: var(--text-color);
        }
        #user-profile-section .profile-header {
            text-align: center;
            margin-bottom: 50px;
        }
        #user-profile-section .profile-header h2 {
            font-family: 'Montserrat', sans-serif;
            font-size: 3.2em;
            color: var(--accent-color);
            margin-bottom: 10px;
        }
        #user-profile-section .profile-header p {
            font-size: 1.2em;
            color: var(--text-color);
            opacity: 0.8;
        }
        #user-profile-section .profile-details,
        #user-profile-section .profile-posts {
            background-color: var(--secondary-bg);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            margin-bottom: 40px;
        }
        #user-profile-section h3 {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.8em;
            color: var(--gold-color);
            margin-bottom: 25px;
            border-bottom: 2px solid rgba(255,215,0,0.2);
            padding-bottom: 10px;
        }
        #user-profile-section p strong {
            color: var(--accent-color);
        }
        #user-profile-section .user-posts-list {
            list-style: none;
            padding: 0;
        }
        #user-profile-section .user-posts-list li {
            background-color: var(--primary-bg);
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.2);
        }
        #user-profile-section .user-posts-list li h4 {
            color: var(--gold-color);
            font-size: 1.3em;
            margin-bottom: 5px;
        }
        #user-profile-section .user-posts-list li p {
            font-size: 0.95em;
            color: var(--text-color);
            opacity: 0.9;
        }
        #user-profile-section .user-posts-list li .post-date {
            font-size: 0.8em;
            color: var(--text-color);
            opacity: 0.6;
            margin-top: 10px;
            display: block;
        }
        #user-profile-section .no-posts {
            color: var(--text-color);
            opacity: 0.7;
            text-align: center;
            font-style: italic;
        }
        #user-profile-section .back-to-site-btn {
            background-color: var(--gold-color);
            color: var(--primary-bg);
            margin-top: 20px;
        }
        #user-profile-section .back-to-site-btn:hover {
            filter: brightness(0.9);
        }


        /* --- Admin Section Styles --- */
        .admin-full-screen-section {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            width: 100%;
        }

        /* Admin Login Page Styles */
        .admin-login-wrapper {
            font-family: 'Roboto', sans-serif;
            background-color: var(--admin-bg-light);
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            justify-content: center;
            align-items: center;
            color: var(--admin-text-dark);
        }

        .admin-login-wrapper .login-container {
            background-color: #fff;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        .admin-login-wrapper .login-container h2 {
            color: var(--admin-bg-dark);
            margin-bottom: 30px;
            font-size: 2em;
        }

        .admin-login-wrapper .login-container .form-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .admin-login-wrapper .login-container .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 700;
            color: #555;
        }

        .admin-login-wrapper .login-container .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--admin-border-light);
            border-radius: 5px;
            font-size: 1em;
        }

        .admin-btn {
            background-color: var(--admin-bg-dark);
            color: var(--admin-text-light);
            border: none;
            padding: 12px 25px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.1em;
            font-weight: 700;
            transition: background-color 0.3s ease;
            width: 100%;
            margin-top: 15px;
        }

        .admin-btn:hover {
            background-color: #555555;
        }

        .admin-error-message {
            color: var(--error-color);
            text-align: center;
            margin-top: 15px;
            font-weight: 700;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .admin-error-message.show {
            opacity: 1;
        }


        /* Admin Dashboard Page Styles */
        .admin-dashboard-wrapper {
            font-family: 'Roboto', sans-serif;
            background-color: var(--admin-bg-light);
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            color: var(--admin-text-dark);
        }

        .admin-header-dashboard {
            background-color: var(--admin-bg-dark);
            color: var(--admin-text-light);
            padding: 20px 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .admin-header-dashboard .header-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .admin-header-dashboard h1 {
            font-size: 2.2em;
            font-weight: 700;
        }

        .admin-nav-dashboard {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        #admin-welcome {
            font-size: 1.1em;
            font-weight: 400;
            color: #eee;
        }

        .logout-btn {
            background-color: #555;
            color: #fff;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 700;
            font-size: 0.95em;
            transition: background-color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .logout-btn:hover {
            background-color: #777;
        }

        .admin-main-dashboard {
            flex-grow: 1;
            padding: 40px 0;
        }

        .admin-container-dashboard {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .admin-section-dashboard {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
            margin-bottom: 40px;
        }

        .admin-section-dashboard h2 {
            color: var(--admin-bg-dark);
            font-size: 2em;
            margin-bottom: 25px;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
        }

        .admin-dashboard-actions {
            display: flex;
            gap: 20px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        .admin-dashboard-actions .admin-btn {
            width: auto;
            min-width: 150px;
            margin-top: 0;
            padding: 10px 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        .admin-dashboard-actions .admin-btn.post-news {
            background-color: var(--accent-color);
            color: var(--primary-bg);
        }
        .admin-dashboard-actions .admin-btn.post-news:hover {
            background-color: var(--light-accent);
        }


        .table-responsive {
            overflow-x: auto;
        }

        .user-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        .user-table th, .user-table td {
            border: 1px solid #eee;
            padding: 12px 15px;
            text-align: left;
            font-size: 0.95em;
        }

        .user-table th {
            background-color: #f8f8f8;
            font-weight: 700;
            color: #333;
            white-space: nowrap;
        }

        .user-table tbody tr:nth-child(even) {
            background-color: #fbfbfb;
        }

        .user-table tbody tr:hover {
            background-color: var(--admin-hover-light);
        }

        /* Status Badges */
        .status-active {
            background-color: var(--admin-status-active-bg);
            color: var(--admin-status-active-text);
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.85em;
            font-weight: 700;
        }

        .status-inactive {
            background-color: var(--admin-status-inactive-bg);
            color: var(--admin-status-inactive-text);
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.85em;
            font-weight: 700;
        }

        .action-buttons button {
            background-color: var(--admin-bg-dark);
            color: var(--admin-text-light);
            border: none;
            padding: 6px 10px;
            border-radius: 4px;
            cursor: pointer;
            margin-right: 5px;
            transition: background-color 0.3s ease;
            font-size: 0.8em;
        }

        .action-buttons button:hover {
            background-color: #555;
        }

        /* Statistics Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }

        .stat-card {
            background-color: #f8f8f8;
            padding: 25px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-card h3 {
            font-size: 1.2em;
            color: #555;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .stat-card h3 i {
            color: var(--admin-bg-dark);
            font-size: 1.3em;
        }

        .stat-card p {
            font-size: 2.5em;
            font-weight: 700;
            color: var(--admin-bg-dark);
        }

        /* Responsividade (geral) */
        @media (max-width: 992px) {
            header.site-header .header-content {
                flex-direction: row;
                justify-content: space-between;
                align-items: center;
            }
            .hero-content h2 {
                font-size: 3.5em;
            }
            .founder-info h3 {
                font-size: 1.2em;
            }
            .big-v {
                font-size: 8em;
            }
            .section-title {
                font-size: 2.5em;
            }
            .news-grid, .posts-grid {
                grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            }
            .about-content p {
                font-size: 1em;
            }
            .admin-header-dashboard .header-container {
                flex-direction: column;
                gap: 15px;
                text-align: center;
            }
            .admin-nav-dashboard {
                flex-direction: column;
                gap: 10px;
            }
            .admin-login-wrapper .login-container, .admin-section-dashboard {
                padding: 25px;
            }
            .admin-header-dashboard h1 {
                font-size: 1.8em;
            }
            .admin-section-dashboard h2 {
                font-size: 1.8em;
            }
            .stats-grid {
                grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            }
            #user-profile-section .profile-header h2 {
                font-size: 2.5em;
            }
        }

        @media (max-width: 768px) {
            .hero-section {
                height: 80vh;
            }
            .hero-content h2 {
                font-size: 2.8em;
            }
            .founder-info h3 {
                font-size: 1em;
            }
            .big-v {
                font-size: 6em;
            }
            .section-title {
                font-size: 2em;
            }
            .card-content h3, .card-content h4 {
                font-size: 1.3em;
            }
            footer.site-footer .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            footer.site-footer .footer-col ul {
                padding-left: 0;
            }
            .social-links {
                margin-top: 20px;
            }
            .sidebar.open {
                width: 100%;
            }
            #user-profile-section .profile-header h2 {
                font-size: 2em;
            }
            .admin-dashboard-actions {
                flex-direction: column;
                align-items: center;
            }
            .admin-dashboard-actions .admin-btn {
                width: 80%;
            }
        }

        @media (max-width: 480px) {
            .logo h1 {
                font-size: 1.8em;
            }
            .hero-content h2 {
                font-size: 2em;
            }
            .founder-info h3 {
                font-size: 1.1em;
            }
            .big-v {
                font-size: 5em;
            }
            .section-title {
                font-size: 1.8em;
            }
            .section-padding {
                padding: 60px 0;
            }
            .card-content {
                padding: 20px;
            }
            .form-group label {
                font-size: 0.9em;
            }
            .form-group input, .form-group textarea {
                font-size: 0.9em;
            }
            .modal-content {
                padding: 25px 30px;
            }
            .modal-content h2 {
                font-size: 1.8em;
            }
            .close-button {
                font-size: 1.8em;
                right: 15px;
                top: 5px;
            }
            .admin-login-wrapper .login-container {
                padding: 25px;
            }
            .admin-login-wrapper .login-container h2 {
                font-size: 1.6em;
            }
            .admin-btn {
                padding: 10px 20px;
                font-size: 1em;
            }
            .admin-header-dashboard h1 {
                font-size: 1.5em;
            }
            .admin-section-dashboard h2 {
                font-size: 1.5em;
            }
            .user-table th, .user-table td {
                padding: 8px 10px;
                font-size: 0.85em;
            }
            .stat-card h3 {
                font-size: 1.1em;
            }
            .stat-card p {
                font-size: 2em;
            }
            #user-profile-section .profile-header h2 {
                font-size: 1.8em;
            }
        }
    </style>
</head>
<body>
    <!-- Cabeçalho do Site Principal -->
    <header id="site-main-header" class="site-header">
        <div class="header-content">
            <div class="logo">
                <h1>VANGUARD <span class="evolution-text">EVOLUTION</span></h1>
            </div>
            <button class="menu-toggle" onclick="toggleSidebar()">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- Sidebar de Navegação -->
    <div id="mySidebar" class="sidebar">
        <a href="javascript:void(0)" class="closebtn" onclick="toggleSidebar()">&times;</a>
        <a href="#" onclick="showSiteSection('hero-section', event)">Início</a>
        <a href="#noticias" onclick="showSiteSection('news-section', event)">Notícias</a>
        <a href="#postagens" onclick="showSiteSection('posts-section', event)">Postagens</a>
        <a href="#sobre" onclick="showSiteSection('about-section', event)">Sobre</a>
        <a href="#contato" onclick="showSiteSection('contact-section', event)">Contato</a>
        <!-- Botões de Login/Perfil e Registrar (visibilidade controlada pelo JS) -->
        <button id="sidebar-auth-btn" class="sidebar-btn login"><i class="fas fa-user-circle"></i> Login</button>
        <button id="sidebar-register-btn" class="sidebar-btn"><i class="fas fa-user-plus"></i> Registrar</button>
        <button id="sidebar-create-post-btn" class="sidebar-btn create-post-btn" style="display: none;"><i class="fas fa-plus-square"></i> Criar Postagem</button>
        <button id="sidebar-logout-btn" class="sidebar-btn" style="background-color: #e74c3c; display: none;"><i class="fas fa-sign-out-alt"></i> Sair</button>
    </div>

    <!-- Conteúdo Principal do Site (Visível por padrão) -->
    <main id="site-content">
        <!-- Hero Section -->
        <section id="hero-section" class="hero-section">
            <div class="hero-overlay"></div>
            <div class="container hero-content">
                <h2 class="animate-fade-in-up">VANGUARD <span class="evolution-text">EVOLUTION</span></h2>
                <div class="founder-info animate-fade-in-up delay-1">
                    <h3>Fundado por <span class="founder-name">Newox Vanguard</span></h3>
                    <span class="big-v">V</span>
                </div>
            </div>
        </section>

        <!-- Seção de Destaque / Notícias Recentes -->
        <section id="noticias" class="news-section section-padding reveal">
            <div class="container">
                <h2 class="section-title">Últimas Notícias <i class="fas fa-newspaper"></i></h2>
                <div id="news-grid-container" class="news-grid">
                    <!-- Notícias dinâmicas serão injetadas aqui -->
                </div>
                <div class="text-center mt-4">
                    <a href="#" class="btn secondary-btn">Ver Todas as Notícias <i class="fas fa-angle-right"></i></a>
                </div>
            </div>
        </section>

        <!-- Seção de Postagens -->
        <section id="postagens" class="posts-section section-padding bg-darker reveal">
            <div class="container">
                <h2 class="section-title">Nossas Postagens <i class="fas fa-pen-nib"></i></h2>
                <div id="posts-grid-container" class="posts-grid">
                    <!-- Postagens dinâmicas serão injetadas aqui -->
                </div>
                <div class="text-center mt-4">
                    <a href="#" class="btn primary-btn">Ver Todas as Postagens <i class="fas fa-angle-right"></i></a>
                </div>
            </div>
        </section>

        <!-- Seção Sobre Nós -->
        <section id="sobre" class="about-section section-padding reveal">
            <div class="container">
                <h2 class="section-title">Sobre Nós <i class="fas fa-info-circle"></i></h2>
                <div class="about-content animate-fade-in">
                    <p>A <strong>VANGUARD EVOLUTION</strong> nasceu da visão de <strong>Newox Vanguard</strong> de criar uma plataforma para insights profundos, notícias relevantes e postagens que inspiram. Nosso objetivo é explorar o futuro, analisar o presente e capacitar nossos leitores com conhecimento.</p>
                    <p>Acreditamos no poder da informação e na importância de uma visão de vanguarda para o mundo em constante mudança. Junte-se à nossa jornada!</p>
                    <img src="https://via.placeholder.com/800x450/1B2A41/E0E0E0?text=Vanguard+Evolution+Team" alt="Equipe Vanguard Evolution" class="about-image">
                </div>
            </div>
        </section>

        <!-- Seção de Contato -->
        <section id="contato" class="contact-section section-padding bg-darker reveal">
            <div class="container">
                <h2 class="section-title">Fale Conosco <i class="fas fa-envelope"></i></h2>
                <div class="contact-form animate-fade-in">
                    <form action="#" method="POST">
                        <div class="form-group">
                            <label for="name">Nome:</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email:</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Mensagem:</label>
                            <textarea id="message" name="message" rows="6" required></textarea>
                        </div>
                        <button type="submit" class="btn primary-btn">Enviar Mensagem <i class="fas fa-paper-plane"></i></button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- Seção de Perfil do Usuário (Inicialmente oculta) -->
    <div id="user-profile-section" style="display: none;">
        <div class="container">
            <div class="profile-header">
                <h2>Meu Perfil</h2>
                <p>Boas-vindas à sua área personalizada, <span id="profile-username-display"></span>!</p>
            </div>

            <div class="profile-details">
                <h3>Detalhes da Conta</h3>
                <p><strong>Usuário:</strong> <span id="profile-username"></span></p>
                <p><strong>Email:</strong> <span id="profile-email"></span></p>
            </div>

            <div class="profile-posts">
                <h3>Minhas Postagens</h3>
                <ul id="user-posts-list" class="user-posts-list">
                    <!-- Postagens do usuário serão injetadas aqui -->
                </ul>
                <p id="no-user-posts" class="no-posts" style="display: none;">Você ainda não criou nenhuma postagem.</p>
            </div>

            <div class="text-center">
                <button class="btn primary-btn back-to-site-btn" onclick="showMainSite(event)"><i class="fas fa-arrow-left"></i> Voltar ao Site</button>
            </div>
        </div>
    </div>

    <!-- Seção de Login do Administrador (Inicialmente oculta) -->
    <div id="admin-login-section" class="admin-full-screen-section admin-login-wrapper" style="display: none;">
        <div class="login-container">
            <h2>Painel de Administração</h2>
            <form id="admin-login-form">
                <div class="form-group">
                    <label for="admin-username">Usuário:</label>
                    <input type="text" id="admin-username" name="admin-username" required>
                </div>
                <div class="form-group">
                    <label for="admin-password">Senha:</label>
                    <input type="password" id="admin-password" name="admin-password" required>
                </div>
                <button type="submit" class="admin-btn">Entrar</button>
                <p id="admin-login-message" class="admin-error-message"></p>
            </form>
            <button class="admin-btn" style="background-color: #777; margin-top: 15px;" onclick="showMainSite(event)">Voltar ao Site</button>
        </div>
    </div>

    <!-- Seção do Dashboard do Administrador (Inicialmente oculta) -->
    <div id="admin-dashboard-section" class="admin-full-screen-section admin-dashboard-wrapper" style="display: none;">
        <header class="admin-header-dashboard">
            <div class="header-container">
                <h1>Painel de Administração</h1>
                <nav class="admin-nav-dashboard">
                    <span id="admin-welcome">Olá, Admin!</span>
                    <a href="#" id="admin-logout-btn-dashboard" class="logout-btn"><i class="fas fa-sign-out-alt"></i> Sair</a>
                </nav>
            </div>
        </header>

        <main class="admin-main-dashboard">
            <div class="admin-container-dashboard">
                <section class="admin-section-dashboard">
                    <h2>Gerenciamento de Conteúdo</h2>
                    <div class="admin-dashboard-actions">
                        <button id="admin-post-news-btn" class="admin-btn post-news"><i class="fas fa-plus"></i> Postar Nova Notícia</button>
                        <!-- Adicione outros botões de gerenciamento se necessário -->
                    </div>
                </section>
                <section class="admin-section-dashboard">
                    <h2>Gerenciamento de Usuários</h2>
                    <div class="table-responsive">
                        <table class="user-table">
                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Usuário</th>
                                    <th>Senha (Exemplo)</th>
                                    <th>Email</th>
                                    <th>Status</th>
                                    <th>Ações</th>
                                </tr>
                            </thead>
                            <tbody id="user-data-body">
                                <!-- Os dados dos usuários serão inseridos aqui pelo JavaScript -->
                            </tbody>
                        </table>
                    </div>
                </section>

                <section class="admin-section-dashboard">
                    <h2>Estatísticas Rápidas</h2>
                    <div class="stats-grid">
                        <div class="stat-card">
                            <h3><i class="fas fa-users"></i> Total de Usuários</h3>
                            <p id="total-users-stat">0</p>
                        </div>
                        <div class="stat-card">
                            <h3><i class="fas fa-pen"></i> Total de Postagens</h3>
                            <p id="total-posts-stat">0</p>
                        </div>
                        <div class="stat-card">
                            <h3><i class="fas fa-newspaper"></i> Total de Notícias</h3>
                            <p id="total-news-stat">0</p>
                        </div>
                        <div class="stat-card">
                            <h3><i class="fas fa-eye"></i> Visualizações Hoje</h3>
                            <p>12,450</p>
                        </div>
                    </div>
                </section>
            </div>
        </main>
    </div>

    <!-- Rodapé do Site Principal -->
    <footer id="site-main-footer" class="site-footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-col logo-col">
                    <h3>VANGUARD EVOLUTION</h3>
                    <p>Sua perspectiva para o futuro.</p>
                </div>
                <div class="footer-col">
                    <h4>Links Rápidos</h4>
                    <ul>
                        <li><a href="#" onclick="showSiteSection('news-section', event)">Notícias</a></li>
                        <li><a href="#" onclick="showSiteSection('posts-section', event)">Postagens</a></li>
                        <li><a href="#" onclick="showSiteSection('about-section', event)">Sobre</a></li>
                        <li><a href="#" onclick="showSiteSection('contact-section', event)">Contato</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h4>Redes Sociais</h4>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 VANGUARD EVOLUTION. Todos os direitos reservados. Design por Newox Vanguard.</p>
                <!-- Botão de Acesso Admin -->
                <button class="admin-link-btn" id="go-to-admin-login"><i class="fas fa-user-shield"></i> Acesso Admin</button>
            </div>
        </div>
    </footer>

    <!-- Modal de Login do Usuário -->
    <div id="login-modal" class="modal">
        <div class="modal-content">
            <span class="close-button" data-modal="login-modal">&times;</span>
            <h2>Login</h2>
            <form id="login-form">
                <div class="form-group">
                    <label for="username">Usuário:</label>
                    <input type="text" id="username" name="username" required>
                </div>
                <div class="form-group">
                    <label for="password">Senha:</label>
                    <input type="password" id="password" name="password" required>
                </div>
                <button type="submit" class="btn primary-btn">Entrar</button>
                <p id="login-message" class="error-message"></p>
            </form>
        </div>
    </div>

    <!-- Modal de Registro do Usuário -->
    <div id="register-modal" class="modal">
        <div class="modal-content">
            <span class="close-button" data-modal="register-modal">&times;</span>
            <h2>Registrar</h2>
            <form id="register-form">
                <div class="form-group">
                    <label for="reg-username">Usuário:</label>
                    <input type="text" id="reg-username" name="reg-username" required>
                </div>
                <div class="form-group">
                    <label for="reg-email">Email:</label>
                    <input type="email" id="reg-email" name="reg-email" required>
                </div>
                <div class="form-group">
                    <label for="reg-password">Senha:</label>
                    <input type="password" id="reg-password" name="reg-password" required>
                </div>
                <div class="form-group">
                    <label for="reg-confirm-password">Confirmar Senha:</label>
                    <input type="password" id="reg-confirm-password" name="reg-confirm-password" required>
                </div>
                <button type="submit" class="btn primary-btn">Registrar</button>
                <p id="register-message" class="error-message"></p>
            </form>
        </div>
    </div>

    <!-- Modal de Criar Postagem (Usuário) -->
    <div id="create-post-modal" class="modal">
        <div class="modal-content">
            <span class="close-button" data-modal="create-post-modal">&times;</span>
            <h2>Criar Nova Postagem</h2>
            <form id="create-post-form">
                <div class="form-group">
                    <label for="post-title">Título:</label>
                    <input type="text" id="post-title" name="post-title" required>
                </div>
                <div class="form-group">
                    <label for="post-content">Conteúdo:</label>
                    <textarea id="post-content" name="post-content" rows="8" required></textarea>
                </div>
                <button type="submit" class="btn primary-btn">Publicar Postagem <i class="fas fa-paper-plane"></i></button>
                <p id="create-post-message" class="error-message"></p>
            </form>
        </div>
    </div>

    <!-- Modal de Criar Notícia (Admin) -->
    <div id="create-news-modal" class="modal">
        <div class="modal-content">
            <span class="close-button" data-modal="create-news-modal">&times;</span>
            <h2>Postar Nova Notícia</h2>
            <form id="create-news-form">
                <div class="form-group">
                    <label for="news-title">Título da Notícia:</label>
                    <input type="text" id="news-title" name="news-title" required>
                </div>
                <div class="form-group">
                    <label for="news-content">Conteúdo da Notícia:</label>
                    <textarea id="news-content" name="news-content" rows="8" required></textarea>
                </div>
                <button type="submit" class="btn primary-btn">Publicar Notícia <i class="fas fa-upload"></i></button>
                <p id="create-news-message" class="error-message"></p>
            </form>
        </div>
    </div>


    <script>
        // JAVASCRIPT CONSOLIDADO DO SITE E ADMIN COM PERSISTÊNCIA VIA localStorage

        document.addEventListener('DOMContentLoaded', () => {
            const siteMainHeader = document.getElementById('site-main-header');
            const siteContent = document.getElementById('site-content');
            const siteMainFooter = document.getElementById('site-main-footer');
            const userProfileSection = document.getElementById('user-profile-section');
            const adminLoginSection = document.getElementById('admin-login-section');
            const adminDashboardSection = document.getElementById('admin-dashboard-section');
            const mySidebar = document.getElementById('mySidebar');
            
            // Elementos da sidebar para controle de visibilidade
            const sidebarAuthBtn = document.getElementById('sidebar-auth-btn'); // Botão de Login/Perfil
            const sidebarRegisterBtn = document.getElementById('sidebar-register-btn'); // Botão de Registrar
            const sidebarCreatePostBtn = document.getElementById('sidebar-create-post-btn'); // Botão de Criar Postagem
            const sidebarLogoutBtn = document.getElementById('sidebar-logout-btn'); // Botão de Sair (logout)

            // --- Funções de persistência no localStorage ---
            function saveToLocalStorage(key, data) {
                localStorage.setItem(key, JSON.stringify(data));
            }

            function loadFromLocalStorage(key, defaultValue) {
                const data = localStorage.getItem(key);
                return data ? JSON.parse(data) : defaultValue;
            }

            // --- Simulação de dados: Usuários, Postagens e Notícias (agora com persistência) ---
            let registeredUsers = loadFromLocalStorage('registeredUsers', [
                { id: 1, user: 'Newox', pass: 'objeto', email: 'newox.user@example.com', status: 'Ativo' },
            ]);
            let nextUserId = registeredUsers.length > 0 ? Math.max(...registeredUsers.map(u => u.id)) + 1 : 1;

            let sitePosts = loadFromLocalStorage('sitePosts', [
                { id: 1, title: '5 Dicas Essenciais para Aumentar sua Produtividade', content: 'Pequenas mudanças diárias podem levar a grandes resultados. Descubra como ser mais eficiente.', author: 'Newox Vanguard', authorId: 1, date: 'Outubro 27, 2025' },
                { id: 2, title: 'Desenvolva sua Criatividade: Exercícios Práticos', content: 'A criatividade é uma habilidade que pode ser treinada. Liberte seu potencial criativo.', author: 'Equipe Vanguard', authorId: 0, date: 'Outubro 26, 2025' }
            ]);
            let nextPostId = sitePosts.length > 0 ? Math.max(...sitePosts.map(p => p.id)) + 1 : 1;

            let siteNews = loadFromLocalStorage('siteNews', [
                { id: 1, title: 'O Impacto da IA na Sociedade Moderna', content: 'Descubra como a inteligência artificial está moldando nosso futuro e transformando indústrias.', author: 'Admin', date: 'Outubro 28, 2025', image: 'https://via.placeholder.com/400x250/00C9A7/0A1128?text=Tecnologia' },
                { id: 2, title: 'Análise do Mercado Financeiro Global 2025', content: 'Tendências e previsões para a economia mundial no próximo ano. O que esperar?', author: 'Admin', date: 'Outubro 28, 2025', image: 'https://via.placeholder.com/400x250/FFD700/0A1128?text=Economia' },
                { id: 3, title: 'Inovações Sustentáveis que Podem Salvar o Planeta', content: 'Conheça projetos e tecnologias revolucionárias focadas na sustentabilidade ambiental.', author: 'Admin', date: 'Outubro 27, 2025', image: 'https://via.placeholder.com/400x250/1B2A41/E0E0E0?text=Inovacao' }
            ]);
            let nextNewsId = siteNews.length > 0 ? Math.max(...siteNews.map(n => n.id)) + 1 : 1;

            let loggedInUser = loadFromLocalStorage('loggedInUser', null); // Carrega o usuário logado
            let isAdminLoggedIn = loadFromLocalStorage('isAdminLoggedIn', false); // Carrega status do admin

            // --- Funções para controlar a visibilidade das seções ---
            function hideAllSections() {
                siteMainHeader.style.display = 'none';
                siteContent.style.display = 'none';
                siteMainFooter.style.display = 'none';
                userProfileSection.style.display = 'none';
                adminLoginSection.style.display = 'none';
                adminDashboardSection.style.display = 'none';
                mySidebar.classList.remove('open');
                window.scrollTo(0, 0);
            }

            function showMainSite(e) {
                if (e) e.preventDefault();
                hideAllSections();
                siteMainHeader.style.display = 'flex';
                siteContent.style.display = 'block';
                siteMainFooter.style.display = 'flex';
                document.body.style.backgroundColor = 'var(--primary-bg)';
                document.body.style.color = 'var(--text-color)';
                document.body.style.fontFamily = 'Poppins, sans-serif';
                renderNews();
                renderPosts();
                updateSidebarAuthButtons();
            }

            function showUserProfileSection(e) {
                if (e) e.preventDefault();
                if (!loggedInUser) {
                    alert('Você precisa estar logado para acessar seu perfil!');
                    openModal(document.getElementById('login-modal'));
                    return;
                }
                hideAllSections();
                userProfileSection.style.display = 'block';
                document.body.style.backgroundColor = 'var(--primary-bg)';
                document.body.style.color = 'var(--text-color)';
                document.body.style.fontFamily = 'Poppins, sans-serif';
                populateUserProfile();
            }

            function showAdminLogin(e) {
                if (e) e.preventDefault();
                hideAllSections();
                adminLoginSection.style.display = 'flex';
                document.body.style.backgroundColor = 'var(--admin-bg-light)';
                document.body.style.color = 'var(--admin-text-dark)';
                document.body.style.fontFamily = 'Roboto, sans-serif';
            }

            function showAdminDashboard(e) {
                if (e) e.preventDefault();
                // Verifica novamente o status do admin (em caso de navegação direta)
                if (!isAdminLoggedIn) {
                    showAdminLogin();
                    return;
                }
                hideAllSections();
                adminDashboardSection.style.display = 'flex';
                document.body.style.backgroundColor = 'var(--admin-bg-light)';
                document.body.style.color = 'var(--admin-text-dark)';
                document.body.style.fontFamily = 'Roboto, sans-serif';
                populateUserData();
                updateAdminStats();
            }

            // --- LÓGICA DA SIDEBAR ---
            window.toggleSidebar = () => {
                mySidebar.classList.toggle('open');
            };

            window.addEventListener('click', (event) => {
                const isClickInsideSidebar = mySidebar.contains(event.target);
                const isClickOnMenuToggle = event.target.closest('.menu-toggle');
                
                if (mySidebar.classList.contains('open') && !isClickInsideSidebar && !isClickOnMenuToggle) {
                    mySidebar.classList.remove('open');
                }
            });

            // --- LÓGICA DE RENDERIZAÇÃO DE CONTEÚDO ---

            function renderNews() {
                const newsGridContainer = document.getElementById('news-grid-container');
                if (!newsGridContainer) return;

                newsGridContainer.innerHTML = '';

                siteNews.slice().reverse().forEach(news => {
                    const article = document.createElement('article');
                    article.classList.add('news-card');
                    article.innerHTML = `
                        <img src="${news.image}" alt="${news.title}">
                        <div class="card-content">
                            <h3>${news.title}</h3>
                            <p>${news.content.substring(0, 100)}...</p>
                            <a href="#" class="read-more">Leia Mais <i class="fas fa-angle-right"></i></a>
                        </div>
                    `;
                    newsGridContainer.appendChild(article);
                });
            }

            function renderPosts() {
                const postsGridContainer = document.getElementById('posts-grid-container');
                if (!postsGridContainer) return;

                postsGridContainer.innerHTML = '';

                sitePosts.slice().reverse().forEach(post => {
                    const article = document.createElement('article');
                    article.classList.add('post-card');
                    article.innerHTML = `
                        <img src="https://via.placeholder.com/300x200/${(post.authorId % 2 === 0 ? 'FFD700' : '00C9A7')}/0A1128?text=Postagem" alt="${post.title}">
                        <div class="card-content">
                            <h4>${post.title}</h4>
                            <p class="post-meta">Por ${post.author} | ${post.date}</p>
                            <p>${post.content.substring(0, 100)}...</p>
                            <a href="#" class="read-more">Continuar Lendo <i class="fas fa-angle-right"></i></a>
                        </div>
                    `;
                    postsGridContainer.appendChild(article);
                });
            }

            // --- Scroll suave para links de navegação da sidebar ---
            document.querySelectorAll('#mySidebar a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href').substring(1);
                    showSiteSection(targetId, e);
                });
            });

            window.showSiteSection = (id, event) => {
                if (event) event.preventDefault();
                showMainSite();
                setTimeout(() => {
                    const targetElement = document.getElementById(id);
                    if (targetElement) {
                        targetElement.scrollIntoView({ behavior: 'smooth' });
                    }
                    document.querySelectorAll('#mySidebar a').forEach(link => link.classList.remove('active'));
                    const correspondingLink = document.querySelector(`#mySidebar a[href="#${id}"]`);
                    if (correspondingLink) correspondingLink.classList.add('active');
                    else if (id === 'hero-section') document.querySelector('#mySidebar a:first-of-type').classList.add('active');
                }, 50);
            };


            // === Observador de Interseção para Animações de Revelação ===
            const sections = document.querySelectorAll('.reveal');
            const options = {
                root: null,
                rootMargin: '0px',
                threshold: 0.2
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                    }
                });
            }, options);

            sections.forEach(section => {
                observer.observe(section);
            });

            // Aplica animação aos cards no carregamento da página ou ao entrar na viewport
            const animatedCards = document.querySelectorAll('.animate-scale-in, .animate-slide-in-left, .animate-slide-in-right, .animate-fade-in');
            const cardOptions = {
                root: null,
                rootMargin: '0px',
                threshold: 0.1
            };

            const cardObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationPlayState = 'running';
                        observer.unobserve(entry.target);
                    }
                });
            }, cardOptions);

            animatedCards.forEach(card => {
                card.style.animationPlayState = 'paused';
                cardObserver.observe(card);
            });


            // --- Lógica dos Modais (Login, Registro, Criar Postagem, Criar Notícia) ---
            const loginModal = document.getElementById('login-modal');
            const registerModal = document.getElementById('register-modal');
            const createPostModal = document.getElementById('create-post-modal');
            const createNewsModal = document.getElementById('create-news-modal');

            // Funções genéricas para abrir/fechar modais
            function openModal(modalElement) {
                modalElement.classList.add('open');
                modalElement.querySelector('.error-message').classList.remove('show');
                const form = modalElement.querySelector('form');
                if (form) form.reset();
                mySidebar.classList.remove('open');
            }

            function closeModal(modalElement) {
                modalElement.classList.remove('open');
            }

            // Event Listeners para botões da sidebar
            sidebarAuthBtn.addEventListener('click', () => {
                if (loggedInUser) {
                    showUserProfileSection();
                } else {
                    openModal(loginModal);
                }
            });
            sidebarRegisterBtn.addEventListener('click', () => openModal(registerModal));
            sidebarCreatePostBtn.addEventListener('click', () => {
                if (loggedInUser) {
                    openModal(createPostModal);
                } else {
                    alert('Você precisa estar logado para criar uma postagem!');
                    openModal(loginModal);
                }
            });
            sidebarLogoutBtn.addEventListener('click', (e) => {
                e.preventDefault();
                loggedInUser = null;
                localStorage.removeItem('loggedInUser');
                updateSidebarAuthButtons();
                showMainSite();
                alert('Você foi desconectado.');
            });


            // Event Listeners para botões de fechar (X) em todos os modais
            document.querySelectorAll('.close-button').forEach(button => {
                button.addEventListener('click', (e) => {
                    const modalId = e.target.dataset.modal;
                    const modalToClose = document.getElementById(modalId);
                    if (modalToClose) {
                        closeModal(modalToClose);
                    }
                });
            });

            // Fecha o modal se clicar fora
            window.addEventListener('click', (event) => {
                if (event.target == loginModal) closeModal(loginModal);
                if (event.target == registerModal) closeModal(registerModal);
                if (event.target == createPostModal) closeModal(createPostModal);
                if (event.target == createNewsModal) closeModal(createNewsModal);
            });


            // --- Lógica de Login do Usuário ---
            const loginForm = document.getElementById('login-form');
            const usernameInput = document.getElementById('username');
            const passwordInput = document.getElementById('password');
            const loginMessage = document.getElementById('login-message');

            loginForm.addEventListener('submit', (e) => {
                e.preventDefault();

                const username = usernameInput.value;
                const password = passwordInput.value;

                const userFound = registeredUsers.find(u => u.user === username && u.pass === password);

                if (userFound) {
                    loginMessage.textContent = 'Login bem-sucedido!';
                    loginMessage.style.color = '#2ecc71';
                    loginMessage.classList.add('show');
                    loggedInUser = userFound;
                    saveToLocalStorage('loggedInUser', loggedInUser); // Salva o usuário logado

                    setTimeout(() => {
                        closeModal(loginModal);
                        updateSidebarAuthButtons();
                        showMainSite();
                    }, 1500);

                } else {
                    loginMessage.textContent = 'Usuário ou senha incorretos.';
                    loginMessage.style.color = 'var(--error-color)';
                    loginMessage.classList.add('show');
                    passwordInput.value = '';
                }
            });

            // Função para atualizar os botões de autenticação na sidebar
            function updateSidebarAuthButtons() {
                if (loggedInUser) {
                    sidebarAuthBtn.innerHTML = `<i class="fas fa-user-circle"></i> Olá, ${loggedInUser.user}!`;
                    sidebarAuthBtn.classList.add('profile-btn');
                    sidebarAuthBtn.classList.remove('login');
                    sidebarRegisterBtn.style.display = 'none';
                    sidebarCreatePostBtn.style.display = 'flex';
                    sidebarLogoutBtn.style.display = 'flex'; // Mostra o botão de logout
                } else {
                    sidebarAuthBtn.innerHTML = '<i class="fas fa-user-circle"></i> Login';
                    sidebarAuthBtn.classList.remove('profile-btn');
                    sidebarAuthBtn.classList.add('login');
                    sidebarRegisterBtn.style.display = 'flex';
                    sidebarCreatePostBtn.style.display = 'none';
                    sidebarLogoutBtn.style.display = 'none';
                }
            }


            // --- Lógica de Registro do Usuário ---
            const registerForm = document.getElementById('register-form');
            const regUsernameInput = document.getElementById('reg-username');
            const regEmailInput = document.getElementById('reg-email');
            const regPasswordInput = document.getElementById('reg-password');
            const regConfirmPasswordInput = document.getElementById('reg-confirm-password');
            const registerMessage = document.getElementById('register-message');

            registerForm.addEventListener('submit', (e) => {
                e.preventDefault();

                const username = regUsernameInput.value;
                const email = regEmailInput.value;
                const password = regPasswordInput.value;
                const confirmPassword = regConfirmPasswordInput.value;

                if (password !== confirmPassword) {
                    registerMessage.textContent = 'As senhas não coincidem!';
                    registerMessage.style.color = 'var(--error-color)';
                    registerMessage.classList.add('show');
                    regConfirmPasswordInput.value = '';
                    return;
                }

                if (registeredUsers.some(u => u.user.toLowerCase() === username.toLowerCase())) {
                    registerMessage.textContent = 'Nome de usuário já existe!';
                    registerMessage.style.color = 'var(--error-color)';
                    registerMessage.classList.add('show');
                    return;
                }
                
                if (registeredUsers.some(u => u.email.toLowerCase() === email.toLowerCase())) {
                    registerMessage.textContent = 'Email já registrado!';
                    registerMessage.style.color = 'var(--error-color)';
                    registerMessage.classList.add('show');
                    return;
                }

                const newUser = {
                    id: nextUserId++,
                    user: username,
                    pass: password,
                    email: email,
                    status: 'Ativo'
                };
                registeredUsers.push(newUser);
                saveToLocalStorage('registeredUsers', registeredUsers); // Salva novos usuários

                registerMessage.textContent = 'Registro bem-sucedido! Faça login agora.';
                registerMessage.style.color = '#2ecc71';
                registerMessage.classList.add('show');

                setTimeout(() => {
                    closeModal(registerModal);
                    openModal(loginModal);
                    usernameInput.value = username;
                    // populateUserData(); // Não precisa atualizar aqui, só no admin dashboard
                }, 1500);
            });

            // --- Lógica de Criar Postagem (Usuário) ---
            const createPostForm = document.getElementById('create-post-form');
            const postTitleInput = document.getElementById('post-title');
            const postContentTextarea = document.getElementById('post-content');
            const createPostMessage = document.getElementById('create-post-message');

            createPostForm.addEventListener('submit', (e) => {
                e.preventDefault();

                if (!loggedInUser) {
                    createPostMessage.textContent = 'Você precisa estar logado para postar!';
                    createPostMessage.style.color = 'var(--error-color)';
                    createPostMessage.classList.add('show');
                    return;
                }

                const title = postTitleInput.value;
                const content = postContentTextarea.value;
                const currentDate = new Date().toLocaleDateString('pt-BR', { year: 'numeric', month: 'long', day: 'numeric' });

                const newPost = {
                    id: nextPostId++,
                    title: title,
                    content: content,
                    author: loggedInUser.user,
                    authorId: loggedInUser.id,
                    date: currentDate
                };
                sitePosts.push(newPost);
                saveToLocalStorage('sitePosts', sitePosts); // Salva novas postagens

                createPostMessage.textContent = 'Postagem criada com sucesso!';
                createPostMessage.style.color = '#2ecc71';
                createPostMessage.classList.add('show');

                setTimeout(() => {
                    closeModal(createPostModal);
                    renderPosts();
                    // populateUserProfile(); // Atualiza as postagens no perfil do usuário
                    updateAdminStats(); // Atualiza as estatísticas no admin
                    showSiteSection('postagens');
                }, 1500);
            });


            // --- Lógica do Perfil do Usuário ---
            const profileUsernameDisplay = document.getElementById('profile-username-display');
            const profileUsername = document.getElementById('profile-username');
            const profileEmail = document.getElementById('profile-email');
            const userPostsList = document.getElementById('user-posts-list');
            const noUserPostsMessage = document.getElementById('no-user-posts');

            function populateUserProfile() {
                if (!loggedInUser) return;

                profileUsernameDisplay.textContent = loggedInUser.user;
                profileUsername.textContent = loggedInUser.user;
                profileEmail.textContent = loggedInUser.email;

                userPostsList.innerHTML = '';
                const userSpecificPosts = sitePosts.filter(post => post.authorId === loggedInUser.id).reverse();

                if (userSpecificPosts.length > 0) {
                    noUserPostsMessage.style.display = 'none';
                    userSpecificPosts.forEach(post => {
                        const listItem = document.createElement('li');
                        listItem.innerHTML = `
                            <h4>${post.title}</h4>
                            <p>${post.content.substring(0, 150)}...</p>
                            <span class="post-date">${post.date}</span>
                        `;
                        userPostsList.appendChild(listItem);
                    });
                } else {
                    noUserPostsMessage.style.display = 'block';
                }
            }


            // --- Lógica do Painel de Administração ---

            // Botão "Acesso Admin" no rodapé
            const goToAdminLoginLink = document.getElementById('go-to-admin-login');
            goToAdminLoginLink.addEventListener('click', showAdminLogin);

            // Lógica para o formulário de Login do Administrador
            const adminLoginForm = document.getElementById('admin-login-form');
            if (adminLoginForm) {
                adminLoginForm.addEventListener('submit', (e) => {
                    e.preventDefault();

                    const adminUsernameInput = document.getElementById('admin-username');
                    const adminPasswordInput = document.getElementById('admin-password');
                    const adminLoginMessage = document.getElementById('admin-login-message');

                    const username = adminUsernameInput.value;
                    const password = adminPasswordInput.value;

                    const correctAdminUsername = 'newox';
                    const correctAdminPassword = 'objeto';

                    if (username === correctAdminUsername && password === correctAdminPassword) {
                        adminLoginMessage.textContent = 'Login bem-sucedido! Redirecionando para o dashboard...';
                        adminLoginMessage.style.color = '#28a745';
                        adminLoginMessage.classList.add('show');

                        isAdminLoggedIn = true;
                        saveToLocalStorage('isAdminLoggedIn', true);
                        saveToLocalStorage('adminUser', username); // Salva o nome do admin

                        setTimeout(() => {
                            showAdminDashboard();
                        }, 1500);

                    } else {
                        adminLoginMessage.textContent = 'Usuário ou senha de administrador incorretos.';
                        adminLoginMessage.style.color = 'var(--error-color)';
                        adminLoginMessage.classList.add('show');
                        adminPasswordInput.value = '';
                    }
                });
            }

            // Lógica para o Dashboard do Administrador
            const userDataBody = document.getElementById('user-data-body');
            const adminWelcome = document.getElementById('admin-welcome');
            const adminLogoutBtnDashboard = document.getElementById('admin-logout-btn-dashboard');
            const adminPostNewsBtn = document.getElementById('admin-post-news-btn');

            const totalUsersStat = document.getElementById('total-users-stat');
            const totalPostsStat = document.getElementById('total-posts-stat');
            const totalNewsStat = document.getElementById('total-news-stat');


            // Função para popular a tabela de usuários
            function populateUserData() {
                if (!userDataBody) return;

                if (!isAdminLoggedIn) { // Verifica o estado de isAdminLoggedIn
                    showAdminLogin();
                    return;
                }

                const loggedInAdminUser = loadFromLocalStorage('adminUser', 'Admin'); // Puxa o nome do admin do localStorage
                if (adminWelcome) {
                    adminWelcome.textContent = `Olá, ${loggedInAdminUser}!`;
                }

                userDataBody.innerHTML = '';

                // Inclui todos os usuários (iniciais + registrados dinamicamente)
                registeredUsers.forEach(user => {
                    const row = userDataBody.insertRow();
                    row.innerHTML = `
                        <td>${user.id}</td>
                        <td>${user.user}</td>
                        <td>${user.pass}</td>
                        <td>${user.email}</td>
                        <td><span class="status-${user.status === 'Ativo' ? 'active' : 'inactive'}">${user.status}</span></td>
                        <td class="action-buttons">
                            <button onclick="editUser(${user.id})">Editar</button>
                            <button onclick="deleteUser(${user.id})">Excluir</button>
                        </td>
                    `;
                });
            }

            // Função para atualizar as estatísticas do admin
            function updateAdminStats() {
                if (totalUsersStat) totalUsersStat.textContent = registeredUsers.length;
                if (totalPostsStat) totalPostsStat.textContent = sitePosts.length;
                if (totalNewsStat) totalNewsStat.textContent = siteNews.length;
            }

            window.editUser = (id) => {
                alert(`Editar usuário com ID: ${id}`);
            };

            window.deleteUser = (id) => {
                if (confirm(`Tem certeza que deseja excluir o usuário com ID: ${id}?`)) {
                    const initialLength = registeredUsers.length;
                    registeredUsers = registeredUsers.filter(user => user.id !== id);
                    if (registeredUsers.length < initialLength) {
                        alert(`Usuário com ID: ${id} excluído (simulado).`);
                        saveToLocalStorage('registeredUsers', registeredUsers); // Salva a lista atualizada
                        populateUserData();
                        updateAdminStats();
                    } else {
                        alert(`Usuário com ID: ${id} não encontrado.`);
                    }
                }
            };

            // Lógica de Criar Notícia (Admin)
            const createNewsForm = document.getElementById('create-news-form');
            const newsTitleInput = document.getElementById('news-title');
            const newsContentTextarea = document.getElementById('news-content');
            const createNewsMessage = document.getElementById('create-news-message');

            adminPostNewsBtn.addEventListener('click', () => {
                if (!isAdminLoggedIn) {
                    alert('Você precisa estar logado como administrador para postar notícias!');
                    showAdminLogin();
                    return;
                }
                openModal(createNewsModal);
            });

            createNewsForm.addEventListener('submit', (e) => {
                e.preventDefault();

                const title = newsTitleInput.value;
                const content = newsContentTextarea.value;
                const currentDate = new Date().toLocaleDateString('pt-BR', { year: 'numeric', month: 'long', day: 'numeric' });

                const newNews = {
                    id: nextNewsId++,
                    title: title,
                    content: content,
                    author: loadFromLocalStorage('adminUser', 'Admin'),
                    date: currentDate,
                    image: `https://via.placeholder.com/400x250/00C9A7/0A1128?text=Nova+Noticia+${nextNewsId-1}`
                };
                siteNews.push(newNews);
                saveToLocalStorage('siteNews', siteNews); // Salva novas notícias

                createNewsMessage.textContent = 'Notícia publicada com sucesso!';
                createNewsMessage.style.color = '#2ecc71';
                createNewsMessage.classList.add('show');

                setTimeout(() => {
                    closeModal(createNewsModal);
                    renderNews();
                    updateAdminStats();
                    showAdminDashboard();
                }, 1500);
            });


            // Lógica de Logout do Admin (Botão no Dashboard)
            if (adminLogoutBtnDashboard) {
                adminLogoutBtnDashboard.addEventListener('click', (e) => {
                    e.preventDefault();
                    isAdminLoggedIn = false;
                    localStorage.removeItem('isAdminLoggedIn');
                    localStorage.removeItem('adminUser');
                    showMainSite();
                    alert('Administrador desconectado.');
                });
            }

            // --- Inicialização ao Carregar a Página ---
            // Verifica o estado de login (admin ou usuário) ao carregar a página e mostra a seção apropriada
            if (isAdminLoggedIn) {
                showAdminDashboard();
            } else {
                showMainSite();
            }
        });
    </script>
</body>
</html>
