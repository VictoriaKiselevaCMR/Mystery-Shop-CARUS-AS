
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Доступы на портал</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400..700&display=swap" rel="stylesheet">
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
            letter-spacing: 0.3px;
            min-width: 200px;
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
            background: #f0f6f4;
            padding: 6px 12px;
            border-radius: 40px;
            display: inline-block;
        }

        .example-block {
            background: #f4faf8;
            border-radius: 1rem;
            padding: 12px 16px;
            margin-top: 12px;
            font-size: 0.8rem;
            color: #2c6b5c;
            border-left: 4px solid #2c7a6e;
        }

        .example-block strong {
            color: #1a5c4e;
        }

        .example-block code {
            background: #e0eee7;
            padding: 2px 8px;
            border-radius: 4px;
            font-family: 'SF Mono', monospace;
            font-size: 0.8rem;
        }

        .access-card {
            background: #fefef7;
            border-radius: 1.8rem;
            border: 1px solid #e0ede8;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.03);
            animation: fadeIn 0.25s ease;
            margin-bottom: 20px;
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

        .dual-access {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .access-entry {
            border-bottom: 1px solid #e8f0ec;
            padding-bottom: 16px;
            margin-bottom: 16px;
        }

        .access-entry:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }

        .access-entry .credential-block {
            border-color: #e0ede8;
        }

        @media (max-width: 640px) {
            .dual-access {
                grid-template-columns: 1fr;
            }
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
            🔐 Доступы на портал
            <span>CS / UNI</span>
        </h1>
        <p>Поиск по коду дилерского центра и городу</p>
    </div>

    <div class="access-body">
        <div class="search-area">
            <label>🔑 Код ДЦ и город</label>
            <div class="input-group">
                <input type="text" id="dcCodeInput" class="code-input" 
                       placeholder="EURUS06200 | Воронеж" 
                       autocomplete="off" spellcheck="false">
                <button id="showAccessBtn" class="show-btn">🔓 Показать доступ</button>
            </div>
            <div class="example-block">
                <strong>📌 Пример правильного ввода:</strong><br>
                • <code>EURUS06200 | Воронеж</code>
            </div>
            <div class="hint-text">
                💡 Формат: <strong>КОД_ДЦ | ГОРОД</strong> (вертикальная черта с пробелами). Город указывайте точно как указано на портале DNM.
            </div>
        </div>

        <div id="dynamicAccessPanel">
            <div class="placeholder-box" id="placeholderMsg">
                🔐 Введите код ДЦ и город в формате «КОД | ГОРОД» и нажмите «Показать доступ»
            </div>
            <div id="credentialCard" style="display: none;"></div>
        </div>
        <div class="footer-note">
            ⚡ Полная база: все коды ДЦ из официальной выгрузки. Доступ возможен только при совпадении кода И города.
        </div>
    </div>
</div>

<script>
    // ----- ДАННЫЕ (полностью из таблицы) -----
    const data = [
        { code: "EURUS06199", title: "Чанган Центр FRESH Волгоград", region: "ЮФО", city: "Волгоград", address: "400010, Волгоградская область, г. Волгоград, пр-кт. Им. маршала Советского Союза Г.К. Жукова, д. 94д", service: "wsve", servicePwd: "wsve65", sales: "pohf", salesPwd: "pohf16" },
        { code: "EURUS06200", title: "Чанган Центр FRESH Воронеж", region: "ЦФО", city: "Воронеж", address: "396005, Воронежская обл., р-н Рамонский, Солнечный п., Московское шоссе ул., 16", service: "fdhu", servicePwd: "fdhu1", sales: "hswr", salesPwd: "hswr2" },
        { code: "EURUS06213", title: "Чанган Центр Олимп", region: "СЗФО", city: "Санкт-Петербург", address: "191167, г. Санкт-Петербург, ул.Исполкомская, д.15А", service: "dgsx", servicePwd: "dgsx34", sales: "wsat", salesPwd: "wsat87" },
        { code: "EURUS06214", title: "Чанган Центр Мэйджор Светлановский", region: "СЗФО", city: "Санкт-Петербург", address: "194223, г. Санкт-Петербург, ул. Орбели , д.35", service: "iter", servicePwd: "iter34", sales: "edcv", salesPwd: "edcv32" },
        { code: "EURUS06214", title: "Юни Центр Мэйджор Светлановский", region: "СЗФО", city: "Санкт-Петербург", address: "194223, г. Санкт-Петербург, ул. Орбели , д.35, литера Ж", service: "gfdy", servicePwd: "gfdy43", sales: "tcvd", salesPwd: "tcvd76" },
        { code: "EURUS06215", title: "Чанган Центр Мэйджор", region: "ЦФО", city: "Москва", address: "123007, г. Москва, 1-я Магистральная ул., дом 13, строение 1", service: "brde", servicePwd: "brde32", sales: "lkrt", salesPwd: "lkrt76" },
        { code: "EURUS06232", title: "Чанган Центр Мэйджор Сити", region: "ЦФО", city: "Москва", address: "143420, Московская обл., г. Красногорск, д. Михалково, М9 Балтия дор., строение 2", service: "irws", servicePwd: "irws18", sales: "gcmu", salesPwd: "gcmu44" },
        { code: "EURUS06237", title: "Чанган Центр Мэйджор Запад", region: "ЦФО", city: "Москва", address: "142784, г.Москва, п. Московский, д. Говорово, МКАД 47км, д.8, стр.1", service: "lbdh", servicePwd: "lbdh33", sales: "mnre", salesPwd: "mnre47" },
        { code: "EURUS06238", title: "Чанган Центр Мэйджор Юг", region: "ЦФО", city: "Москва", address: "140091, Московская область, г. Дзержинский, ул. Алексеевская, д.8", service: "glcx", servicePwd: "glcx99", sales: "awrq", salesPwd: "awrq90" },
        { code: "EURUS06239", title: "Чанган Центр Мэйджор Тушино", region: "ЦФО", city: "Москва", address: "125363, г.Москва, Цветочный проезд, д.6", service: "xztr", servicePwd: "xztr18", sales: "mbsd", salesPwd: "mbsd55" },
        { code: "EURUS06250", title: "Юни Центр Мэйджор Север", region: "ЦФО", city: "Москва", address: "141014, Московская область, г. Мытищи, ул. Красноармейская, вл.39, стр.1, МКАД 92-й км", service: "riop", servicePwd: "riop41", sales: "sare", salesPwd: "sare94" },
        { code: "EURUS06297", title: "Чанган Центр Мэйджор Строгино", region: "ЦФО", city: "Москва", address: "123458 г. Москва, ул. Маршала Прошлякова , д.13", service: "vblo", servicePwd: "vblo54", sales: "qazd", salesPwd: "qazd83" },
        { code: "EURUS06293", title: "Чанган Центр ТрансТехСервис", region: "ПФО", city: "Набережные Челны", address: "423800, Респ. Татарстан, г. Набережные Челны, ул. Машиностроительная, дом 1/2", service: "xsxd", servicePwd: "xsxd37", sales: "fofw", salesPwd: "fofw75" },
        { code: "EURUS06318", title: "Чанган Центр ТрансТехСервис Уфа", region: "ПФО", city: "Уфа", address: "450018, Респ. Башкортостан, г. Уфа, ул. Рубежная, дом 182", service: "oier", servicePwd: "oier49", sales: "dspo", salesPwd: "dspo33" },
        { code: "EURUS06330", title: "Чанган Центр ТрансТехСервис Казань Декабристов", region: "ПФО", city: "Казань", address: "420034, Респ. Татарстан, г. Казань, ул. Декабристов, дом 81В", service: "ghye", servicePwd: "ghye70", sales: "bidx", salesPwd: "bidx62" },
        { code: "EURUS06363", title: "Чанган Центр ТрансТехСервис Ижевск", region: "ПФО", city: "Ижевск", address: "426003, Удмуртская Респ., г. Ижевск, ул. Карла Маркса, дом 89", service: "pyws", servicePwd: "pyws63", sales: "savb", salesPwd: "savb11" },
        { code: "EURUS06376", title: "Чанган Центр ТрансТехСервис Нижнекамск", region: "ПФО", city: "Нижнекамск", address: "423577, Республика Татарстан, г. Нижнекамск, ул. Спортивная, д. 4", service: "pilx", servicePwd: "pilx32", sales: "lksa", salesPwd: "lksa41" },
        { code: "EURUS06384", title: "Чанган Центр ТрансТехСервис Мамадышский", region: "ПФО", city: "Казань", address: "420083, Респ. Татарстан, г. Казань, ул. Мамадышский Тракт, дом 30", service: "slvw", servicePwd: "slvw90", sales: "dqal", salesPwd: "dqal33" },
        { code: "EURUS06216", title: "Чанган Центр Автомир на Щелковском", region: "ЦФО", city: "Москва", address: "107497, г. Москва, ул. Иркутская, д. 5/6, строение 1, помещение 321", service: "zazt", servicePwd: "zazt54", sales: "fdcc", salesPwd: "fdcc99" },
        { code: "EURUS06217", title: "Чанган Центр Автомир на Дмитровском", region: "ЦФО", city: "Москва", address: "127247 г. Москва, Дмитровское шоссе, дом 98 стр.1", service: "vbds", servicePwd: "vbds37", sales: "epyt", salesPwd: "epyt59" },
        { code: "EURUS06309", title: "Чанган Центр Автомир на Дунайском", region: "СЗФО", city: "Санкт-Петербург", address: "196158, г. Санкт-Петербург, Дунайский проспект, дом 25/3, лит.А", service: "tvcv", servicePwd: "tvcv39", sales: "qazc", salesPwd: "qazc31" },
        { code: "EURUS06340", title: "Чанган Центр Автомир", region: "ЦФО", city: "Брянск", address: "241019, Брянская обл., г. Брянск, Станке Димитрова пр-кт, дом 114", service: "spre", servicePwd: "spre11", sales: "dplk", salesPwd: "dplk93" },
        { code: "EURUS06341", title: "Чанган Центр Автомир на Петухова", region: "СФО", city: "Новосибирск", address: "630119, Новосибирская обл., г. Новосибирск, ул. Петухова, дом 87", service: "dpiq", servicePwd: "dpiq09", sales: "jpew", salesPwd: "jpew04" },
        { code: "EURUS06369", title: "Чанган Центр Автомир Люблино", region: "ЦФО", city: "Москва", address: "109559, г. Москва, Ставропольская ул., дом 41", service: "frwa", servicePwd: "frwa36", sales: "zpkd", salesPwd: "zpkd91" },
        { code: "EURUS06267", title: "Чанган Центр Дельта Моторс", region: "ЮФО", city: "Ростов-на-Дону", address: "344015, Ростовская обл., г. Ростов-на-Дону, ул. Малиновского, дом 172/3а", service: "drtq", servicePwd: "drtq33", sales: "fedp", salesPwd: "fedp32" },
        { code: "EURUS06268", title: "Чанган Центр Сокол Моторс Таганрог", region: "ЮФО", city: "Таганрог", address: "347942, Ростовская обл., г. Таганрог, Ростовское ш., дом 10а, строение 2", service: "qasd", servicePwd: "qasd58", sales: "dlob", salesPwd: "dlob49" },
        { code: "EURUS06269", title: "Чанган Центр Сокол Моторс Шолохова", region: "ЮФО", city: "Ростов-на-Дону", address: "344009, г. Ростов-на-Дону, ул. Шолохова, 235", service: "cmnb", servicePwd: "cmnb05", sales: "dewq", salesPwd: "dewq85" },
        { code: "EURUS06300", title: "Чанган Центр Сокол Моторс Шахты", region: "ЮФО", city: "Шахты", address: "346513, Ростовская область, г. Шахты, ул.Дачная, 272Б", service: "uohg", servicePwd: "uohg66", sales: "rpit", salesPwd: "rpit16" },
        { code: "EURUS06301", title: "Чанган Центр Сокол Моторс Волгодонск", region: "ЮФО", city: "Волгодонск", address: "347375, г. Ростовская область, г. Волгодонск, пр-т Курчатова, 50В", service: "jknc", servicePwd: "jknc12", sales: "dews", salesPwd: "dews43" },
        { code: "EURUS06223", title: "Юни Центр Санрайз Групп", region: "ЦФО", city: "Москва", address: "141402, Московская область, г. Химки, Ленинградское шоссе, вл. 15", service: "sgfr", servicePwd: "sgfr48", sales: "qper", salesPwd: "qper77" },
        { code: "EURUS06359", title: "Юни Центр Санрайз Групп", region: "СЗФО", city: "Мурманск", address: "183034, Мурманская обл., г. Мурманск, Домостроительная ул., дом 16", service: "dfpa", servicePwd: "dfpa17", sales: "erlk", salesPwd: "erlk09" },
        { code: "EURUS06345", title: "Чанган Центр Вологда", region: "СЗФО", city: "Вологда", address: "160028, г. Вологда, Окружное ш., дом 8а", service: "zxuy", servicePwd: "zxuy22", sales: "wpbf", salesPwd: "wpbf00" },
        { code: "EURUS06221", title: "Чанган Центр Вагнер", region: "СЗФО", city: "Санкт-Петербург", address: "198205, г. Санкт-Петербург, Таллинское ш. (Старо-Паново тер.), д. 157, лит. А.", service: "clue", servicePwd: "clue43", sales: "sprw", salesPwd: "sprw31" },
        { code: "EURUS06316", title: "Чанган Центр Вагнер Выборгский", region: "СЗФО", city: "Санкт-Петербург", address: "194362, г. Санкт-Петербург, Выборгское ш., дом 352, литера А", service: "srqp", servicePwd: "srqp97", sales: "cvye", salesPwd: "cvye04" },
        { code: "EURUS06351", title: "Чанган Центр Окружная", region: "СЗФО", city: "Калининград", address: "236009, Калининградская обл., г. Калининград, ул. Большая Окружная, дом 19", service: "erty", servicePwd: "erty05", sales: "ohvr", salesPwd: "ohvr83" },
        { code: "EURUS06224", title: "Чанган Центр Оптима Краснодар", region: "ЮФО", city: "Краснодар", address: "350051, Краснодарский край, г.Краснодар, ул. им. Дзержинского, д. 229/5", service: "lbvd", servicePwd: "lbvd71", sales: "kloc", salesPwd: "kloc03" },
        { code: "EURUS06228", title: "Чанган Центр Оптима Сочи", region: "ЮФО", city: "Сочи", address: "354003, Краснодарский край, г. Сочи, ул. Конституции СССР, 48", service: "sdrq", servicePwd: "sdrq21", sales: "ertq", salesPwd: "ertq08" },
        { code: "EURUS06252", title: "Чанган Центр ГК АсАвто Тольятти", region: "ПФО", city: "Тольятти", address: "445140, Тольятти, с. Тифомеевка, ул.Солнечная 1а", service: "gfda", servicePwd: "gfda78", sales: "sadu", salesPwd: "sadu43" },
        { code: "EURUS06338", title: "Чанган Центр Автобан", region: "УФО", city: "Екатеринбург", address: "620091, Свердловская обл., г. Екатеринбург, ул. Бабушкина, дом 9", service: "zxcm", servicePwd: "zxcm33", sales: "dotw", salesPwd: "dotw08" },
        { code: "EURUS06289", title: "Чанган Центр Новомосковск", region: "ЦФО", city: "Новомосковск", address: "301657, г. Новомосковск, ул. Космонавтов,  д. 37Д", service: "swql", servicePwd: "swql55", sales: "erti", salesPwd: "erti00" },
        { code: "EURUS06328", title: "Чанган Центр Агат на Комсомольском", region: "ПФО", city: "Нижний Новгород", address: "603028, Нижегородская обл., г. Нижний Новгород, Комсомольское ш., дом 7В", service: "dfpo", servicePwd: "dfpo11", sales: "vcjs", salesPwd: "vcjs22" },
        { code: "EURUS06282", title: "Чанган Центр АвтоЮг", region: "ЮФО", city: "Ставрополь", address: "355042, г. Ставрополь, ул. Доваторцев, д. 62", service: "sdpo", servicePwd: "sdpo33", sales: "vmzg", salesPwd: "vmzg44" },
        { code: "EURUS06355", title: "Чанган Центр Юг-Авто", region: "ЮФО", city: "Краснодар", address: "385100, Респ. Адыгея, Тахтамукайский р-н, Тахтамукай аул, ул. Краснодарская, дом 3", service: "wnbs", servicePwd: "wnbs67", sales: "lktr", salesPwd: "lktr98" },
        { code: "EURUS06263", title: "Чанган Центр АвтоГЕРМЕС", region: "ЦФО", city: "Москва", address: "121471, г. Москва, Рябиновая ул., д. 43Б", service: "dfpp", servicePwd: "dfpp55", sales: "dpyy", salesPwd: "dpyy33" },
        { code: "EURUS06292", title: "Чанган Центр Чебоксары", region: "ПФО", city: "Чебоксары", address: "428030, Чувашская Республика - Чувашия, Чебоксарский р-н, д. Пихтулино, ул. Автомобилистов, дом 2", service: "xlmn", servicePwd: "xlmn77", sales: "fcal", salesPwd: "fcal81" },
        { code: "EURUS06285", title: "Чанган Центр Автоимпорт", region: "ЦФО", city: "Тула", address: "300022, Тульская обл., г. Тула, ул. Октябрьская, дом 320А/1", service: "dfcx", servicePwd: "dfcx65", sales: "iuqw", salesPwd: "iuqw29" },
        { code: "EURUS06286", title: "Чанган Центр Автоимпорт Юг", region: "ЦФО", city: "Рязань", address: "390047, г. Рязань, ул. Куйбышевское шоссе, 42В", service: "fpqm", servicePwd: "fpqm01", sales: "oiqa", salesPwd: "oiqa05" },
        { code: "EURUS06326", title: "Чанган Центр на Гагарина", region: "ПФО", city: "Нижний Новгород", address: "603057, Нижегородская обл., г. Нижний Новгород, пр-кт Гагарина, дом 29д", service: "linw", servicePwd: "linw88", sales: "fgbr", salesPwd: "fgbr06" },
        { code: "EURUS06191", title: "Чанган Центр Автокласс", region: "ЦФО", city: "Тула", address: "300045, Тульская обл., г. Тула, Новомосковское ш., дом 27, офис 1", service: "nbxc", servicePwd: "nbxc32", sales: "mnbw", salesPwd: "mnbw26" },
        { code: "EURUS06236", title: "Чанган Центр ААА Моторс", region: "ЮФО", city: "Ростов-на-Дону", address: "344000, Ростовская обл., г. Ростов-на-Дону, ул.Текучева, д.352 Б", service: "vfys", servicePwd: "vfys91", sales: "yucv", salesPwd: "yucv66" },
        { code: "EURUS06305", title: "Чанган Центр Максимум", region: "СЗФО", city: "Санкт-Петербург", address: "188669, Ленинградская обл., Всеволожский муниципальный район, Муринское городское поселение, территория Транспортная, дом 6", service: "pjvc", servicePwd: "pjvc33", sales: "rtbv", salesPwd: "rtbv87" },
        { code: "EURUS06281", title: "Чанган Центр БЦР Моторс", region: "ПФО", city: "Нижний Новгород", address: "603058, г. Нижний Новгород, ул. Новикова-Прибоя, 4", service: "ghlk", servicePwd: "ghlk54", sales: "dfgm", salesPwd: "dfgm90" },
        { code: "EURUS06279", title: "Чанган Центр Арена Авто", region: "ПФО", city: "Тольятти", address: "445043, Самарская область,  г. Тольятти, Южное шоссе, 32", service: "demj", servicePwd: "demj97", sales: "zxbv", salesPwd: "zxbv30" },
        { code: "EURUS06145", title: "Чанган Центр Автолига", region: "ПФО", city: "Нижний Новгород", address: "603124, Нижегородская обл., г. Нижний Новгород, Московское ш., дом 302, корпус Г", service: "pmnf", servicePwd: "pmnf11", sales: "cvcs", salesPwd: "cvcs77" },
        { code: "EURUS06173", title: "Чанган Центр Софийская", region: "СЗФО", city: "Санкт-Петербург", address: "192102, г. Санкт-Петербург, ул. Софийская, дом 2", service: "gfmn", servicePwd: "gfmn80", sales: "zxxr", salesPwd: "zxxr29" },
        { code: "EURUS06211", title: "Чанган Центр Агат", region: "ЮФО", city: "Волгоград", address: "400048, Волгоградская обл., г. Волгоград, Авиаторов ш., дом 2А", service: "sopz", servicePwd: "sopz60", sales: "zzsp", salesPwd: "zzsp81" },
        { code: "EURUS06242", title: "Чанган Центр АСПЭК-Авто", region: "ПФО", city: "Ижевск", address: "426072 г. Ижевск, ул. Союзная, д. 2Д/1", service: "xpre", servicePwd: "xpre07", sales: "pwet", salesPwd: "pwet09" },
        { code: "EURUS06242", title: "Юни Центр АСПЭК-Авто", region: "ПФО", city: "Ижевск", address: "426072 г. Ижевск, ул. Союзная, д. 2Д/2", service: "phbd", servicePwd: "phbd84", sales: "yyhc", salesPwd: "yyhc71" },
        { code: "EURUS06280", title: "Чанган Центр Темп Авто Ростов-на-Дону", region: "ЮФО", city: "Ростов-на-Дону", address: "346720, Ростовская обл., Аксайский р-н, г. Аксай, Западная ул., дом 37, корпус В", service: "gfdb", servicePwd: "gfdb08", sales: "gfqq", salesPwd: "gfqq99" },
        { code: "EURUS06069", title: "Чанган Центр Базис Пермякова", region: "УФО", city: "Тюмень", address: "625051 г. Тюмень, Пермякова, 19", service: "hgvv", servicePwd: "hgvv40", sales: "coww", salesPwd: "coww81" },
        { code: "EURUS06306", title: "Чанган Центр Ринг Воронеж", region: "ЦФО", city: "Воронеж", address: "394033, г. Воронеж, ул. Изыскателей, д.39, корп.2", service: "dfoe", servicePwd: "dfoe72", sales: "vcdd", salesPwd: "vcdd63" },
        { code: "EURUS06403", title: "Чанган Центр Ринг Авто", region: "ЦФО", city: "Липецк", address: "398008, Липецкая обл., г. Липецк, ул. 50 лет НЛМК, строение 24", service: "bbtt", servicePwd: "bbtt95", sales: "pksd", salesPwd: "pksd11" },
        { code: "EURUS06329", title: "Чанган Центр Авторай", region: "ПФО", city: "Ульяновск", address: "432067, Ульяновская обл., г. Ульяновск, ул. Алексея Наганова, дом 14", service: "dcur", servicePwd: "dcur73", sales: "gvxx", salesPwd: "gvxx24" },
        { code: "EURUS06147", title: "Чанган Центр Лидер", region: "ЦФО", city: "Рязань", address: "390020  г. Рязань, Московское шоссе, д.65в", service: "jgff", servicePwd: "jgff77", sales: "vvew", salesPwd: "vvew66" },
        { code: "EURUS06288", title: "Чанган Центр АГАТ Аэропорт", region: "ЮФО", city: "Астрахань", address: "414018, Астраханская область, г. Астрахань, ул. Аэропортовское шоссе, д. 73", service: "grsl", servicePwd: "grsl45", sales: "fsoo", salesPwd: "fsoo29" },
        { code: "EURUS06347", title: "Чанган Центр Автопортрет", region: "СЗФО", city: "Санкт-Петербург", address: "197374, г. Санкт-Петербург, ул. Школьная, дом 75, корпус 2, лит. А", service: "ojvd", servicePwd: "ojvd05", sales: "toof", salesPwd: "toof78" },
        { code: "EURUS06251", title: "Чанган Центр Агат Ярославль", region: "ЦФО", city: "Ярославль", address: "150044, Ярославская обл., г. Ярославль, ш. Промышленное, д. 53", service: "xxoi", servicePwd: "xxoi43", sales: "iihf", salesPwd: "iihf66" },
        { code: "EURUS06248", title: "Чанган Центр Новокар", region: "ЮФО", city: "Новороссийск", address: "353960, Краснодарский край, г.о. г. Новороссийск, г. Новороссийск, тер. Цемдолина, ул. Золотая Рыбка, дом 112", service: "nbrf", servicePwd: "nbrf05", sales: "wslb", salesPwd: "wslb63" },
        { code: "EURUS06229", title: "Чанган Центр Саранск", region: "ПФО", city: "Саранск", address: "430014, Респ. Мордовия, г.о. Саранск, г. Саранск, ул. Волгоградская, д. 91", service: "sdec", servicePwd: "sdec47", sales: "ppoi", salesPwd: "ppoi81" },
        { code: "EURUS06337", title: "Чанган Центр Квазар", region: "ЦФО", city: "Москва", address: "142715, Московская область, Ленинский район, сельское поселение Совхоз им. Ленина, 26 км. МКАД, владение 5, строение 4", service: "eglg", servicePwd: "eglg03", sales: "innd", salesPwd: "innd50" },
        { code: "EURUS06299", title: "Чанган Центр КАН АВТО", region: "ПФО", city: "Казань", address: "420064, Респ. Татарстан, г. Казань, ул. Оренбургский Тракт, дом 209в", service: "ooes", servicePwd: "ooes60", sales: "kmcc", salesPwd: "kmcc44" },
        { code: "EURUS06149", title: "Чанган Центр Автосити", region: "ЦФО", city: "Воронеж", address: "394065, г. Воронеж, Проспект Патриотов, д.47", service: "zlmf", servicePwd: "zlmf73", sales: "gcla", salesPwd: "gcla33" },
        { code: "EURUS06325", title: "Чанган Центр Уникум", region: "УФО", city: "Нижний Тагил", address: "620049, г. Нижний Тагил, Черноисточинское шоссе, дом 74 А", service: "sdoj", servicePwd: "sdoj66", sales: "uutr", salesPwd: "uutr48" },
        { code: "EURUS06193", title: "Чанган Центр Автофорум Восток", region: "ПФО", city: "Саратов", address: "410018 г. Саратов, ул. Усть-Курдюмская, д. 33", service: "ggdd", servicePwd: "ggdd53", sales: "lljj", salesPwd: "lljj54" },
        { code: "EURUS06187", title: "Чанган Центр Регинас Магнитогорск", region: "УФО", city: "Магнитогорск", address: "455008, г. Магнитогорск, ул. Зеленый Лог, 53", service: "jgrc", servicePwd: "jgrc76", sales: "xoes", salesPwd: "xoes69" },
        { code: "EURUS06201", title: "Чанган Центр Регинас на Кашириных", region: "УФО", city: "Челябинск", address: "454003, г. Челябинск, ул. Братьев Кашириных, 141А", service: "vvoo", servicePwd: "vvoo40", sales: "xord", salesPwd: "xord42" },
        { code: "EURUS06201", title: "Юни Центр Регинас на Кашириных", region: "УФО", city: "Челябинск", address: "454003, г. Челябинск, ул. Братьев Кашириных, 141Б", service: "ihcv", servicePwd: "ihcv44", sales: "sljf", salesPwd: "sljf65" },
        { code: "EURUS06202", title: "Чанган Центр Регинас на Гурзуфской", region: "УФО", city: "Екатеринбург", address: "620102, г. Екатеринбург, ул. Гурзуфская, 63", service: "dhre", servicePwd: "dhre11", sales: "ekgf", salesPwd: "ekgf15" },
        { code: "EURUS06203", title: "Чанган Центр Регинас Миасс", region: "УФО", city: "Миасс", address: "456320, г. Миасс, Тургоякское шоссе, 3/19", service: "bbed", servicePwd: "bbed28", sales: "oifn", salesPwd: "oifn12" },
        { code: "EURUS06245", title: "Чанган Центр Регинас на Свердловском", region: "УФО", city: "Челябинск", address: "454008, г. Челябинск, Свердловский Тракт, 5", service: "bflo", servicePwd: "bflo19", sales: "vusu", salesPwd: "vusu14" },
        { code: "EURUS06254", title: "Чанган Центр Регинас на Высоцкого", region: "УФО", city: "Екатеринбург", address: "620072, г. Екатеринбург, ул. Высоцкого, 3", service: "uhdd", servicePwd: "uhdd55", sales: "ssoi", salesPwd: "ssoi51" },
        { code: "EURUS06398", title: "Чанган Центр Регинас на Ленина", region: "УФО", city: "Челябинск", address: "454007, г. Челябинск, проспект Ленина, д. 19Д", service: "srec", servicePwd: "srec11", sales: "pnnd", salesPwd: "pnnd12" },
        { code: "EURUS06304", title: "Чанган Центр АвтоФорум", region: "ПФО", city: "Саратов", address: "410020 г. Саратов, ул. им. Шехурдина А.П., д.6, К.6", service: "zasz", servicePwd: "zasz13", sales: "cfee", salesPwd: "cfee16" },
        { code: "EURUS06246", title: "Чанган Центр Фастар на Речном", region: "СФО", city: "Новосибирск", address: "630009, Новосибирская область, г. Новосибирск, ул. Большевистская , дом  14/2", service: "bbge", servicePwd: "bbge21", sales: "reoj", salesPwd: "reoj99" },
        { code: "EURUS06311", title: "Чанган Центр ДАВ-АВТО", region: "ПФО", city: "Пермь", address: "614025, Пермский край, г. Пермь, ул. Героев Хасана, дом 76", service: "wwjb", servicePwd: "wwjb33", sales: "qpgd", salesPwd: "qpgd55" },
        { code: "EURUS06150", title: "Чанган Центр АЦ Кунцево", region: "ЦФО", city: "Москва", address: "143025, Московская обл., г. Одинцово, с. Немчиновка, ул. Московская, дом 61", service: "rtdd", servicePwd: "rtdd77", sales: "bbdc", salesPwd: "bbdc96" },
        { code: "EURUS06137", title: "Чанган Центр Экспокар Краснодар", region: "ЮФО", city: "Краснодар", address: "385140, Россия, Ресублика Адыгея, Тахтамукайский район, пгт Яблоновский, ул. Тургеневское шоссе 31", service: "hhgw", servicePwd: "hhgw84", sales: "jbdd", salesPwd: "jbdd66" },
        { code: "EURUS06344", title: "Чанган Центр Автоград", region: "УФО", city: "Тюмень", address: "625014, Тюменская обл., г. Тюмень, ул. Республики, дом 280", service: "gedd", servicePwd: "gedd81", sales: "iydd", salesPwd: "iydd42" },
        { code: "EURUS06255", title: "Чанган Центр Самара-Авто", region: "ПФО", city: "Самара", address: "443125, г. Самара, ул. Московское шоссе, 264", service: "gcsx", servicePwd: "gcsx83", sales: "iydf", salesPwd: "iydf77" },
        { code: "EURUS06287", title: "Чанган Центр Энгельс", region: "ПФО", city: "Энгельс", address: "413112, Саратовская обл., г. Энгельс, проспект Волжский, здание 75, Литера А", service: "dduu", servicePwd: "dduu99", sales: "ygvc", salesPwd: "ygvc44" },
        { code: "EURUS06270", title: "Чанган Центр Темп Авто", region: "ЮФО", city: "Краснодар", address: "350010, Краснодарский край, г. Краснодар, ул. Ростовское шоссе, 12/6", service: "yfsd", servicePwd: "yfsd33", sales: "jjhd", salesPwd: "jjhd65" },
        { code: "EURUS06154", title: "Чанган Центр Барнаул", region: "СФО", city: "Барнаул", address: "656067, Алтайский край,  г. Барнаул, проезд Северный Власихинский, д. 65", service: "ddoo", servicePwd: "ddoo29", sales: "brph", salesPwd: "brph70" },
        { code: "EURUS06400", title: "Юни Центр Барнаул", region: "СФО", city: "Барнаул", address: "656006, Алтайский край, г. Барнаул, ул. Малахова, д. 94А", service: "trnb", servicePwd: "trnb00", sales: "zxwp", salesPwd: "zxwp08" },
        { code: "EURUS06013", title: "Чанган Центр Альметьевск", region: "ПФО", city: "Альметьевск", address: "423454, г. Альметьевск, ул. Геофизическая, 58/2", service: "sdom", servicePwd: "sdom13", sales: "xxpp", salesPwd: "xxpp82" },
        { code: "EURUS06107", title: "Чанган Центр Диалог Авто", region: "ПФО", city: "Казань", address: "420004, г. Казань, Горьковское шоссе, д. 47, к.1, офис 101", service: "hgvs", servicePwd: "hgvs23", sales: "diop", salesPwd: "diop68" },
        { code: "EURUS06256", title: "Чанган Центр АсАвто Юг", region: "ПФО", city: "Самара", address: "443085, Самарская обл., г. Самара, Южное шоссе, 10", service: "eiyt", servicePwd: "eiyt48", sales: "bvdq", salesPwd: "bvdq11" },
        { code: "EURUS06061", title: "Чанган Центр Демидыч Пермь", region: "ПФО", city: "Пермь", address: "614060, г. Пермь, ул. Уральская, д. 119", service: "aaiu", servicePwd: "aaiu65", sales: "cdoo", salesPwd: "cdoo83" },
        { code: "EURUS06261", title: "Чанган Центр Демидыч Уфа", region: "ПФО", city: "Уфа", address: "450032, г. Уфа, ул. Дмитрия Донского, д. 53", service: "hecb", servicePwd: "hecb39", sales: "wlvq", salesPwd: "wlvq22" },
        { code: "EURUS06261", title: "Юни Центр Демидыч Уфа", region: "ПФО", city: "Уфа", address: "450032 г. Уфа, ул. Дмитрия Донского, д.53а", service: "ssbr", servicePwd: "ssbr69", sales: "wojc", salesPwd: "wojc34" },
        { code: "EURUS06308", title: "Чанган Центр Прагматика Купчино", region: "СЗФО", city: "Санкт-Петербург", address: "192289, г. Санкт-Петербург, Малая Балканская, дом 57", service: "xesd", servicePwd: "xesd33", sales: "ddjh", salesPwd: "ddjh65" },
        { code: "EURUS06204", title: "Чанган Центр Киров", region: "ПФО", city: "Киров", address: "610033, Кировская обл., г. Киров, ул. Московская, дом 106", service: "ernb", servicePwd: "ernb77", sales: "ccyy", salesPwd: "ccyy11" },
        { code: "EURUS06189", title: "Чанган Центр Тверь", region: "ЦФО", city: "Тверь", address: "170546, Тверская область, Калининский район, сп. Бурашевское, Промышленная зона Боровлево-1, комплекс 1, стр. 1", service: "ggfj", servicePwd: "ggfj34", sales: "uhfd", salesPwd: "uhfd66" },
        { code: "EURUS06155", title: "Чанган Центр АвтоГрад в Добром", region: "ЦФО", city: "Владимир", address: "600032, Владимирская обл., г. Владимир, ул. Растопчина, дом 1Б", service: "azsf", servicePwd: "azsf71", sales: "fkuc", salesPwd: "fkuc33" },
        { code: "EURUS06163", title: "Чанган Центр Белгород", region: "ЦФО", city: "Белгород", address: "308010,  г. Белгород, ул. Студенческая, 1Л", service: "hymc", servicePwd: "hymc94", sales: "dugc", salesPwd: "dugc99" },
        { code: "EURUS06183", title: "Чанган Центр Минеральные Воды", region: "СКФО", city: "Минеральные Воды", address: "357204, Ставропольский край, Минераловодский р-н, х. Красный Пахарь, Автомобильная ул., дом 19, корпус 2", service: "dssl", servicePwd: "dssl34", sales: "bvfr", salesPwd: "bvfr55" },
        { code: "EURUS06151", title: "Чанган Центр Авилон", region: "ЦФО", city: "Москва", address: "109316, г. Москва, Волгоградский пр., д.41, корп.1", service: "vbbq", servicePwd: "vbbq17", sales: "ofdx", salesPwd: "ofdx06" },
        { code: "EURUS06243", title: "Чанган Центр Калуга", region: "ЦФО", city: "Калуга", address: "248025, г. Калуга, ул. Зерновая, д.52", service: "etyi", servicePwd: "etyi11", sales: "erfd", salesPwd: "erfd18" },
        { code: "EURUS06253", title: "Юни Центр Брянск", region: "ЦФО", city: "Брянск", address: "241050, г. Брянск, пр-т Станке Димитрова, 45", service: "hgff", servicePwd: "hgff46", sales: "dhrz", salesPwd: "dhrz77" },
        { code: "EURUS06283", title: "Чанган Центр Автосалон-2000", region: "ПФО", city: "Оренбург", address: "460041, Оренбургская обл., г. Оренбург, Нежинское шоссе, дом 9", service: "dduy", servicePwd: "dduy06", sales: "zzsw", salesPwd: "zzsw22" },
        { code: "EURUS06284", title: "Чанган Центр Автосалон-2000", region: "ПФО", city: "Орск", address: "Оренбургская обл., г. Орск, Новый город, 234 м на северо-запад от АЗС ЗАО «Уралтехснабпром» по ул. Новотроицкое шоссе, дом 60", service: "kvnq", servicePwd: "kvnq39", sales: "hhgf", salesPwd: "hhgf64" },
        { code: "EURUS06312", title: "Чанган Центр Арконт", region: "ЮФО", city: "Волжский", address: "404133, Волгоградская обл., г. Волжский, просп. Ленина, дом 359", service: "mnrr", servicePwd: "mnrr32", sales: "yggv", salesPwd: "yggv41" },
        { code: "EURUS06385", title: "Чанган Центр Арконт", region: "ЮФО", city: "Краснодар", address: "350912, Краснодарский край, г. Краснодар, ул. Аэропортовская, дом 4", service: "brjh", servicePwd: "brjh08", sales: "fdou", salesPwd: "fdou34" },
        { code: "EURUS06370", title: "Чанган Центр Курск", region: "ЦФО", city: "Курск", address: "305047, Курская обл., г.о. город Курск, ул. Энгельса, дом 173Д", service: "fdwl", servicePwd: "fdwl30", sales: "ubdr", salesPwd: "ubdr33" },
        { code: "EURUS06381", title: "Чанган Центр Корс", region: "ЦФО", city: "Коломна", address: "140483, Московская обл., г. Коломна, с. Никульское, тер. автодорога М5 Урал, строение 1В", service: "ceap", servicePwd: "ceap46", sales: "bbtl", salesPwd: "bbtl35" },
        { code: "EURUS06395", title: "Чанган Центр Корс", region: "ЦФО", city: "Орел", address: "302009, Орловская обл., г. Орёл, ул. Раздольная, дом 8", service: "btkk", servicePwd: "btkk17", sales: "voer", salesPwd: "voer46" },
        { code: "EURUS06366", title: "Юни Центр Автолоцман", region: "ПФО", city: "Пенза", address: "440028, Пензенская обл., г. Пенза, пр-кт Победы, дом 53Б", service: "rrkd", servicePwd: "rrkd53", sales: "iyff", salesPwd: "iyff85" },
        { code: "EURUS06368", title: "Чанган Центр Аларм Моторс", region: "СЗФО", city: "Санкт-Петербург", address: "194355, г. Санкт-Петербург, Выборгское ш., дом 27", service: "cotd", servicePwd: "cotd48", sales: "fhjh", salesPwd: "fhjh37" },
        { code: "EURUS06372", title: "Чанган Центр АТК Моторс", region: "ПФО", city: "Самара", address: "443046, Самарская обл., г. Самара, п. Зубчаниновка, ш. Аэропортовское, участок 1Ж, строение 2", service: "ggwi", servicePwd: "ggwi28", sales: "djlu", salesPwd: "djlu92" },
        { code: "EURUS06373", title: "Чанган Центр Оптима Тамань", region: "ЮФО", city: "Краснодар", address: "353556, Краснодарский край, Темрюкский р-н, станица Тамань, ул. 8-я Гвардейская, дом 97", service: "lgsr", servicePwd: "lgsr60", sales: "gdoj", salesPwd: "gdoj63" },
        { code: "EURUS06374", title: "Чанган Центр Рыбинск", region: "ЦФО", city: "Рыбинск", address: "152973, Ярославская обл., Рыбинский муниципальный район, Покровское сельское поселение, деревня Выгорода, земельный участок 14В", service: "jdlh", servicePwd: "jdlh62", sales: "ofrb", salesPwd: "ofrb17" },
        { code: "EURUS06375", title: "Чанган Центр Агат на Промышленном", region: "ЦФО", city: "Владимир", address: "600005, Владимирская обл., г. Владимир, Промышленный проезд, дом 1", service: "soyu", servicePwd: "soyu53", sales: "dfik", salesPwd: "dfik93" },
        { code: "EURUS06377", title: "Чанган Центр Автопрестиж", region: "ПФО", city: "Пермь", address: "614068, Пермский край, г. Пермь, ул. Спешилова, 77", service: "khfd", servicePwd: "khfd32", sales: "ohfe", salesPwd: "ohfe95" },
        { code: "EURUS06386", title: "Чанган Центр Рольф Ясенево", region: "ЦФО", city: "Москва", address: "117628, г. Москва, вн.тер.г. муниципальный округ Коммунарка, территория МКАД, километр 40-й, дом 1, строение 2", service: "rdjl", servicePwd: "rdjl91", sales: "kidu", salesPwd: "kidu54" },
        { code: "EURUS06387", title: "Чанган Центр Рольф Химки", region: "ЦФО", city: "Москва", address: "141410, Московская обл., г. Химки, Ленинградское ш., владение 21", service: "igrv", servicePwd: "igrv35", sales: "pjdg", salesPwd: "pjdg92" },
        { code: "EURUS06389", title: "Чанган Центр БЦР-ПЕЧЁРЫ", region: "ПФО", city: "Нижний Новгород", address: "603163, Нижегородская обл., г. Нижний Новгород, Казанское ш., дом 6Б", service: "ldhi", servicePwd: "ldhi05", sales: "eely", salesPwd: "eely43" },
        { code: "EURUS06388", title: "Чанган Центр Автопродикс", region: "СЗФО", city: "Санкт-Петербург", address: "195299, г. Санкт-Петербург, ул. Руставели, дом 55, корпус 1, стр. 2, пом.13", service: "ofrn", servicePwd: "ofrn97", sales: "ovdn", salesPwd: "ovdn30" },
        { code: "EURUS06390", title: "Чанган Центр АНТ", region: "СФО", city: "Барнаул", address: "656006, Алтайский край, г. Барнаул, Павловский тракт, дом 249Е", service: "zpiu", servicePwd: "zpiu40", sales: "ohff", salesPwd: "ohff73" },
        { code: "EURUS06391", title: "Чанган Центр Сатурн", region: "УФО", city: "Челябинск", address: "454045, Челябинская обл., г. Челябинск, ул. Блюхера, дом 123А", service: "tffg", servicePwd: "tffg02", sales: "jddq", salesPwd: "jddq74" },
        { code: "EURUS06392", title: "Чанган Центр Фрагмент на Копейском", region: "УФО", city: "Челябинск", address: "454119, г. Челябинск, Копейское шоссе, д. 33а", service: "dpuy", servicePwd: "dpuy55", sales: "llkw", salesPwd: "llkw66" },
        { code: "EURUS06393", title: "Чанган Центр СИЛЬВЕР", region: "УФО", city: "Курган", address: "640014, Курганская обл., г. Курган, Маршала Голикова пр-кт, дом 10Ж", service: "fdwe", servicePwd: "fdwe20", sales: "rhfi", salesPwd: "rhfi43" },
        { code: "EURUS06397", title: "Чанган Центр СИЛЬВЕР", region: "УФО", city: "Магнитогорск", address: "453618, Респ. Башкортостан, Абзелиловский р-н, с. Красная Башкирия, ул. 50 лет Победы, дом 56", service: "hfue", servicePwd: "hfue85", sales: "ljfg", salesPwd: "ljfg83" },
        { code: "EURUS06396", title: "Чанган Центр Агат-Авто", region: "СФО", city: "Братск", address: "665717, Иркутская обл., г.о. город Братск, г. Братск, ж/р Центральный, ул. Коммунальная, дом 9", service: "ihcy", servicePwd: "ihcy03", sales: "loey", salesPwd: "loey86" },
        { code: "EURUS06361", title: "Чанган Центр Фаравто", region: "СКФО", city: "Махачкала", address: "368530, Респ. Дагестан, Карабудахкентский р-н, с. Карабудахкент, тер. Аэропорт, ул. Аэропортовская, здание 9", service: "serd", servicePwd: "serd23", sales: "eldh", salesPwd: "eldh11" },
        { code: "EURUS06356", title: "Чанган Центр НИКА АВТО", region: "ПФО", city: "Оренбург", address: "460056, Оренбургская обл., г. Оренбург, улица Волгоградская, дом 5/3", service: "ngbd", servicePwd: "ngbd79", sales: "lfji", salesPwd: "lfji81" },
        { code: "EURUS06360", title: "Чанган Центр Автомаркет", region: "СЗФО", city: "Мурманск", address: "183038, Мурманская обл., г. Мурманск, Кольский пр-кт, дом 118", service: "jdvg", servicePwd: "jdvg54", sales: "kgyf", salesPwd: "kgyf33" },
        { code: "EURUS06354", title: "Чанган Центр Великий Новгород", region: "СЗФО", city: "Великий Новгород", address: "173008, г. Великий Новгород, ул. Северная, д.2", service: "hdon", servicePwd: "hdon63", sales: "hfie", salesPwd: "hfie35" },
        { code: "EURUS06404", title: "Юни Центр Великий Новгород", region: "СЗФО", city: "Великий Новгород", address: "173008, Новгородская обл., г. Великий Новгород, ул. Большая Санкт-Петербургская, дом 173, строение 3", service: "artg", servicePwd: "artg51", sales: "spyf", salesPwd: "spyf77" },
        { code: "EURUS06039", title: "Чанган Центр Автостиль Автово", region: "СЗФО", city: "Санкт-Петербург", address: "198152, г. Санкт-Петербург, ул. Краснопутиловская, д.65, литера А, пом.5-Н №3", service: "dlie", servicePwd: "dlie44", sales: "ppoq", salesPwd: "ppoq18" },
        { code: "EURUS06209", title: "Чанган Центр Армада-Авто", region: "ПФО", city: "Ульяновск", address: "432045, Ульяновская область, город Ульяновск, Московское шоссе, дом 5В стр. 1", service: "ziun", servicePwd: "ziun55", sales: "jfkp", salesPwd: "jfkp83" },
        { code: "EURUS06265", title: "Чанган Центр Оскол", region: "ЦФО", city: "Старый Оскол", address: "309516, Белгородская область, город Старый Оскол,проспект Алексея Угарова, 18Д", service: "qety", servicePwd: "qety80", sales: "mdhb", salesPwd: "mdhb92" },
        { code: "EURUS06298", title: "Чанган Центр Орехово-Зуево", region: "ЦФО", city: "Орехово-Зуево", address: "142611, Московская область, г. Орехово-Зуево, ул. Красина, д. 4.", service: "ljds", servicePwd: "ljds61", sales: "wonf", salesPwd: "wonf08" },
        { code: "EURUS06135", title: "Чанган Центр Калининград", region: "СЗФО", city: "Калининград", address: "236011,  г. Калининград, ул. Аллея Смелых, д. 200б", service: "okge", servicePwd: "okge61", sales: "oygc", salesPwd: "oygc98" },
        { code: "EURUS06272", title: "Чанган Центр Томск", region: "СФО", city: "Томск", address: "634031, г. Томск, ул. Ивановского, 8в", service: "dytf", servicePwd: "dytf54", sales: "efgh", salesPwd: "efgh25" },
        { code: "EURUS06093", title: "Чанган Центр Серпухов", region: "ЦФО", city: "Серпухов", address: "142204, Московская область, г. Серпухов, Московское шоссе, д.106", service: "kwrd", servicePwd: "kwrd36", sales: "vcte", salesPwd: "vcte12" },
        { code: "EURUS06349", title: "Юни Центр Хабаровск", region: "ДФО", city: "Хабаровск", address: "680042, Хабаровский край, г. Хабаровск, ул. Воронежская, дом 79", service: "vzxo", servicePwd: "vzxo02", sales: "sdmb", salesPwd: "sdmb19" },
        { code: "EURUS06350", title: "Чанган Центр Медведь", region: "СФО", city: "Абакан", address: "655017, Респ. Хакасия, г. Абакан, Молодежный кв-л, дом 2В", service: "dvne", servicePwd: "dvne06", sales: "fytr", salesPwd: "fytr44" },
        { code: "EURUS06307", title: "Юни Центр Абакан", region: "СФО", city: "Абакан", address: "655017, Респ. Хакасия, г. Абакан, квартал Молодежный 5 \"Л\".", service: "jvjr", servicePwd: "jvjr27", sales: "iied", salesPwd: "iied46" },
        { code: "EURUS06240", title: "Чанган Центр Кузбасс", region: "СФО", city: "Кемерово", address: "650066, Кемеровская область - Кузбасс, г. Кемерово, проспект Октябрьский, 2А", service: "gfod", servicePwd: "gfod82", sales: "gfcv", salesPwd: "gfcv71" },
        { code: "EURUS06197", title: "Чанган Центр Нижневартовск", region: "УФО", city: "Нижневартовск", address: "628616, Ханты-Мансийский Автономный округ - Югра АО, г. Нижневартовск, ул. Северная, владение 33А", service: "mnus", servicePwd: "mnus88", sales: "xxhh", salesPwd: "xxhh43" },
        { code: "EURUS06220", title: "Чанган Центр Автополе", region: "СЗФО", city: "Санкт-Петербург", address: "188693, Ленинградская обл., Всеволожский р-н, г. Кудрово, г.п. Заневское, пр-кт Строителей, здание 35 торговый зал 2-Н", service: "sohg", servicePwd: "sohg56", sales: "clgs", salesPwd: "clgs43" },
        { code: "EURUS06332", title: "Юни Центр Улан-Удэ", region: "ДФО", city: "Улан-Удэ", address: "670023, Респ. Бурятия, г. Улан-Удэ, ул. Кабанская, дом 52", service: "pgtd", servicePwd: "pgtd01", sales: "ojdg", salesPwd: "ojdg33" },
        { code: "EURUS06185", title: "Чанган Центр Восток", region: "УФО", city: "Екатеринбург", address: "623700, Свердловская область, г.  Березовский, ул. Кольцевая, стр. 4", service: "sohy", servicePwd: "sohy77", sales: "xxrf", salesPwd: "xxrf22" },
        { code: "EURUS06274", title: "Чанган Центр Измайлово", region: "ЦФО", city: "Москва", address: "143912,  МО, г. Балашиха, Западная коммунальная зона, шоссе Энтузиастов, д. 11 А", service: "sdtw", servicePwd: "sdtw05", sales: "tskf", salesPwd: "tskf39" },
        { code: "EURUS06295", title: "Чанган Центр FAVORIT MOTORS МКАД", region: "ЦФО", city: "Реутов", address: "143968, Московская обл., г. Реутов, МКАД 2 км., дом 7", service: "vbwe", servicePwd: "vbwe54", sales: "iehu", salesPwd: "iehu09" },
        { code: "EURUS06294", title: "Чанган Центр VERRA", region: "ПФО", city: "Пермь", address: "614513, Пермский край, м.р-н Пермский, с.п. Савинское, тер. Шоссе Космонавтов, д. 427", service: "xpgt", servicePwd: "xpgt84", sales: "kbeh", salesPwd: "kbeh73" },
        { code: "EURUS06235", title: "Чанган Центр Пятигорск", region: "СКФО", city: "Пятигорск", address: "357500, Ставропольский край, г. Пятигорск, ул. Ермолова, 50", service: "dspw", servicePwd: "dspw95", sales: "dspw", salesPwd: "dspw43" },
        { code: "EURUS06314", title: "Чанган Центр Новый Уренгой", region: "УФО", city: "Новый Уренгой", address: "614513, Ямало-Ненецкий АО, г. Новый Уренгой, ул. Магистральная, дом 50а", service: "geni", servicePwd: "geni32", sales: "xigt", salesPwd: "xigt27" },
        { code: "EURUS06226", title: "Чанган Центр Липецк", region: "ЦФО", city: "Липецк", address: "398024, г. Липецк, ул. Юных Натуралистов, д. 18, стр.Б", service: "edki", servicePwd: "edki44", sales: "xohe", salesPwd: "xohe66" },
        { code: "EURUS06334", title: "Чанган Центр Лаки Моторс", region: "УФО", city: "Екатеринбург", address: "620103, г. Екатеринбург, ул. Селькоровская, дом 22", service: "don’t", servicePwd: "dont87", sales: "rjwk", salesPwd: "rjwk19" },
        { code: "EURUS06192", title: "Чанган Центр Тамбов", region: "ЦФО", city: "Тамбов", address: "392000, г. Тамбов. Киквидзе улица, дом 85Г", service: "kdgy", servicePwd: "kdgy22", sales: "fdal", salesPwd: "fdal33" },
        { code: "EURUS06035", title: "Чанган Центр Радар Авто", region: "ЦФО", city: "Иваново", address: "153007, г. Иваново, ул. Фрунзе, д. 92", service: "xort", servicePwd: "xort64", sales: "innn", salesPwd: "innn40" },
        { code: "EURUS06310", title: "Чанган Центр Базис Окружная", region: "УФО", city: "Тюмень", address: "625025, Тюменская обл., г. Тюмень, Окружная дорога, дом 202", service: "wlnu", servicePwd: "wlnu88", sales: "aspo", salesPwd: "aspo29" },
        { code: "EURUS06346", title: "Юни Центр Вологда", region: "СЗФО", city: "Вологда", address: "160024, Вологодская обл., г. Вологда, ул. Северная, дом 25А", service: "yerc", servicePwd: "yerc08", sales: "ngrh", salesPwd: "ngrh43" },
        { code: "EURUS06262", title: "Чанган Центр FAVORIT MOTORS Юг", region: "ЦФО", city: "Москва", address: "117545, г. Москва, 1-ый Дорожный проезд, д. 4, корп. 1", service: "igfy", servicePwd: "igfy41", sales: "hdgh", salesPwd: "hdgh72" },
        { code: "EURUS06233", title: "Чанган Центр Башавтоком", region: "ПФО", city: "Уфа", address: "450071, г. Уфа, Пр. С. Юлаева, 89", service: "jnye", servicePwd: "jnye55", sales: "wohg", salesPwd: "wohg11" },
        { code: "EURUS06234", title: "Чанган Центр Башавтоком Юг", region: "ПФО", city: "Стерлитамак", address: "453102, г. Стерлитамак, ул. Космонавтов, 1", service: "nhdu", servicePwd: "nhdu48", sales: "hdli", salesPwd: "hdli08" },
        { code: "EURUS06234", title: "Юни Центр Башавтоком Юг", region: "ПФО", city: "Стерлитамак", address: "453103, г. Стерлитамак, ул. Элеваторная, дом 86, корпус А", service: "htdf", servicePwd: "htdf94", sales: "jdey", salesPwd: "jdey77" },
        { code: "EURUS06302", title: "Чанган Центр Башавтоком Север", region: "ПФО", city: "Октябрьский", address: "452606, г. Октябрьский, ул. Северная, 19/27", service: "xkut", servicePwd: "xkut59", sales: "jheu", salesPwd: "jheu73" },
        { code: "EURUS06327", title: "Чанган Центр КАН АВТО Сибирский", region: "ПФО", city: "Казань", address: "420053, Респ. Татарстан, г. Казань, ул. Сибирский Тракт, дом 51", service: "dbhq", servicePwd: "dbhq50", sales: "bhdh", salesPwd: "bhdh82" },
        { code: "EURUS06212", title: "Чанган Центр Внуково", region: "ЦФО", city: "Москва", address: "108811, г. Москва, Московский поселение, вн.тер.г., д. Картмазово, ул. Киевская, дом 1, пом.62", service: "djip", servicePwd: "djip83", sales: "hehe", salesPwd: "hehe23" },
        { code: "EURUS06335", title: "Юни Центр Лаки Моторс", region: "УФО", city: "Екатеринбург", address: "620076, Свердловская обл., г. Екатеринбург, ул. Щербакова, дом 142А", service: "vdht", servicePwd: "vdht66", sales: "hfsc", salesPwd: "hfsc78" },
        { code: "EURUS06321", title: "Чанган Центр Россо", region: "СФО", city: "Иркутск", address: "664050, Иркутская обл., г. Иркутск, ул. Дыбовского, дом 17", service: "hrse", servicePwd: "hrse11", sales: "krfsg", salesPwd: "krfsg04" },
        { code: "EURUS06247", title: "Чанган Центр FAVORIT MOTORS Север", region: "ЦФО", city: "Москва", address: "125239, г. Москва, ул. Коптевская, дом 69А, строение 5", service: "rgws", servicePwd: "rgws49", sales: "fjye", salesPwd: "fjye32" },
        { code: "EURUS06017", title: "Чанган Центр Восток-Авто", region: "ПФО", city: "Оренбург", address: "460021, Оренбургская обл., г. Оренбург, ул. Туркестанская, дом 161А", service: "kdye", servicePwd: "kdye31", sales: "jesr", salesPwd: "jesr30" },
        { code: "EURUS06207", title: "Чанган Центр Премьер Авто", region: "ЦФО", city: "Смоленск", address: "214011, Смоленская обл.,  г. Смоленск,  ул. Кутузова, дом 15, корпус Б", service: "jsst", servicePwd: "jsst96", sales: "hrws", salesPwd: "hrws04" },
        { code: "EURUS06353", title: "Чанган Центр Медведь Север", region: "СФО", city: "Красноярск", address: "660118, Красноярский край, г. Красноярск, Северное шоссе, дом 19\"д\"", service: "jwry", servicePwd: "jwry83", sales: "jtsr", salesPwd: "jtsr63" },
        { code: "EURUS06348", title: "Юни Центр Пенза", region: "ПФО", city: "Пенза", address: "440066, Пензенская обл., г. Пенза, Победы пр-кт, дом 121/1", service: "kfds", servicePwd: "kfds77", sales: "fsfu", salesPwd: "fsfu91" },
        { code: "EURUS06175", title: "Чанган Центр СК-Моторс", region: "УФО", city: "Сургут", address: "628415, г. Сургут, пр-кт Ленина, дом 76/1", service: "gsew", servicePwd: "gsew72", sales: "gese", salesPwd: "gese26" },
        { code: "EURUS06315", title: "Чанган Центр АвтоПремьер Зубово", region: "ПФО", city: "Уфа", address: "450522, Респ. Башкортостан, м. р-н Уфимский, С.П. Зубовский сельсовет, с. Зубово, ул. Электрозаводская, здание 18", service: "jumi", servicePwd: "jumi83", sales: "jehy", salesPwd: "jehy02" },
        { code: "EURUS06266", title: "Чанган Центр Архангельск", region: "СЗФО", city: "Архангельск", address: "163062, г. Архангельск, ул. Папанина, дом 23", service: "jdie", servicePwd: "jdie88", sales: "heeo", salesPwd: "heeo60" },
        { code: "EURUS06291", title: "Чанган Центр Сыктывкар", region: "СЗФО", city: "Сыктывкар", address: "167000, Республика Коми, г.Сыктывкар, ул. Гаражная, д. 19", service: "kejo", servicePwd: "kejo02", sales: "jeie", salesPwd: "jeie52" },
        { code: "EURUS06333", title: "Чанган Центр Улан-Удэ", region: "ДФО", city: "Улан-Удэ", address: "670045, г. Улан-Удэ, ул. Шаляпина, дом 39", service: "pejk", servicePwd: "pejk42", sales: "erfe", salesPwd: "erfe04" },
        { code: "EURUS06290", title: "Чанган Центр Кострома", region: "ЦФО", city: "Кострома", address: "156014, Костромская обл., г. Кострома, ул. Сутырина, дом 2А", service: "kgrs", servicePwd: "kgrs89", sales: "pkrj", salesPwd: "pkrj07" },
        { code: "EURUS06219", title: "Чанган Центр Авторусь Подольск", region: "ЦФО", city: "Москва", address: "142111, Московская область, г. Подольск, пр-т Юных Ленинцев, д. 1И, помещение 2.1", service: "khuc", servicePwd: "khuc15", sales: "khey", salesPwd: "khey17" },
        { code: "EURUS06165", title: "Чанган Центр Новокузнецк", region: "СФО", city: "Новокузнецк", address: "654006, Кемеровская область - Кузбасс обл., г. Новокузнецк, ул. Орджоникидзе, дом 24", service: "endu", servicePwd: "endu10", sales: "lhey", salesPwd: "lhey48" },
        { code: "EURUS06322", title: "Чанган Центр Иркут на Трактовой", region: "СФО", city: "Иркутск", address: "664014, г. Иркутск, ул. Трактовая, дом 21", service: "hehb", servicePwd: "hehb88", sales: "tdbj", salesPwd: "tdbj26" },
        { code: "EURUS06171", title: "Чанган Центр Йошкар-Ола", region: "ПФО", city: "Йошкар-Ола", address: "424913, г. Йошкар-Ола, Кокшайский проезд, 49 а", service: "jeon", servicePwd: "jeon38", sales: "hfew", salesPwd: "hfew25" },
        { code: "EURUS06320", title: "Чанган Центр Атик-Моторс", region: "ДФО", city: "Благовещенск", address: "675028, Амурская обл., г. Благовещенск, Новотроицкое шоссе, дом 12/1", service: "jdin", servicePwd: "jdin72", sales: "heln", salesPwd: "heln49" },
        { code: "EURUS06343", title: "Чанган Центр Альянс Моторс", region: "УФО", city: "Сургут", address: "628415, Ханты-Мансийский Автономный округ - Югра АО, г. Сургут, Профсоюзов ул., дом 65", service: "jeje", servicePwd: "jeje83", sales: "gein", salesPwd: "gein02" },
        { code: "EURUS06257", title: "Юни Центр Курган", region: "УФО", city: "Курган", address: "640027, г. Курган, ул. Б.Петрова, 102", service: "fojd", servicePwd: "fojd27", sales: "hekf", salesPwd: "hekf82" },
        { code: "EURUS06230", title: "Юни Центр Зеленоград", region: "ЦФО", city: "Москва", address: "141552, Московская обл., Солнечногорский р-н, Ржавки р.п., м-н 2, строение 13/2", service: "jdke", servicePwd: "jdke29", sales: "neuo", salesPwd: "neuo44" },
        { code: "EURUS06271", title: "Чанган Центр Атлант-М", region: "ЦФО", city: "Москва", address: "129128, г. Москва, ул. Бажова, д. 17, стр.1", service: "oidj", servicePwd: "oidj13", sales: "ljgf", salesPwd: "ljgf74" },
        { code: "EURUS06331", title: "Чанган Центр Варшавка", region: "ЦФО", city: "Москва", address: "117405, Московская обл., Ленинский г.о., п. Битца, МКАД 32 км, строение 3", service: "hbdu", servicePwd: "hbdu02", sales: "ehdh", salesPwd: "ehdh73" },
        { code: "EURUS06180", title: "Чанган Центр КМ/Ч-Север", region: "ЦФО", city: "Москва", address: "125599, г. Москва, 78-км. МКАД, дом 2, корпус 4", service: "hebi", servicePwd: "hebi92", sales: "hedj", salesPwd: "hedj63" },
        { code: "EURUS06259", title: "Чанган Центр Ноябрьск", region: "УФО", city: "Ноябрьск", address: "629800  г. Ноябрьск,  ул. Магистральная, 87а", service: "jenr", servicePwd: "jenr74", sales: "inee", salesPwd: "inee72" },
        { code: "EURUS06205", title: "Чанган Центр Череповец", region: "СЗФО", city: "Череповец", address: "162677,  Вологодская область, Череповецкий р-н, д. Солманское, ул.Центральная 11Б", service: "оеау", servicePwd: "оеау01", sales: "orju", salesPwd: "orju93" },
        { code: "EURUS06241", title: "Чанган Центр Пенза", region: "ПФО", city: "Пенза", address: "440028, г. Пенза, ул. Беляева 2В", service: "hdif", servicePwd: "hdif83", sales: "onye", salesPwd: "onye68" },
        { code: "EURUS06296", title: "Юни Центр Псков", region: "СЗФО", city: "Псков", address: "180006, г. Псков, улица Леона Поземского, дом 114", service: "heee", servicePwd: "heee93", sales: "kibe", salesPwd: "kibe72" },
        { code: "EURUS06339", title: "Юни Центр Глазурит", region: "УФО", city: "Екатеринбург", address: "620091, Свердловская обл., г. Екатеринбург, ул. Фронтовых бригад, дом 27, оф.7", service: "ybod", servicePwd: "ybod95", sales: "ieyf", salesPwd: "ieyf47" },
        { code: "EURUS06336", title: "Чанган Центр АСМОТО", region: "УФО", city: "Екатеринбург", address: "620000, Свердловская обл., г. Верхняя Пышма, ул. Петрова, дом 44а", service: "feel", servicePwd: "efel63", sales: "jkdg", salesPwd: "jkdg07" },
        { code: "EURUS06319", title: "Чанган Центр Сумотори-Авто", region: "ДФО", city: "Артем", address: "692770, Приморский край, г. Артем, ул. Тульская, дом 2", service: "jdhh", servicePwd: "jdhh34", sales: "rsvj", salesPwd: "rsvj99" },
        { code: "EURUS06317", title: "Юни Центр Автоплюс", region: "УФО", city: "Нижний Тагил", address: "622049, Свердловская обл., г. Нижний Тагил, Черноисточинское шоссе, дом 68, строение 1", service: "bdnf", servicePwd: "bdnf44", sales: "kdhb", salesPwd: "kdhb56" },
        { code: "EURUS06352", title: "Чанган Центр Алтуфьево", region: "ЦФО", city: "Москва", address: "141031, Московская обл., г. Мытищи, Поселок Нагорное, километр МКАД 85-й (ТПЗ Алтуфьево тер.), владение 5, строение 1", service: "hrew", servicePwd: "hrew82", sales: "jenu", salesPwd: "jenu65" },
        { code: "EURUS06260", title: "Чанган Центр Нягань", region: "УФО", city: "Нягань", address: "628183, Ханты-Мансийский автономный округ-Югра, г. Нягань, пр-кт Нефтяников, д. 1, корп. 2", service: "jseg", servicePwd: "jseg04", sales: "dnj", salesPwd: "dnj69" },
        { code: "EURUS06367", title: "Чанган Центр Авто Премиум", region: "СЗФО", city: "Санкт-Петербург", address: "195426, г. Санкт-Петербург, ул. Хасанская, дом 5, корпус 2", service: "kdcb", servicePwd: "kdcb55", sales: "idnc", salesPwd: "idnc03" },
        { code: "EURUS06371", title: "Чанган Центр на Копылова", region: "СФО", city: "Красноярск", address: "660100, Красноярский край, г. Красноярск, ул. Копылова, здание 57", service: "fjif", servicePwd: "fjif13", sales: "gduh", salesPwd: "gduh60" },
        { code: "EURUS06379", title: "Чанган Центр Феникс-Авто", region: "СФО", city: "Омск", address: "644015, Омская обл., г. Омск, Суворова ул., дом 93", service: "infh", servicePwd: "infh68", sales: "infh", salesPwd: "infh67" },
        { code: "EURUS06380", title: "Чанган Центр БАКРА 2.0", region: "ЮФО", city: "Краснодар", address: "350058, Краснодарский край, г. Краснодар, ул. Селезнева, дом 204В", service: "fnhl", servicePwd: "fnhl97", sales: "bgdy", salesPwd: "bgdy22" },
        { code: "EURUS06382", title: "Чанган Центр Фастар на Станционной", region: "СФО", city: "Новосибирск", address: "630096, Новосибирская обл., г. Новосибирск, Станционная ул., дом 88", service: "jdve", servicePwd: "jdve00", sales: "okdk", salesPwd: "okdk50" },
        { code: "EURUS06383", title: "Чанган Центр Автопрестиж", region: "ЮФО", city: "Ставрополь", address: "355035, Ставропольский край, г. Ставрополь, Кулакова пр-кт, дом 16А", service: "kfnr", servicePwd: "kfnr46", sales: "kege", salesPwd: "kege34" },
        { code: "EURUS06394", title: "Чанган Центр К-Моторс", region: "СЗФО", city: "Петрозаводск", address: "185014, г. Петрозаводск, Лесной проспект, д. 55, стр. 1.", service: "jdue", servicePwd: "jdue99", sales: "imyd", salesPwd: "imyd60" },
        { code: "EURUS06405", title: "Чанган Центр Альянс", region: "СФО", city: "Омск", address: "644106, Омская обл., г. Омск, ул. Волгоградская, дом 38, корпус 2", service: "dohy", servicePwd: "dohy32", sales: "hduw", salesPwd: "hduw15" },
        { code: "EURUS06406", title: "Чанган Центр Автопрестиж", region: "ПФО", city: "Самара", address: "443028, г. Самара, Московское шоссе, 24-й километр, 42с1", service: "jdhr", servicePwd: "jdhr88", sales: "deju", salesPwd: "deju73" }
    ];

    // ----- ФУНКЦИЯ КОПИРОВАНИЯ -----
    function copyToClipboard(text, btnElement) {
        if (!text) return;
        navigator.clipboard.writeText(text).then(() => {
            const originalText = btnElement.textContent;
            btnElement.textContent = '✅ Готово!';
            setTimeout(() => {
                btnElement.textContent = originalText;
            }, 1500);
        }).catch(() => {
            alert('Не удалось скопировать');
        });
    }

    // ----- ОСНОВНАЯ ФУНКЦИЯ ПОИСКА -----
    function searchAccess() {
        const input = document.getElementById('dcCodeInput');
        const rawValue = input.value.trim();
        const placeholderMsg = document.getElementById('placeholderMsg');
        const credentialCard = document.getElementById('credentialCard');

        // Проверяем формат
        const parts = rawValue.split('|').map(s => s.trim());
        if (parts.length !== 2 || !parts[0] || !parts[1]) {
            placeholderMsg.style.display = 'block';
            credentialCard.style.display = 'none';
            placeholderMsg.innerHTML = '❌ Ошибка: используйте формат <strong>КОД | ГОРОД</strong><br><small>Пример: EURUS06200 | Воронеж</small>';
            return;
        }

        const searchCode = parts[0].toUpperCase();
        const searchCity = parts[1];

        // Ищем все записи с таким кодом
        const results = data.filter(item => 
            item.code.toUpperCase() === searchCode
        );

        if (results.length === 0) {
            placeholderMsg.style.display = 'block';
            credentialCard.style.display = 'none';
            placeholderMsg.innerHTML = `❌ Код <strong>${searchCode}</strong> не найден в базе.<br><small>Проверьте правильность ввода</small>`;
            return;
        }

        // Проверяем город — должен совпадать хотя бы у одной записи
        const cityMatch = results.some(item => 
            item.city.toLowerCase() === searchCity.toLowerCase()
        );

        if (!cityMatch) {
            placeholderMsg.style.display = 'block';
            credentialCard.style.display = 'none';
            placeholderMsg.innerHTML = `❌ Город <strong>${searchCity}</strong> не найден для кода ${searchCode}.<br><small>Проверьте правильность написания города</small>`;
            return;
        }

        // Фильтруем только те записи, где город совпадает
        const filteredResults = results.filter(item => 
            item.city.toLowerCase() === searchCity.toLowerCase()
        );

        // Скрываем плейсхолдер
        placeholderMsg.style.display = 'none';
        credentialCard.style.display = 'block';

        // Строим HTML
        let html = '';

        // Общая информация (берем из первой записи)
        const first = filteredResults[0];
        const isMulti = filteredResults.length > 1;

        html += `
            <div class="access-card">
                <div class="dc-header">
                    <div class="dc-code">${first.code}</div>
                    <div class="dc-title">${isMulti ? 'Доступы CS + UNI' : first.title}</div>
                </div>
                <div class="info-grid">
                    <div class="detail-row">
                        <span class="detail-item"><strong>Округ:</strong> ${first.region}</span>
                        <span class="detail-item"><strong>Город:</strong> ${first.city}</span>
                        <span class="detail-item" style="flex:1; min-width:180px;"><strong>Адрес:</strong> ${first.address}</span>
                    </div>
        `;

        // Если несколько записей — показываем все доступы
        if (isMulti) {
            html += `<div style="display:flex; flex-direction:column; gap:16px;">`;
            filteredResults.forEach((item, index) => {
                const label = item.title.includes('Юни') ? 'Юни Центр' : 'Чанган Центр';
                html += `
                    <div class="access-entry">
                        <div style="font-weight:600; color:#1a5c4e; margin-bottom:10px; font-size:0.95rem;">${label} (${item.title.replace(/^(Чанган|Юни) Центр /, '')})</div>
                        <div class="dual-access">
                            <div class="credential-block">
                                <div class="cred-label">🔧 Сервисный доступ</div>
                                <div class="cred-value">
                                    <span>${item.service}</span>
                                    <button class="copy-btn" data-copy="${item.service}">Копировать</button>
                                </div>
                                <div style="margin-top: 6px; font-size: 0.9rem; font-family: monospace; color: #295f52;">
                                    Пароль: ${item.servicePwd}
                                    <button class="copy-btn" style="margin-left: 10px;" data-copy="${item.servicePwd}">Копировать</button>
                                </div>
                            </div>
                            <div class="credential-block">
                                <div class="cred-label">📈 Доступ для продаж</div>
                                <div class="cred-value">
                                    <span>${item.sales}</span>
                                    <button class="copy-btn" data-copy="${item.sales}">Копировать</button>
                                </div>
                                <div style="margin-top: 6px; font-size: 0.9rem; font-family: monospace; color: #295f52;">
                                    Пароль: ${item.salesPwd}
                                    <button class="copy-btn" style="margin-left: 10px;" data-copy="${item.salesPwd}">Копировать</button>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
            });
            html += `</div>`;
        } else {
            // Одна запись — показываем как обычно
            const item = filteredResults[0];
            html += `
                <div class="dual-access">
                    <div class="credential-block">
                        <div class="cred-label">🔧 Сервисный доступ</div>
                        <div class="cred-value">
                            <span>${item.service}</span>
                            <button class="copy-btn" data-copy="${item.service}">Копировать</button>
                        </div>
                        <div style="margin-top: 6px; font-size: 0.9rem; font-family: monospace; color: #295f52;">
                            Пароль: ${item.servicePwd}
                            <button class="copy-btn" style="margin-left: 10px;" data-copy="${item.servicePwd}">Копировать</button>
                        </div>
                    </div>
                    <div class="credential-block">
                        <div class="cred-label">📈 Доступ для продаж</div>
                        <div class="cred-value">
                            <span>${item.sales}</span>
                            <button class="copy-btn" data-copy="${item.sales}">Копировать</button>
                        </div>
                        <div style="margin-top: 6px; font-size: 0.9rem; font-family: monospace; color: #295f52;">
                            Пароль: ${item.salesPwd}
                            <button class="copy-btn" style="margin-left: 10px;" data-copy="${item.salesPwd}">Копировать</button>
                        </div>
                    </div>
                </div>
            `;
        }

        html += `
                </div>
            </div>
        `;

        credentialCard.innerHTML = html;

        // Навешиваем обработчики на кнопки копирования
        document.querySelectorAll('.copy-btn[data-copy]').forEach(btn => {
            btn.addEventListener('click', function(e) {
                const text = this.getAttribute('data-copy');
                if (text) {
                    copyToClipboard(text, this);
                }
            });
        });
    }

    // ----- СОБЫТИЯ -----
    const searchBtn = document.getElementById('showAccessBtn');
    const inputField = document.getElementById('dcCodeInput');

    searchBtn.addEventListener('click', searchAccess);

    inputField.addEventListener('keydown', function(e) {
        if (e.key === 'Enter') {
            e.preventDefault();
            searchAccess();
        }
    });

    // При загрузке показываем пример
    window.addEventListener('DOMContentLoaded', function() {
        inputField.value = 'EURUS06200 | Воронеж';
        setTimeout(searchAccess, 300);
    });
</script>

</body>
</html>
