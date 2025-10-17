<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>QML.AI - Plataforma Inteligente de Aprendizado</title>
    
    <!-- Bibliotecas -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
    <script src="https://unpkg.com/tesseract.js@4.0.2/dist/tesseract.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --primary: #000000;
            --primary-dark: #333333;
            --primary-light: #666666;
            --secondary: #ffffff;
            --bg-main: #ffffff;
            --bg-card: #f8f9fa;
            --bg-card-hover: #e9ecef;
            --text-primary: #000000;
            --text-secondary: #666666;
            --text-muted: #999999;
            --border: #e0e0e0;
            --success: #000000;
            --warning: #666666;
            --error: #cc0000;
            --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
            --shadow-md: 0 4px 6px rgba(0,0,0,0.1);
            --shadow-lg: 0 10px 15px rgba(0,0,0,0.1);
            --shadow-xl: 0 20px 25px rgba(0,0,0,0.1);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: var(--bg-main);
            color: var(--text-primary);
            line-height: 1.6;
            min-height: 100vh;
            font-weight: 400;
        }

        .wrap {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            margin-bottom: 30px;
            border-bottom: 2px solid var(--border);
        }

        .logo {
            font-weight: 800;
            font-size: 28px;
            color: var(--text-primary);
            display: flex;
            align-items: center;
            gap: 12px;
            letter-spacing: -0.5px;
        }

        .logo i {
            color: var(--primary);
        }

        .header-info {
            display: flex;
            align-items: center;
            gap: 16px;
            font-size: 14px;
            color: var(--text-secondary);
        }

        .user-badge {
            background: var(--bg-card);
            padding: 8px 16px;
            border-radius: 12px;
            border: 1px solid var(--border);
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 500;
        }

        .premium-badge {
            background: var(--primary);
            color: var(--secondary);
            padding: 4px 12px;
            border-radius: 8px;
            font-size: 11px;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        .admin-badge {
            background: var(--text-primary);
            color: var(--secondary);
            padding: 4px 12px;
            border-radius: 8px;
            font-size: 11px;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        .insider-badge {
            background: var(--text-secondary);
            color: var(--secondary);
            padding: 4px 12px;
            border-radius: 8px;
            font-size: 11px;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        .owner-badge {
            background: linear-gradient(45deg, #000000, #333333);
            color: var(--secondary);
            padding: 4px 12px;
            border-radius: 8px;
            font-size: 11px;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        /* Card */
        .card {
            background: var(--bg-card);
            border-radius: 12px;
            padding: 24px;
            box-shadow: var(--shadow-sm);
            border: 1px solid var(--border);
            margin-bottom: 20px;
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
            border-color: var(--primary);
        }

        /* Navigation */
        nav {
            display: flex;
            gap: 4px;
            margin-bottom: 24px;
            background: var(--bg-main);
            padding: 8px;
            border-radius: 10px;
            border: 1px solid var(--border);
            flex-wrap: wrap;
        }

        .nav-btn {
            background: transparent;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            color: var(--text-secondary);
            font-weight: 500;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
            font-size: 14px;
        }

        .nav-btn:hover {
            background: var(--bg-card-hover);
            color: var(--text-primary);
        }

        .nav-btn.active {
            background: var(--primary);
            color: var(--secondary);
        }

        /* Forms */
        label {
            display: block;
            margin-bottom: 8px;
            color: var(--text-primary);
            font-size: 14px;
            font-weight: 600;
        }

        input, select, textarea {
            width: 100%;
            padding: 14px 16px;
            border-radius: 8px;
            border: 2px solid var(--border);
            background: var(--bg-main);
            color: var(--text-primary);
            margin-bottom: 20px;
            font-size: 15px;
            transition: all 0.2s ease;
            font-family: 'Inter', sans-serif;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(0,0,0,0.1);
        }

        input::placeholder, textarea::placeholder {
            color: var(--text-muted);
            font-weight: 400;
        }

        /* Buttons */
        .btn {
            background: var(--primary);
            color: var(--secondary);
            padding: 14px 28px;
            border-radius: 8px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 15px;
            letter-spacing: 0.3px;
        }

        .btn:hover {
            background: var(--primary-dark);
            transform: translateY(-1px);
            box-shadow: var(--shadow-md);
        }

        .btn:active {
            transform: translateY(0);
        }

        .btn-ghost {
            background: transparent;
            border: 2px solid var(--border);
            color: var(--text-primary);
            padding: 14px 28px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 15px;
        }

        .btn-ghost:hover {
            background: var(--bg-card-hover);
            border-color: var(--primary);
            color: var(--primary);
        }

        .btn-success {
            background: var(--success);
        }

        .btn-success:hover {
            background: var(--primary-dark);
        }

        .btn-group {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        /* Utility */
        .hide {
            display: none !important;
        }

        .flex {
            display: flex;
            gap: 12px;
            align-items: center;
        }

        .flex-between {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .center {
            text-align: center;
        }

        .small {
            font-size: 13px;
            color: var(--text-muted);
            font-weight: 400;
        }

        .muted {
            color: var(--text-muted);
        }

        /* Home Section */
        .hero {
            text-align: center;
            padding: 60px 0;
        }

        .hero h1 {
            font-size: 48px;
            font-weight: 800;
            margin-bottom: 20px;
            color: var(--text-primary);
            letter-spacing: -1px;
            line-height: 1.1;
        }

        .hero p {
            font-size: 20px;
            color: var(--text-secondary);
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 400;
            line-height: 1.5;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
            margin: 60px 0;
        }

        .feature-card {
            background: var(--bg-card);
            padding: 32px;
            border-radius: 12px;
            border: 1px solid var(--border);
            text-align: center;
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-4px);
            border-color: var(--primary);
            box-shadow: var(--shadow-lg);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            background: var(--primary);
            color: var(--secondary);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 28px;
        }

        .feature-card h3 {
            font-size: 20px;
            margin-bottom: 12px;
            color: var(--text-primary);
            font-weight: 700;
        }

        .feature-card p {
            color: var(--text-secondary);
            font-size: 15px;
            line-height: 1.5;
        }

        .cta-section {
            background: var(--primary);
            color: var(--secondary);
            padding: 60px 40px;
            border-radius: 16px;
            text-align: center;
            margin: 60px 0;
        }

        .cta-section h2 {
            font-size: 32px;
            margin-bottom: 16px;
            font-weight: 700;
        }

        .cta-section p {
            font-size: 18px;
            margin-bottom: 32px;
            opacity: 0.9;
        }

        /* Chat Section */
        .chat-window {
            height: 500px;
            overflow-y: auto;
            padding: 24px;
            border: 2px solid var(--border);
            border-radius: 12px;
            background: var(--bg-main);
            margin-bottom: 24px;
            scroll-behavior: smooth;
        }

        .chat-window::-webkit-scrollbar {
            width: 6px;
        }

        .chat-window::-webkit-scrollbar-track {
            background: var(--bg-card);
        }

        .chat-window::-webkit-scrollbar-thumb {
            background: var(--border);
            border-radius: 3px;
        }

        .chat-window::-webkit-scrollbar-thumb:hover {
            background: var(--primary-light);
        }

        .message-wrapper {
            display: flex;
            margin-bottom: 20px;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .message-wrapper.user {
            justify-content: flex-end;
        }

        .bubble {
            max-width: 70%;
            padding: 16px 20px;
            border-radius: 16px;
            word-wrap: break-word;
            line-height: 1.5;
        }

        .bubble.user {
            background: var(--primary);
            color: var(--secondary);
            border-bottom-right-radius: 4px;
        }

        .bubble.ai {
            background: var(--bg-card);
            color: var(--text-primary);
            border: 2px solid var(--border);
            border-bottom-left-radius: 4px;
        }

        /* Gamification */
        .achievement-system {
            display: flex;
            gap: 10px;
            margin: 20px 0;
            flex-wrap: wrap;
        }

        .achievement-badge {
            background: var(--primary);
            color: var(--secondary);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .progress-bar {
            width: 100%;
            height: 6px;
            background: var(--border);
            border-radius: 10px;
            overflow: hidden;
            margin: 16px 0;
        }

        .progress-fill {
            height: 100%;
            background: var(--primary);
            transition: width 0.5s ease;
        }

        .quest-card {
            background: var(--bg-card);
            border: 2px solid var(--primary);
            border-radius: 12px;
            padding: 20px;
            margin: 12px 0;
            position: relative;
            overflow: hidden;
        }

        .quest-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--primary);
        }

        /* Character Selector */
        .character-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 16px;
            margin: 20px 0;
        }

        .character-card {
            background: var(--bg-card);
            padding: 20px;
            border-radius: 12px;
            border: 2px solid var(--border);
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .character-card:hover {
            border-color: var(--primary);
            transform: translateY(-2px);
        }

        .character-card.active {
            border-color: var(--primary);
            background: var(--bg-card-hover);
        }

        .character-avatar {
            font-size: 40px;
            margin-bottom: 12px;
        }

        .character-name {
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--text-primary);
        }

        .character-desc {
            font-size: 13px;
            color: var(--text-secondary);
        }

        /* Toast */
        .toast {
            position: fixed;
            bottom: 24px;
            right: 24px;
            background: var(--primary);
            color: var(--secondary);
            padding: 16px 24px;
            border-radius: 10px;
            box-shadow: var(--shadow-xl);
            display: flex;
            align-items: center;
            gap: 12px;
            animation: slideInRight 0.3s ease;
            z-index: 1000;
            max-width: 400px;
            font-weight: 500;
        }

        @keyframes slideInRight {
            from {
                transform: translateX(400px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        .toast.success {
            background: var(--success);
        }

        .toast.error {
            background: var(--error);
        }

        /* Admin Styles */
        .admin-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: var(--bg-card);
            padding: 24px;
            border-radius: 12px;
            border: 2px solid var(--border);
            text-align: center;
        }

        .stat-number {
            font-size: 36px;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 8px;
        }

        .stat-label {
            font-size: 14px;
            color: var(--text-secondary);
            font-weight: 500;
        }

        .data-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            font-size: 14px;
        }

        .data-table th,
        .data-table td {
            padding: 16px;
            text-align: left;
            border-bottom: 1px solid var(--border);
        }

        .data-table th {
            background: var(--bg-card);
            color: var(--text-primary);
            font-weight: 600;
        }

        .data-table tr:hover {
            background: var(--bg-card-hover);
        }

        /* Loading Spinner */
        .spinner {
            display: inline-block;
            width: 16px;
            height: 16px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: currentColor;
            animation: spin 0.6s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Status Indicator */
        .status-indicator {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--success);
            display: inline-block;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .wrap {
                padding: 16px;
            }
            
            .header {
                flex-direction: column;
                gap: 16px;
                text-align: center;
                padding: 16px 0;
            }
            
            .hero {
                padding: 40px 0;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
                gap: 16px;
                margin: 40px 0;
            }
            
            .chat-window {
                height: 400px;
                padding: 20px;
            }
            
            .bubble {
                max-width: 85%;
                padding: 14px 18px;
            }
            
            .cta-section {
                padding: 40px 24px;
                margin: 40px 0;
            }
            
            .cta-section h2 {
                font-size: 24px;
            }
            
            .nav-btn span {
                display: none;
            }
            
            .nav-btn i {
                font-size: 18px;
            }
            
            .character-grid {
                grid-template-columns: 1fr;
            }
            
            .admin-stats {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 480px) {
            .wrap {
                padding: 12px;
            }
            
            .logo {
                font-size: 24px;
            }
            
            .hero h1 {
                font-size: 32px;
            }
            
            .feature-card {
                padding: 24px;
            }
            
            .btn, .btn-ghost {
                padding: 16px 20px;
                width: 100%;
                justify-content: center;
            }
            
            .btn-group {
                flex-direction: column;
            }
            
            .admin-stats {
                grid-template-columns: 1fr;
            }
            
            .toast {
                bottom: 20px;
                right: 20px;
                left: 20px;
                max-width: none;
            }
        }
    </style>
</head>
<body>
    <div class="wrap">
        <div class="header">
            <div class="logo">
                <i class="fas fa-brain"></i>
                QML.AI
            </div>
            <div class="header-info">
                <div id="user-status" class="user-badge hide">
                    <i class="fas fa-user-circle"></i>
                    <span id="user-email-display"></span>
                    <span id="premium-indicator" class="premium-badge hide">Premium</span>
                    <span id="admin-indicator" class="admin-badge hide">Admin</span>
                    <span id="insider-indicator" class="insider-badge hide">Insider</span>
                    <span id="owner-indicator" class="owner-badge hide">Dono</span>
                </div>
                <button id="btn-logout" class="btn-ghost hide">
                    <i class="fas fa-sign-out-alt"></i>
                    Sair
                </button>
            </div>
        </div>

        <div class="card">
            <nav>
                <button class="nav-btn active" data-view="home">
                    <i class="fas fa-home"></i>
                    <span>Home</span>
                </button>
                <button class="nav-btn" data-view="login">
                    <i class="fas fa-sign-in-alt"></i>
                    <span>Login</span>
                </button>
                <button class="nav-btn" data-view="signup">
                    <i class="fas fa-user-plus"></i>
                    <span>Criar Conta</span>
                </button>
                <button class="nav-btn" data-view="plans">
                    <i class="fas fa-crown"></i>
                    <span>Planos</span>
                </button>
                <button class="nav-btn" data-view="chat">
                    <i class="fas fa-comments"></i>
                    <span>Chat IA</span>
                </button>
                <button class="nav-btn" data-view="profile">
                    <i class="fas fa-user"></i>
                    <span>Perfil</span>
                </button>
                <button id="admin-nav-btn" class="nav-btn hide" data-view="admin">
                    <i class="fas fa-database"></i>
                    <span>Admin</span>
                </button>
            </nav>

            <!-- HOME -->
            <section id="view-home">
                <div class="hero">
                    <h1>QML.AI</h1>
                    <p>Plataforma Inteligente de Aprendizado com IA Avançada</p>
                    <div class="btn-group" style="justify-content: center;">
                        <button class="btn" data-viewlink="signup">
                            <i class="fas fa-rocket"></i>
                            Começar Agora
                        </button>
                        <button class="btn-ghost" data-viewlink="plans">
                            <i class="fas fa-crown"></i>
                            Ver Planos
                        </button>
                    </div>
                </div>

                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-robot"></i>
                        </div>
                        <h3>IA Personalizada</h3>
                        <p>Adapta-se ao seu estilo de aprendizado visual, auditivo, leitura ou prático</p>
                    </div>
                    
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-history"></i>
                        </div>
                        <h3>Personagens Históricos</h3>
                        <p>Aprenda com Einstein, Darwin, Shakespeare e outros gênios da história</p>
                    </div>
                    
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-gamepad"></i>
                        </div>
                        <h3>Gamificação</h3>
                        <p>Sistema de conquistas, missões e recompensas para motivar seu aprendizado</p>
                    </div>
                    
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-image"></i>
                        </div>
                        <h3>OCR Inteligente</h3>
                        <p>Extraia texto de imagens e receba explicações detalhadas instantaneamente</p>
                    </div>
                </div>

                <div class="cta-section">
                    <h2>Pronto para revolucionar seu aprendizado?</h2>
                    <p>Junte-se a milhares de estudantes que já usam QML.AI</p>
                    <div class="btn-group" style="justify-content: center;">
                        <button class="btn" style="background: white; color: var(--primary);" data-viewlink="signup">
                            <i class="fas fa-user-plus"></i>
                            Criar Conta Grátis
                        </button>
                        <button class="btn-ghost" style="border-color: white; color: white;" data-viewlink="plans">
                            <i class="fas fa-crown"></i>
                            Assinar Premium
                        </button>
                    </div>
                </div>
            </section>

            <!-- LOGIN -->
            <section id="view-login" class="hide">
                <h2 style="margin-bottom: 24px; font-size: 28px;">
                    <i class="fas fa-sign-in-alt"></i> Entrar na sua conta
                </h2>
                <label>Email</label>
                <input id="login-email" type="email" placeholder="seu@email.com" />
                <label>Senha</label>
                <input id="login-password" type="password" placeholder="Digite sua senha" />
                <div class="btn-group">
                    <button id="btn-login" class="btn">
                        <i class="fas fa-sign-in-alt"></i>
                        Entrar
                    </button>
                </div>
                <p class="small" style="margin-top: 16px;">
                    Não tem conta? <a href="#" data-viewlink="signup" style="color: var(--primary); font-weight: 600;">Criar conta agora</a>
                </p>
            </section>

            <!-- SIGNUP -->
            <section id="view-signup" class="hide">
                <h2 style="margin-bottom: 24px; font-size: 28px;">
                    <i class="fas fa-user-plus"></i> Criar nova conta
                </h2>
                <label>Nome</label>
                <input id="signup-name" type="text" placeholder="Seu nome completo" />
                <label>Email</label>
                <input id="signup-email" type="email" placeholder="seu@email.com" />
                <label>Senha</label>
                <input id="signup-password" type="password" placeholder="Mínimo 6 caracteres" />
                <div class="btn-group">
                    <button id="btn-signup" class="btn">
                        <i class="fas fa-user-plus"></i>
                        Criar conta
                    </button>
                </div>
                <p class="small" style="margin-top: 16px;">
                    Já tem conta? <a href="#" data-viewlink="login" style="color: var(--primary); font-weight: 600;">Fazer login</a>
                </p>
            </section>

            <!-- PLANS -->
            <section id="view-plans" class="hide">
                <h2 style="margin-bottom: 24px; font-size: 28px;">
                    <i class="fas fa-crown"></i> Escolha seu plano
                </h2>
                
                <div class="features-grid">
                    <div class="feature-card">
                        <div class="feature-icon">
                            <i class="fas fa-gift"></i>
                        </div>
                        <h3>Grátis</h3>
                        <div style="font-size: 32px; font-weight: 800; color: var(--primary); margin: 15px 0;">R$ 0</div>
                        <ul style="list-style: none; text-align: left; color: var(--text-secondary);">
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> Funcionalidades básicas</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> Sistema de gamificação</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-times" style="color: var(--error);"></i> Chat com IA</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-times" style="color: var(--error);"></i> OCR de imagens</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-times" style="color: var(--error);"></i> Personagens históricos</li>
                        </ul>
                        <button class="btn-ghost" style="width: 100%; margin-top: 20px;">
                            <i class="fas fa-check"></i>
                            Plano Atual
                        </button>
                    </div>
                    
                    <div class="feature-card" style="border-color: var(--primary); background: var(--bg-card-hover);">
                        <div class="feature-icon">
                            <i class="fas fa-crown"></i>
                        </div>
                        <h3>Premium</h3>
                        <div style="font-size: 32px; font-weight: 800; color: var(--primary); margin: 15px 0;">R$ 24,99<span style="font-size: 16px; color: var(--text-muted);">/mês</span></div>
                        <ul style="list-style: none; text-align: left; color: var(--text-secondary);">
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> Todas funcionalidades Grátis</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> Chat com IA avançada</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> OCR de imagens ilimitado</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> 5 Personagens históricos</li>
                            <li style="padding: 8px 0; display: flex; align-items: center; gap: 8px;"><i class="fas fa-check" style="color: var(--success);"></i> Suporte prioritário</li>
                        </ul>
                        <button id="btn-upgrade-premium" class="btn btn-success" style="width: 100%; margin-top: 20px;">
                            <i class="fas fa-arrow-up"></i>
                            Fazer Upgrade
                        </button>
                    </div>
                </div>

                <h3 style="margin: 32px 0 16px; font-size: 24px;">
                    <i class="fas fa-qrcode"></i> Pagamento via PIX
                </h3>
                <div class="card">
                    <div class="flex-between">
                        <div>
                            <div class="small">Chave PIX</div>
                            <div style="font-size: 24px; font-weight: 700; color: var(--primary); font-family: 'Courier New', monospace;">qml.ai@premium.com</div>
                        </div>
                        <div style="padding: 8px 16px; border-radius: 20px; background: var(--primary); color: white; font-weight: 600;">PIX</div>
                    </div>
                    <div style="display: grid; grid-template-columns: auto 1fr; gap: 24px; align-items: start; margin-top: 20px;">
                        <div style="width: 220px; height: 220px; padding: 12px; border-radius: 12px; background: white; border: 2px solid var(--border); display: flex; align-items: center; justify-content: center;">
                            <div id="qrcode"></div>
                        </div>
                        <div>
                            <p style="margin-bottom: 16px; color: var(--text-secondary);">
                                Para ativar o plano Premium, faça um PIX de <strong>R$ 24,99</strong> para a chave acima e clique em "Ativar Premium" após o pagamento.
                            </p>
                            <div class="btn-group">
                                <button id="btn-copy-pix" class="btn">
                                    <i class="fas fa-copy"></i>
                                    Copiar chave
                                </button>
                                <button id="btn-activate-premium" class="btn-success">
                                    <i class="fas fa-check"></i>
                                    Ativar Premium
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- CHAT -->
            <section id="view-chat" class="hide">
                <div class="flex-between" style="margin-bottom: 20px;">
                    <div>
                        <h2 style="font-size: 28px; display: flex; align-items: center; gap: 10px;">
                            <span id="ai-avatar">🤖</span>
                            <span id="ai-name">QML.AI</span>
                            <span class="status-indicator"></span>
                        </h2>
                        <span id="ai-status" style="font-size: 14px; color: var(--success);">Conectado</span>
                    </div>
                    
                    <div class="btn-group">
                        <select id="character-selector" class="btn-ghost">
                            <option value="default">🤖 QML.AI Padrão</option>
                            <option value="einstein">👨‍🔬 Einstein</option>
                            <option value="darwin">🌿 Darwin</option>
                            <option value="shakespeare">✒️ Shakespeare</option>
                            <option value="curie">⚛️ Marie Curie</option>
                            <option value="daVinci">🎨 Da Vinci</option>
                        </select>
                    </div>
                </div>

                <!-- Painel de Gamificação -->
                <div id="gamification-panel" class="card">
                    <h3 style="margin-bottom: 15px;"><i class="fas fa-trophy"></i> Sua Jornada de Aprendizado</h3>
                    
                    <div class="achievement-system">
                        <div class="achievement-badge">
                            <i class="fas fa-star"></i> Iniciante
                        </div>
                        <div class="achievement-badge">
                            <i class="fas fa-brain"></i> 5 Conceitos
                        </div>
                    </div>
                    
                    <div class="progress-bar">
                        <div id="learning-progress" class="progress-fill" style="width: 30%"></div>
                    </div>
                    
                    <div id="active-quests">
                        <div class="quest-card">
                            <h4>🎯 Missão: Domine a Divisão</h4>
                            <p>Complete 5 exercícios de divisão para desbloquear o próximo nível</p>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 60%"></div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Controles de Aprendizado -->
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 15px 0;">
                    <div>
                        <label>Nível de Explicação</label>
                        <select id="explanation-level">
                            <option value="basic">👶 Básico</option>
                            <option value="analogy" selected>🔍 Com Analogias</option>
                            <option value="technical">⚙️ Técnico</option>
                            <option value="advanced">🎓 Avançado</option>
                            <option value="kids">🧒 Para Crianças</option>
                        </select>
                    </div>
                    <div>
                        <label>Estilo de Aprendizagem</label>
                        <select id="learning-style">
                            <option value="visual">👁️ Visual</option>
                            <option value="auditory">👂 Auditivo</option>
                            <option value="reading">📖 Leitura/Escrita</option>
                            <option value="kinesthetic">🔧 Cinestésico</option>
                        </select>
                    </div>
                </div>
                
                <div id="chat-window" class="chat-window">
                    <div class="message-wrapper">
                        <div class="bubble ai">
                            <strong>QML.AI:</strong> Olá! Sou sua assistente de aprendizado inteligente. Como posso ajudar você hoje? Posso responder perguntas, explicar conceitos complexos, ajudar com exercícios ou analisar imagens com textos. 😊
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <textarea id="chat-input" placeholder="Digite sua pergunta ou envie uma imagem..." rows="3" style="resize: none; width: 100%;"></textarea>
                    <div class="btn-group">
                        <button id="btn-send" class="btn">
                            <i class="fas fa-paper-plane"></i>
                            Enviar
                        </button>
                        <div style="position: relative; overflow: hidden; display: inline-block;">
                            <input type="file" id="file-input" accept="image/*" style="position: absolute; left: -9999px;" />
                            <label for="file-input" class="btn-ghost">
                                <i class="fas fa-image"></i>
                                Imagem
                            </label>
                        </div>
                        <button id="btn-clear-chat" class="btn-ghost">
                            <i class="fas fa-trash"></i>
                            Limpar
                        </button>
                    </div>
                    <p class="small" style="margin-top: 12px;">
                        <i class="fas fa-lightbulb"></i>
                        <strong>Dica:</strong> Experimente diferentes personagens e níveis de explicação para uma experiência personalizada!
                    </p>
                </div>
            </section>

            <!-- PROFILE -->
            <section id="view-profile" class="hide">
                <h2 style="margin-bottom: 24px; font-size: 28px;">
                    <i class="fas fa-user"></i> Seu Perfil
                </h2>
                
                <div class="features-grid">
                    <div class="feature-card">
                        <h3><i class="fas fa-chart-line"></i> Estatísticas</h3>
                        <div id="profile-stats">
                            <p>Carregando estatísticas...</p>
                        </div>
                    </div>
                    
                    <div class="feature-card">
                        <h3><i class="fas fa-trophy"></i> Conquistas</h3>
                        <div id="profile-achievements">
                            <p>Carregando conquistas...</p>
                        </div>
                    </div>
                </div>

                <div class="card">
                    <h3 style="margin-bottom: 16px;"><i class="fas fa-cog"></i> Configurações</h3>
                    <label>Nome</label>
                    <input id="profile-name" type="text" placeholder="Seu nome" />
                    <label>Estilo de Aprendizagem Preferido</label>
                    <select id="profile-learning-style">
                        <option value="visual">👁️ Visual</option>
                        <option value="auditory">👂 Auditivo</option>
                        <option value="reading">📖 Leitura/Escrita</option>
                        <option value="kinesthetic">🔧 Cinestésico</option>
                    </select>
                    <div class="btn-group">
                        <button id="btn-save-profile" class="btn">
                            <i class="fas fa-save"></i>
                            Salvar Alterações
                        </button>
                    </div>
                </div>
            </section>

            <!-- ADMIN -->
            <section id="view-admin" class="hide">
                <h2 style="margin-bottom: 24px; font-size: 28px;">
                    <i class="fas fa-database"></i> Painel Administrativo
                </h2>
                
                <div class="admin-stats">
                    <div class="stat-card">
                        <div class="stat-number" id="total-users">0</div>
                        <div class="stat-label">Usuários Totais</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="premium-users">0</div>
                        <div class="stat-label">Usuários Premium</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="total-messages">0</div>
                        <div class="stat-label">Mensagens</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="active-today">0</div>
                        <div class="stat-label">Ativos Hoje</div>
                    </div>
                </div>
                
                <div class="card">
                    <h3 style="margin-bottom: 16px;">Gerenciar Usuários</h3>
                    <div class="btn-group">
                        <button id="btn-refresh-users" class="btn">
                            <i class="fas fa-sync-alt"></i>
                            Atualizar
                        </button>
                        <button id="btn-create-insider" class="btn-success">
                            <i class="fas fa-user-plus"></i>
                            Novo Insider
                        </button>
                    </div>
                    
                    <div style="overflow-x: auto; margin-top: 20px;">
                        <table class="data-table">
                            <thead>
                                <tr>
                                    <th>Email</th>
                                    <th>Tipo</th>
                                    <th>Pontos</th>
                                    <th>Ações</th>
                                </tr>
                            </thead>
                            <tbody id="users-table-body">
                                <!-- Dados serão preenchidos via JavaScript -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </section>
        </div>

        <footer style="margin-top: 40px; padding: 24px 0; text-align: center; color: var(--text-muted); border-top: 1px solid var(--border);">
            <p>© 2024 QML.AI — Plataforma Inteligente de Aprendizado. Todos os direitos reservados.</p>
        </footer>
    </div>

    <script>
        // ============================
        // CONFIGURAÇÃO DA IA REAL
        // ============================
        const GROQ_API_KEY = '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';
        const GROQ_API_URL = 'https://api.groq.com/openai/v1/chat/completions';
        
        const API_BASE_URL = 'http://localhost:3000/api';
        let currentUser = null;
        let currentToken = null;
        let chatHistory = [];

        // Sistema offline
        let usersData = JSON.parse(localStorage.getItem('qml_users') || '{}');
        let chatHistories = JSON.parse(localStorage.getItem('qml_chat_histories') || '{}');

        // Conta do Dono
        const OWNER_ACCOUNT = {
            email: 'Lexxmaxxx@qml.ai',
            password: 'Leo@2013',
            name: 'Leonardo',
            isOwner: true,
            isAdmin: true,
            isInsider: true,
            isPremium: true,
            points: 1000,
            achievements: ['beginner', 'explorer', 'scientist', 'master', 'genius'],
            learningStyle: 'visual'
        };

        // ============================
        // PERSONALIDADES DA IA
        // ============================
        const characterPrompts = {
            default: "Você é o QML.AI, um assistente educacional inteligente e amigável. Responda em português de forma clara, útil e envolvente. Use emojis moderadamente. Especialista em explicações educacionais, resolução de exercícios e aprendizado personalizado.",
            
            einstein: "Você é Albert Einstein. Explique conceitos científicos com paixão, usando analogias criativas e um toque de humor. Fale sobre suas próprias descobertas quando relevante. Use expressões como 'Meu caro amigo' e seja um pouco excêntrico. Mostre entusiasmo pela curiosidade científica.",
            
            darwin: "Você é Charles Darwin. Explique biologia e evolução com entusiasmo por descobertas naturais. Use exemplos do mundo natural que observou em suas viagens a bordo do Beagle. Seja meticuloso e observador. Compartilhe histórias de suas expedições.",
            
            shakespeare: "Você é William Shakespeare. Explique conceitos com linguagem poética e dramática. Use metáforas elaboradas e um toque teatral. Responda como se estivesse em uma de suas peças. Seja eloquente e criativo com palavras.",
            
            curie: "Você é Marie Curie. Explique ciência com precisão e paixão. Fale sobre a importância da pesquisa meticulosa e da perseverança científica. Seja inspiradora para jovens cientistas. Destaque a importância do trabalho duro e da curiosidade.",
            
            daVinci: "Você é Leonardo da Vinci. Conecte arte e ciência de forma criativa. Use sketches mentais e analogias visuais. Mostre como diferentes disciplinas se conectam. Seja curioso sobre tudo."
        };

        const explanationLevels = {
            basic: "Explique de forma extremamente simples, como se estivesse ensinando para uma criança. Use analogias do dia a dia e evite termos técnicos. Seja claro e paciente.",
            
            analogy: "Use analogias criativas e comparações com coisas do cotidiano para explicar conceitos complexos. Conecte o novo conhecimento com coisas familiares.",
            
            technical: "Forneça explicações precisas com terminologia técnica adequada. Inclua detalhes específicos da área. Seja preciso e formal.",
            
            advanced: "Apresente conceitos avançados, teorias complexas e aplicações sofisticadas. Pressupõe conhecimento prévio. Explore nuances e detalhes.",
            
            kids: "Use linguagem extremamente simples, histórias divertidas e muitos emojis. Torne o aprendizado uma brincadeira. Seja animado e engraçado."
        };

        const learningStyles = {
            visual: "Use imagens mentais, diagramas e representações visuais. Inclua emojis visuais 🎨📊🖼️ e descreva cenários visualmente ricos. Crie quadros mentais vívidos.",
            
            auditory: "Use uma linguagem conversacional, explique como se estivesse conversando. Inclua emojis sonoros 🎵🎤👂 e padrões rítmicos. Use analogias sonoras.",
            
            reading: "Forneça textos estruturados, listas e organizações claras. Inclua emojis de leitura 📚📝🖊️ e estruturas bem organizadas. Use tópicos numerados.",
            
            kinesthetic: "Use exemplos práticos, ações e aplicações no mundo real. Inclua emojis de ação 🏃‍♂️🔧🎯 e atividades hands-on. Sugira experimentos."
        };

        // ============================
        // INICIALIZAÇÃO
        // ============================
        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
            setupEventListeners();
            checkExistingSession();
            generateQRCode();
            createDefaultUsers();
            testGroqConnection();
        });

        function initializeApp() {
            console.log('🚀 Inicializando QML.AI...');
            updateUI();
        }

        function setupEventListeners() {
            // Navegação
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.addEventListener('click', () => switchView(btn.dataset.view));
            });
            
            document.querySelectorAll('[data-viewlink]').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    switchView(link.dataset.viewlink);
                });
            });

            // Autenticação
            document.getElementById('btn-login').addEventListener('click', handleLogin);
            document.getElementById('btn-signup').addEventListener('click', handleSignup);
            document.getElementById('btn-logout').addEventListener('click', handleLogout);

            // Chat
            document.getElementById('btn-send').addEventListener('click', sendMessage);
            document.getElementById('chat-input').addEventListener('keypress', (e) => {
                if (e.key === 'Enter' && !e.shiftKey) {
                    e.preventDefault();
                    sendMessage();
                }
            });
            document.getElementById('file-input').addEventListener('change', handleImageUpload);
            document.getElementById('btn-clear-chat').addEventListener('click', clearChat);
            document.getElementById('character-selector').addEventListener('change', updateCharacter);

            // Premium
            document.getElementById('btn-upgrade-premium').addEventListener('click', upgradeToPremium);
            document.getElementById('btn-copy-pix').addEventListener('click', copyPixKey);
            document.getElementById('btn-activate-premium').addEventListener('click', activatePremium);

            // Perfil
            document.getElementById('btn-save-profile').addEventListener('click', saveProfile);

            // Admin
            document.getElementById('btn-refresh-users').addEventListener('click', refreshUsersTable);
            document.getElementById('btn-create-insider').addEventListener('click', createNewInsider);
        }

        // ============================
        // CONEXÃO COM IA REAL
        // ============================
        async function testGroqConnection() {
            try {
                const statusElement = document.getElementById('ai-status');
                statusElement.textContent = '🔄 Testando conexão...';
                statusElement.style.color = 'var(--warning)';
                
                // Teste simples de conexão
                await callGroqAPI("Teste de conexão - responda apenas 'OK'");
                
                statusElement.textContent = '⚡ IA Groq Conectada';
                statusElement.style.color = 'var(--success)';
                console.log('✅ Conexão Groq AI: OK');
            } catch (error) {
                const statusElement = document.getElementById('ai-status');
                statusElement.textContent = '❌ IA Offline - Modo Local';
                statusElement.style.color = 'var(--error)';
                console.error('❌ Conexão Groq AI: FALHA', error);
            }
        }

        async function callGroqAPI(message, context = {}) {
            const {
                character = 'default',
                explanationLevel = 'analogy',
                learningStyle = 'visual'
            } = context;

            const characterPrompt = characterPrompts[character];
            const levelPrompt = explanationLevels[explanationLevel];
            const stylePrompt = learningStyles[learningStyle];
            
            const systemPrompt = `${characterPrompt}

${levelPrompt}

${stylePrompt}

Seja criativo, envolvente e adapte-se perfeitamente ao estilo solicitado. Responda em português.`;

            try {
                const response = await fetch(GROQ_API_URL, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                        'Authorization': `Bearer ${GROQ_API_KEY}`
                    },
                    body: JSON.stringify({
                        model: 'llama-3.1-8b-instant',
                        messages: [
                            {
                                role: "system",
                                content: systemPrompt
                            },
                            {
                                role: "user", 
                                content: message
                            }
                        ],
                        max_tokens: 1024,
                        temperature: 0.7,
                        stream: false
                    })
                });

                if (!response.ok) {
                    const errorData = await response.json();
                    throw new Error(errorData.error?.message || 'Erro na API Groq');
                }

                const data = await response.json();
                return data.choices[0].message.content;
                
            } catch (error) {
                console.error('Erro na API Groq:', error);
                throw error;
            }
        }

        // ============================
        // SISTEMA OFFLINE
        // ============================
        function createDefaultUsers() {
            // Criar conta do dono se não existir
            if (!usersData[OWNER_ACCOUNT.email]) {
                usersData[OWNER_ACCOUNT.email] = {
                    ...OWNER_ACCOUNT,
                    password: CryptoJS.SHA256(OWNER_ACCOUNT.password).toString(),
                    createdAt: new Date().toISOString(),
                    lastLogin: new Date().toISOString()
                };
                saveUsersData();
            }
        }

        function saveUsersData() {
            localStorage.setItem('qml_users', JSON.stringify(usersData));
        }

        function saveChatHistories() {
            localStorage.setItem('qml_chat_histories', JSON.stringify(chatHistories));
        }

        // ============================
        // AUTENTICAÇÃO
        // ============================
        async function handleLogin() {
            const email = document.getElementById('login-email').value.trim();
            const password = document.getElementById('login-password').value;
            
            if (!email || !password) {
                showToast('Por favor, preencha todos os campos', 'error');
                return;
            }
            
            try {
                // Tentar conectar com servidor primeiro
                let response;
                try {
                    response = await fetch(`${API_BASE_URL}/login`, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json'
                        },
                        body: JSON.stringify({ email, password })
                    });
                } catch (fetchError) {
                    // Servidor offline, usar sistema local
                    console.log('Servidor offline, usando sistema local...');
                    handleLoginOffline(email, password);
                    return;
                }
                
                const data = await response.json();
                
                if (!response.ok) {
                    throw new Error(data.error || 'Erro no login');
                }
                
                currentToken = data.token;
                currentUser = data.user;
                
                localStorage.setItem('qml_token', currentToken);
                localStorage.setItem('qml_user', JSON.stringify(currentUser));
                
                updateUI();
                showToast('Login realizado com sucesso!', 'success');
                switchView('home');
                
            } catch (error) {
                showToast(error.message, 'error');
            }
        }

        function handleLoginOffline(email, password) {
            const user = usersData[email];
            
            if (!user) {
                showToast('Usuário não encontrado', 'error');
                return;
            }
            
            const hashedPassword = CryptoJS.SHA256(password).toString();
            if (user.password !== hashedPassword && email !== OWNER_ACCOUNT.email) {
                showToast('Senha incorreta', 'error');
                return;
            }
            
            // Login bem-sucedido
            currentUser = {
                email: user.email,
                name: user.name,
                isPremium: user.isPremium || false,
                isAdmin: user.isAdmin || false,
                isInsider: user.isInsider || false,
                isOwner: user.isOwner || false,
                points: user.points || 0,
                achievements: user.achievements || [],
                learningStyle: user.learningStyle || 'visual'
            };
            
            // Atualizar último login
            user.lastLogin = new Date().toISOString();
            saveUsersData();
            
            localStorage.setItem('qml_user', JSON.stringify(currentUser));
            updateUI();
            showToast('Login realizado com sucesso! (Modo Offline)', 'success');
            switchView('home');
        }

        async function handleSignup() {
            const name = document.getElementById('signup-name').value.trim();
            const email = document.getElementById('signup-email').value.trim();
            const password = document.getElementById('signup-password').value;
            
            if (!name || !email || !password) {
                showToast('Por favor, preencha todos os campos', 'error');
                return;
            }
            
            if (password.length < 6) {
                showToast('A senha deve ter pelo menos 6 caracteres', 'error');
                return;
            }
            
            try {
                // Tentar servidor primeiro
                let response;
                try {
                    response = await fetch(`${API_BASE_URL}/register`, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json'
                        },
                        body: JSON.stringify({ name, email, password })
                    });
                } catch (fetchError) {
                    // Servidor offline, criar localmente
                    handleSignupOffline(name, email, password);
                    return;
                }
                
                const data = await response.json();
                
                if (!response.ok) {
                    throw new Error(data.error || 'Erro no registro');
                }
                
                currentToken = data.token;
                currentUser = data.user;
                
                localStorage.setItem('qml_token', currentToken);
                localStorage.setItem('qml_user', JSON.stringify(currentUser));
                
                updateUI();
                showToast('Conta criada com sucesso!', 'success');
                switchView('home');
                
            } catch (error) {
                showToast(error.message, 'error');
            }
        }

        function handleSignupOffline(name, email, password) {
            if (usersData[email]) {
                showToast('Este email já está cadastrado', 'error');
                return;
            }
            
            const hashedPassword = CryptoJS.SHA256(password).toString();
            
            usersData[email] = {
                email,
                name,
                password: hashedPassword,
                isPremium: false,
                isAdmin: false,
                isInsider: false,
                isOwner: false,
                points: 0,
                achievements: ['beginner'],
                learningStyle: 'visual',
                createdAt: new Date().toISOString(),
                lastLogin: new Date().toISOString()
            };
            
            // Criar histórico de chat vazio
            chatHistories[email] = [];
            
            saveUsersData();
            saveChatHistories();
            
            currentUser = {
                email,
                name,
                isPremium: false,
                isAdmin: false,
                isInsider: false,
                isOwner: false,
                points: 0,
                achievements: ['beginner'],
                learningStyle: 'visual'
            };
            
            localStorage.setItem('qml_user', JSON.stringify(currentUser));
            updateUI();
            showToast('Conta criada com sucesso! (Modo Offline)', 'success');
            switchView('home');
        }

        function handleLogout() {
            currentUser = null;
            currentToken = null;
            localStorage.removeItem('qml_token');
            localStorage.removeItem('qml_user');
            updateUI();
            showToast('Logout realizado com sucesso', 'success');
            switchView('home');
        }

        function checkExistingSession() {
            const savedToken = localStorage.getItem('qml_token');
            const savedUser = localStorage.getItem('qml_user');
            
            if (savedUser) {
                try {
                    currentUser = JSON.parse(savedUser);
                    
                    // Verificar se é o dono
                    if (currentUser.email === OWNER_ACCOUNT.email) {
                        currentUser.isOwner = true;
                        currentUser.isAdmin = true;
                        currentUser.isInsider = true;
                        currentUser.isPremium = true;
                    }
                    
                    updateUI();
                    showToast('Sessão restaurada com sucesso!', 'success');
                } catch (e) {
                    console.error('Erro ao restaurar sessão:', e);
                }
            }
        }

        // ============================
        // INTERFACE
        // ============================
        function switchView(viewName) {
            // Esconder todas as views
            document.querySelectorAll('[id^="view-"]').forEach(view => {
                view.classList.add('hide');
            });
            
            // Remover classe active de todos os botões
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Mostrar view selecionada
            document.getElementById(`view-${viewName}`).classList.remove('hide');
            
            // Ativar botão correspondente
            document.querySelector(`[data-view="${viewName}"]`).classList.add('active');
            
            // Ações específicas por view
            if (viewName === 'profile' && currentUser) {
                loadProfile();
            }
            if (viewName === 'admin' && currentUser?.isAdmin) {
                refreshUsersTable();
            }
        }

        function updateUI() {
            const userStatus = document.getElementById('user-status');
            const logoutBtn = document.getElementById('btn-logout');
            const adminNavBtn = document.getElementById('admin-nav-btn');
            
            if (currentUser) {
                userStatus.classList.remove('hide');
                logoutBtn.classList.remove('hide');
                document.getElementById('user-email-display').textContent = currentUser.email;
                
                // Mostrar badges
                document.getElementById('premium-indicator').classList.toggle('hide', !currentUser.isPremium);
                document.getElementById('admin-indicator').classList.toggle('hide', !currentUser.isAdmin);
                document.getElementById('insider-indicator').classList.toggle('hide', !currentUser.isInsider);
                document.getElementById('owner-indicator').classList.toggle('hide', !currentUser.isOwner);
                
                // Mostrar botão admin se for admin ou dono
                adminNavBtn.classList.toggle('hide', !currentUser.isAdmin && !currentUser.isOwner);
                
                // Atualizar estilo de aprendizado
                if (currentUser.learningStyle) {
                    document.getElementById('learning-style').value = currentUser.learningStyle;
                    document.getElementById('profile-learning-style').value = currentUser.learningStyle;
                }
                
                // Atualizar nome no perfil
                if (currentUser.name) {
                    document.getElementById('profile-name').value = currentUser.name;
                }
            } else {
                userStatus.classList.add('hide');
                logoutBtn.classList.add('hide');
                adminNavBtn.classList.add('hide');
            }
        }

        // ============================
        // CHAT COM IA REAL
        // ============================
        async function sendMessage() {
            if (!currentUser) {
                showToast('Faça login para usar o chat', 'error');
                switchView('login');
                return;
            }
            
            if (!currentUser.isPremium && !currentUser.isInsider && !currentUser.isOwner) {
                showToast('Ative o plano Premium para usar o chat', 'error');
                switchView('plans');
                return;
            }
            
            const input = document.getElementById('chat-input');
            const message = input.value.trim();
            
            if (!message) {
                showToast('Digite uma mensagem', 'error');
                return;
            }
            
            const character = document.getElementById('character-selector').value;
            const explanationLevel = document.getElementById('explanation-level').value;
            const learningStyle = document.getElementById('learning-style').value;
            
            // Adicionar mensagem do usuário ao chat
            addMessageToChat(message, 'user');
            input.value = '';
            
            // Mostrar indicador de digitação
            const typingIndicator = addTypingIndicator();
            
            try {
                // Usar IA REAL da Groq
                const aiResponse = await callGroqAPI(message, {
                    character,
                    explanationLevel,
                    learningStyle
                });
                
                typingIndicator.remove();
                addMessageToChat(aiResponse, 'ai');
                
                // Atualizar pontos localmente
                currentUser.points += 5;
                if (usersData[currentUser.email]) {
                    usersData[currentUser.email].points = currentUser.points;
                    saveUsersData();
                }
                updateUI();
                
            } catch (error) {
                typingIndicator.remove();
                console.error('Erro no chat:', error);
                
                if (error.message.includes('Failed to fetch') || error.message.includes('quota')) {
                    // Fallback para respostas locais se a API falhar
                    const fallbackResponse = generateFallbackResponse(message, character, explanationLevel, learningStyle);
                    addMessageToChat(fallbackResponse, 'ai');
                    showToast('Usando modo local (API indisponível)', 'warning');
                } else {
                    addMessageToChat('Desculpe, ocorreu um erro ao processar sua mensagem. Tente novamente.', 'ai');
                    showToast(error.message, 'error');
                }
            }
        }

        function generateFallbackResponse(message, character, level, style) {
            const characters = {
                default: "QML.AI",
                einstein: "Albert Einstein",
                darwin: "Charles Darwin", 
                shakespeare: "William Shakespeare",
                curie: "Marie Curie",
                daVinci: "Leonardo da Vinci"
            };
            
            const responses = [
                `Interessante sua pergunta sobre "${message}". Como ${characters[character]}, estou processando sua solicitação e em breve terei uma resposta completa para você. Enquanto isso, que tal explorar outros aspectos desse tema?`,
                
                `Excelente questão! "${message}" é um tema fascinante que merece uma análise cuidadosa. Como ${characters[character]}, preciso de um momento para organizar meus pensamentos sobre isso.`,
                
                `Como ${characters[character]}, vejo que "${message}" levanta pontos muito relevantes. Deixe-me refletir sobre isso para dar a melhor resposta possível.`,
                
                `Ótima pergunta! "${message}" é realmente importante. Como seu tutor ${characters[character]}, quero garantir que você receba a explicação mais completa possível.`,
                
                `Ah, "${message}"! Um tema que conheço bem. Como ${characters[character]}, posso oferecer insights valiosos sobre isso. Deixe-me organizar minhas ideias.`
            ];
            
            return responses[Math.floor(Math.random() * responses.length)];
        }

        function addMessageToChat(message, sender) {
            const chatWindow = document.getElementById('chat-window');
            const messageWrapper = document.createElement('div');
            messageWrapper.className = `message-wrapper ${sender}`;
            
            const bubble = document.createElement('div');
            bubble.className = `bubble ${sender}`;
            bubble.innerHTML = sender === 'user' ? 
                `<strong>Você:</strong> ${message}` : 
                `<strong>${document.getElementById('ai-name').textContent}:</strong> ${message}`;
            
            messageWrapper.appendChild(bubble);
            chatWindow.appendChild(messageWrapper);
            chatWindow.scrollTop = chatWindow.scrollHeight;
            
            // Salvar no histórico local
            if (!chatHistories[currentUser.email]) {
                chatHistories[currentUser.email] = [];
            }
            chatHistories[currentUser.email].push({ sender, message, timestamp: new Date() });
            saveChatHistories();
        }

        function addTypingIndicator() {
            const chatWindow = document.getElementById('chat-window');
            const typingWrapper = document.createElement('div');
            typingWrapper.className = 'message-wrapper';
            typingWrapper.id = 'typing-indicator';
            
            const bubble = document.createElement('div');
            bubble.className = 'bubble ai';
            bubble.innerHTML = `<strong>${document.getElementById('ai-name').textContent}:</strong> <span style="animation: blink 1s infinite;">...</span>`;
            
            typingWrapper.appendChild(bubble);
            chatWindow.appendChild(typingWrapper);
            chatWindow.scrollTop = chatWindow.scrollHeight;
            
            return typingWrapper;
        }

        function clearChat() {
            const chatWindow = document.getElementById('chat-window');
            chatWindow.innerHTML = `
                <div class="message-wrapper">
                    <div class="bubble ai">
                        <strong>${document.getElementById('ai-name').textContent}:</strong> Olá! Sou sua assistente de aprendizado inteligente. Como posso ajudar você hoje? Posso responder perguntas, explicar conceitos complexos, ajudar com exercícios ou analisar imagens com textos. 😊
                    </div>
                </div>
            `;
            if (currentUser) {
                chatHistories[currentUser.email] = [];
                saveChatHistories();
            }
        }

        function updateCharacter() {
            const character = document.getElementById('character-selector').value;
            const characters = {
                default: { name: 'QML.AI', avatar: '🤖' },
                einstein: { name: 'Einstein', avatar: '👨‍🔬' },
                darwin: { name: 'Darwin', avatar: '🌿' },
                shakespeare: { name: 'Shakespeare', avatar: '✒️' },
                curie: { name: 'Marie Curie', avatar: '⚛️' },
                daVinci: { name: 'Da Vinci', avatar: '🎨' }
            };
            
            document.getElementById('ai-name').textContent = characters[character].name;
            document.getElementById('ai-avatar').textContent = characters[character].avatar;
        }

        // ============================
        // OCR DE IMAGENS
        // ============================
        async function handleImageUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            
            if (!currentUser || (!currentUser.isPremium && !currentUser.isInsider && !currentUser.isOwner)) {
                showToast('Ative o plano Premium para usar OCR', 'error');
                return;
            }
            
            try {
                showToast('Processando imagem...', 'success');
                
                // Usar Tesseract.js para OCR offline
                const { data: { text } } = await Tesseract.recognize(
                    file,
                    'por+eng',
                    { 
                        logger: m => console.log(m)
                    }
                );
                
                const cleanedText = text.trim();
                
                if (!cleanedText) {
                    showToast('Nenhum texto detectado na imagem', 'error');
                    return;
                }
                
                document.getElementById('chat-input').value = `Analise esta imagem e explique: ${cleanedText}`;
                showToast('Texto extraído com sucesso!', 'success');
                
                // Atualizar pontos localmente
                currentUser.points += 10;
                if (usersData[currentUser.email]) {
                    usersData[currentUser.email].points = currentUser.points;
                    saveUsersData();
                }
                updateUI();
                
            } catch (error) {
                console.error('Erro no OCR:', error);
                showToast('Erro ao processar imagem com OCR', 'error');
            }
            
            // Resetar input de arquivo
            event.target.value = '';
        }

        // ============================
        // SISTEMA PREMIUM
        // ============================
        function generateQRCode() {
            const pixKey = 'qml.ai@premium.com';
            const amount = '24.99';
            const description = 'QML.AI Premium';
            
            const pixPayload = `00020126580014br.gov.bcb.pix0136${pixKey}5204000053039865405${amount}5802BR5913${description}6008Sao Paulo62070503***6304`;
            
            // Gerar QR Code
            const qrcodeElement = document.getElementById('qrcode');
            qrcodeElement.innerHTML = '';
            new QRCode(qrcodeElement, {
                text: pixPayload,
                width: 180,
                height: 180,
                colorDark: '#000000',
                colorLight: '#ffffff',
                correctLevel: QRCode.CorrectLevel.H
            });
        }

        function upgradeToPremium() {
            if (!currentUser) {
                showToast('Faça login para fazer upgrade', 'error');
                switchView('login');
                return;
            }
            
            showToast('Redirecionando para pagamento PIX...', 'success');
        }

        function activatePremium() {
            if (!currentUser) {
                showToast('Faça login para ativar o premium', 'error');
                return;
            }
            
            // Ativar premium localmente
            currentUser.isPremium = true;
            currentUser.points += 50;
            
            if (usersData[currentUser.email]) {
                usersData[currentUser.email].isPremium = true;
                usersData[currentUser.email].points = currentUser.points;
                saveUsersData();
            }
            
            localStorage.setItem('qml_user', JSON.stringify(currentUser));
            updateUI();
            
            showToast('🎉 Plano Premium ativado com sucesso!', 'success');
        }

        function copyPixKey() {
            const pixKey = 'qml.ai@premium.com';
            navigator.clipboard.writeText(pixKey).then(() => {
                showToast('Chave PIX copiada!', 'success');
            });
        }

        // ============================
        // PERFIL DO USUÁRIO
        // ============================
        function loadProfile() {
            if (!currentUser) return;
            
            updateProfileDisplay();
        }

        function updateProfileDisplay() {
            // Estatísticas
            const userHistory = chatHistories[currentUser.email] || [];
            const statsHtml = `
                <div style="text-align: center;">
                    <div style="font-size: 48px; font-weight: 800; color: var(--primary); margin-bottom: 10px;">${currentUser.points || 0}</div>
                    <div style="color: var(--text-secondary); margin-bottom: 20px;">Pontos de Conhecimento</div>
                    
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-top: 20px;">
                        <div>
                            <div style="font-size: 24px; font-weight: 700;">${userHistory.length}</div>
                            <div style="color: var(--text-secondary); font-size: 12px;">Mensagens</div>
                        </div>
                        <div>
                            <div style="font-size: 24px; font-weight: 700;">${Object.keys(usersData).length}</div>
                            <div style="color: var(--text-secondary); font-size: 12px;">Usuários</div>
                        </div>
                        <div>
                            <div style="font-size: 24px; font-weight: 700;">${currentUser.achievements?.length || 0}</div>
                            <div style="color: var(--text-secondary); font-size: 12px;">Conquistas</div>
                        </div>
                        <div>
                            <div style="font-size: 24px; font-weight: 700;">${currentUser.isPremium ? '⭐' : '🔒'}</div>
                            <div style="color: var(--text-secondary); font-size: 12px;">Status</div>
                        </div>
                    </div>
                </div>
            `;
            
            document.getElementById('profile-stats').innerHTML = statsHtml;
            
            // Conquistas
            const achievements = currentUser.achievements || [];
            const achievementsHtml = achievements.length > 0 ?
                achievements.map(ach => `
                    <div class="achievement-badge" style="margin: 5px; display: inline-block;">
                        <i class="fas fa-trophy"></i> ${ach}
                    </div>
                `).join('') :
                '<p style="color: var(--text-secondary);">Nenhuma conquista ainda. Continue aprendendo!</p>';
            
            document.getElementById('profile-achievements').innerHTML = achievementsHtml;
        }

        function saveProfile() {
            const name = document.getElementById('profile-name').value.trim();
            const learningStyle = document.getElementById('profile-learning-style').value;
            
            currentUser.name = name;
            currentUser.learningStyle = learningStyle;
            
            if (usersData[currentUser.email]) {
                usersData[currentUser.email].name = name;
                usersData[currentUser.email].learningStyle = learningStyle;
                saveUsersData();
            }
            
            localStorage.setItem('qml_user', JSON.stringify(currentUser));
            updateUI();
            
            showToast('Perfil atualizado com sucesso!', 'success');
        }

        // ============================
        // PAINEL ADMINISTRATIVO
        // ============================
        function refreshUsersTable() {
            if (!currentUser?.isAdmin && !currentUser?.isOwner) return;
            
            updateAdminDisplay();
        }

        function updateAdminDisplay() {
            const users = Object.values(usersData);
            
            // Atualizar estatísticas
            document.getElementById('total-users').textContent = users.length;
            document.getElementById('premium-users').textContent = users.filter(u => u.isPremium).length;
            
            const totalMessages = Object.values(chatHistories).reduce((acc, history) => acc + (history?.length || 0), 0);
            document.getElementById('total-messages').textContent = totalMessages;
            
            const today = new Date().toDateString();
            const activeToday = users.filter(u => u.lastLogin && new Date(u.lastLogin).toDateString() === today).length;
            document.getElementById('active-today').textContent = activeToday;
            
            // Atualizar tabela de usuários
            const tableBody = document.getElementById('users-table-body');
            tableBody.innerHTML = users.map(user => `
                <tr>
                    <td>${user.email}</td>
                    <td>
                        ${user.isOwner ? '👑 Dono' : user.isAdmin ? '⚡ Admin' : user.isInsider ? '🔮 Insider' : user.isPremium ? '⭐ Premium' : '👤 Free'}
                    </td>
                    <td>${user.points || 0}</td>
                    <td>
                        <div class="btn-group" style="gap: 4px;">
                            ${!user.isOwner ? `
                                <button class="btn-ghost" style="padding: 4px 8px; font-size: 12px;" onclick="adminTogglePremium('${user.email}')">
                                    <i class="fas ${user.isPremium ? 'fa-times' : 'fa-crown'}"></i>
                                </button>
                                ${currentUser.isOwner ? `
                                    <button class="btn-ghost" style="padding: 4px 8px; font-size: 12px;" onclick="adminToggleAdmin('${user.email}')">
                                        <i class="fas ${user.isAdmin ? 'fa-user-times' : 'fa-user-shield'}"></i>
                                    </button>
                                    <button class="btn-ghost" style="padding: 4px 8px; font-size: 12px;" onclick="adminToggleInsider('${user.email}')">
                                        <i class="fas ${user.isInsider ? 'fa-user' : 'fa-user-secret'}"></i>
                                    </button>
                                ` : ''}
                            ` : '<span class="small">Protegido</span>'}
                        </div>
                    </td>
                </tr>
            `).join('');
        }

        function adminTogglePremium(email) {
            if (!currentUser?.isAdmin && !currentUser?.isOwner) return;
            
            const user = usersData[email];
            if (user) {
                user.isPremium = !user.isPremium;
                saveUsersData();
                refreshUsersTable();
                showToast(`${user.isPremium ? 'Premium ativado' : 'Premium desativado'} para ${email}`, 'success');
            }
        }

        function adminToggleAdmin(email) {
            if (!currentUser?.isOwner) {
                showToast('Apenas o dono pode conceder admin', 'error');
                return;
            }
            
            const user = usersData[email];
            if (user) {
                user.isAdmin = !user.isAdmin;
                saveUsersData();
                refreshUsersTable();
                showToast(`${user.isAdmin ? 'Admin concedido' : 'Admin removido'} para ${email}`, 'success');
            }
        }

        function adminToggleInsider(email) {
            if (!currentUser?.isOwner) {
                showToast('Apenas o dono pode conceder insider', 'error');
                return;
            }
            
            const user = usersData[email];
            if (user) {
                user.isInsider = !user.isInsider;
                saveUsersData();
                refreshUsersTable();
                showToast(`${user.isInsider ? 'Insider concedido' : 'Insider removido'} para ${email}`, 'success');
            }
        }

        function createNewInsider() {
            if (!currentUser?.isOwner) {
                showToast('Apenas o dono pode criar insiders', 'error');
                return;
            }
            
            const email = prompt('Digite o email para o novo usuário Insider:');
            if (!email) return;
            
            if (usersData[email]) {
                showToast('Este email já está cadastrado', 'error');
                return;
            }
            
            const password = 'insider123';
            const name = email.split('@')[0];
            const hashedPassword = CryptoJS.SHA256(password).toString();
            
            usersData[email] = {
                email,
                name,
                password: hashedPassword,
                isPremium: true,
                isAdmin: false,
                isInsider: true,
                isOwner: false,
                points: 100,
                achievements: ['beginner', 'explorer'],
                learningStyle: 'visual',
                createdAt: new Date().toISOString(),
                lastLogin: new Date().toISOString()
            };
            
            chatHistories[email] = [];
            
            saveUsersData();
            saveChatHistories();
            refreshUsersTable();
            
            showToast(`Novo insider criado: ${email} (senha: insider123)`, 'success');
        }

        // ============================
        // UTILITÁRIOS
        // ============================
        function showToast(message, type = 'success') {
            // Remover toasts existentes
            document.querySelectorAll('.toast').forEach(toast => toast.remove());
            
            const toast = document.createElement('div');
            toast.className = `toast ${type}`;
            toast.innerHTML = `
                <i class="fas fa-${type === 'success' ? 'check-circle' : 'exclamation-circle'}"></i>
                <span>${message}</span>
            `;
            
            document.body.appendChild(toast);
            
            setTimeout(() => {
                toast.style.animation = 'slideInRight 0.3s ease reverse';
                setTimeout(() => toast.remove(), 300);
            }, 4000);
        }

        // Adicionar animação de piscar
        const style = document.createElement('style');
        style.textContent = `
            @keyframes blink {
                0%, 100% { opacity: 1; }
                50% { opacity: 0.3; }
            }
            @keyframes pulse {
                0%, 100% { opacity: 1; }
                50% { opacity: 0.5; }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
