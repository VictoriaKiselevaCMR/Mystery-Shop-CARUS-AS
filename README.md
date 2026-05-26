<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Тайный покупатель • Доступ по коду ДЦ</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #eef2f5;
            font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            padding: 2rem 1.25rem;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .portal-container {
            max-width: 950px;
            width: 100%;
            background: white;
            border-radius: 2rem;
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }

        .mystery-header {
            background: linear-gradient(135deg, #1a3c34, #0f2c2a);
            padding: 1.8rem 2rem;
            color: white;
        }

        .mystery-header h1 {
            font-size: 1.9rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .mystery-header h1 span {
            background: #d9a13b;
            font-size: 1rem;
            padding: 4px 12px;
            border-radius: 40px;
            font-weight: 600;
            color: #1e2f2a;
        }

        .mystery-header p {
            opacity: 0.85;
            margin-top: 8px;
            font-size: 0.95rem;
        }

        .access-body {
            padding: 2rem 2rem 2.2rem;
        }

        .search-area {
            margin-bottom: 2rem;
        }

        .search-area label {
            font-weight: 600;
            color: #1f4d44;
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1rem;
            margin-bottom: 10px;
        }

        .input-group {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            align-items: center;
        }

        .code-input {
            flex: 1;
            padding: 14px 18px;
            font-size: 1rem;
            font-weight: 500;
            background: #ffffff;
            border: 2px solid #cbdde2;
            border-radius: 48px;
            font-family: 'SF Mono', 'Fira Code', monospace;
            transition: all 0.2s;
            letter-spacing: 0.5px;
        }

        .code-input:focus {
            outline: none;
            border-color: #2c7a6e;
            box-shadow: 0 0 0 3px rgba(44, 122, 110, 0.2);
        }

        .show-btn {
            background: #2c7a6e;
            color: white;
            border: none;
            padding: 14px 28px;
            border-radius: 48px;
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.2s;
            font-family: inherit;
            white-space: nowrap;
        }

        .show-btn:hover {
            background: #1e5f54;
            transform: scale(0.98);
        }

        .hint-text {
            font-size: 0.75rem;
            color: #6f9b8e;
            margin-top: 8px;
            margin-left: 12px;
        }

        .access-card {
            background: #fefef7;
            border-radius: 1.8rem;
            border: 1px solid #e0ede8;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.03);
            animation: fadeIn 0.25s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(6px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .dc-header {
            background: #f4faf8;
            padding: 1rem 1.8rem;
            border-bottom: 1px solid #ddece6;
        }

        .dc-code {
            font-family: monospace;
            font-weight: 800;
            background: #2c7a6e20;
            display: inline-block;
            padding: 5px 14px;
            border-radius: 40px;
            font-size: 0.85rem;
            color: #195a4e;
        }

        .dc-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-top: 10px;
            color: #1e3b34;
        }

        .info-grid {
            padding: 1.6rem 1.8rem 1.8rem;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .credential-block {
            background: #ffffff;
            border-radius: 1.4rem;
            border: 1px solid #deeae5;
            padding: 1.2rem 1.5rem;
        }

        .cred-label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 700;
            color: #6b9085;
            margin-bottom: 6px;
        }

        .cred-value {
            font-family: 'SF Mono', 'Fira Code', monospace;
            font-size: 1.35rem;
            font-weight: 700;
            color: #1b4e43;
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 15px;
        }

        .copy-btn {
            background: #eef3f1;
            border: none;
            font-size: 0.7rem;
            padding: 6px 16px;
            border-radius: 60px;
            font-weight: 600;
            cursor: pointer;
            color: #1d5e50;
            transition: 0.2s;
            font-family: inherit;
        }

        .copy-btn:hover {
            background: #cfe3dc;
        }

        .detail-row {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            justify-content: flex-start;
            background: #fafefc;
            padding: 14px 18px;
            border-radius: 1.2rem;
            font-size: 0.9rem;
            border: 1px solid #e4efe9;
        }

        .detail-item {
            color: #2c5e52;
        }

        .detail-item strong {
            color: #15473e;
        }

        .placeholder-box {
            background: #f6fbf9;
            border-radius: 2rem;
            padding: 3rem 2rem;
            text-align: center;
            color: #608e81;
            border: 1px dashed #bcd7cf;
            font-weight: 500;
        }

        .error-box {
            background: #fff5f0;
            border-radius: 2rem;
            padding: 2rem;
            text-align: center;
            color: #c25a2c;
            border: 1px solid #ffddd0;
            font-weight: 500;
        }

        .footer-note {
            margin-top: 24px;
            font-size: 0.7rem;
            text-align: center;
            color: #8bada2;
            border-top: 1px solid #e0eae5;
            padding-top: 20px;
        }

        @media (max-width: 640px) {
            .access-body {
                padding: 1.5rem;
            }
            .cred-value {
                font-size: 1rem;
            }
            .input-group {
                flex-direction: column;
                align-items: stretch;
            }
            .show-btn {
                justify-content: center;
                text-align: center;
            }
        }
    </style>
</head>
<body>
<div class="portal-container">
    <div class="mystery-header">
        <h1>
            🕵️ Тайный покупатель
            <span>доступ по коду ДЦ</span>
        </h1>
        <p>Введите ваш код дилерского центра — нажмите «Показать доступ», чтобы получить логин и пароль для портала</p>
    </div>

    <div class="access-body">
        <div class="search-area">
            <label>🔑 Код дилерского центра (ДЦ)</label>
            <div class="input-group">
                <input type="text" id="dcCodeInput" class="code-input" 
                       placeholder="Например: EURUS01100" autocomplete="off" spellcheck="false">
                <button id="showAccessBtn" class="show-btn">🔓 Показать доступ</button>
            </div>
            <div class="hint-text">💡 Введите точный код ДЦ (без пробелов) и нажмите кнопку</div>
        </div>

        <div id="dynamicAccessPanel">
            <div class="placeholder-box" id="placeholderMsg">
                🔐 Введите код ДЦ и нажмите «Показать доступ», чтобы получить учётные данные для портала «Тайный покупатель»
            </div>
            <div id="credentialCard" style="display: none;"></div>
        </div>
        <div class="footer-note">
            ⚡ Полная база: все коды ДЦ из официальной выгрузки (логины и пароли для сервисного доступа)
        </div>
    </div>
</div>

<script>
    // ============================================================
    // ПОЛНЫЙ СПРАВОЧНИК КОДОВ ДЦ ИЗ ФАЙЛА (все строки)
    // ============================================================
    const dcAccessData = {
        "EURUS06199": { login: "wsve", password: "wsve65", holding: "Фреш", name: "Чанган Центр FRESH Волгоград", region: "ЮФО", city: "Волгоград" },
        "EURUS06200": { login: "fdhu", password: "fdhu1", holding: "Фреш", name: "Чанган Центр FRESH Воронеж", region: "ЦФО", city: "Воронеж" },
        "EURUS06213": { login: "dgsx", password: "dgsx34", holding: "Major", name: "Чанган Центр Олимп", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06214": { login: "iter", password: "iter34", holding: "Major", name: "Чанган Центр Мэйджор Светлановский (CS)", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06214_UNI": { login: "gfdy", password: "gfdy43", holding: "Major", name: "Юни Центр Мэйджор Светлановский (UNI)", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06215": { login: "brde", password: "brde32", holding: "Major", name: "Чанган Центр Мэйджор", region: "ЦФО", city: "Москва" },
        "EURUS06232": { login: "irws", password: "irws18", holding: "Major", name: "Чанган Центр Мэйджор Сити", region: "ЦФО", city: "Москва" },
        "EURUS06237": { login: "lbdh", password: "lbdh33", holding: "Major", name: "Чанган Центр Мэйджор Запад", region: "ЦФО", city: "Москва" },
        "EURUS06238": { login: "glcx", password: "glcx99", holding: "Major", name: "Чанган Центр Мэйджор Юг", region: "ЦФО", city: "Москва" },
        "EURUS06239": { login: "xztr", password: "xztr18", holding: "Major", name: "Чанган Центр Мэйджор Тушино", region: "ЦФО", city: "Москва" },
        "EURUS06250": { login: "riop", password: "riop41", holding: "Major", name: "Юни Центр Мэйджор Север", region: "ЦФО", city: "Москва" },
        "EURUS06297": { login: "vblo", password: "vblo54", holding: "Major", name: "Чанган Центр Мэйджор Строгино", region: "ЦФО", city: "Москва" },
        "EURUS06293": { login: "xsxd", password: "xsxd37", holding: "ТТС", name: "Чанган Центр ТрансТехСервис", region: "ПФО", city: "Набережные Челны" },
        "EURUS06318": { login: "oier", password: "oier49", holding: "ТТС", name: "Чанган Центр ТрансТехСервис Уфа", region: "ПФО", city: "Уфа" },
        "EURUS06330": { login: "ghye", password: "ghye70", holding: "ТТС", name: "Чанган Центр ТрансТехСервис Казань Декабристов", region: "ПФО", city: "Казань" },
        "EURUS06363": { login: "pyws", password: "pyws63", holding: "ТТС", name: "Чанган Центр ТрансТехСервис Ижевск", region: "ПФО", city: "Ижевск" },
        "EURUS06376": { login: "pilx", password: "pilx32", holding: "ТТС", name: "Чанган Центр ТрансТехСервис Нижнекамск", region: "ПФО", city: "Нижнекамск" },
        "EURUS06384": { login: "slvw", password: "slvw90", holding: "ТТС", name: "Чанган Центр ТрансТехСервис Мамадышский", region: "ПФО", city: "Казань" },
        "EURUS06216": { login: "zazt", password: "zazt54", holding: "Автомир", name: "Чанган Центр Автомир на Щелковском", region: "ЦФО", city: "Москва" },
        "EURUS06217": { login: "vbds", password: "vbds37", holding: "Автомир", name: "Чанган Центр Автомир на Дмитровском", region: "ЦФО", city: "Москва" },
        "EURUS06309": { login: "tvcv", password: "tvcv39", holding: "Автомир", name: "Чанган Центр Автомир на Дунайском", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06340": { login: "spre", password: "spre11", holding: "Автомир", name: "Чанган Центр Автомир", region: "ЦФО", city: "Брянск" },
        "EURUS06341": { login: "dpiq", password: "dpiq09", holding: "Автомир", name: "Чанган Центр Автомир на Петухова", region: "СФО", city: "Новосибирск" },
        "EURUS06369": { login: "frwa", password: "frwa36", holding: "Автомир", name: "Чанган Центр Автомир Люблино", region: "ЦФО", city: "Москва" },
        "EURUS06267": { login: "drtq", password: "drtq33", holding: "Атлант Моторс", name: "Чанган Центр Дельта Моторс", region: "ЮФО", city: "Ростов-на-Дону" },
        "EURUS06268": { login: "qasd", password: "qasd58", holding: "Атлант Моторс", name: "Чанган Центр Сокол Моторс Таганрог", region: "ЮФО", city: "Таганрог" },
        "EURUS06269": { login: "cmnb", password: "cmnb05", holding: "Атлант Моторс", name: "Чанган Центр Сокол Моторс Шолохова", region: "ЮФО", city: "Ростов-на-Дону" },
        "EURUS06300": { login: "uohg", password: "uohg66", holding: "Атлант Моторс", name: "Чанган Центр Сокол Моторс Шахты", region: "ЮФО", city: "Шахты" },
        "EURUS06301": { login: "jknc", password: "jknc12", holding: "Атлант Моторс", name: "Чанган Центр Сокол Моторс Волгодонск", region: "ЮФО", city: "Волгодонск" },
        "EURUS06223": { login: "sgfr", password: "sgfr48", holding: "САНРАЙЗ ГРУПП", name: "Юни Центр Санрайз Групп", region: "ЦФО", city: "Москва" },
        "EURUS06359": { login: "dfpa", password: "dfpa17", holding: "САНРАЙЗ ГРУПП", name: "Юни Центр Санрайз Групп", region: "СЗФО", city: "Мурманск" },
        "EURUS06345": { login: "zxuy", password: "zxuy22", holding: "САНРАЙЗ ГРУПП", name: "Чанган Центр Вологда", region: "СЗФО", city: "Вологда" },
        "EURUS06221": { login: "clue", password: "clue43", holding: "Авторитэйл", name: "Чанган Центр Вагнер", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06316": { login: "srqp", password: "srqp97", holding: "Авторитэйл", name: "Чанган Центр Вагнер Выборгский", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06351": { login: "erty", password: "erty05", holding: "Автомобильный дом", name: "Чанган Центр Окружная", region: "СЗФО", city: "Калининград" },
        "EURUS06224": { login: "lbvd", password: "lbvd71", holding: "ОПТИМА КУБАНЬ", name: "Чанган Центр Оптима Краснодар", region: "ЮФО", city: "Краснодар" },
        "EURUS06228": { login: "sdrq", password: "sdrq21", holding: "ОПТИМА КУБАНЬ", name: "Чанган Центр Оптима Сочи", region: "ЮФО", city: "Сочи" },
        "EURUS06252": { login: "gfda", password: "gfda78", holding: "АсАвто", name: "Чанган Центр ГК АсАвто Тольятти", region: "ПФО", city: "Тольятти" },
        "EURUS06338": { login: "zxcm", password: "zxcm33", holding: "", name: "Чанган Центр Автобан", region: "УФО", city: "Екатеринбург" },
        "EURUS06289": { login: "swql", password: "swql55", holding: "Автокласс", name: "Чанган Центр Новомосковск", region: "ЦФО", city: "Новомосковск" },
        "EURUS06328": { login: "dfpo", password: "dfpo11", holding: "АГАТ", name: "Чанган Центр Агат на Комсомольском", region: "ПФО", city: "Нижний Новгород" },
        "EURUS06282": { login: "sdpo", password: "sdpo33", holding: "АвтоЮг", name: "Чанган Центр АвтоЮг", region: "ЮФО", city: "Ставрополь" },
        "EURUS06355": { login: "wnbs", password: "wnbs67", holding: "Юг-Авто", name: "Чанган Центр Юг-Авто", region: "ЮФО", city: "Краснодар" },
        "EURUS06263": { login: "dfpp", password: "dfpp55", holding: "", name: "Чанган Центр АвтоГЕРМЕС", region: "ЦФО", city: "Москва" },
        "EURUS06292": { login: "xlmn", password: "xlmn77", holding: "", name: "Чанган Центр Чебоксары", region: "ПФО", city: "Чебоксары" },
        "EURUS06285": { login: "dfcx", password: "dfcx65", holding: "Автоимпорт", name: "Чанган Центр Автоимпорт", region: "ЦФО", city: "Тула" },
        "EURUS06286": { login: "fpqm", password: "fpqm01", holding: "Автоимпорт", name: "Чанган Центр Автоимпорт Юг", region: "ЦФО", city: "Рязань" },
        "EURUS06326": { login: "linw", password: "linw88", holding: "БЦР", name: "Чанган Центр на Гагарина", region: "ПФО", city: "Нижний Новгород" },
        "EURUS06191": { login: "nbxc", password: "nbxc32", holding: "Автокласс", name: "Чанган Центр Автокласс", region: "ЦФО", city: "Тула" },
        "EURUS06236": { login: "vfys", password: "vfys91", holding: "", name: "Чанган Центр ААА Моторс", region: "ЮФО", city: "Ростов-на-Дону" },
        "EURUS06305": { login: "pjvc", password: "pjvc33", holding: "", name: "Чанган Центр Максимум", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06281": { login: "ghlk", password: "ghlk54", holding: "БЦР", name: "Чанган Центр БЦР Моторс", region: "ПФО", city: "Нижний Новгород" },
        "EURUS06279": { login: "demj", password: "demj97", holding: "", name: "Чанган Центр Арена Авто", region: "ПФО", city: "Тольятти" },
        "EURUS06145": { login: "pmnf", password: "pmnf11", holding: "", name: "Чанган Центр Автолига", region: "ПФО", city: "Нижний Новгород" },
        "EURUS06173": { login: "gfmn", password: "gfmn80", holding: "", name: "Чанган Центр Софийская", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06211": { login: "sopz", password: "sopz60", holding: "АГАТ", name: "Чанган Центр Агат", region: "ЮФО", city: "Волгоград" },
        "EURUS06242_CS": { login: "xpre", password: "xpre07", holding: "АСПЭК", name: "Чанган Центр АСПЭК-Авто (CS)", region: "ПФО", city: "Ижевск" },
        "EURUS06242_UNI": { login: "phbd", password: "phbd84", holding: "АСПЭК", name: "Юни Центр АСПЭК-Авто (UNI)", region: "ПФО", city: "Ижевск" },
        "EURUS06280": { login: "gfdb", password: "gfdb08", holding: "Темп авто", name: "Чанган Центр Темп Авто Ростов-на-Дону", region: "ЮФО", city: "Ростов-на-Дону" },
        "EURUS06069": { login: "hgvv", password: "hgvv40", holding: "Базис Моторс", name: "Чанган Центр Базис Пермякова", region: "УФО", city: "Тюмень" },
        "EURUS06306": { login: "dfoe", password: "dfoe72", holding: "Ринг Авто", name: "Чанган Центр Ринг Воронеж", region: "ЦФО", city: "Воронеж" },
        "EURUS06403": { login: "bbtt", password: "bbtt95", holding: "Ринг Авто", name: "Чанган Центр Ринг Авто", region: "ЦФО", city: "Липецк" },
        "EURUS06329": { login: "dcur", password: "dcur73", holding: "", name: "Чанган Центр Авторай", region: "ПФО", city: "Ульяновск" },
        "EURUS06147": { login: "jgff", password: "jgff77", holding: "", name: "Чанган Центр Лидер", region: "ЦФО", city: "Рязань" },
        "EURUS06288": { login: "grsl", password: "grsl45", holding: "АГАТ", name: "Чанган Центр АГАТ Аэропорт", region: "ЮФО", city: "Астрахань" },
        "EURUS06347": { login: "ojvd", password: "ojvd05", holding: "", name: "Чанган Центр Автопортрет", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06251": { login: "xxoi", password: "xxoi43", holding: "АГАТ", name: "Чанган Центр Агат Ярославль", region: "ЦФО", city: "Ярославль" },
        "EURUS06248": { login: "nbrf", password: "nbrf05", holding: "", name: "Чанган Центр Новокар", region: "ЮФО", city: "Новороссийск" },
        "EURUS06229": { login: "sdec", password: "sdec47", holding: "АГАТ", name: "Чанган Центр Саранск", region: "ПФО", city: "Саранск" },
        "EURUS06337": { login: "eglg", password: "eglg03", holding: "", name: "Чанган Центр Квазар", region: "ЦФО", city: "Москва" },
        "EURUS06299": { login: "ooes", password: "ooes60", holding: "КАН АВТО", name: "Чанган Центр КАН АВТО", region: "ПФО", city: "Казань" },
        "EURUS06149": { login: "zlmf", password: "zlmf73", holding: "", name: "Чанган Центр Автосити", region: "ЦФО", city: "Воронеж" },
        "EURUS06325": { login: "sdoj", password: "sdoj66", holding: "", name: "Чанган Центр Уникум", region: "УФО", city: "Нижний Тагил" },
        "EURUS06193": { login: "ggdd", password: "ggdd53", holding: "Автофорум", name: "Чанган Центр Автофорум Восток", region: "ПФО", city: "Саратов" },
        "EURUS06187": { login: "jgrc", password: "jgrc76", holding: "Регинас", name: "Чанган Центр Регинас Магнитогорск", region: "УФО", city: "Магнитогорск" },
        "EURUS06201": { login: "vvoo", password: "vvoo40", holding: "Регинас", name: "Чанган Центр Регинас на Кашириных (CS)", region: "УФО", city: "Челябинск" },
        "EURUS06201_UNI": { login: "ihcv", password: "ihcv44", holding: "Регинас", name: "Юни Центр Регинас на Кашириных (UNI)", region: "УФО", city: "Челябинск" },
        "EURUS06202": { login: "dhre", password: "dhre11", holding: "Регинас", name: "Чанган Центр Регинас на Гурзуфской", region: "УФО", city: "Екатеринбург" },
        "EURUS06203": { login: "bbed", password: "bbed28", holding: "Регинас", name: "Чанган Центр Регинас Миасс", region: "УФО", city: "Миасс" },
        "EURUS06245": { login: "bflo", password: "bflo19", holding: "Регинас", name: "Чанган Центр Регинас на Свердловском", region: "УФО", city: "Челябинск" },
        "EURUS06254": { login: "uhdd", password: "uhdd55", holding: "Регинас", name: "Чанган Центр Регинас на Высоцкого", region: "УФО", city: "Екатеринбург" },
        "EURUS06398": { login: "srec", password: "srec11", holding: "Регинас", name: "Чанган Центр Регинас на Ленина", region: "УФО", city: "Челябинск" },
        "EURUS06304": { login: "zasz", password: "zasz13", holding: "Автофорум", name: "Чанган Центр АвтоФорум", region: "ПФО", city: "Саратов" },
        "EURUS06246": { login: "bbge", password: "bbge21", holding: "Фастар", name: "Чанган Центр Фастар на Речном", region: "СФО", city: "Новосибирск" },
        "EURUS06311": { login: "wwjb", password: "wwjb33", holding: "ДАВ АВТО", name: "Чанган Центр ДАВ-АВТО", region: "ПФО", city: "Пермь" },
        "EURUS06150": { login: "rtdd", password: "rtdd77", holding: "", name: "Чанган Центр АЦ Кунцево", region: "ЦФО", city: "Москва" },
        "EURUS06137": { login: "hhgw", password: "hhgw84", holding: "ЭКСПОКАР", name: "Чанган Центр Экспокар Краснодар", region: "ЮФО", city: "Краснодар" },
        "EURUS06344": { login: "gedd", password: "gedd81", holding: "", name: "Чанган Центр Автоград", region: "УФО", city: "Тюмень" },
        "EURUS06255": { login: "gcsx", password: "gcsx83", holding: "Фастар", name: "Чанган Центр Самара-Авто", region: "ПФО", city: "Самара" },
        "EURUS06287": { login: "dduu", password: "dduu99", holding: "", name: "Чанган Центр Энгельс", region: "ПФО", city: "Энгельс" },
        "EURUS06270": { login: "yfsd", password: "yfsd33", holding: "Темп Авто", name: "Чанган Центр Темп Авто", region: "ЮФО", city: "Краснодар" },
        "EURUS06154": { login: "ddoo", password: "ddoo29", holding: "Тисс Авто", name: "Чанган Центр Барнаул (CS)", region: "СФО", city: "Барнаул" },
        "EURUS06400": { login: "trnb", password: "trnb00", holding: "Тисс Авто", name: "Юни Центр Барнаул (UNI)", region: "СФО", city: "Барнаул" },
        "EURUS06013": { login: "sdom", password: "sdom13", holding: "Диалог", name: "Чанган Центр Альметьевск", region: "ПФО", city: "Альметьевск" },
        "EURUS06107": { login: "hgvs", password: "hgvs23", holding: "Диалог", name: "Чанган Центр Диалог Авто", region: "ПФО", city: "Казань" },
        "EURUS06256": { login: "eiyt", password: "eiyt48", holding: "АсАвто", name: "Чанган Центр АсАвто Юг", region: "ПФО", city: "Самара" },
        "EURUS06061": { login: "aaiu", password: "aaiu65", holding: "Демидыч", name: "Чанган Центр Демидыч Пермь", region: "ПФО", city: "Пермь" },
        "EURUS06261": { login: "hecb", password: "hecb39", holding: "Демидыч", name: "Чанган Центр Демидыч Уфа (CS)", region: "ПФО", city: "Уфа" },
        "EURUS06261_UNI": { login: "ssbr", password: "ssbr69", holding: "Демидыч", name: "Юни Центр Демидыч Уфа (UNI)", region: "ПФО", city: "Уфа" },
        "EURUS06308": { login: "xesd", password: "xesd33", holding: "Прагматика", name: "Чанган Центр Прагматика Купчино", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06204": { login: "ernb", password: "ernb77", holding: "", name: "Чанган Центр Киров", region: "ПФО", city: "Киров" },
        "EURUS06189": { login: "ggfj", password: "ggfj34", holding: "Авто Премиум", name: "Чанган Центр Тверь", region: "ЦФО", city: "Тверь" },
        "EURUS06155": { login: "azsf", password: "azsf71", holding: "", name: "Чанган Центр АвтоГрад в Добром", region: "ЦФО", city: "Владимир" },
        "EURUS06163": { login: "hymc", password: "hymc94", holding: "", name: "Чанган Центр Белгород", region: "ЦФО", city: "Белгород" },
        "EURUS06183": { login: "dssl", password: "dssl34", holding: "", name: "Чанган Центр Минеральные Воды", region: "СКФО", city: "Минеральные Воды" },
        "EURUS06151": { login: "vbbq", password: "vbbq17", holding: "Авилон", name: "Чанган Центр Авилон", region: "ЦФО", city: "Москва" },
        "EURUS06243": { login: "etyi", password: "etyi11", holding: "Автопрестиж", name: "Чанган Центр Калуга", region: "ЦФО", city: "Калуга" },
        "EURUS06253": { login: "hgff", password: "hgff46", holding: "", name: "Юни Центр Брянск", region: "ЦФО", city: "Брянск" },
        "EURUS06283": { login: "dduy", password: "dduy06", holding: "Автосалон-2000", name: "Чанган Центр Автосалон-2000", region: "ПФО", city: "Оренбург" },
        "EURUS06284": { login: "kvnq", password: "kvnq39", holding: "Автосалон-2000", name: "Чанган Центр Автосалон-2000", region: "ПФО", city: "Орск" },
        "EURUS06312": { login: "mnrr", password: "mnrr32", holding: "Арконт", name: "Чанган Центр Арконт", region: "ЮФО", city: "Волжский" },
        "EURUS06385": { login: "brjh", password: "brjh08", holding: "Арконт", name: "Чанган Центр Арконт", region: "ЮФО", city: "Краснодар" },
        "EURUS06370": { login: "fdwl", password: "fdwl30", holding: "КОРС Групп", name: "Чанган Центр Курск", region: "ЦФО", city: "Курск" },
        "EURUS06381": { login: "ceap", password: "ceap46", holding: "КОРС Групп", name: "Чанган Центр Корс", region: "ЦФО", city: "Коломна" },
        "EURUS06395": { login: "btkk", password: "btkk17", holding: "КОРС Групп", name: "Чанган Центр Корс", region: "ЦФО", city: "Орел" },
        "EURUS06366": { login: "rrkd", password: "rrkd53", holding: "", name: "Юни Центр Автолоцман", region: "ПФО", city: "Пенза" },
        "EURUS06368": { login: "cotd", password: "cotd48", holding: "Аларм", name: "Чанган Центр Аларм Моторс", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06372": { login: "ggwi", password: "ggwi28", holding: "", name: "Чанган Центр АТК Моторс", region: "ПФО", city: "Самара" },
        "EURUS06373": { login: "lgsr", password: "lgsr60", holding: "ОПТИМА КУБАНЬ", name: "Чанган Центр Оптима Тамань", region: "ЮФО", city: "Краснодар" },
        "EURUS06374": { login: "jdlh", password: "jdlh62", holding: "АБЦГрупп", name: "Чанган Центр Рыбинск", region: "ЦФО", city: "Рыбинск" },
        "EURUS06375": { login: "soyu", password: "soyu53", holding: "АГАТ", name: "Чанган Центр Агат на Промышленном", region: "ЦФО", city: "Владимир" },
        "EURUS06377": { login: "khfd", password: "khfd32", holding: "Автопрестиж", name: "Чанган Центр Автопрестиж", region: "ПФО", city: "Пермь" },
        "EURUS06386": { login: "rdjl", password: "rdjl91", holding: "РОЛЬФ", name: "Чанган Центр Рольф Ясенево", region: "ЦФО", city: "Москва" },
        "EURUS06387": { login: "igrv", password: "igrv35", holding: "РОЛЬФ", name: "Чанган Центр Рольф Химки", region: "ЦФО", city: "Москва" },
        "EURUS06389": { login: "ldhi", password: "ldhi05", holding: "БЦР", name: "Чанган Центр БЦР-ПЕЧЁРЫ", region: "ПФО", city: "Нижний Новгород" },
        "EURUS06388": { login: "ofrn", password: "ofrn97", holding: "", name: "Чанган Центр Автопродикс", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06390": { login: "zpiu", password: "zpiu40", holding: "", name: "Чанган Центр АНТ", region: "СФО", city: "Барнаул" },
        "EURUS06391": { login: "tffg", password: "tffg02", holding: "", name: "Чанган Центр Сатурн", region: "УФО", city: "Челябинск" },
        "EURUS06392": { login: "dpuy", password: "dpuy55", holding: "", name: "Чанган Центр Фрагмент на Копейском", region: "УФО", city: "Челябинск" },
        "EURUS06393": { login: "fdwe", password: "fdwe20", holding: "Сильвер-Авто ГРУПП", name: "Чанган Центр СИЛЬВЕР", region: "УФО", city: "Курган" },
        "EURUS06397": { login: "hfue", password: "hfue85", holding: "Сильвер-Авто ГРУПП", name: "Чанган Центр СИЛЬВЕР", region: "УФО", city: "Магнитогорск" },
        "EURUS06396": { login: "ihcy", password: "ihcy03", holding: "", name: "Чанган Центр Агат-Авто", region: "СФО", city: "Братск" },
        "EURUS06361": { login: "serd", password: "serd23", holding: "", name: "Чанган Центр Фаравто", region: "СКФО", city: "Махачкала" },
        "EURUS06356": { login: "ngbd", password: "ngbd79", holding: "", name: "Чанган Центр НИКА АВТО", region: "ПФО", city: "Оренбург" },
        "EURUS06360": { login: "jdvg", password: "jdvg54", holding: "", name: "Чанган Центр Автомаркет", region: "СЗФО", city: "Мурманск" },
        "EURUS06354": { login: "hdon", password: "hdon63", holding: "АВТОСТИЛЬ", name: "Чанган Центр Великий Новгород (CS)", region: "СЗФО", city: "Великий Новгород" },
        "EURUS06404": { login: "artg", password: "artg51", holding: "АВТОСТИЛЬ", name: "Юни Центр Великий Новгород (UNI)", region: "СЗФО", city: "Великий Новгород" },
        "EURUS06039": { login: "dlie", password: "dlie44", holding: "АВТОСТИЛЬ", name: "Чанган Центр Автостиль Автово", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06209": { login: "ziun", password: "ziun55", holding: "", name: "Чанган Центр Армада-Авто", region: "ПФО", city: "Ульяновск" },
        "EURUS06265": { login: "qety", password: "qety80", holding: "Ринг Авто", name: "Чанган Центр Оскол", region: "ЦФО", city: "Старый Оскол" },
        "EURUS06298": { login: "ljds", password: "ljds61", holding: "", name: "Чанган Центр Орехово-Зуево", region: "ЦФО", city: "Орехово-Зуево" },
        "EURUS06135": { login: "okge", password: "okge61", holding: "", name: "Чанган Центр Калининград", region: "СЗФО", city: "Калининград" },
        "EURUS06272": { login: "dytf", password: "dytf54", holding: "", name: "Чанган Центр Томск", region: "СФО", city: "Томск" },
        "EURUS06093": { login: "kwrd", password: "kwrd36", holding: "", name: "Чанган Центр Серпухов", region: "ЦФО", city: "Серпухов" },
        "EURUS06349": { login: "vzxo", password: "vzxo02", holding: "", name: "Юни Центр Хабаровск", region: "ДФО", city: "Хабаровск" },
        "EURUS06350": { login: "dvne", password: "dvne06", holding: "МЕДВЕДЬ", name: "Чанган Центр Медведь", region: "СФО", city: "Абакан" },
        "EURUS06307": { login: "jvjr", password: "jvjr27", holding: "", name: "Юни Центр Абакан", region: "СФО", city: "Абакан" },
        "EURUS06240": { login: "gfod", password: "gfod82", holding: "Сибимпэкс", name: "Чанган Центр Кузбасс", region: "СФО", city: "Кемерово" },
        "EURUS06197": { login: "mnus", password: "mnus88", holding: "", name: "Чанган Центр Нижневартовск", region: "УФО", city: "Нижневартовск" },
        "EURUS06220": { login: "sohg", password: "sohg56", holding: "Автополе", name: "Чанган Центр Автополе", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06332": { login: "pgtd", password: "pgtd01", holding: "", name: "Юни Центр Улан-Удэ", region: "ДФО", city: "Улан-Удэ" },
        "EURUS06185": { login: "sohy", password: "sohy77", holding: "", name: "Чанган Центр Восток", region: "УФО", city: "Екатеринбург" },
        "EURUS06274": { login: "sdtw", password: "sdtw05", holding: "Великан", name: "Чанган Центр Измайлово", region: "ЦФО", city: "Москва" },
        "EURUS06295": { login: "vbwe", password: "vbwe54", holding: "FAVORIT MOTORS", name: "Чанган Центр FAVORIT MOTORS МКАД", region: "ЦФО", city: "Реутов" },
        "EURUS06294": { login: "xpgt", password: "xpgt84", holding: "", name: "Чанган Центр VERRA", region: "ПФО", city: "Пермь" },
        "EURUS06235": { login: "dspw", password: "dspw95", holding: "АвтоЮг", name: "Чанган Центр Пятигорск", region: "СКФО", city: "Пятигорск" },
        "EURUS06314": { login: "geni", password: "geni32", holding: "ВОСТОК МОТОРС", name: "Чанган Центр Новый Уренгой", region: "УФО", city: "Новый Уренгой" },
        "EURUS06226": { login: "edki", password: "edki44", holding: "Великан", name: "Чанган Центр Липецк", region: "ЦФО", city: "Липецк" },
        "EURUS06334": { login: "dont", password: "dont87", holding: "Лаки Моторс", name: "Чанган Центр Лаки Моторс", region: "УФО", city: "Екатеринбург" },
        "EURUS06192": { login: "kdgy", password: "kdgy22", holding: "", name: "Чанган Центр Тамбов", region: "ЦФО", city: "Тамбов" },
        "EURUS06035": { login: "xort", password: "xort64", holding: "", name: "Чанган Центр Радар Авто", region: "ЦФО", city: "Иваново" },
        "EURUS06310": { login: "wlnu", password: "wlnu88", holding: "Базис Моторс", name: "Чанган Центр Базис Окружная", region: "УФО", city: "Тюмень" },
        "EURUS06346": { login: "yerc", password: "yerc08", holding: "", name: "Юни Центр Вологда", region: "СЗФО", city: "Вологда" },
        "EURUS06262": { login: "igfy", password: "igfy41", holding: "FAVORIT MOTORS", name: "Чанган Центр FAVORIT MOTORS Юг", region: "ЦФО", city: "Москва" },
        "EURUS06233": { login: "jnye", password: "jnye55", holding: "Башавтоком", name: "Чанган Центр Башавтоком", region: "ПФО", city: "Уфа" },
        "EURUS06234": { login: "nhdu", password: "nhdu48", holding: "Башавтоком", name: "Чанган Центр Башавтоком Юг (CS)", region: "ПФО", city: "Стерлитамак" },
        "EURUS06234_UNI": { login: "htdf", password: "htdf94", holding: "Башавтоком", name: "Юни Центр Башавтоком Юг (UNI)", region: "ПФО", city: "Стерлитамак" },
        "EURUS06302": { login: "xkut", password: "xkut59", holding: "Башавтоком", name: "Чанган Центр Башавтоком Север", region: "ПФО", city: "Октябрьский" },
        "EURUS06327": { login: "dbhq", password: "dbhq50", holding: "КАН АВТО", name: "Чанган Центр КАН АВТО Сибирский", region: "ПФО", city: "Казань" },
        "EURUS06212": { login: "djip", password: "djip83", holding: "", name: "Чанган Центр Внуково", region: "ЦФО", city: "Москва" },
        "EURUS06335": { login: "vdht", password: "vdht66", holding: "Лаки Моторс", name: "Юни Центр Лаки Моторс", region: "УФО", city: "Екатеринбург" },
        "EURUS06321": { login: "hrse", password: "hrse11", holding: "", name: "Чанган Центр Россо", region: "СФО", city: "Иркутск" },
        "EURUS06247": { login: "rgws", password: "rgws49", holding: "FAVORIT MOTORS", name: "Чанган Центр FAVORIT MOTORS Север", region: "ЦФО", city: "Москва" },
        "EURUS06017": { login: "kdye", password: "kdye31", holding: "", name: "Чанган Центр Восток-Авто", region: "ПФО", city: "Оренбург" },
        "EURUS06207": { login: "jsst", password: "jsst96", holding: "", name: "Чанган Центр Премьер Авто", region: "ЦФО", city: "Смоленск" },
        "EURUS06353": { login: "jwry", password: "jwry83", holding: "МЕДВЕДЬ", name: "Чанган Центр Медведь Север", region: "СФО", city: "Красноярск" },
        "EURUS06348": { login: "kfds", password: "kfds77", holding: "Сура-Моторс", name: "Юни Центр Пенза", region: "ПФО", city: "Пенза" },
        "EURUS06175": { login: "gsew", password: "gsew72", holding: "СК-Моторс", name: "Чанган Центр СК-Моторс", region: "УФО", city: "Сургут" },
        "EURUS06315": { login: "jumi", password: "jumi83", holding: "", name: "Чанган Центр АвтоПремьер Зубово", region: "ПФО", city: "Уфа" },
        "EURUS06266": { login: "jdie", password: "jdie88", holding: "АКСЕЛЬ", name: "Чанган Центр Архангельск", region: "СЗФО", city: "Архангельск" },
        "EURUS06291": { login: "kejo", password: "kejo02", holding: "", name: "Чанган Центр Сыктывкар", region: "СЗФО", city: "Сыктывкар" },
        "EURUS06333": { login: "pejk", password: "pejk42", holding: "", name: "Чанган Центр Улан-Удэ", region: "ДФО", city: "Улан-Удэ" },
        "EURUS06290": { login: "kgrs", password: "kgrs89", holding: "", name: "Чанган Центр Кострома", region: "ЦФО", city: "Кострома" },
        "EURUS06219": { login: "khuc", password: "khuc15", holding: "Авторусь", name: "Чанган Центр Авторусь Подольск", region: "ЦФО", city: "Москва" },
        "EURUS06165": { login: "endu", password: "endu10", holding: "Сибимпэкс", name: "Чанган Центр Новокузнецк", region: "СФО", city: "Новокузнецк" },
        "EURUS06322": { login: "hehb", password: "hehb88", holding: "", name: "Чанган Центр Иркут на Трактовой", region: "СФО", city: "Иркутск" },
        "EURUS06171": { login: "jeon", password: "jeon38", holding: "", name: "Чанган Центр Йошкар-Ола", region: "ПФО", city: "Йошкар-Ола" },
        "EURUS06320": { login: "jdin", password: "jdin72", holding: "", name: "Чанган Центр Атик-Моторс", region: "ДФО", city: "Благовещенск" },
        "EURUS06343": { login: "jeje", password: "jeje83", holding: "", name: "Чанган Центр Альянс Моторс", region: "УФО", city: "Сургут" },
        "EURUS06257": { login: "fojd", password: "fojd27", holding: "", name: "Юни Центр Курган", region: "УФО", city: "Курган" },
        "EURUS06230": { login: "jdke", password: "jdke29", holding: "", name: "Юни Центр Зеленоград", region: "ЦФО", city: "Москва" },
        "EURUS06271": { login: "oidj", password: "oidj13", holding: "", name: "Чанган Центр Атлант-М", region: "ЦФО", city: "Москва" },
        "EURUS06331": { login: "hbdu", password: "hbdu02", holding: "Авторитэйл", name: "Чанган Центр Варшавка", region: "ЦФО", city: "Москва" },
        "EURUS06180": { login: "hebi", password: "hebi92", holding: "", name: "Чанган Центр КМ/Ч-Север", region: "ЦФО", city: "Москва" },
        "EURUS06259": { login: "jenr", password: "jenr74", holding: "СК-Моторс", name: "Чанган Центр Ноябрьск", region: "УФО", city: "Ноябрьск" },
        "EURUS06205": { login: "оеау", password: "оеау01", holding: "", name: "Чанган Центр Череповец", region: "СЗФО", city: "Череповец" },
        "EURUS06241": { login: "hdif", password: "hdif83", holding: "Сура-Моторс", name: "Чанган Центр Пенза", region: "ПФО", city: "Пенза" },
        "EURUS06296": { login: "heee", password: "heee93", holding: "", name: "Юни Центр Псков", region: "СЗФО", city: "Псков" },
        "EURUS06339": { login: "ybod", password: "ybod95", holding: "", name: "Юни Центр Глазурит", region: "УФО", city: "Екатеринбург" },
        "EURUS06336": { login: "feel", password: "efel63", holding: "", name: "Чанган Центр АСМОТО", region: "УФО", city: "Екатеринбург" },
        "EURUS06319": { login: "jdhh", password: "jdhh34", holding: "", name: "Чанган Центр Сумотори-Авто", region: "ДФО", city: "Артем" },
        "EURUS06317": { login: "bdnf", password: "bdnf44", holding: "", name: "Юни Центр Автоплюс", region: "УФО", city: "Нижний Тагил" },
        "EURUS06352": { login: "hrew", password: "hrew82", holding: "Автодом", name: "Чанган Центр Алтуфьево", region: "ЦФО", city: "Москва" },
        "EURUS06260": { login: "jseg", password: "jseg04", holding: "СК-Моторс", name: "Чанган Центр Нягань", region: "УФО", city: "Нягань" },
        "EURUS06367": { login: "kdcb", password: "kdcb55", holding: "Авто Премиум", name: "Чанган Центр Авто Премиум", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06371": { login: "fjif", password: "fjif13", holding: "МЕДВЕДЬ", name: "Чанган Центр на Копылова", region: "СФО", city: "Красноярск" },
        "EURUS06379": { login: "infh", password: "infh68", holding: "", name: "Чанган Центр Феникс-Авто", region: "СФО", city: "Омск" },
        "EURUS06380": { login: "fnhl", password: "fnhl97", holding: "", name: "Чанган Центр БАКРА 2.0", region: "ЮФО", city: "Краснодар" },
        "EURUS06382": { login: "jdve", password: "jdve00", holding: "Фастар", name: "Чанган Центр Фастар на Станционной", region: "СФО", city: "Новосибирск" },
        "EURUS06383": { login: "kfnr", password: "kfnr46", holding: "Автопрестиж", name: "Чанган Центр Автопрестиж", region: "ЮФО", city: "Ставрополь" },
        "EURUS06394": { login: "jdue", password: "jdue99", holding: "", name: "Чанган Центр К-Моторс", region: "СЗФО", city: "Петрозаводск" },
        "EURUS06405": { login: "dohy", password: "dohy32", holding: "", name: "Чанган Центр Альянс", region: "СФО", city: "Омск" },
        "EURUS06406": { login: "jdhr", password: "jdhr88", holding: "Автопрестиж", name: "Чанган Центр Автопрестиж", region: "ПФО", city: "Самара" }
    };

    // DOM элементы
    const inputElement = document.getElementById('dcCodeInput');
    const showBtn = document.getElementById('showAccessBtn');
    const placeholderDiv = document.getElementById('placeholderMsg');
    const cardContainer = document.getElementById('credentialCard');

    // Функция копирования
    function copyToClipboard(text, btnElement) {
        navigator.clipboard.writeText(text).then(() => {
            const originalText = btnElement.innerText;
            btnElement.innerText = '✅ Скопировано!';
            setTimeout(() => { btnElement.innerText = originalText; }, 1500);
        }).catch(() => {
            alert('Не удалось скопировать');
        });
    }

    // Рендер карточки доступа
    function renderAccessCard(code, data) {
        if (!data) return null;
        return `
            <div class="access-card">
                <div class="dc-header">
                    <span class="dc-code">${code}</span>
                    <div class="dc-title">${data.name}</div>
                    <div style="font-size:0.8rem; color:#5f8d80; margin-top: 6px;">${data.holding ? data.holding + ' · ' : ''}${data.region} · ${data.city}</div>
                </div>
                <div class="info-grid">
                    <div class="credential-block">
                        <div class="cred-label">🔐 ЛОГИН ДЛЯ ПОРТАЛА ТАЙНЫЙ ПОКУПАТЕЛЬ</div>
                        <div class="cred-value">
                            <span>${data.login}</span>
                            <button class="copy-btn" data-copy="${data.login}">📋 Копировать логин</button>
                        </div>
                    </div>
                    <div class="credential-block">
                        <div class="cred-label">🗝️ ПАРОЛЬ (СЕРВИСНЫЙ ДОСТУП)</div>
                        <div class="cred-value">
                            <span>${data.password}</span>
                            <button class="copy-btn" data-copy="${data.password}">📋 Копировать пароль</button>
                        </div>
                    </div>
                    <div style="background:#eef6f2; border-radius: 18px; padding: 10px 16px; font-size:0.8rem; color: #2c6b5c;">
                        🎯 Данные для входа на платформу «Тайный покупатель» (оценка качества сервиса)
                    </div>
                </div>
            </div>
        `;
    }

    // Показать доступ по введённому коду
    function showAccess() {
        const enteredCode = inputElement.value.trim();
        
        if (!enteredCode) {
            cardContainer.style.display = 'none';
            placeholderDiv.style.display = 'flex';
            placeholderDiv.innerHTML = '⚠️ Введите код дилерского центра.';
            return;
        }
        
        if (dcAccessData[enteredCode]) {
            const data = dcAccessData[enteredCode];
            const cardHtml = renderAccessCard(enteredCode, data);
            cardContainer.innerHTML = cardHtml;
            cardContainer.style.display = 'block';
            placeholderDiv.style.display = 'none';
            
            // Привязываем обработчики копирования
            document.querySelectorAll('.copy-btn').forEach(btn => {
                const copyValue = btn.getAttribute('data-copy');
                if (copyValue) {
                    btn.addEventListener('click', (e) => {
                        e.stopPropagation();
                        copyToClipboard(copyValue, btn);
                    });
                }
            });
        } else {
            cardContainer.style.display = 'none';
            placeholderDiv.style.display = 'flex';
            placeholderDiv.innerHTML = `❌ Код "${enteredCode}" не найден в справочнике.<br>Проверьте правильность ввода или обратитесь к администратору.`;
        }
    }

    // Обработчик кнопки
    showBtn.addEventListener('click', showAccess);
    
    // Нажатие Enter в поле ввода
    inputElement.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') {
            e.preventDefault();
            showAccess();
        }
    });

    // Инициализация: показываем плейсхолдер
    placeholderDiv.innerHTML = '🔐 Введите код ДЦ и нажмите «Показать доступ», чтобы получить учётные данные для портала «Тайный покупатель»';
</script>
</body>
</html>
