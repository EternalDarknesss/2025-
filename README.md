((я так чувствую))

Презентация: https://disk.yandex.ru/i/PY3KipO1cEwHVA

Код:
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Teen Hustle — Поиск работы для подростков 14-17 лет</title>

  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --accent:#08a0ff; --muted:#98a6b2; --glass: rgba(255,255,255,0.03);
      --max-width:1100px; --radius:12px; font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%;background:linear-gradient(180deg,#071124 0%, #041325 60%); color:#ffffff;}
    .wrap{max-width:var(--max-width);margin:28px auto;padding:20px;}
    header{display:flex;gap:20px;align-items:center;justify-content:space-between}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,#0ea5e9,#7c3aed);display:grid;place-items:center;font-weight:700;color:#021025}
    h1{font-size:1.35rem;margin:0;color:#ffffff}
    p.lead{margin:0;color:#ffffff;font-size:0.95rem;opacity:0.9}

    .profile-container{position:fixed;top:20px;right:20px;display:flex;align-items:center;gap:12px;z-index:1000;background:var(--card);padding:10px 15px;border-radius:var(--radius);border:1px solid rgba(255,255,255,0.05);box-shadow:0 4px 12px rgba(0,0,0,0.3);backdrop-filter:blur(10px)}
    .profile-avatar{width:40px;height:40px;border-radius:50%;background:linear-gradient(135deg,#7c3aed,#0ea5e9);display:flex;align-items:center;justify-content:center;font-weight:600;color:#021025;cursor:pointer;border:2px solid rgba(255,255,255,0.1);transition:all 0.3s ease;font-size:0.9rem}
    .profile-avatar:hover{border-color:var(--accent);transform:scale(1.05)}
    .profile-info{display:flex;flex-direction:column;align-items:flex-end}
    .profile-name{font-weight:600;font-size:0.9rem;color:#ffffff;display:flex;align-items:center;gap:8px}
    .profile-age{color:var(--accent);font-size:0.8rem;opacity:0.9}
    .profile-status{font-size:0.75rem;color:#ffffff;display:flex;align-items:center;gap:6px;opacity:0.8}
    .status-dot{width:6px;height:6px;border-radius:50%;background:#10b981}
    .profile-dropdown{position:absolute;top:100%;right:0;margin-top:10px;background:var(--card);border-radius:var(--radius);padding:12px;min-width:200px;box-shadow:0 10px 25px rgba(0,0,0,0.3);border:1px solid rgba(255,255,255,0.05);display:none;z-index:1001}
    .profile-dropdown.show{display:block}
    .dropdown-header{padding:8px 12px;border-bottom:1px solid rgba(255,255,255,0.05);margin-bottom:8px}
    .dropdown-header strong{color:#ffffff}
    .dropdown-header div{color:#ffffff;opacity:0.8}
    .dropdown-item{display:flex;align-items:center;gap:10px;padding:10px 12px;border-radius:8px;color:#ffffff;text-decoration:none;transition:all 0.2s ease;cursor:pointer;opacity:0.9}
    .dropdown-item:hover{background:var(--glass);color:#ffffff;opacity:1}
    .dropdown-divider{height:1px;background:rgba(255,255,255,0.05);margin:8px 0}
    
    .mode-switcher{display:flex;align-items:center;gap:8px;margin:8px 0}
    .mode-label{font-size:0.8rem;color:#ffffff;opacity:0.9}
    .switch{position:relative;display:inline-block;width:48px;height:24px}
    .switch input{opacity:0;width:0;height:0}
    .slider{position:absolute;cursor:pointer;top:0;left:0;right:0;bottom:0;background-color:rgba(255,255,255,0.1);transition:.4s;border-radius:34px}
    .slider:before{position:absolute;content:"";height:18px;width:18px;left:3px;bottom:3px;background-color:var(--accent);transition:.4s;border-radius:50%}
    input:checked + .slider{background-color:rgba(8,160,255,0.2)}
    input:checked + .slider:before{transform:translateX(24px)}

    .filters-section{background:var(--glass);padding:16px;border-radius:12px;margin:18px 0;display:grid;grid-template-columns:repeat(5, 1fr) auto;gap:12px;align-items:end}
    .filter-group{display:flex;flex-direction:column;gap:6px}
    .filter-label{font-size:0.8rem;color:#ffffff;opacity:0.9}
    .searchbox{display:flex;gap:8px;align-items:center}
    input[type="search"], select, input[type="number"]{background:transparent;border:1px solid rgba(255,255,255,0.15);color:#ffffff;font-size:0.95rem;outline:none;padding:8px 10px;width:100%;border-radius:8px}
    input[type="search"]::placeholder, select option, input[type="number"]::placeholder{color:rgba(255,255,255,0.6)}
    input[type="search"]:focus, select:focus, input[type="number"]:focus{border-color:var(--accent)}
    select option{background:#000000;color:#ffffff}
    button.btn{background:var(--accent);border:0;padding:10px 16px;border-radius:10px;color:#021025;font-weight:600;cursor:pointer;transition:opacity 0.2s}
    button.btn:hover{opacity:0.9}
    button.ghost{background:transparent;border:1px solid rgba(255,255,255,0.15);padding:8px 12px;border-radius:10px;color:#ffffff;cursor:pointer;transition:all 0.2s;opacity:0.9}
    button.ghost:hover{background:rgba(255,255,255,0.1);border-color:rgba(255,255,255,0.3);opacity:1}
    button.reject-btn{background:transparent;border:1px solid rgba(255,100,100,0.5);padding:6px 10px;border-radius:8px;color:#ff6b6b;font-size:0.8rem;cursor:pointer}
    button.reject-btn:hover{background:rgba(255,100,100,0.2);border-color:rgba(255,100,100,0.7)}
    .filters{display:flex;gap:8px;flex-wrap:wrap;align-items:center;justify-content:flex-end}

    main{display:grid;grid-template-columns:1fr 360px;gap:20px}
    .job-list{display:grid;gap:12px}
    .job{background:linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02));padding:12px;border-radius:10px;display:flex;gap:12px;align-items:flex-start;border:1px solid rgba(255,255,255,0.05)}
    .job .meta{flex:1}
    .job h3{margin:0;font-size:1.05rem;color:#ffffff}
    .chips{display:flex;gap:8px;margin-top:8px;flex-wrap:wrap}
    .chip{background:rgba(255,255,255,0.08);padding:6px 8px;border-radius:999px;font-size:0.82rem;color:#ffffff;opacity:0.9}
    .job .actions{display:flex;flex-direction:column;gap:8px}
    .job small{color:#ffffff;opacity:0.8}

    aside.card{background:var(--card);padding:14px;border-radius:12px;border:1px solid rgba(255,255,255,0.05)}
    .card h4{margin:4px 0 10px 0;color:#ffffff}
    .quick-stats{display:flex;gap:8px;flex-wrap:wrap}
    .stat{background:rgba(255,255,255,0.05);padding:10px;border-radius:10px;min-width:100px;text-align:center;border:1px solid rgba(255,255,255,0.05)}
    .stat strong{color:#ffffff;font-size:1.2rem}
    .stat div{color:#ffffff;opacity:0.9}

    /* Стили для кандидатов */
    .candidate-item {
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.05);
      border-radius: var(--radius);
      padding: 16px;
      margin-bottom: 16px;
      transition: all 0.3s ease;
    }

    .candidate-item:hover {
      background: rgba(255,255,255,0.05);
      border-color: var(--accent);
    }

    .candidate-item.removing {
      opacity: 0;
      transform: translateX(20px);
      transition: all 0.3s ease;
    }

    .resume-section {
      background: rgba(8,160,255,0.05);
      border-radius: 8px;
      padding: 12px;
      margin: 12px 0;
      border-left: 3px solid var(--accent);
    }

    .resume-section h5 {
      color: var(--accent);
      margin-bottom: 8px;
      font-size: 0.95rem;
    }

    .resume-content {
      color: var(--muted);
      font-size: 0.9rem;
      line-height: 1.5;
    }

    .resume-link {
      display: inline-block;
      color: var(--accent);
      text-decoration: none;
      padding: 6px 12px;
      background: rgba(8,160,255,0.1);
      border-radius: 20px;
      margin-top: 8px;
      transition: all 0.2s ease;
    }

    .resume-link:hover {
      background: var(--accent);
      color: #021025;
    }

    /* Стили для заявок соискателя */
    .application-item {
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.05);
      border-radius: var(--radius);
      padding: 16px;
      margin-bottom: 16px;
      transition: all 0.3s ease;
    }

    .application-item:hover {
      background: rgba(255,255,255,0.05);
      border-color: var(--accent);
    }

    .application-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 12px;
    }

    .application-title {
      font-size: 1.1rem;
      font-weight: 600;
      color: var(--accent);
    }

    .application-date {
      font-size: 0.8rem;
      color: var(--muted);
    }

    .application-company {
      color: var(--muted);
      font-size: 0.9rem;
      margin-bottom: 8px;
    }

    .application-skills {
      background: rgba(255,255,255,0.02);
      border-radius: 8px;
      padding: 10px;
      margin: 10px 0;
      font-size: 0.9rem;
    }

    .application-status {
      display: inline-block;
      background: rgba(8,160,255,0.1);
      color: var(--accent);
      padding: 4px 12px;
      border-radius: 20px;
      font-size: 0.8rem;
      margin-top: 8px;
    }

    .modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.8);display:none;align-items:center;justify-content:center;padding:20px;z-index:2000}
    .modal{background:#021023;padding:16px;border-radius:12px;max-width:400px;width:100%;border:1px solid rgba(255,255,255,0.1)}
    .modal header{display:flex;justify-content:space-between;align-items:center;margin-bottom:15px}
    .modal header strong{color:#ffffff}
    .modal form{display:flex;flex-direction:column;gap:10px}
    .modal input, .modal select{background:transparent;border:1px solid rgba(255,255,255,0.15);padding:10px;border-radius:8px;color:#ffffff}
    .modal input::placeholder{color:rgba(255,255,255,0.5)}
    .modal input:focus{border-color:var(--accent);outline:none}
    
    .login-hint{font-size:0.8rem;opacity:0.7;margin-top:5px;text-align:center}
    .footer-links{display:flex;gap:20px;justify-content:center;margin-top:10px;font-size:0.8rem}
    .footer-links a{color:#ffffff;opacity:0.7;text-decoration:none;cursor:pointer}
    .footer-links a:hover{opacity:1;color:var(--accent)}
    
    .age-hint{font-size:0.75rem;opacity:0.7;margin-top:2px;text-align:left}
    
    /* Уведомления */
    .notification-container {
      position: fixed;
      bottom: 20px;
      right: 20px;
      z-index: 9999;
      display: flex;
      flex-direction: column;
      gap: 10px;
      max-width: 350px;
    }

    .notification {
      background: var(--card);
      border-left: 4px solid var(--accent);
      border-radius: var(--radius);
      padding: 16px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
      animation: slideIn 0.3s ease forwards;
      display: flex;
      align-items: flex-start;
      gap: 12px;
      border: 1px solid rgba(255,255,255,0.05);
      backdrop-filter: blur(10px);
    }

    .notification-icon {
      font-size: 1.5rem;
      line-height: 1;
    }

    .notification-content {
      flex: 1;
    }

    .notification-title {
      font-weight: 600;
      margin-bottom: 4px;
      color: #ffffff;
    }

    .notification-message {
      font-size: 0.9rem;
      opacity: 0.9;
      color: #ffffff;
    }

    .notification-close {
      background: transparent;
      border: none;
      color: rgba(255,255,255,0.5);
      cursor: pointer;
      font-size: 1.2rem;
      padding: 0 4px;
      transition: color 0.2s;
    }

    .notification-close:hover {
      color: #ffffff;
    }

    @keyframes slideIn {
      from {
        transform: translateX(100%);
        opacity: 0;
      }
      to {
        transform: translateX(0);
        opacity: 1;
      }
    }

    @keyframes slideOut {
      from {
        transform: translateX(0);
        opacity: 1;
      }
      to {
        transform: translateX(100%);
        opacity: 0;
      }
    }

    .notification.fade-out {
      animation: slideOut 0.3s ease forwards;
    }

    /* Стили для карточек функций в разработке */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
      margin: 15px 0;
    }

    .feature-card {
      background: rgba(255,255,255,0.03);
      border: 1px solid rgba(255,255,255,0.05);
      border-radius: var(--radius);
      padding: 15px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-align: center;
    }

    .feature-card:hover {
      background: rgba(8,160,255,0.1);
      border-color: var(--accent);
      transform: translateY(-2px);
    }

    .feature-icon {
      font-size: 2rem;
      margin-bottom: 8px;
    }

    .feature-title {
      font-weight: 600;
      margin-bottom: 4px;
    }

    .feature-desc {
      font-size: 0.8rem;
      opacity: 0.7;
    }

    .feature-badge {
      display: inline-block;
      background: rgba(8,160,255,0.2);
      color: var(--accent);
      padding: 4px 8px;
      border-radius: 20px;
      font-size: 0.7rem;
      margin-top: 8px;
    }

    /* Стили для страниц функций */
    .feature-page {
      padding: 20px;
      text-align: center;
    }

    .feature-page-icon {
      font-size: 4rem;
      margin-bottom: 20px;
    }

    .feature-page-title {
      font-size: 1.5rem;
      font-weight: 700;
      margin-bottom: 10px;
      background: linear-gradient(135deg, #0ea5e9, #7c3aed);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .feature-page-desc {
      color: var(--muted);
      margin-bottom: 30px;
      line-height: 1.6;
    }

    .feature-progress {
      background: rgba(255,255,255,0.05);
      border-radius: 20px;
      height: 8px;
      margin: 20px 0;
      overflow: hidden;
    }

    .feature-progress-bar {
      height: 100%;
      background: linear-gradient(90deg, var(--accent), #7c3aed);
      width: 30%;
      border-radius: 20px;
    }

    .feature-status {
      display: flex;
      justify-content: space-between;
      color: var(--muted);
      font-size: 0.9rem;
      margin-bottom: 30px;
    }

    .feature-actions {
      display: flex;
      gap: 10px;
      justify-content: center;
    }

    /* Стили для employer modal */
    #employerModal .modal {
      max-width: 600px;
      max-height: 80vh;
      overflow-y: auto;
    }

    #employerModal .modal::-webkit-scrollbar {
      width: 6px;
    }

    #employerModal .modal::-webkit-scrollbar-track {
      background: rgba(255,255,255,0.05);
    }

    #employerModal .modal::-webkit-scrollbar-thumb {
      background: var(--accent);
      border-radius: 3px;
    }

    /* Стили для my applications modal */
    #myApplicationsModal .modal {
      max-width: 600px;
      max-height: 80vh;
      overflow-y: auto;
    }

    #myApplicationsModal .modal::-webkit-scrollbar {
      width: 6px;
    }

    #myApplicationsModal .modal::-webkit-scrollbar-track {
      background: rgba(255,255,255,0.05);
    }

    #myApplicationsModal .modal::-webkit-scrollbar-thumb {
      background: var(--accent);
      border-radius: 3px;
    }

    @media (max-width:960px){
      main{grid-template-columns:1fr}
      .filters-section{grid-template-columns:1fr;gap:12px}
      .filter-group:last-child{grid-column:1;margin-top:8px}
      .features-grid{grid-template-columns:1fr}
    }
    @media (max-width:768px){
      .profile-container{position:static;margin-top:10px;align-self:flex-end}
    }
  </style>
</head>
<body>
  <div class="wrap" role="application" aria-labelledby="title">
    <header>
      <div class="brand">
        <div class="logo" aria-hidden="true">TH❤</div>
        <div>
          <h1 id="title">Teen Hustle</h1>
          <p class="lead">Поиск работы для подростков 14-17 лет</p>
        </div>
      </div>

      <div class="filters" aria-hidden="false">
        <button class="ghost" id="show-favs" title="Показать сохраненные вакансии">❤ Сохранённые <span id="fav-count" style="margin-left:6px;color:#ffffff;opacity:0.8">0</span></button>
        <button class="ghost" id="action-button">Мои заявки</button>
        <button class="ghost" id="dev-menu-btn" title="Меню разработки">⚙️ Разработка</button>
      </div>
    </header>

    <div class="profile-container" id="profileContainer">
      <div class="profile-info" id="profileInfo" style="display: none;">
        <div class="profile-name">
          <span id="profileName"></span>
          <span class="profile-age" id="profileAge"></span>
        </div>
        <div class="profile-status">
          <div class="status-dot"></div>
          <span>В сети</span>
        </div>
      </div>
      <div class="profile-avatar" id="profileToggle">
        <span id="avatarText">👤</span>
      </div>
      <div class="profile-dropdown" id="profileDropdown">
        <div id="profileDropdownContent"></div>
      </div>
    </div>

    <!-- Модальное окно логина -->
    <div class="modal-backdrop" id="loginModal">
      <div class="modal">
        <header>
          <strong>Вход в профиль</strong>
          <button class="ghost" id="closeLoginBtn" style="padding:5px 10px;">✕</button>
        </header>
        <form id="loginForm">
          <input type="text" id="loginName" placeholder="Имя и фамилия" required value="Анна Петрова">
          <input type="email" id="loginEmail" placeholder="Email" required value="anna@example.com">
          <div style="display:flex;gap:10px;margin:5px 0">
            <label style="display:flex;align-items:center;gap:5px;">
              <input type="radio" name="userType" value="seeker" id="userTypeSeeker" checked> Соискатель (14-17 лет)
            </label>
            <label style="display:flex;align-items:center;gap:5px;">
              <input type="radio" name="userType" value="employer" id="userTypeEmployer"> Работодатель (18+)
            </label>
          </div>
          <input type="number" id="loginAge" placeholder="Возраст" min="14" max="17" required value="16">
          <div class="age-hint" id="ageHint">Для соискателя: от 14 до 17 лет</div>
          <button type="submit" class="btn">Войти</button>
          <div class="login-hint">Просим указать свой настоящий возраст, иначе ваш аккаунт может быть удален!(+блокировка по номеру)</div>
        </form>
      </div>
    </div>

    <div class="filters-section" role="search" aria-label="Фильтры поиска работы">
      <div class="filter-group">
        <div class="filter-label">Поиск по названию</div>
        <input id="q" type="search" placeholder="Например: выгульщик собак" aria-label="Поиск вакансий" />
      </div>
      
      <div class="filter-group">
        <div class="filter-label">Тип работы</div>
        <select id="type" aria-label="Тип работы">
          <option value="">Любая категория</option>
          <option value="разгрузка">Разгрузка</option>
          <option value="расфасовщик">Расфасовщик</option>
          <option value="помощник">Помощник</option>
          <option value="тестировщик">Тестировщик</option>
          <option value="ручная работа">Ручная работа</option>
        </select>
      </div>
      
      <div class="filter-group">
        <div class="filter-label">Местоположение</div>
        <input id="location" type="search" placeholder="Город или 'из дома'" aria-label="Местоположение" />
      </div>
      
      <div class="filter-group">
        <div class="filter-label">Ваш возраст (14-17)</div>
        <input id="age" type="number" min="14" max="17" placeholder="14-17" aria-label="Ваш возраст" title="Введите возраст от 14 до 17 лет" />
      </div>
      
      <div class="filter-group">
        <div class="filter-label">Макс. часов в неделю</div>
        <select id="maxHours" aria-label="Максимум часов в неделю" title="Максимум часов в неделю">
          <option value="">Любое количество часов</option>
          <option value="10">≤10 часов в неделю</option>
          <option value="20">≤20 часов в неделю</option>
          <option value="30">≤30 часов в неделю</option>
        </select>
      </div>
      
      <div class="filter-group" style="display:flex;flex-direction:column;gap:8px;justify-content:flex-end;height:100%">
        <div style="display:flex;gap:8px;justify-content:flex-end">
          <button class="btn" id="searchBtn" aria-label="Поиск">Поиск</button>
          <button class="ghost" id="clear">Очистить</button>
        </div>
      </div>
    </div>

    <main>
      <section aria-labelledby="results-title">
        <h2 id="results-title" style="font-size:1.05rem;margin:6px 0 12px 0;color:#ffffff">Результат:</h2>

        <div class="job-list" id="jobs" role="list" aria-live="polite"></div>

        <div style="margin-top:12px;display:flex;gap:8px;align-items:center">
          <button class="ghost" id="loadMore">Загрузить больше вакансий</button>
        </div>
      </section>

      <aside class="card" aria-labelledby="sidebar-title">
        <h4 id="sidebar-title">Быстрая статистика</h4>
        <div class="quick-stats" id="stats">
          <div class="stat"><strong id="stat-count">5</strong><div style="font-size:.82rem">Вакансии</div></div>
          <div class="stat"><strong id="stat-remote">2</strong><div style="font-size:.82rem">Из дома</div></div>
          <div class="stat"><strong id="stat-types">5</strong><div style="font-size:.82rem">Типы</div></div>
        </div>

        <hr style="border:none;height:1px;background:rgba(255,255,255,0.1);margin:12px 0">

        <div>
          <h4 style="margin-bottom:6px;color:#ffffff">Советы для подростков 14-17 лет:</h4>
          <ul style="margin:0;padding-left:18px;color:#ffffff;font-size:.95rem;opacity:0.9">
            <li>Соблюдайте субординацию!</li>
            <li>Используйте простое электронное письмо и краткое резюме или описание навыков!</li>
            <li>Если вы трудоустроены на одну вакансию, то можете быть устроены и на другую (за невыполненную работу - штраф от работодателя, можно оспорить)</li>
          </ul>
        </div>

        <hr style="border:none;height:1px;background:rgba(255,255,255,0.1);margin:12px 0">

        <div>
          <h4 style="margin-bottom:6px;color:#ffffff">Работодатель? Опубликуйте вакансию!</h4>
          <p style="margin:0;color:#ffffff;opacity:0.9">Мы рекомендуем указать чёткие требования к возрасту (14-17 лет) и рабочему времени!</p>
        </div>
      </aside>
    </main>

    <footer>
      <p style="margin:8px 0 0 0">Прототип для защиты в МГТУ имени Баумана. Для подростков 14-17 лет.</p>
      <div class="footer-links">
        <a class="footer-link" data-page="about">О проекте</a>
        <a class="footer-link" data-page="rules">Правила</a>
        <a class="footer-link" data-page="help">Помощь</a>
        <a class="footer-link" data-page="contact">Контакты</a>
      </div>
    </footer>
  </div>

  <!-- Контейнер для уведомлений -->
  <div class="notification-container" id="notificationContainer"></div>

  <!-- Модальное окно моих заявок -->
  <div class="modal-backdrop" id="myApplicationsModal">
    <div class="modal">
      <header>
        <strong>📋 Мои заявки</strong>
        <button class="ghost" id="closeMyApplicationsModal" style="padding:5px 10px;">✕</button>
      </header>
      <div id="myApplicationsContent">
        <div style="text-align:center;padding:40px 20px;color:#ffffff;opacity:0.9">
          <div style="font-size:48px;margin-bottom:20px">📭</div>
          <h3 style="color:#ffffff;margin-bottom:12px">У вас пока нет заявок</h3>
          <p>Откликнитесь на первую вакансию!</p>
        </div>
        <div id="applicationsList" style="display:none"></div>
      </div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelMyApplicationsModal">Закрыть</button>
      </div>
    </div>
  </div>

  <!-- Модальное окно разработки (главное меню) -->
  <div class="modal-backdrop" id="devModal">
    <div class="modal" style="max-width: 600px;">
      <header>
        <strong>⚙️ Меню разработки</strong>
        <button class="ghost" id="closeDevModal" style="padding:5px 10px;">✕</button>
      </header>
      <div style="padding: 10px 0;">
        <p style="color: var(--muted); margin-bottom: 15px;">Выберите функцию для просмотра деталей:</p>
        <div class="features-grid">
          <div class="feature-card" data-feature="profile">
            <div class="feature-icon">👤</div>
            <div class="feature-title">Редактирование профиля</div>
            <div class="feature-desc">Настройка личных данных</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="messages">
            <div class="feature-icon">💬</div>
            <div class="feature-title">Система сообщений</div>
            <div class="feature-desc">Чат с работодателями</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="notifications">
            <div class="feature-icon">🔔</div>
            <div class="feature-title">Настройки уведомлений</div>
            <div class="feature-desc">Управление оповещениями</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="stats">
            <div class="feature-icon">📊</div>
            <div class="feature-title">Расширенная статистика</div>
            <div class="feature-desc">Аналитика и графики</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="export">
            <div class="feature-icon">📤</div>
            <div class="feature-title">Экспорт данных</div>
            <div class="feature-desc">Скачать свои заявки</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="import">
            <div class="feature-icon">📥</div>
            <div class="feature-title">Импорт данных</div>
            <div class="feature-desc">Загрузить резюме</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="theme">
            <div class="feature-icon">🎨</div>
            <div class="feature-title">Настройки темы</div>
            <div class="feature-desc">Оформление сайта</div>
            <div class="feature-badge">в разработке</div>
          </div>
          <div class="feature-card" data-feature="backup">
            <div class="feature-icon">💾</div>
            <div class="feature-title">Резервное копирование</div>
            <div class="feature-desc">Сохранение данных</div>
            <div class="feature-badge">в разработке</div>
          </div>
        </div>
      </div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelDevModal">Закрыть</button>
      </div>
    </div>
  </div>

  <!-- Модальные окна для каждой функции в разработке -->
  <div class="modal-backdrop" id="featureProfileModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>👤 Редактирование профиля</strong>
        <button class="ghost close-feature-modal" data-modal="featureProfileModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">👤</div>
        <div class="feature-page-title">Редактирование профиля</div>
        <div class="feature-page-desc">
          Функция редактирования профиля находится в активной разработке. 
          Скоро вы сможете изменять свои личные данные, загружать фото и настраивать приватность.
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 45%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>45% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Мы сообщим вам, когда функция будет готова!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureProfileModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureMessagesModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>💬 Система сообщений</strong>
        <button class="ghost close-feature-modal" data-modal="featureMessagesModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">💬</div>
        <div class="feature-page-title">Система сообщений</div>
        <div class="feature-page-desc">
          Внутренний чат для общения с работодателями находится в разработке. 
          Вы сможете обсуждать детали вакансий, договариваться о собеседованиях и получать обратную связь.
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 25%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>25% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Мы сообщим вам о запуске чата!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureMessagesModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureNotificationsModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>🔔 Настройки уведомлений</strong>
        <button class="ghost close-feature-modal" data-modal="featureNotificationsModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">🔔</div>
        <div class="feature-page-title">Настройки уведомлений</div>
        <div class="feature-page-desc">
          Управляйте тем, какие уведомления вы хотите получать: новые вакансии, ответы работодателей, 
          напоминания и многое другое. Функция в разработке.
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 15%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>15% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Скоро вы сможете настроить уведомления!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureNotificationsModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureStatsModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>📊 Расширенная статистика</strong>
        <button class="ghost close-feature-modal" data-modal="featureStatsModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">📊</div>
        <div class="feature-page-title">Расширенная статистика</div>
        <div class="feature-page-desc">
          Подробная аналитика ваших откликов, просмотров и успешных трудоустройств. 
          Графики, диаграммы и полезные метрики для эффективного поиска работы.
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 10%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>10% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Статистика скоро появится!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureStatsModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureExportModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>📤 Экспорт данных</strong>
        <button class="ghost close-feature-modal" data-modal="featureExportModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">📤</div>
        <div class="feature-page-title">Экспорт данных</div>
        <div class="feature-page-desc">
          Скачивайте свои заявки, резюме и историю откликов в различных форматах: 
          PDF, Excel, JSON. Удобно для архивации и печати.
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 20%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>20% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Экспорт данных будет доступен скоро!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureExportModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureImportModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>📥 Импорт данных</strong>
        <button class="ghost close-feature-modal" data-modal="featureImportModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">📥</div>
        <div class="feature-page-title">Импорт данных</div>
        <div class="feature-page-desc">
          Загружайте готовые резюме в форматах PDF, DOCX или создавайте их прямо на сайте 
          с помощью удобного конструктора.
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 30%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>30% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Импорт резюме скоро заработает!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureImportModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureThemeModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>🎨 Настройки темы</strong>
        <button class="ghost close-feature-modal" data-modal="featureThemeModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">🎨</div>
        <div class="feature-page-title">Настройки темы</div>
        <div class="feature-page-desc">
          Выбирайте цветовое оформление сайта под свой вкус: темная тема, светлая, 
          цветные акценты и многое другое. Индивидуальный стиль для каждого!
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 50%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>50% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Скоро вы сможете менять тему!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureThemeModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="featureBackupModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>💾 Резервное копирование</strong>
        <button class="ghost close-feature-modal" data-modal="featureBackupModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">💾</div>
        <div class="feature-page-title">Резервное копирование</div>
        <div class="feature-page-desc">
          Автоматическое сохранение ваших данных, возможность восстановления 
          в случае потери информации. Ваши данные в безопасности!
        </div>
        <div class="feature-progress">
          <div class="feature-progress-bar" style="width: 35%;"></div>
        </div>
        <div class="feature-status">
          <span>⚙️ В разработке</span>
          <span>35% готово</span>
        </div>
        <div class="feature-actions">
          <button class="btn" onclick="showNotification('🔔', 'Уведомление', 'Бэкапы скоро появятся!')">🔔 Уведомить меня</button>
          <button class="ghost close-feature-modal" data-modal="featureBackupModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <!-- Модальные окна для футера -->
  <div class="modal-backdrop" id="aboutModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>ℹ️ О проекте</strong>
        <button class="ghost close-footer-modal" data-modal="aboutModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">ℹ️</div>
        <div class="feature-page-title">Teen Hustle</div>
        <div class="feature-page-desc">
          Платформа для поиска работы подростками 14-17 лет. Мы помогаем молодым людям 
          найти первую работу, получить ценный опыт и заработать первые деньги.
        </div>
        <div style="text-align: left; margin-top: 20px;">
          <p><strong>Наша миссия:</strong> Сделать процесс трудоустройства подростков простым, безопасным и эффективным.</p>
          <p><strong>Для кого:</strong> Подростки 14-17 лет, работодатели, готовые работать с молодежью.</p>
          <p><strong>Преимущества:</strong> Проверенные вакансии, защита прав, поддержка 24/7.</p>
        </div>
        <div class="feature-actions" style="margin-top: 20px;">
          <button class="ghost close-footer-modal" data-modal="aboutModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="rulesModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>📜 Правила</strong>
        <button class="ghost close-footer-modal" data-modal="rulesModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">📜</div>
        <div class="feature-page-title">Правила платформы</div>
        <div style="text-align: left; margin-top: 20px;">
          <ol style="padding-left: 20px; color: var(--muted);">
            <li style="margin-bottom: 10px;">Указывайте только настоящий возраст. За фальсификацию - блокировка!</li>
            <li style="margin-bottom: 10px;">Соблюдайте субординацию и уважайте других пользователей.</li>
            <li style="margin-bottom: 10px;">Не передавайте личные данные третьим лицам.</li>
            <li style="margin-bottom: 10px;">При трудоустройстве обязательно заключайте договор.</li>
            <li style="margin-bottom: 10px;">В случае конфликтов обращайтесь в поддержку.</li>
          </ol>
        </div>
        <div class="feature-actions" style="margin-top: 20px;">
          <button class="ghost close-footer-modal" data-modal="rulesModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="helpModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>❓ Помощь</strong>
        <button class="ghost close-footer-modal" data-modal="helpModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">❓</div>
        <div class="feature-page-title">Центр помощи</div>
        <div style="text-align: left; margin-top: 20px;">
          <p><strong>Часто задаваемые вопросы:</strong></p>
          <ul style="list-style: none; padding: 0;">
            <li style="margin-bottom: 10px;">❓ <strong>Как откликнуться на вакансию?</strong> Нажмите кнопку "Откликнуться" на карточке вакансии и заполните форму.</li>
            <li style="margin-bottom: 10px;">❓ <strong>Как сохранить вакансию?</strong> Нажмите сердечко на карточке вакансии.</li>
            <li style="margin-bottom: 10px;">❓ <strong>Безопасно ли это?</strong> Да, мы проверяем всех работодателей.</li>
            <li style="margin-bottom: 10px;">❓ <strong>Сколько стоит?</strong> Платформа полностью бесплатна для соискателей.</li>
          </ul>
          <p style="margin-top: 20px;"><strong>Служба поддержки:</strong> support@teenhustle.ru</p>
        </div>
        <div class="feature-actions" style="margin-top: 20px;">
          <button class="ghost close-footer-modal" data-modal="helpModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="contactModal">
    <div class="modal" style="max-width: 500px;">
      <header>
        <strong>📞 Контакты</strong>
        <button class="ghost close-footer-modal" data-modal="contactModal" style="padding:5px 10px;">✕</button>
      </header>
      <div class="feature-page">
        <div class="feature-page-icon">📞</div>
        <div class="feature-page-title">Свяжитесь с нами</div>
        <div style="text-align: left; margin-top: 20px;">
          <p><strong>Email:</strong> info@teenhustle.ru</p>
          <p><strong>Телефон:</strong> +7 (999) 123-45-67</p>
          <p><strong>Адрес:</strong> г. Москва, ул. Баумана, д. 5</p>
          <p><strong>Время работы:</strong> Пн-Пт 9:00 - 18:00</p>
        </div>
        <div class="feature-actions" style="margin-top: 20px;">
          <button class="btn" onclick="showNotification('📧', 'Письмо отправлено', 'Мы ответим вам в ближайшее время!')">✉️ Написать нам</button>
          <button class="ghost close-footer-modal" data-modal="contactModal">Закрыть</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="modal" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal" role="document">
      <header>
        <strong id="modalTitle">Откликнуться на вакансию</strong>
        <button id="closeModal" class="ghost" aria-label="Закрыть">✕</button>
      </header>

      <form id="applyForm" novalidate>
        <input type="hidden" id="jobId" />
        
        <div>
          <label for="appName">ФИО</label>
          <input id="appName" type="text" required placeholder="Фамилия Имя Отчество" />
        </div>
        
        <div>
          <label for="appAge">Ваш возраст</label>
          <input id="appAge" type="number" required min="14" max="17" placeholder="14" title="Введите возраст от 14 до 17 лет" />
        </div>
        
        <div>
          <label for="appEmail">Email</label>
            <input id="appEmail" type="email" required placeholder="тинэйджерпочта@mail.ru" />
        </div>
        
        <label for="appSkills">Ваши навыки и умения</label>
        <textarea id="appSkills" placeholder="Перечислите ваши навыки через запятую..." required></textarea>
        
        <label for="appMotivation">Почему вы хотите работать именно у нас?</label>
        <textarea id="appMotivation" placeholder="Расскажите о вашей мотивации..." rows="3"></textarea>
        
        <div>
          <input type="checkbox" id="appGuardian" name="appGuardian" required>
          <label for="appGuardian">Подтверждаю, что имею согласие родителей/опекунов на трудоустройство</label>
        </div>
        
        <div>
          <input type="checkbox" id="appSchedule" name="appSchedule" required>
          <label for="appSchedule">Готов(а) соблюдать рабочий график и согласовывать изменения с работодателем</label>
        </div>
        
        <div>
          <input type="checkbox" id="appDocuments" name="appDocuments" required>
          <label for="appDocuments">Имею все необходимые документы (паспорт, СНИЛС, ИНН, мед.справка)</label>
        </div>
        
        <label for="appNote">Дополнительная информация (если есть резюме, желательно прикрепить через "Google Docs")</label>
        <textarea id="appNote" placeholder="Дополнительные сведения о себе, ссылка на резюме..." rows="2"></textarea>
        
        <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
          <button type="button" class="ghost" id="cancelApply">Закрыть</button>
          <button type="submit" class="btn">Отправить заявку</button>
        </div>
      </form>
    </div>
  </div>

  <div class="modal-backdrop" id="employerModal" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal" role="document">
      <header>
        <strong id="employerModalTitle">Отклики на вакансию</strong>
        <button id="closeEmployerModal" class="ghost" aria-label="Закрыть">✕</button>
      </header>

      <div id="employerModalContent">
        <div style="text-align:center;padding:40px 20px;color:#ffffff;opacity:0.9">
          <div style="font-size:48px;margin-bottom:20px">📋</div>
          <h3 style="color:#ffffff;margin-bottom:12px">Отклики на вакансию</h3>
          <p>Тут будут появляться кандидаты, которые хотят устроиться к вам!</p>
          <p style="font-size:0.9rem;margin-top:20px">Пока здесь пусто, но скоро появятся первые соискатели</p>
        </div>
        
        <div id="candidatesList" style="display:none"></div>
      </div>
      
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelEmployerModal">Закрыть</button>
      </div>
    </div>
  </div>

  <script>
    let currentUser = null;
    let isEmployerMode = false;
    
    document.addEventListener('DOMContentLoaded', function() {
      const savedUser = localStorage.getItem('currentUser');
      if (savedUser) {
        currentUser = JSON.parse(savedUser);
        isEmployerMode = currentUser.mode === 'employer';
        updateProfileUI();
        showNotification('🔄', 'Сессия восстановлена', 'Добро пожаловать обратно, ' + currentUser.name + '!');
      } else {
        document.getElementById('loginModal').style.display = 'flex';
      }

      initProfileDropdown();
      clearFavoritesOnFirstLoad();
      initializeUserMode();
      
      document.getElementById('userTypeSeeker').addEventListener('change', updateAgeField);
      document.getElementById('userTypeEmployer').addEventListener('change', updateAgeField);
      
      initDevMenu();
      
      initFooterLinks();
      
      initMyApplicationsModal();
      
      setTimeout(() => {
        showNotification('👋', 'Добро пожаловать!', 'Рады видеть вас на Teen Hustle');
      }, 1000);
    });

    window.showNotification = function(icon, title, message, duration = 5000) {
      const container = document.getElementById('notificationContainer');
      const notification = document.createElement('div');
      notification.className = 'notification';
      notification.innerHTML = `
        <div class="notification-icon">${icon}</div>
        <div class="notification-content">
          <div class="notification-title">${title}</div>
          <div class="notification-message">${message}</div>
        </div>
        <button class="notification-close" onclick="this.parentElement.classList.add('fade-out'); setTimeout(() => this.parentElement.remove(), 300);">&times;</button>
      `;
      
      container.appendChild(notification);
      
      setTimeout(() => {
        if (notification.parentNode) {
          notification.classList.add('fade-out');
          setTimeout(() => notification.remove(), 300);
        }
      }, duration);
    }

    function initDevMenu() {
      const devBtn = document.getElementById('dev-menu-btn');
      const devModal = document.getElementById('devModal');
      const closeDevModal = document.getElementById('closeDevModal');
      const cancelDevModal = document.getElementById('cancelDevModal');
      
      if (devBtn) {
        devBtn.addEventListener('click', () => {
          devModal.style.display = 'flex';
        });
      }
      
      if (closeDevModal) {
        closeDevModal.addEventListener('click', () => {
          devModal.style.display = 'none';
        });
      }
      
      if (cancelDevModal) {
        cancelDevModal.addEventListener('click', () => {
          devModal.style.display = 'none';
        });
      }
      
      document.querySelectorAll('.feature-card').forEach(card => {
        card.addEventListener('click', (e) => {
          const feature = e.currentTarget.dataset.feature;
          const modalId = `feature${feature.charAt(0).toUpperCase() + feature.slice(1)}Modal`;
          const modal = document.getElementById(modalId);
          
          if (modal) {
            devModal.style.display = 'none';
            modal.style.display = 'flex';
          }
        });
      });
      
      document.querySelectorAll('.close-feature-modal').forEach(btn => {
        btn.addEventListener('click', (e) => {
          const modalId = e.currentTarget.dataset.modal;
          const modal = document.getElementById(modalId);
          if (modal) {
            modal.style.display = 'none';
          }
        });
      });
    }

    function initMyApplicationsModal() {
      const myApplicationsModal = document.getElementById('myApplicationsModal');
      const closeBtn = document.getElementById('closeMyApplicationsModal');
      const cancelBtn = document.getElementById('cancelMyApplicationsModal');
      
      if (closeBtn) {
        closeBtn.addEventListener('click', () => {
          myApplicationsModal.style.display = 'none';
        });
      }
      
      if (cancelBtn) {
        cancelBtn.addEventListener('click', () => {
          myApplicationsModal.style.display = 'none';
        });
      }
    }

    function showMyApplications() {
      if (!currentUser) {
        showNotification('⚠️', 'Требуется вход', 'Пожалуйста, войдите в профиль');
        document.getElementById('loginModal').style.display = 'flex';
        return;
      }
      
      const applications = loadApplications();
      const userEmail = currentUser.email;
      const userApplications = applications.filter(app => app.email === userEmail);
      
      const emptyState = document.querySelector('#myApplicationsContent > div[style*="text-align:center"]');
      const applicationsList = document.getElementById('applicationsList');
      
      if (userApplications.length === 0) {
        if (emptyState) emptyState.style.display = 'block';
        if (applicationsList) applicationsList.style.display = 'none';
      } else {
        if (emptyState) emptyState.style.display = 'none';
        if (applicationsList) {
          applicationsList.style.display = 'block';
          applicationsList.innerHTML = '';
          
          userApplications.sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
          
          userApplications.forEach(app => {
            const job = jobsData.find(j => j.id === app.jobId) || { title: 'Неизвестная вакансия', company: 'Неизвестная компания' };
            const date = new Date(app.timestamp).toLocaleString('ru-RU', {
              day: '2-digit',
              month: '2-digit',
              year: 'numeric',
              hour: '2-digit',
              minute: '2-digit'
            });
            
            const appElement = document.createElement('div');
            appElement.className = 'application-item';
            appElement.innerHTML = `
              <div class="application-header">
                <span class="application-title">${escapeHtml(job.title)}</span>
                <span class="application-date">${date}</span>
              </div>
              <div class="application-company">${escapeHtml(job.company || 'Компания не указана')}</div>
              <div class="application-skills">
                <strong>Навыки:</strong> ${escapeHtml(app.skills)}
              </div>
              ${app.motivation ? `<div style="margin: 8px 0; color: var(--muted);"><strong>Мотивация:</strong> ${escapeHtml(app.motivation)}</div>` : ''}
              <div class="application-status">✓ Заявка отправлена</div>
            `;
            
            applicationsList.appendChild(appElement);
          });
        }
      }
      
      document.getElementById('myApplicationsModal').style.display = 'flex';
    }

    function initFooterLinks() {
      document.querySelectorAll('.footer-link').forEach(link => {
        link.addEventListener('click', (e) => {
          e.preventDefault();
          const page = e.target.dataset.page;
          const modalId = page + 'Modal';
          const modal = document.getElementById(modalId);
          
          if (modal) {
            modal.style.display = 'flex';
          }
        });
      });
      
      document.querySelectorAll('.close-footer-modal').forEach(btn => {
        btn.addEventListener('click', (e) => {
          const modalId = e.currentTarget.dataset.modal;
          const modal = document.getElementById(modalId);
          if (modal) {
            modal.style.display = 'none';
          }
        });
      });
    }

    function updateAgeField() {
      const ageInput = document.getElementById('loginAge');
      const ageHint = document.getElementById('ageHint');
      
      if (document.getElementById('userTypeSeeker').checked) {
        ageInput.min = 14;
        ageInput.max = 17;
        ageInput.placeholder = "14-17";
        ageInput.value = 16;
        ageHint.textContent = "Для соискателя: от 14 до 17 лет";
      } else {
        ageInput.min = 18;
        ageInput.max = 100;
        ageInput.placeholder = "18+";
        ageInput.value = 35;
        ageHint.textContent = "Для работодателя: от 18 лет";
      }
    }

    document.getElementById('loginForm').addEventListener('submit', function(e) {
      e.preventDefault();
      
      const name = document.getElementById('loginName').value;
      const email = document.getElementById('loginEmail').value;
      const age = parseInt(document.getElementById('loginAge').value);
      const mode = document.querySelector('input[name="userType"]:checked').value;
      
      if (mode === 'seeker' && (age < 14 || age > 17)) {
        showNotification('❌', 'Ошибка', 'Для соискателя возраст должен быть от 14 до 17 лет');
        return;
      }
      if (mode === 'employer' && (age < 18 || age > 100)) {
        showNotification('❌', 'Ошибка', 'Для работодателя возраст должен быть от 18 лет');
        return;
      }
      
      currentUser = { name, email, age, mode };
      isEmployerMode = mode === 'employer';
      
      localStorage.setItem('currentUser', JSON.stringify(currentUser));
      document.getElementById('loginModal').style.display = 'none';
      
      updateProfileUI();
      updateModeFromUser();
      
      showNotification('✅', 'Успешно!', `Добро пожаловать, ${name}!`);
    });

    document.getElementById('closeLoginBtn').addEventListener('click', function() {
      document.getElementById('loginModal').style.display = 'none';
      showNotification('👋', 'До встречи!', 'Войдите в профиль, чтобы продолжить');
    });

    function updateProfileUI() {
      if (currentUser) {
        document.getElementById('profileInfo').style.display = 'flex';
        document.getElementById('profileName').textContent = currentUser.name;
        document.getElementById('profileAge').textContent = currentUser.age + ' лет';
        document.getElementById('avatarText').textContent = currentUser.name.split(' ').map(n => n[0]).join('').substring(0,2).toUpperCase() || '👤';
        
        updateDropdownContent();
      }
    }

    function updateDropdownContent() {
      const dropdownContent = document.getElementById('profileDropdownContent');
      dropdownContent.innerHTML = `
        <div class="dropdown-header">
          <strong>${escapeHtml(currentUser.name)}</strong>
          <div style="font-size:0.8rem;margin-top:4px">${escapeHtml(currentUser.email)}</div>
          <div style="font-size:0.8rem;margin-top:2px;color:var(--accent)">${currentUser.age} лет</div>
        </div>
        
        <div class="mode-switcher">
          <span class="mode-label">Соискатель</span>
          <label class="switch">
            <input type="checkbox" id="modeToggle" ${isEmployerMode ? 'checked' : ''}>
            <span class="slider"></span>
          </label>
          <span class="mode-label">Работодатель</span>
        </div>
        
        <div class="dropdown-item" id="mode-display">${isEmployerMode ? '👔 Режим: Работодатель' : '👤 Режим: Соискатель'}</div>
        <div class="dropdown-divider"></div>
        <div class="dropdown-item" id="settings-btn">⚙️ Настройки</div>
        <div class="dropdown-item" id="help-btn">❓ Помощь</div>
        <div class="dropdown-divider"></div>
        <div class="dropdown-item" id="logoutBtn">🚪 Выйти</div>
      `;

      document.getElementById('modeToggle').addEventListener('change', function(e) {
        isEmployerMode = e.target.checked;
        currentUser.mode = isEmployerMode ? 'employer' : 'seeker';
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        
        document.getElementById('mode-display').innerHTML = isEmployerMode ? '👔 Режим: Работодатель' : '👤 Режим: Соискатель';
        
        updateActionButton();
        updateFavsButton();
        renderJobs(visibleJobs, true);
        
        showNotification('🔄', 'Режим изменён', isEmployerMode ? 'Теперь вы работодатель' : 'Теперь вы соискатель');
      });

      document.getElementById('settings-btn').addEventListener('click', function() {
        document.getElementById('devModal').style.display = 'flex';
      });

      document.getElementById('help-btn').addEventListener('click', function() {
        document.getElementById('helpModal').style.display = 'flex';
      });

      document.getElementById('logoutBtn').addEventListener('click', function() {
        localStorage.removeItem('currentUser');
        currentUser = null;
        document.getElementById('profileInfo').style.display = 'none';
        document.getElementById('avatarText').textContent = '👤';
        document.getElementById('loginModal').style.display = 'flex';
        showNotification('👋', 'Вы вышли', 'До скорой встречи!');
      });
    }

    function updateModeFromUser() {
      if (currentUser) {
        isEmployerMode = currentUser.mode === 'employer';
        const modeToggle = document.getElementById('modeToggle');
        if (modeToggle) {
          modeToggle.checked = isEmployerMode;
        }
        const modeDisplay = document.getElementById('mode-display');
        if (modeDisplay) {
          modeDisplay.innerHTML = isEmployerMode ? '👔 Режим: Работодатель' : '👤 Режим: Соискатель';
        }
        updateActionButton();
        updateFavsButton();
      }
    }

    const jobsData = [
      {id:'j1',title:'Выгрузка фуры',company:'Магнит',location:'ул. Братиславская, 14, Москва',type:'разгрузка',remote:false,hoursPerWeek:20,МинимальныйВозраст:14,description:'Выгружаете фуру - получаете деньги за смену',tags:['Физическая работа','Оплата за выполненную работу']},
      {id:'j2',title:'Упаковщик-комплектовщик',company:'Мармеладыч',location:'ул. Матросова, 134, Тольятти',type:'расфасовщик',remote:false,hoursPerWeek:15,МинимальныйВозраст:16,description:'Расфасовываете товар по выданному примеру',tags:['Внимательность','Монотонная работа']},
      {id:'j3',title:'Выгульщик Собак и/или Няня для домашних животных',location:'Выезд на адрес',type:'помощник',remote:false,hoursPerWeek:10,МинимальныйВозраст:14,description:'Выгуливаешь собак/сидишь с домашними животными и получаешь оплату в конце недели',tags:['Животные','Няня для животных','Договорные часы работы']},
      {id:'j4',title:'Рукоделие и продажа изделий',location:'Ваш дом',type:'ручная работа',remote:true,hoursPerWeek:0,МинимальныйВозраст:16,description:'Продаешь изделия на заказ и получаешь деньги в конце дня',tags:['Работа на заказ','Удаленная работа','Отправка результата почтой']},
      {id:'j5',title:'Тестировщик приложений',company:'Valve',location:'Ваш дом',type:'тестировщик',remote:true,hoursPerWeek:10,МинимальныйВозраст:14,description:'Тестируете приложение. Ищите наличие багов/недочетов/ошибок и сообщаете о них работодателю',tags:['Тестировщик','Удаленная работа','Активное общение с работодателем']}
    ];

    let visibleJobs = [];
    let pageSize = 4;
    let page = 0;
    let isShowingFavorites = false;
    let currentJobIdForApplications = null;

    const $jobs = document.getElementById('jobs');
    const $q = document.getElementById('q');
    const $type = document.getElementById('type');
    const $location = document.getElementById('location');
    const $age = document.getElementById('age');
    const $maxHours = document.getElementById('maxHours');
    const $searchBtn = document.getElementById('searchBtn');
    const $clear = document.getElementById('clear');
    const $loadMore = document.getElementById('loadMore');
    const $statCount = document.getElementById('stat-count');
    const $statRemote = document.getElementById('stat-remote');
    const $statTypes = document.getElementById('stat-types');
    const $favCount = document.getElementById('fav-count');
    const $showFavs = document.getElementById('show-favs');
    const $actionButton = document.getElementById('action-button');
    const $modeToggle = document.getElementById('modeToggle');
    const $modeDisplay = document.getElementById('mode-display');

    const modal = document.getElementById('modal');
    const modalTitle = document.getElementById('modalTitle');
    const jobIdField = document.getElementById('jobId');

    const employerModal = document.getElementById('employerModal');
    const employerModalTitle = document.getElementById('employerModalTitle');
    const candidatesList = document.getElementById('candidatesList');

    const LS_FAVS = 'teen_hustle_favorites_v1';
    const LS_FIRST_LOAD = 'teen_hustle_first_load';
    const LS_USER_MODE = 'teen_hustle_user_mode';
    const LS_APPLICATIONS = 'teen_hustle_applications';

    function initProfileDropdown() {
      const profileToggle = document.getElementById('profileToggle');
      const profileDropdown = document.getElementById('profileDropdown');
      if (profileToggle && profileDropdown) {
        profileToggle.addEventListener('click', function(e) {
          e.stopPropagation();
          profileDropdown.classList.toggle('show');
        });
        document.addEventListener('click', function() {
          profileDropdown.classList.remove('show');
        });
        profileDropdown.addEventListener('click', function(e) {
          e.stopPropagation();
        });
      }
    }

    function clearFavoritesOnFirstLoad() {
      const firstLoad = localStorage.getItem(LS_FIRST_LOAD);
      if (!firstLoad) {
        localStorage.setItem(LS_FAVS, JSON.stringify([]));
        localStorage.setItem(LS_FIRST_LOAD, 'true');
      }
    }

    function initializeUserMode() {
      const savedMode = localStorage.getItem(LS_USER_MODE);
      if (savedMode === 'employer') {
        isEmployerMode = true;
        if ($modeToggle) $modeToggle.checked = true;
      } else {
        isEmployerMode = false;
        if ($modeToggle) $modeToggle.checked = false;
      }
      updateModeDisplay();
      updateActionButton();
      updateFavsButton();
      renderJobs(visibleJobs, true);
      
      if ($modeToggle) {
        $modeToggle.addEventListener('change', function() {
          isEmployerMode = this.checked;
          localStorage.setItem(LS_USER_MODE, isEmployerMode ? 'employer' : 'seeker');
          updateModeDisplay();
          updateActionButton();
          updateFavsButton();
          renderJobs(visibleJobs, true);
        });
      }
    }

    function updateModeDisplay() {
      if ($modeDisplay) {
        if (isEmployerMode) {
          $modeDisplay.innerHTML = '👔 Режим: Работодатель';
        } else {
          $modeDisplay.innerHTML = '👤 Режим: Соискатель';
        }
      }
    }

    function updateActionButton() {
      if (isEmployerMode) {
        $actionButton.textContent = 'Опубликовать вакансию';
        $actionButton.title = 'Опубликовать новую вакансию';
      } else {
        $actionButton.textContent = 'Мои заявки';
        $actionButton.title = 'Посмотреть мои заявки на вакансии';
      }
    }

    function updateFavsButton() {
      if (isEmployerMode) {
        $showFavs.innerHTML = '👥 Кандидаты вакансий <span id="fav-count" style="margin-left:6px;opacity:0.8">0</span>';
        $showFavs.title = 'Просмотреть кандидатов на вакансии';
      } else {
        $showFavs.innerHTML = '❤ Сохранённые <span id="fav-count" style="margin-left:6px;opacity:0.8">0</span>';
        $showFavs.title = 'Показать сохраненные вакансии';
      }
      updateFavCount();
    }

    function loadFavorites(){
      try{return JSON.parse(localStorage.getItem(LS_FAVS) || '[]');}catch(e){return [];}
    }
    
    function saveFavorites(arr){
      localStorage.setItem(LS_FAVS, JSON.stringify(arr));
      updateFavCount();
    }
    
    function updateFavCount(){
      const favs = loadFavorites();
      const $favCount = document.getElementById('fav-count');
      if (isEmployerMode) {
        $favCount.textContent = '0';
      } else {
        $favCount.textContent = favs.length;
      }
    }
    
    updateFavCount();

    function loadApplications() {
      try {
        return JSON.parse(localStorage.getItem(LS_APPLICATIONS) || '[]');
      } catch(e) {
        return [];
      }
    }
    
    function saveApplications(applications) {
      localStorage.setItem(LS_APPLICATIONS, JSON.stringify(applications));
    }
    
    function removeApplication(appId) {
      const applications = loadApplications();
      const index = applications.findIndex(app => 
        app.email === appId.email && 
        app.timestamp === appId.timestamp
      );
      
      if (index !== -1) {
        applications.splice(index, 1);
        saveApplications(applications);
        return true;
      }
      return false;
    }

    function createJobCard(job){
      const card = document.createElement('article');
      card.className = 'job';
      card.setAttribute('role','listitem');
      
      let actionButtons = '';
      if (isEmployerMode) {
        actionButtons = `
          <button class="btn applications" data-id="${job.id}" aria-label="Просмотреть отклики на ${escapeHtml(job.title)}">📊 Отклики</button>
          <button class="ghost edit-job" data-id="${job.id}">✏ Редактировать</button>
        `;
      } else {
        actionButtons = `
          <button class="btn apply" data-id="${job.id}" aria-label="Откликнуться на ${escapeHtml(job.title)}">Откликнуться!</button>
          <button class="ghost fav" data-id="${job.id}" aria-pressed="false">❤ Сохранить!</button>
        `;
      }
      
      card.innerHTML = `
        <div class="meta">
          <h3>${escapeHtml(job.title)}</h3>
          <div style="display:flex;gap:8px;align-items:center;margin-top:6px">
            <small style="opacity:0.9">${escapeHtml(job.company || job.location)}</small>
            <small style="opacity:0.9">•</small>
            <small style="opacity:0.9">${escapeHtml(job.location)}</small>
          </div>
          <p style="margin:8px 0 0 0;font-size:.95rem;opacity:0.9">${escapeHtml(job.description)}</p>
          <div class="chips" aria-hidden="false">
            <span class="chip">${escapeHtml(job.type)}</span>
            <span class="chip">${job.remote ? 'Удалённая работа' : (job.hoursPerWeek > 0 ? job.hoursPerWeek + ' часов в неделю' : 'Гибкий график')}</span>
            <span class="chip">мин. возраст: ${job.МинимальныйВозраст}+</span>
            ${job.tags.slice(0,3).map(t => `<span class="chip">${escapeHtml(t)}</span>`).join('')}
          </div>
        </div>
        <div class="actions">
          ${actionButtons}
          <small style="opacity:0.8">${job.type}</small>
        </div>
      `;
      
      if (!isEmployerMode) {
        card.querySelector('.apply')?.addEventListener('click', () => openApplyModal(job.id));
        const favBtn = card.querySelector('.fav');
        favBtn?.addEventListener('click', () => toggleFav(job.id, favBtn));
        const favs = loadFavorites();
        if (favs.includes(job.id)) {
          favBtn.setAttribute('aria-pressed','true'); 
          favBtn.textContent = '✓ Сохранено!';
          favBtn.style.color = 'var(--accent)';
        }
      } else {
        card.querySelector('.applications')?.addEventListener('click', () => viewApplications(job.id));
        card.querySelector('.edit-job')?.addEventListener('click', () => editJob(job.id));
      }
      
      return card;
    }

    function renderJobs(list, reset=true){
      if (reset){ 
        $jobs.innerHTML = ''; 
        page = 0; 
      }
      const start = page * pageSize;
      const end = start + pageSize;
      const slice = list.slice(start, end);
      slice.forEach(job => $jobs.appendChild(createJobCard(job)));
      page++;
      
      $loadMore.style.display = (page * pageSize < list.length) ? 'inline-block' : 'none';
      updateStats(list);
    }

    function updateStats(list) {
      $statCount.textContent = list.length;
      $statRemote.textContent = list.filter(j => j.remote).length;
      $statTypes.textContent = new Set(list.map(j => j.type)).size;
    }

    function matchesFilter(job, q, type, loc, ageVal, maxHoursVal){
      if (q) {
        const searchText = (job.title + ' ' + (job.company || '') + ' ' + job.description + ' ' + job.tags.join(' ')).toLowerCase();
        if (!searchText.includes(q.toLowerCase())) {
          return false;
        }
      }
      
      if (type && job.type !== type) {
        return false;
      }
      
      if (loc) {
        const locLower = loc.toLowerCase();
        if (locLower.includes('дом') || locLower.includes('удален') || locLower.includes('из дома')) {
          if (!job.remote) return false;
        } else if (!job.location.toLowerCase().includes(locLower)) {
          return false;
        }
      }
      
      if (ageVal) {
        const age = Number(ageVal);
        if (age < 14 || age > 17) return false;
        if (age < Number(job.МинимальныйВозраст)) return false;
      }
      
      if (maxHoursVal && maxHoursVal !== '') {
        const maxHours = Number(maxHoursVal);
        if (job.hoursPerWeek > maxHours) return false;
      }
      
      return true;
    }

    function performSearch(e){
      if (e) e.preventDefault && e.preventDefault();
      
      const q = $q.value.trim();
      const type = $type.value;
      const loc = $location.value.trim();
      const ageVal = $age.value ? Number($age.value) : null;
      const maxHoursVal = $maxHours.value;
      
      if (ageVal && (ageVal < 14 || ageVal > 17)) {
        showNotification('❌', 'Ошибка', 'Для подростков от 14 до 17 лет включительно');
        $age.focus();
        return;
      }
      
      isShowingFavorites = false;
      visibleJobs = jobsData.filter(job => matchesFilter(job, q, type, loc, ageVal, maxHoursVal));
      renderJobs(visibleJobs, true);
      
      showNotification('🔍', 'Поиск выполнен', `Найдено вакансий: ${visibleJobs.length}`);
    }

    function toggleFav(id, button){
      const favs = loadFavorites();
      const idx = favs.indexOf(id);
      if (idx === -1){
        favs.push(id);
        button.setAttribute('aria-pressed','true'); 
        button.textContent = '✓ Сохранено!';
        button.style.color = 'var(--accent)';
        showNotification('❤️', 'Сохранено', 'Вакансия добавлена в избранное');
      } else {
        favs.splice(idx,1);
        button.setAttribute('aria-pressed','false'); 
        button.textContent = '❤ Сохранить!';
        button.style.color = '';
        showNotification('💔', 'Удалено', 'Вакансия удалена из избранного');
      }
      saveFavorites(favs);
      
      if (isShowingFavorites) {
        showFavorites();
      }
      updateFavCount();
    }

    function showFavorites(){
      if (isEmployerMode) {
        viewAllCandidates();
      } else {
        const favs = loadFavorites();
        const list = jobsData.filter(j => favs.includes(j.id));
        isShowingFavorites = true;
        renderJobs(list, true);
        showNotification('⭐', 'Избранное', `Показано ${list.length} сохраненных вакансий`);
      }
    }

    function openApplyModal(jobId){
      if (!currentUser) {
        showNotification('⚠️', 'Требуется вход', 'Пожалуйста, войдите в профиль');
        document.getElementById('loginModal').style.display = 'flex';
        return;
      }
      const job = jobsData.find(j => j.id === jobId);
      modalTitle.textContent = 'Откликнуться на вакансию: ' + job.title;
      jobIdField.value = jobId;
      modal.style.display = 'flex';
      modal.setAttribute('aria-hidden','false');
      
      document.getElementById('applyForm').reset();
      
      document.getElementById('appName').focus();
    }
    
    function closeModal(){
      modal.style.display = 'none';
      modal.setAttribute('aria-hidden','true');
      document.getElementById('applyForm').reset();
    }

    function viewApplications(jobId) {
      const job = jobsData.find(j => j.id === jobId);
      currentJobIdForApplications = jobId;
      employerModalTitle.textContent = 'Отклики на вакансию: ' + job.title;
      renderCandidatesList(jobId);
    }
    
    function renderCandidatesList(jobId = null) {
      const applications = loadApplications();
      let filteredApplications = applications;
      
      if (jobId) {
        filteredApplications = applications.filter(app => app.jobId === jobId);
      }
      
      if (filteredApplications.length > 0) {
        candidatesList.style.display = 'block';
        candidatesList.innerHTML = '';
        
        filteredApplications.forEach((app, index) => {
          const job = jobsData.find(j => j.id === app.jobId);
          
          const candidateElement = document.createElement('div');
          candidateElement.className = 'candidate-item';
          candidateElement.setAttribute('data-app-id', JSON.stringify({email: app.email, timestamp: app.timestamp}));
          
          candidateElement.innerHTML = `
            <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
              <strong style="font-size:1rem">${escapeHtml(app.name)}</strong>
              <span style="color:var(--accent);font-size:0.9rem">${app.age} лет</span>
            </div>
            
            <div style="margin-bottom:10px">
              <div style="font-size:0.85rem;opacity:0.9;margin-bottom:4px">
                <strong>Email:</strong> ${escapeHtml(app.email)}
              </div>
              ${jobId ? '' : `<div style="font-size:0.85rem;opacity:0.9;margin-bottom:4px">
                <strong>Вакансия:</strong> ${job ? escapeHtml(job.title) : 'Неизвестная вакансия'}
              </div>`}
              <div style="font-size:0.85rem;opacity:0.9;margin-bottom:4px">
                <strong>Навыки:</strong> ${escapeHtml(app.skills)}
              </div>
              <div style="font-size:0.85rem;opacity:0.9;margin-bottom:4px">
                <strong>Отправлено:</strong> ${new Date(app.timestamp).toLocaleString('ru-RU')}
              </div>
            </div>
            
            <div class="resume-section">
              <h5>📄 Резюме кандидата</h5>
              <div class="resume-content">
                <p style="margin:0 0 8px 0">${escapeHtml(app.note || 'Кандидат предоставил резюме с подробным описанием опыта и навыков.')}</p>
                <a href="#" class="resume-link" onclick="event.preventDefault(); showNotification('📄', 'Резюме', 'Функция просмотра резюме в разработке');">
                  <span>🔗 Открыть резюме</span>
                </a>
              </div>
            </div>
            
            ${app.motivation ? `
            <div class="resume-section">
              <h5>💬 Мотивационное письмо</h5>
              <div class="resume-content">
                ${escapeHtml(app.motivation)}
              </div>
            </div>
            ` : ''}
            
            <div style="display:flex;gap:8px;margin-top:12px;justify-content:space-between">
              <div style="display:flex;gap:8px">
                <button class="ghost" style="font-size:0.8rem" onclick="event.stopPropagation();contactCandidate('${escapeHtml(app.email)}')">
                  📧 Написать
                </button>
                <button class="btn" style="font-size:0.8rem;padding:6px 10px" onclick="event.stopPropagation();acceptCandidate(this, '${escapeHtml(app.email)}', '${app.timestamp}')">
                  ✅ Принять
                </button>
              </div>
              <button class="reject-btn" onclick="event.stopPropagation();rejectCandidate(this, '${escapeHtml(app.email)}', '${app.timestamp}')">
                ❌ Отказать
              </button>
            </div>
          `;
          
          candidatesList.appendChild(candidateElement);
        });
        
        document.getElementById('employerModalContent').querySelector('div[style*="text-align:center"]').style.display = 'none';
      } else {
        candidatesList.style.display = 'none';
        document.getElementById('employerModalContent').querySelector('div[style*="text-align:center"]').style.display = 'block';
      }
      
      employerModal.style.display = 'flex';
      employerModal.setAttribute('aria-hidden','false');
    }
    
    function viewAllCandidates() {
      employerModalTitle.textContent = 'Все кандидаты на ваши вакансии';
      renderCandidatesList();
    }
    
    function closeEmployerModal(){
      employerModal.style.display = 'none';
      employerModal.setAttribute('aria-hidden','true');
      candidatesList.style.display = 'none';
      document.getElementById('employerModalContent').querySelector('div[style*="text-align:center"]').style.display = 'block';
    }
    
    function contactCandidate(email) {
      showNotification('📧', 'Написать', `Функция отправки сообщений на email ${email} в разработке`);
    }
    
    function acceptCandidate(button, email, timestamp) {
      const candidateItem = button.closest('.candidate-item');
      const appId = JSON.parse(candidateItem.getAttribute('data-app-id'));
      
      if (confirm(`Принять кандидата на работу? На email ${email} будет отправлено приглашение.`)) {
        candidateItem.classList.add('removing');
        
        setTimeout(() => {
          if (removeApplication(appId)) {
            candidateItem.remove();
            
            const remainingCandidates = candidatesList.querySelectorAll('.candidate-item');
            if (remainingCandidates.length === 0) {
              candidatesList.style.display = 'none';
              document.getElementById('employerModalContent').querySelector('div[style*="text-align:center"]').style.display = 'block';
            }
            
            showNotification('✅', 'Кандидат принят!', `Приглашение отправлено на ${email}`);
          } else {
            showNotification('❌', 'Ошибка', 'Не удалось найти заявку кандидата');
          }
        }, 300);
      }
    }
    
    function rejectCandidate(button, email, timestamp) {
      const candidateItem = button.closest('.candidate-item');
      const appId = JSON.parse(candidateItem.getAttribute('data-app-id'));
      
      if (confirm(`Отказать кандидату? На email ${email} будет отправлено уведомление об отказе.`)) {
        candidateItem.classList.add('removing');
        
        setTimeout(() => {
          if (removeApplication(appId)) {
            candidateItem.remove();
            
            const remainingCandidates = candidatesList.querySelectorAll('.candidate-item');
            if (remainingCandidates.length === 0) {
              candidatesList.style.display = 'none';
              document.getElementById('employerModalContent').querySelector('div[style*="text-align:center"]').style.display = 'block';
            }
            
            showNotification('❌', 'Отказ отправлен', `Кандидату на email ${email}`);
          } else {
            showNotification('❌', 'Ошибка', 'Не удалось найти заявку кандидата');
          }
        }, 300);
      }
    }

    function editJob(jobId) {
      showNotification('✏️', 'Редактирование', 'Функция редактирования вакансии в разработке');
    }

    document.getElementById('closeModal').addEventListener('click', closeModal);
    document.getElementById('cancelApply').addEventListener('click', closeModal);
    
    document.getElementById('closeEmployerModal').addEventListener('click', closeEmployerModal);
    document.getElementById('cancelEmployerModal').addEventListener('click', closeEmployerModal);
    
    window.addEventListener('keydown', e => { 
      if (e.key === 'Escape') {
        closeModal();
        closeEmployerModal();
        document.getElementById('myApplicationsModal').style.display = 'none';
        
        document.querySelectorAll('.modal-backdrop').forEach(modal => {
          modal.style.display = 'none';
        });
      }
    });

    document.getElementById('applyForm').addEventListener('submit', function(e){
      e.preventDefault();
      
      if (!currentUser) {
        showNotification('⚠️', 'Требуется вход', 'Пожалуйста, войдите в профиль');
        document.getElementById('loginModal').style.display = 'flex';
        return;
      }
      
      const name = document.getElementById('appName').value.trim();
      const email = document.getElementById('appEmail').value.trim();
      const age = Number(document.getElementById('appAge').value);
      const skills = document.getElementById('appSkills').value.trim();
      const motivation = document.getElementById('appMotivation').value.trim();
      const guardian = document.getElementById('appGuardian').checked;
      const schedule = document.getElementById('appSchedule').checked;
      const documents = document.getElementById('appDocuments').checked;
      const note = document.getElementById('appNote').value.trim();
      const jobId = document.getElementById('jobId').value;
      
      if (!name || !email) { 
        showNotification('❌', 'Ошибка', 'Заполните все обязательные поля: ФИО и Email');
        return; 
      }
      
      if (age < 14 || age > 17) { 
        showNotification('❌', 'Ошибка', 'Вакансии доступны только для подростков от 14 до 17 лет');
        document.getElementById('appAge').focus();
        return; 
      }
      
      if (!guardian || !schedule || !documents) {
        showNotification('❌', 'Ошибка', 'Необходимо согласиться со всеми условиями');
        return;
      }
      
      if (!skills) {
        showNotification('❌', 'Ошибка', 'Укажите хотя бы один навык');
        document.getElementById('appSkills').focus();
        return;
      }
      
      closeModal();
      
      const applicationData = {
        jobId: jobId,
        name: name,
        age: age,
        email: email,
        skills: skills,
        motivation: motivation,
        note: note || 'Кандидат предоставил резюме с подробным описанием опыта и навыков.',
        timestamp: new Date().toISOString()
      };
      
      const applications = loadApplications();
      applications.push(applicationData);
      saveApplications(applications);
      
      showNotification('✅', 'Заявка отправлена!', 'Работодатель рассмотрит её в ближайшее время');
    });

    $actionButton.addEventListener('click', function() {
      if (!currentUser) {
        showNotification('⚠️', 'Требуется вход', 'Пожалуйста, войдите в профиль');
        document.getElementById('loginModal').style.display = 'flex';
        return;
      }
      
      if (isEmployerMode) {
        document.getElementById('devModal').style.display = 'flex';
      } else {
        showMyApplications();
      }
    });

    function escapeHtml(str){
      return String(str)
        .replace(/&/g,'&amp;')
        .replace(/</g,'&lt;')
        .replace(/>/g,'&gt;')
        .replace(/"/g,'&quot;')
        .replace(/'/g,'&#39;');
    }

    $searchBtn.addEventListener('click', performSearch);
    $q.addEventListener('keydown', e => { if (e.key === 'Enter') performSearch(e); });
    
    $clear.addEventListener('click', () => {
      $q.value = ''; 
      $type.value = ''; 
      $location.value = ''; 
      $age.value = ''; 
      $maxHours.value = '';
      isShowingFavorites = false;
      visibleJobs = jobsData.slice();
      renderJobs(visibleJobs, true);
      showNotification('🔄', 'Фильтры сброшены', 'Показаны все вакансии');
    });
    
    $loadMore.addEventListener('click', () => renderJobs(visibleJobs, false));
    $showFavs.addEventListener('click', showFavorites);

    visibleJobs = jobsData.slice();
    renderJobs(visibleJobs, true);

    document.getElementById('searchBtn').addEventListener('click', () => {
      document.getElementById('results-title').focus && document.getElementById('results-title').focus();
    });

    $age.addEventListener('focus', function() {
      this.title = 'Введите ваш возраст от 14 до 17 лет';
    });

    window.TeenHustle = { 
      jobsData, 
      performSearch, 
      showFavorites, 
      loadFavorites, 
      saveFavorites,
      showNotification,
      clearFavorites: function() {
        saveFavorites([]);
        updateFavCount();
        if (isShowingFavorites && !isEmployerMode) {
          showFavorites();
        }
        showNotification('🗑️', 'Избранное очищено', 'Все сохраненные вакансии удалены');
      }
    };
    
    window.viewApplications = viewApplications;
    window.editJob = editJob;
    window.contactCandidate = contactCandidate;
    window.acceptCandidate = acceptCandidate;
    window.rejectCandidate = rejectCandidate;
  </script>
</body>
</html>
