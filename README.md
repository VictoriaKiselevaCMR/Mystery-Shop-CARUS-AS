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
            max-width: 900px;
            width: 100%;
            background: white;
            border-radius: 2rem;
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            transition: all 0.2s;
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
            letter-spacing: -0.3px;
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

        .search-wrapper {
            position: relative;
            width: 100%;
        }

        .code-input {
            width: 100%;
            padding: 14px 18px;
            font-size: 1rem;
            font-weight: 500;
            background: #ffffff;
            border: 2px solid #cbdde2;
            border-radius: 48px;
            font-family: 'SF Mono', 'Fira Code', monospace;
            transition: all 0.2s;
            letter-spacing: 0.3px;
        }

        .code-input:focus {
            outline: none;
            border-color: #2c7a6e;
            box-shadow: 0 0 0 3px rgba(44, 122, 110, 0.2);
        }

        /* стили автокомплита (datalist) */
        datalist {
            background: white;
            border-radius: 20px;
            font-family: monospace;
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
            box-shadow: 0 1px 2px rgba(0,0,0,0.02);
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
        <p>Введите код дилерского центра (например, EURUS06200) — отобразятся логин и пароль для входа на портал оценки качества</p>
    </div>

    <div class="access-body">
        <div class="search-area">
            <label>🔑 Код дилерского центра (ДЦ)</label>
            <div class="search-wrapper">
                <input type="text" id="dcCodeInput" class="code-input" 
                       placeholder="Начните вводить код: EURUS, 06200..." 
                       list="dcCodesList" autocomplete="off">
                <datalist id="dcCodesList"></datalist>
                <div class="hint-text">💡 Подсказка: можно вводить часть кода — выберите нужный из выпадающих подсказок</div>
            </div>
        </div>

        <div id="dynamicAccessPanel">
            <div class="placeholder-box" id="placeholderMsg">
                🔐 Введите или выберите код ДЦ из подсказок, чтобы получить учётные данные для портала «Тайный покупатель»<br>
                (логин + пароль)
            </div>
            <div id="credentialCard" style="display: none;"></div>
        </div>
        <div class="footer-note">
            ⚡ Данные соответствуют выгрузке «Доступы на портал (002)» — логины и пароли для сервисного доступа.
        </div>
    </div>
</div>

<script>
    // ---------- ПОЛНЫЙ СПРАВОЧНИК КОДОВ ДЦ (ключ -> данные: логин, пароль, холдинг, название, регион, город) ----------
    const dcAccessData = {
        "EURUS06199": { login: "wsve", password: "wsve65", holding: "Фреш", name: "Чанган Центр FRESH Волгоград", region: "ЮФО", city: "Волгоград" },
        "EURUS06200": { login: "fdhu", password: "fdhu1", holding: "Фреш", name: "Чанган Центр FRESH Воронеж", region: "ЦФО", city: "Воронеж" },
        "EURUS06213": { login: "dgsx", password: "dgsx34", holding: "Major", name: "Чанган Центр Олимп", region: "СЗФО", city: "Санкт-Петербург" },
        "EURUS06214": { login: "iter", password: "iter34", holding: "Major", name: "Чанган Центр Мэйджор Светлановский", region: "СЗФО", city: "Санкт-Петербург" },
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
        "EURUS06403": { login: "bbtt", password: "bbtt95", holding: "Ринг Авто", name: "Чанган Центр Ринг Авто", region: "ЦФО", city: "Липецк" }
    };

    // DOM элементы
    const inputElement = document.getElementById('dcCodeInput');
    const datalistElement = document.getElementById('dcCodesList');
    const placeholderDiv = document.getElementById('placeholderMsg');
    const cardContainer = document.getElementById('credentialCard');

    // Заполняем datalist всеми кодами (для подсказок при вводе)
    const allCodes = Object.keys(dcAccessData).sort();
    allCodes.forEach(code => {
        const option = document.createElement('option');
        option.value = code;
        // Добавляем дополнительную подпись для удобства (показываем название центра рядом)
        const center = dcAccessData[code];
        option.textContent = `${code} — ${center.name.substring(0, 60)}`;
        datalistElement.appendChild(option);
    });

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

    // Обновление информации по введённому коду
    function updateByCode(rawCode) {
        let trimmedCode = rawCode ? rawCode.trim() : '';
        // Прямое совпадение с ключом
        if (trimmedCode && dcAccessData[trimmedCode]) {
            const data = dcAccessData[trimmedCode];
            const cardHtml = renderAccessCard(trimmedCode, data);
            cardContainer.innerHTML = cardHtml;
            cardContainer.style.display = 'block';
            placeholderDiv.style.display = 'none';
            
            // Назначаем копирование
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
            // Если код не найден или пустой — показываем плейсхолдер
            cardContainer.style.display = 'none';
            placeholderDiv.style.display = 'flex';
            if (trimmedCode && !dcAccessData[trimmedCode]) {
                placeholderDiv.innerHTML = `❌ Код "${trimmedCode}" не найден в справочнике. <br> Проверьте ввод или выберите код из подсказок.`;
            } else {
                placeholderDiv.innerHTML = `🔐 Введите или выберите код ДЦ из подсказок, чтобы получить учётные данные для портала «Тайный покупатель»<br>(логин + пароль)`;
            }
        }
    }

    // Обработка выбора из datalist (браузер сам подставляет значение)
    inputElement.addEventListener('input', (e) => {
        const value = e.target.value;
        // Если значение в точности совпадает с одним из кодов (с учётом регистра)
        if (dcAccessData[value]) {
            updateByCode(value);
        } else {
            // Если не совпадает, но пользователь что-то ввел — не показываем ошибку до потери фокуса? 
            // Потеря фокуса обработаем в blur, но при инпуте если пусто — сброс.
            if (value === '') {
                updateByCode('');
            } else {
                // Для частичного ввода не сбрасываем карточку мгновенно, но если ранее был выбран центр и пользователь стирает — сбросим.
                // Но лучше показать, что точного совпадения нет. Вызовем updateByCode, который покажет "не найден" только при точном несовпадении? 
                // Сделаем: если введённая строка не является кодом - показываем плейсхолдер.
                if (!dcAccessData[value]) {
                    cardContainer.style.display = 'none';
                    placeholderDiv.style.display = 'flex';
                    placeholderDiv.innerHTML = `🔎 Нет точного совпадения с кодом "${value}". Введите код из списка подсказок.`;
                }
            }
        }
    });

    // При потере фокуса дополнительная проверка — вдруг пользователь ввёл код вручную без datalist
    inputElement.addEventListener('blur', () => {
        const val = inputElement.value.trim();
        if (val && dcAccessData[val]) {
            updateByCode(val);
        } else if (val && !dcAccessData[val]) {
            cardContainer.style.display = 'none';
            placeholderDiv.style.display = 'flex';
            placeholderDiv.innerHTML = `❌ Код "${val}" не найден. Используйте точный код из справочника (например, EURUS06200).`;
        } else {
            updateByCode('');
        }
    });

    // Инициализация: показываем плейсхолдер
    updateByCode('');
</script>
</body>
</html>
