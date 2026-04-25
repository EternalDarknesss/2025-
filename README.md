((я так чувствую))

Презентация: Ожидайте ссылку на болле актуальную версию!

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
    input[type="search"], select, input[type="number"], textarea{background:transparent;border:1px solid rgba(255,255,255,0.15);color:#ffffff;font-size:0.95rem;outline:none;padding:8px 10px;width:100%;border-radius:8px}
    input[type="search"]::placeholder, select option, input[type="number"]::placeholder, textarea::placeholder{color:rgba(255,255,255,0.6)}
    input[type="search"]:focus, select:focus, input[type="number"]:focus, textarea:focus{border-color:var(--accent)}
    select option{background:#000000;color:#ffffff}
    textarea{resize:vertical;min-height:80px}
    button.btn{background:var(--accent);border:0;padding:10px 16px;border-radius:10px;color:#021025;font-weight:600;cursor:pointer;transition:opacity 0.2s}
    button.btn:hover{opacity:0.9}
    button.ghost{background:transparent;border:1px solid rgba(255,255,255,0.15);padding:8px 12px;border-radius:10px;color:#ffffff;cursor:pointer;transition:all 0.2s;opacity:0.9}
    button.ghost:hover{background:rgba(255,255,255,0.1);border-color:rgba(255,255,255,0.3);opacity:1}
    button.chat-btn{background:linear-gradient(135deg,#7c3aed,#0ea5e9);border:none;padding:8px 12px;border-radius:8px;color:#ffffff;cursor:pointer;font-size:0.85rem;display:flex;align-items:center;gap:6px;transition:all 0.3s ease}
    button.chat-btn:hover{transform:translateY(-2px);box-shadow:0 4px 12px rgba(124,58,237,0.3)}
    button.reject-btn{background:transparent;border:1px solid rgba(255,100,100,0.5);padding:6px 10px;border-radius:8px;color:#ff6b6b;font-size:0.8rem;cursor:pointer}
    button.reject-btn:hover{background:rgba(255,100,100,0.2);border-color:rgba(255,100,100,0.7)}
    button.danger-btn{background:rgba(255,100,100,0.2);border:1px solid rgba(255,100,100,0.5);padding:6px 10px;border-radius:8px;color:#ff6b6b;font-size:0.8rem;cursor:pointer}
    button.danger-btn:hover{background:rgba(255,100,100,0.3);border-color:#ff6b6b}
    .filters{display:flex;gap:8px;flex-wrap:wrap;align-items:center;justify-content:flex-end}

    main{display:grid;grid-template-columns:1fr 360px;gap:20px}
    .job-list{display:grid;gap:12px}
    .job{background:linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02));padding:12px;border-radius:10px;display:flex;gap:12px;align-items:flex-start;border:1px solid rgba(255,255,255,0.05);position:relative;animation:fadeInUp 0.5s ease}
    .job.employer-job{border-left:3px solid var(--accent)}
    .job.new-job{border-left:3px solid #10b981;animation:highlight 2s ease}
    .job .meta{flex:1}
    .job h3{margin:0;font-size:1.05rem;color:#ffffff;display:flex;align-items:center;gap:8px}
    .new-badge{background:#10b981;color:#021025;padding:2px 8px;border-radius:20px;font-size:0.7rem;font-weight:600}
    .chips{display:flex;gap:8px;margin-top:8px;flex-wrap:wrap}
    .chip{background:rgba(255,255,255,0.08);padding:6px 8px;border-radius:999px;font-size:0.82rem;color:#ffffff;opacity:0.9}
    .job .actions{display:flex;flex-direction:row;gap:8px;flex-wrap:wrap;align-items:flex-start}
    .job .btn, .job .ghost, .job .chat-btn{width:auto}
    .job small{color:#ffffff;opacity:0.8}
    .job-badge{position:absolute;top:10px;right:10px;background:var(--accent);color:#021025;padding:4px 8px;border-radius:20px;font-size:0.7rem;font-weight:600}

    @keyframes fadeInUp {
      from {opacity:0;transform:translateY(20px)}
      to {opacity:1;transform:translateY(0)}
    }
    @keyframes highlight {
      0% {background:rgba(16,185,129,0.2)}
      100% {background:linear-gradient(180deg, rgba(255,255,255,0.05), rgba(255,255,255,0.02))}
    }

    aside.card{background:var(--card);padding:14px;border-radius:12px;border:1px solid rgba(255,255,255,0.05)}
    .card h4{margin:4px 0 10px 0;color:#ffffff}
    .quick-stats{display:flex;gap:8px;flex-wrap:wrap}
    .stat{background:rgba(255,255,255,0.05);padding:10px;border-radius:10px;min-width:100px;text-align:center;border:1px solid rgba(255,255,255,0.05)}
    .stat strong{color:#ffffff;font-size:1.2rem}
    .stat div{color:#ffffff;opacity:0.9}

    .form-group{margin-bottom:16px}
    .form-group label{display:block;margin-bottom:6px;color:#ffffff;font-size:0.9rem}
    .form-group input, .form-group select, .form-group textarea{width:100%}
    .tags-input-container{display:flex;flex-wrap:wrap;gap:8px;margin-top:8px}
    .tag-item{background:rgba(8,160,255,0.2);border:1px solid var(--accent);padding:4px 8px;border-radius:20px;display:flex;align-items:center;gap:6px;font-size:0.85rem}
    .tag-item button{background:transparent;border:none;color:#ff6b6b;cursor:pointer;font-size:1rem;padding:0 4px}
    .tag-item button:hover{color:#ff0000}

    .chat-container{display:flex;flex-direction:column;height:500px;background:rgba(0,0,0,0.2);border-radius:12px}
    .chat-messages{flex:1;overflow-y:auto;padding:16px;display:flex;flex-direction:column;gap:8px}
    .chat-message{display:flex;gap:8px;max-width:80%}
    .chat-message.own{margin-right:auto}
    .chat-message.other{margin-left:auto;flex-direction:row-reverse}
    .message-avatar{width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,#7c3aed,#0ea5e9);display:flex;align-items:center;justify-content:center;font-weight:600;font-size:0.8rem;flex-shrink:0}
    .message-content{display:flex;flex-direction:column;gap:4px}
    .message-header{display:flex;align-items:center;gap:8px;font-size:0.8rem}
    .message-sender{font-weight:600;color:var(--accent)}
    .chat-message.other .message-sender{color:#10b981}
    .message-time{opacity:0.6;font-size:0.7rem}
    .message-bubble{background:rgba(255,255,255,0.1);padding:8px 12px;border-radius:12px;word-wrap:break-word}
    .chat-message.own .message-bubble{background:var(--accent);color:#021025}
    .chat-message.other .message-bubble{background:rgba(16,185,129,0.2);border:1px solid rgba(16,185,129,0.3)}
    .chat-input-container{display:flex;gap:8px;padding:16px;border-top:1px solid rgba(255,255,255,0.1)}
    .chat-input{flex:1}
    
    .chat-list{max-height:400px;overflow-y:auto}
    .chat-list-item{padding:12px;border-bottom:1px solid rgba(255,255,255,0.05);cursor:pointer;transition:all 0.2s;display:flex;align-items:center;gap:12px}
    .chat-list-item:hover{background:rgba(255,255,255,0.05)}
    .chat-list-item.active{background:rgba(8,160,255,0.1);border-left:3px solid var(--accent)}
    .chat-avatar{width:40px;height:40px;border-radius:50%;background:linear-gradient(135deg,#7c3aed,#0ea5e9);display:flex;align-items:center;justify-content:center;font-weight:600}
    .chat-info{flex:1}
    .chat-name{font-weight:600;margin-bottom:4px}
    .chat-preview{font-size:0.8rem;opacity:0.7}
    .unread-badge{background:var(--accent);color:#021025;padding:2px 8px;border-radius:20px;font-size:0.7rem;font-weight:600;margin-left:8px}

    .candidate-item{background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.05);border-radius:var(--radius);padding:16px;margin-bottom:16px;transition:all 0.3s ease}
    .candidate-item:hover{background:rgba(255,255,255,0.05);border-color:var(--accent)}
    .candidate-item.removing{opacity:0;transform:translateX(20px);transition:all 0.3s ease}
    .resume-section{background:rgba(8,160,255,0.05);border-radius:8px;padding:12px;margin:12px 0;border-left:3px solid var(--accent)}
    .resume-section h5{color:var(--accent);margin-bottom:8px;font-size:0.95rem}
    .resume-content{color:var(--muted);font-size:0.9rem;line-height:1.5}
    .resume-link{display:inline-block;color:var(--accent);text-decoration:none;padding:6px 12px;background:rgba(8,160,255,0.1);border-radius:20px;margin-top:8px;transition:all 0.2s ease}
    .resume-link:hover{background:var(--accent);color:#021025}
    .application-item{background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.05);border-radius:var(--radius);padding:16px;margin-bottom:16px;transition:all 0.3s ease}
    .application-item:hover{background:rgba(255,255,255,0.05);border-color:var(--accent)}
    .application-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
    .application-title{font-size:1.1rem;font-weight:600;color:var(--accent)}
    .application-date{font-size:0.8rem;color:var(--muted)}
    .application-company{color:var(--muted);font-size:0.9rem;margin-bottom:8px}
    .application-skills{background:rgba(255,255,255,0.02);border-radius:8px;padding:10px;margin:10px 0;font-size:0.9rem}
    .application-status{display:inline-block;background:rgba(8,160,255,0.1);color:var(--accent);padding:4px 12px;border-radius:20px;font-size:0.8rem;margin-top:8px}
    
    .modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.8);display:none;align-items:center;justify-content:center;padding:20px;z-index:2000}
    .modal{background:#021023;padding:16px;border-radius:12px;max-width:600px;width:100%;border:1px solid rgba(255,255,255,0.1);max-height:90vh;overflow-y:auto}
    .modal header{display:flex;justify-content:space-between;align-items:center;margin-bottom:15px}
    .modal header strong{color:#ffffff}
    .modal form{display:flex;flex-direction:column;gap:10px}
    .modal input, .modal select, .modal textarea{background:transparent;border:1px solid rgba(255,255,255,0.15);padding:10px;border-radius:8px;color:#ffffff}
    .modal input::placeholder, .modal textarea::placeholder{color:rgba(255,255,255,0.5)}
    .modal input:focus, .modal select:focus, .modal textarea:focus{border-color:var(--accent);outline:none}
    
    .login-hint{font-size:0.8rem;opacity:0.7;margin-top:5px;text-align:center}
    .footer-links{display:flex;gap:20px;justify-content:center;margin-top:10px;font-size:0.8rem}
    .footer-links a{color:#ffffff;opacity:0.7;text-decoration:none;cursor:pointer}
    .footer-links a:hover{opacity:1;color:var(--accent)}
    .age-hint{font-size:0.75rem;opacity:0.7;margin-top:2px;text-align:left}
    
    .notification-container{position:fixed;bottom:20px;right:20px;z-index:9999;display:flex;flex-direction:column;gap:10px;max-width:350px}
    .notification{background:var(--card);border-left:4px solid var(--accent);border-radius:var(--radius);padding:16px;box-shadow:0 5px 15px rgba(0,0,0,0.3);animation:slideIn 0.3s ease forwards;display:flex;align-items:flex-start;gap:12px;border:1px solid rgba(255,255,255,0.05);backdrop-filter:blur(10px)}
    .notification-icon{font-size:1.5rem;line-height:1}
    .notification-content{flex:1}
    .notification-title{font-weight:600;margin-bottom:4px;color:#ffffff}
    .notification-message{font-size:0.9rem;opacity:0.9;color:#ffffff}
    .notification-close{background:transparent;border:none;color:rgba(255,255,255,0.5);cursor:pointer;font-size:1.2rem;padding:0 4px;transition:color 0.2s}
    .notification-close:hover{color:#ffffff}
    
    @keyframes slideIn{from{transform:translateX(100%);opacity:0}to{transform:translateX(0);opacity:1}}
    @keyframes slideOut{from{transform:translateX(0);opacity:1}to{transform:translateX(100%);opacity:0}}
    .notification.fade-out{animation:slideOut 0.3s ease forwards}
    
    .features-grid{display:grid;grid-template-columns:repeat(2, 1fr);gap:12px;margin:15px 0}
    .feature-card{background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.05);border-radius:var(--radius);padding:15px;cursor:pointer;transition:all 0.3s ease;text-align:center}
    .feature-card:hover{background:rgba(8,160,255,0.1);border-color:var(--accent);transform:translateY(-2px)}
    .feature-icon{font-size:2rem;margin-bottom:8px}
    .feature-title{font-weight:600;margin-bottom:4px}
    .feature-desc{font-size:0.8rem;opacity:0.7}
    .feature-badge{display:inline-block;background:rgba(8,160,255,0.2);color:var(--accent);padding:4px 8px;border-radius:20px;font-size:0.7rem;margin-top:8px}
    .feature-page{padding:20px;text-align:center}
    .feature-page-icon{font-size:4rem;margin-bottom:20px}
    .feature-page-title{font-size:1.5rem;font-weight:700;margin-bottom:10px;background:linear-gradient(135deg, #0ea5e9, #7c3aed);-webkit-background-clip:text;-webkit-text-fill-color:transparent}
    .feature-page-desc{color:var(--muted);margin-bottom:30px;line-height:1.6}
    .feature-progress{background:rgba(255,255,255,0.05);border-radius:20px;height:8px;margin:20px 0;overflow:hidden}
    .feature-progress-bar{height:100%;background:linear-gradient(90deg, var(--accent), #7c3aed);width:30%;border-radius:20px}
    .feature-status{display:flex;justify-content:space-between;color:var(--muted);font-size:0.9rem;margin-bottom:30px}
    .feature-actions{display:flex;gap:10px;justify-content:center}
    
    #employerModal .modal{max-width:600px;max-height:80vh}
    #myApplicationsModal .modal{max-width:600px;max-height:80vh}
    #jobFormModal .modal{max-width:700px}
    #chatModal .modal{max-width:800px}
    #profileEditModal .modal{max-width:500px}
    
    .modal::-webkit-scrollbar{width:6px}
    .modal::-webkit-scrollbar-track{background:rgba(255,255,255,0.05)}
    .modal::-webkit-scrollbar-thumb{background:var(--accent);border-radius:3px}
    
    @media (max-width:960px){main{grid-template-columns:1fr}.filters-section{grid-template-columns:1fr;gap:12px}.features-grid{grid-template-columns:1fr}}
    @media (max-width:768px){.profile-container{position:static;margin-top:10px;align-self:flex-end}}
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
        <button class="ghost" id="show-favs">❤ Сохранённые <span id="fav-count">0</span></button>
        <button class="ghost" id="action-button">Мои заявки</button>
        <button class="ghost" id="chat-menu-btn">💬 Чаты <span id="unread-count">0</span></button>
        <button class="ghost" id="dev-menu-btn">⚙️ Разработка</button>
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

    <div class="filters-section">
      <div class="filter-group">
        <div class="filter-label">Поиск</div>
        <input id="q" type="search" placeholder="Например: выгульщик собак" />
      </div>
      <div class="filter-group">
        <div class="filter-label">Тип работы</div>
        <select id="type">
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
        <input id="location" type="search" placeholder="Город или 'из дома'" />
      </div>
      <div class="filter-group">
        <div class="filter-label">Ваш возраст</div>
        <input id="age" type="number" min="14" max="17" placeholder="14-17" />
      </div>
      <div class="filter-group">
        <div class="filter-label">Макс. часов</div>
        <select id="maxHours">
          <option value="">Любое</option>
          <option value="10">≤10 ч/нед</option>
          <option value="20">≤20 ч/нед</option>
          <option value="30">≤30 ч/нед</option>
        </select>
      </div>
      <div class="filter-group">
        <div style="display:flex;gap:8px;">
          <button class="btn" id="searchBtn">Поиск</button>
          <button class="ghost" id="clear">Очистить</button>
        </div>
      </div>
    </div>

    <main>
      <section>
        <h2 id="results-title">Результат:</h2>
        <div class="job-list" id="jobs"></div>
        <div style="margin-top:12px;">
          <button class="ghost" id="loadMore">Загрузить больше</button>
        </div>
      </section>

      <aside class="card">
        <h4>Быстрая статистика</h4>
        <div class="quick-stats" id="stats">
          <div class="stat"><strong id="stat-count">5</strong><div>Вакансии</div></div>
          <div class="stat"><strong id="stat-remote">2</strong><div>Из дома</div></div>
          <div class="stat"><strong id="stat-types">5</strong><div>Типы</div></div>
        </div>
        <hr style="border:none;height:1px;background:rgba(255,255,255,0.1);margin:12px 0">
        <div>
          <h4>Советы для подростков:</h4>
          <ul style="margin:0;padding-left:18px;opacity:0.9">
            <li>Соблюдайте субординацию!</li>
            <li>Используйте простое резюме!</li>
            <li>Заключайте договор!</li>
          </ul>
        </div>
      </aside>
    </main>

    <footer>
      <p>Прототип для защиты в МГТУ имени Баумана</p>
      <div class="footer-links">
        <a class="footer-link" data-page="about">О проекте</a>
        <a class="footer-link" data-page="rules">Правила</a>
        <a class="footer-link" data-page="help">Помощь</a>
        <a class="footer-link" data-page="contact">Контакты</a>
      </div>
    </footer>
  </div>

  <div class="notification-container" id="notificationContainer"></div>

  <div class="modal-backdrop" id="loginModal">
    <div class="modal">
      <header>
        <strong>Вход в профиль</strong>
        <button class="ghost" id="closeLoginBtn">✕</button>
      </header>
      <form id="loginForm">
        <input type="text" id="loginName" placeholder="Имя и фамилия" required value="Анна Петрова">
        <input type="email" id="loginEmail" placeholder="Email" required value="anna@example.com">
        <div style="display:flex;gap:10px;margin:5px 0">
          <label><input type="radio" name="userType" value="seeker" id="userTypeSeeker" checked> Соискатель (14-17)</label>
          <label><input type="radio" name="userType" value="employer" id="userTypeEmployer"> Работодатель (18+)</label>
        </div>
        <input type="number" id="loginAge" placeholder="Возраст" min="14" max="17" required value="16">
        <div class="age-hint" id="ageHint">Для соискателя: от 14 до 17 лет</div>
        <button type="submit" class="btn">Войти</button>
        <div class="login-hint">Указывайте реальный возраст!</div>
      </form>
    </div>
  </div>

  <div class="modal-backdrop" id="profileEditModal">
    <div class="modal">
      <header>
        <strong>👤 Редактирование профиля</strong>
        <button class="ghost" id="closeProfileEditModal">✕</button>
      </header>
      <form id="profileEditForm">
        <div class="form-group">
          <label>Имя</label>
          <input type="text" id="editProfileName" required>
        </div>
        <div class="form-group">
          <label>Email</label>
          <input type="email" id="editProfileEmail" required>
        </div>
        <div class="form-group">
          <label>Возраст</label>
          <input type="number" id="editProfileAge" min="14" max="100" required>
        </div>
        <div class="form-group">
          <label>О себе</label>
          <textarea id="editProfileBio" rows="3" placeholder="Расскажите о себе..."></textarea>
        </div>
        <div class="form-group">
          <label>Телефон</label>
          <input type="tel" id="editProfilePhone" placeholder="+7 (999) 123-45-67">
        </div>
        <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
          <button type="button" class="ghost" id="cancelProfileEdit">Отмена</button>
          <button type="submit" class="btn">Сохранить</button>
        </div>
      </form>
    </div>
  </div>

  <div class="modal-backdrop" id="chatModal">
    <div class="modal">
      <header>
        <strong id="chatModalTitle">💬 Чаты</strong>
        <button class="ghost" id="closeChatModal">✕</button>
      </header>
      <div style="display:grid;grid-template-columns:280px 1fr;gap:16px;min-height:400px">
        <div>
          <input type="search" id="chatSearch" placeholder="Поиск чата..." style="width:100%;margin-bottom:12px">
          <div class="chat-list" id="chatList"></div>
        </div>
        <div id="chatArea">
          <div id="chatHeader" style="margin-bottom:12px;padding-bottom:8px;border-bottom:1px solid rgba(255,255,255,0.1)">
            <strong id="currentChatName">Выберите чат</strong>
          </div>
          <div class="chat-container">
            <div class="chat-messages" id="chatMessages">
              <div style="text-align:center;color:var(--muted);padding:40px">Выберите чат</div>
            </div>
            <div class="chat-input-container" id="chatInputContainer" style="display:none">
              <input type="text" class="chat-input" id="chatInput" placeholder="Введите сообщение...">
              <button class="btn" id="sendMessageBtn">Отправить</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="myApplicationsModal">
    <div class="modal">
      <header>
        <strong>📋 Мои заявки</strong>
        <button class="ghost" id="closeMyApplicationsModal">✕</button>
      </header>
      <div id="myApplicationsContent">
        <div id="emptyApplicationsState" style="text-align:center;padding:40px">
          <div style="font-size:48px;margin-bottom:20px">📭</div>
          <h3>У вас пока нет заявок</h3>
          <p>Откликнитесь на первую вакансию!</p>
        </div>
        <div id="applicationsList" style="display:none"></div>
      </div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelMyApplicationsModal">Закрыть</button>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="devModal">
    <div class="modal" style="max-width:600px">
      <header>
        <strong>⚙️ Меню разработки</strong>
        <button class="ghost" id="closeDevModal">✕</button>
      </header>
      <div class="features-grid">
        <div class="feature-card" data-feature="profile">
          <div class="feature-icon">👤</div>
          <div class="feature-title">Профиль</div>
          <div class="feature-badge">в разработке</div>
        </div>
        <div class="feature-card" data-feature="messages">
          <div class="feature-icon">💬</div>
          <div class="feature-title">Сообщения</div>
          <div class="feature-badge">готово</div>
        </div>
        <div class="feature-card" data-feature="notifications">
          <div class="feature-icon">🔔</div>
          <div class="feature-title">Уведомления</div>
          <div class="feature-badge">в разработке</div>
        </div>
        <div class="feature-card" data-feature="stats">
          <div class="feature-icon">📊</div>
          <div class="feature-title">Статистика</div>
          <div class="feature-badge">в разработке</div>
        </div>
      </div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelDevModal">Закрыть</button>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="jobFormModal">
    <div class="modal">
      <header>
        <strong id="jobFormTitle">Опубликовать вакансию</strong>
        <button class="ghost" id="closeJobFormModal">✕</button>
      </header>
      <form id="jobForm">
        <input type="hidden" id="editingJobId">
        <div class="form-group">
          <label>Название *</label>
          <input type="text" id="jobTitle" required>
        </div>
        <div class="form-group">
          <label>Компания</label>
          <input type="text" id="jobCompany">
        </div>
        <div class="form-group">
          <label>Местоположение *</label>
          <input type="text" id="jobLocation" required>
        </div>
        <div class="form-group">
          <label>Тип работы *</label>
          <select id="jobType" required>
            <option value="">Выберите</option>
            <option value="разгрузка">Разгрузка</option>
            <option value="расфасовщик">Расфасовщик</option>
            <option value="помощник">Помощник</option>
            <option value="тестировщик">Тестировщик</option>
            <option value="ручная работа">Ручная работа</option>
          </select>
        </div>
        <div class="form-group">
          <label><input type="checkbox" id="jobRemote"> Удаленная работа</label>
        </div>
        <div class="form-group">
          <label>Часов в неделю</label>
          <input type="number" id="jobHours" min="0" max="40" value="10">
        </div>
        <div class="form-group">
          <label>Мин. возраст *</label>
          <input type="number" id="jobMinAge" min="14" max="17" value="14" required>
        </div>
        <div class="form-group">
          <label>Описание *</label>
          <textarea id="jobDescription" rows="4" required></textarea>
        </div>
        <div class="form-group">
          <label>Теги</label>
          <input type="text" id="jobTagsInput" placeholder="Введите тег и нажмите Enter">
          <div class="tags-input-container" id="tagsContainer"></div>
        </div>
        <div class="form-group">
          <label>Оплата</label>
          <input type="text" id="jobSalary">
        </div>
        <div style="display:flex;gap:8px;justify-content:space-between;margin-top:15px">
          <button type="button" class="danger-btn" id="deleteJobBtn" style="display:none">🗑️ Удалить</button>
          <div style="display:flex;gap:8px;margin-left:auto;">
            <button type="button" class="ghost" id="cancelJobForm">Отмена</button>
            <button type="submit" class="btn" id="submitJobBtn">Опубликовать</button>
          </div>
        </div>
      </form>
    </div>
  </div>

  <div class="modal-backdrop" id="modal">
    <div class="modal">
      <header>
        <strong id="modalTitle">Откликнуться</strong>
        <button id="closeModal" class="ghost">✕</button>
      </header>
      <form id="applyForm">
        <input type="hidden" id="jobId">
        <div><label>ФИО</label><input id="appName" type="text" required></div>
        <div><label>Возраст</label><input id="appAge" type="number" min="14" max="17" required></div>
        <div><label>Email</label><input id="appEmail" type="email" required></div>
        <label>Навыки</label><textarea id="appSkills" required></textarea>
        <label>Мотивация</label><textarea id="appMotivation" rows="3"></textarea>
        <div><input type="checkbox" id="appGuardian" required> <label>Согласие родителей</label></div>
        <div><input type="checkbox" id="appSchedule" required> <label>Готов соблюдать график</label></div>
        <div><input type="checkbox" id="appDocuments" required> <label>Есть документы</label></div>
        <label>Доп. информация</label><textarea id="appNote" rows="2"></textarea>
        <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
          <button type="button" class="ghost" id="cancelApply">Закрыть</button>
          <button type="submit" class="btn">Отправить</button>
        </div>
      </form>
    </div>
  </div>

  <div class="modal-backdrop" id="employerModal">
    <div class="modal">
      <header>
        <strong id="employerModalTitle">Отклики</strong>
        <button id="closeEmployerModal" class="ghost">✕</button>
      </header>
      <div id="employerModalContent">
        <div id="emptyCandidatesState" style="text-align:center;padding:40px">
          <div style="font-size:48px;margin-bottom:20px">📋</div>
          <h3>Отклики на вакансию</h3>
          <p>Здесь будут кандидаты</p>
        </div>
        <div id="candidatesList" style="display:none"></div>
      </div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelEmployerModal">Закрыть</button>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="aboutModal">
    <div class="modal">
      <header><strong>О проекте</strong><button class="ghost close-footer-modal" data-modal="aboutModal">✕</button></header>
      <div class="feature-page">
        <div class="feature-page-icon">ℹ️</div>
        <div class="feature-page-title">Teen Hustle</div>
        <div class="feature-page-desc">Платформа для поиска работы подростками 14-17 лет</div>
        <button class="ghost close-footer-modal" data-modal="aboutModal">Закрыть</button>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="rulesModal">
    <div class="modal">
      <header><strong>Правила</strong><button class="ghost close-footer-modal" data-modal="rulesModal">✕</button></header>
      <div class="feature-page">
        <div class="feature-page-icon">📜</div>
        <div class="feature-page-title">Правила платформы</div>
        <ol style="text-align:left">
          <li>Указывайте настоящий возраст</li>
          <li>Соблюдайте субординацию</li>
          <li>Заключайте договор</li>
        </ol>
        <button class="ghost close-footer-modal" data-modal="rulesModal">Закрыть</button>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="helpModal">
    <div class="modal">
      <header><strong>Помощь</strong><button class="ghost close-footer-modal" data-modal="helpModal">✕</button></header>
      <div class="feature-page">
        <div class="feature-page-icon">❓</div>
        <div class="feature-page-title">Центр помощи</div>
        <p>support@teenhustle.ru</p>
        <button class="ghost close-footer-modal" data-modal="helpModal">Закрыть</button>
      </div>
    </div>
  </div>

  <div class="modal-backdrop" id="contactModal">
    <div class="modal">
      <header><strong>Контакты</strong><button class="ghost close-footer-modal" data-modal="contactModal">✕</button></header>
      <div class="feature-page">
        <div class="feature-page-icon">📞</div>
        <div class="feature-page-title">Свяжитесь с нами</div>
        <p>info@teenhustle.ru</p>
        <p>+7 (999) 123-45-67</p>
        <button class="ghost close-footer-modal" data-modal="contactModal">Закрыть</button>
      </div>
    </div>
  </div>

  <script>
    let currentUser = null;
    let isEmployerMode = false;
    let visibleJobs = [];
    let pageSize = 4;
    let page = 0;
    let isShowingFavorites = false;
    let currentJobTags = [];
    let currentChatId = null;
    let chats = [];
    let messages = [];

    const LS_FAVS = 'teen_hustle_favorites_v1';
    const LS_APPLICATIONS = 'teen_hustle_applications';
    const LS_JOBS = 'teen_hustle_jobs';
    const LS_CHATS = 'teen_hustle_chats';
    const LS_MESSAGES = 'teen_hustle_messages';

    let jobsData = [
      {id:'j1',title:'Выгрузка фуры',company:'Магнит',location:'ул. Братиславская, 14',type:'разгрузка',remote:false,hoursPerWeek:20,МинимальныйВозраст:14,description:'Выгружаете фуру',tags:['Физическая работа'],employerId:null,salary:'от 1000 руб/смена',createdAt:Date.now() - 86400000},
      {id:'j2',title:'Упаковщик',company:'Мармеладыч',location:'ул. Матросова, 134',type:'расфасовщик',remote:false,hoursPerWeek:15,МинимальныйВозраст:16,description:'Расфасовка товара',tags:['Внимательность'],employerId:null,salary:'12000 руб/мес',createdAt:Date.now() - 172800000},
      {id:'j3',title:'Выгульщик собак',company:'Частное лицо',location:'Выезд на адрес',type:'помощник',remote:false,hoursPerWeek:10,МинимальныйВозраст:14,description:'Выгул собак',tags:['Животные'],employerId:null,salary:'от 300 руб/час',createdAt:Date.now() - 259200000},
      {id:'j4',title:'Рукоделие',company:'HandMade',location:'Ваш дом',type:'ручная работа',remote:true,hoursPerWeek:0,МинимальныйВозраст:16,description:'Продажа изделий',tags:['Творчество'],employerId:null,salary:'договорная',createdAt:Date.now() - 345600000},
      {id:'j5',title:'Тестировщик',company:'Valve',location:'Ваш дом',type:'тестировщик',remote:true,hoursPerWeek:10,МинимальныйВозраст:14,description:'Тестирование ПО',tags:['IT'],employerId:null,salary:'15000 руб/мес',createdAt:Date.now() - 432000000}
    ];

    function showNotification(icon, title, message, duration = 5000) {
      const container = document.getElementById('notificationContainer');
      const notification = document.createElement('div');
      notification.className = 'notification';
      notification.innerHTML = `
        <div class="notification-icon">${icon}</div>
        <div class="notification-content">
          <div class="notification-title">${escapeHtml(title)}</div>
          <div class="notification-message">${escapeHtml(message)}</div>
        </div>
        <button class="notification-close" onclick="this.parentElement.remove()">&times;</button>
      `;
      container.appendChild(notification);
      setTimeout(() => notification.remove(), duration);
    }

    function escapeHtml(str){
      if (!str) return '';
      return String(str).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
    }

    function loadFavorites(){
      try{return JSON.parse(localStorage.getItem(LS_FAVS) || '[]');}catch(e){return [];}
    }
    
    function saveFavorites(arr){
      localStorage.setItem(LS_FAVS, JSON.stringify(arr));
      updateFavCount();
    }
    
    function loadApplications() {
      try{return JSON.parse(localStorage.getItem(LS_APPLICATIONS) || '[]');}catch(e){return [];}
    }
    
    function saveApplications(apps) {
      localStorage.setItem(LS_APPLICATIONS, JSON.stringify(apps));
    }

    function removeApplication(appId) {
      const applications = loadApplications();
      const index = applications.findIndex(app => app.email === appId.email && app.timestamp === appId.timestamp);
      if (index !== -1) {
        applications.splice(index, 1);
        saveApplications(applications);
        return true;
      }
      return false;
    }

    function loadJobsFromStorage() {
      try{
        const saved = localStorage.getItem(LS_JOBS);
        if(saved) {
          const savedJobs = JSON.parse(saved);
          savedJobs.forEach(job => {
            if(!jobsData.find(j => j.id === job.id)) jobsData.push(job);
          });
        }
      }catch(e){}
    }

    function saveJobsToStorage() {
      try{
        const employerJobs = jobsData.filter(j => j.employerId);
        localStorage.setItem(LS_JOBS, JSON.stringify(employerJobs));
      }catch(e){}
    }

    function loadChats() {
      try{return JSON.parse(localStorage.getItem(LS_CHATS) || '[]');}catch(e){return [];}
    }

    function saveChats(chatsData) {
      localStorage.setItem(LS_CHATS, JSON.stringify(chatsData));
    }

    function loadMessages() {
      try{return JSON.parse(localStorage.getItem(LS_MESSAGES) || '[]');}catch(e){return [];}
    }

    function saveMessages(msgs) {
      localStorage.setItem(LS_MESSAGES, JSON.stringify(msgs));
    }

    function updateFavCount(){
      const favs = loadFavorites();
      document.getElementById('fav-count').textContent = isEmployerMode ? '0' : favs.length;
    }

    function updateChatsCount() {
      if(!currentUser) {
        document.getElementById('unread-count').textContent = '0';
        return;
      }
      const userChats = chats.filter(c => c.participant1 === currentUser.email || c.participant2 === currentUser.email);
      const total = userChats.reduce((sum, c) => {
        return sum + (c.participant1 === currentUser.email ? (c.unreadCount1 || 0) : (c.unreadCount2 || 0));
      }, 0);
      document.getElementById('unread-count').textContent = total;
    }

    function updateCandidatesCount() {
      if(!currentUser || !isEmployerMode) {
        if (!isEmployerMode) updateFavCount();
        return;
      }
      const apps = loadApplications();
      const employerJobs = jobsData.filter(j => j.employerId === currentUser.email).map(j => j.id);
      const candidatesCount = apps.filter(a => employerJobs.includes(a.jobId)).length;
      document.getElementById('fav-count').textContent = candidatesCount;
    }

    function getApplicationsCount(jobId) {
      return loadApplications().filter(a => a.jobId === jobId).length;
    }

    function sortJobsByDate(jobs) {
      return jobs.sort((a, b) => (b.createdAt || 0) - (a.createdAt || 0));
    }

    function getUserName(email) {
      if (email === 'admin@teenhustle.ru') return 'Администратор';
      const applications = loadApplications();
      const app = applications.find(a => a.email === email);
      if (app) return app.name;
      return email.split('@')[0];
    }

    function updateProfileUI() {
      if(currentUser) {
        document.getElementById('profileInfo').style.display = 'flex';
        document.getElementById('profileName').textContent = currentUser.name;
        document.getElementById('profileAge').textContent = currentUser.age + ' лет';
        document.getElementById('avatarText').textContent = currentUser.name.split(' ').map(n => n[0]).join('').substring(0,2).toUpperCase();
        updateDropdownContent();
      }
    }

    function updateDropdownContent() {
      const content = document.getElementById('profileDropdownContent');
      content.innerHTML = `
        <div class="dropdown-header">
          <strong>${escapeHtml(currentUser.name)}</strong>
          <div>${escapeHtml(currentUser.email)}</div>
          <div style="color:var(--accent)">${currentUser.age} лет</div>
        </div>
        <div class="mode-switcher">
          <span class="mode-label">Соискатель</span>
          <label class="switch">
            <input type="checkbox" id="modeToggle" ${isEmployerMode ? 'checked' : ''}>
            <span class="slider"></span>
          </label>
          <span class="mode-label">Работодатель</span>
        </div>
        <div class="dropdown-item" id="mode-display">${isEmployerMode ? '👔 Работодатель' : '👤 Соискатель'}</div>
        <div class="dropdown-divider"></div>
        <div class="dropdown-item" id="editProfileBtn">✏️ Редактировать профиль</div>
        <div class="dropdown-item" id="settings-btn">⚙️ Настройки</div>
        <div class="dropdown-divider"></div>
        <div class="dropdown-item" id="logoutBtn">🚪 Выйти</div>
      `;

      document.getElementById('modeToggle').addEventListener('change', function(e) {
        isEmployerMode = e.target.checked;
        currentUser.mode = isEmployerMode ? 'employer' : 'seeker';
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        document.getElementById('mode-display').innerHTML = isEmployerMode ? '👔 Работодатель' : '👤 Соискатель';
        updateActionButton();
        updateFavsButton();
        updateCandidatesCount();
        renderJobs(visibleJobs, true);
        showNotification('🔄', 'Режим изменён', isEmployerMode ? 'Режим работодателя' : 'Режим соискателя');
      });

      document.getElementById('editProfileBtn').addEventListener('click', () => {
        document.getElementById('profileDropdown').classList.remove('show');
        openProfileEdit();
      });

      document.getElementById('settings-btn').addEventListener('click', () => {
        document.getElementById('profileDropdown').classList.remove('show');
        document.getElementById('devModal').style.display = 'flex';
      });

      document.getElementById('logoutBtn').addEventListener('click', () => {
        localStorage.removeItem('currentUser');
        currentUser = null;
        isEmployerMode = false;
        document.getElementById('profileInfo').style.display = 'none';
        document.getElementById('avatarText').textContent = '👤';
        document.getElementById('loginModal').style.display = 'flex';
        updateChatsCount();
        updateFavsButton();
      });
    }

    function openProfileEdit() {
      if(!currentUser) return;
      document.getElementById('editProfileName').value = currentUser.name || '';
      document.getElementById('editProfileEmail').value = currentUser.email || '';
      document.getElementById('editProfileAge').value = currentUser.age || '';
      document.getElementById('editProfileBio').value = currentUser.bio || '';
      document.getElementById('editProfilePhone').value = currentUser.phone || '';
      document.getElementById('profileEditModal').style.display = 'flex';
    }

    function updateActionButton() {
      const btn = document.getElementById('action-button');
      btn.textContent = isEmployerMode ? 'Опубликовать вакансию' : 'Мои заявки';
    }

    function updateFavsButton() {
      const btn = document.getElementById('show-favs');
      if (isEmployerMode) {
        btn.innerHTML = '👥 Кандидаты <span id="fav-count">0</span>';
        btn.title = 'Просмотреть кандидатов на вакансии';
      } else {
        btn.innerHTML = '❤ Сохранённые <span id="fav-count">0</span>';
        btn.title = 'Показать сохраненные вакансии';
      }
      if (isEmployerMode) {
        updateCandidatesCount();
      } else {
        updateFavCount();
      }
    }

    function updateAgeField() {
      const ageInput = document.getElementById('loginAge');
      const hint = document.getElementById('ageHint');
      if(document.getElementById('userTypeSeeker').checked) {
        ageInput.min = 14; ageInput.max = 17; ageInput.value = 16;
        hint.textContent = 'Для соискателя: от 14 до 17 лет';
      } else {
        ageInput.min = 18; ageInput.max = 100; ageInput.value = 35;
        hint.textContent = 'Для работодателя: от 18 лет';
      }
    }

    function getOrCreateChat(p1, p2, jobId, jobTitle) {
      let chat = chats.find(c => (c.participant1 === p1 && c.participant2 === p2) || (c.participant1 === p2 && c.participant2 === p1));
      if(!chat) {
        chat = {id:'chat_'+Date.now(), participant1:p1, participant2:p2, jobId, jobTitle, createdAt:Date.now(), unreadCount1:0, unreadCount2:0};
        chats.push(chat);
        saveChats(chats);
      }
      return chat;
    }

    function sendMessage(chatId, sender, text) {
      const msg = {id:'msg_'+Date.now(), chatId, sender, text, timestamp:Date.now(), read:false};
      messages.push(msg);
      saveMessages(messages);
      const chat = chats.find(c => c.id === chatId);
      if(chat) {
        chat.lastMessage = text;
        chat.lastMessageTime = Date.now();
        if(chat.participant1 === sender) chat.unreadCount2++; else chat.unreadCount1++;
        saveChats(chats);
      }
      updateChatsCount();
      return msg;
    }

    function getChatMessages(chatId) {
      return messages.filter(m => m.chatId === chatId).sort((a,b) => a.timestamp - b.timestamp);
    }

    function markMessagesAsRead(chatId, userEmail) {
      const chat = chats.find(c => c.id === chatId);
      if(chat) {
        if(chat.participant1 === userEmail) chat.unreadCount1 = 0; else chat.unreadCount2 = 0;
        saveChats(chats);
        messages.forEach(m => {if(m.chatId === chatId && m.sender !== userEmail) m.read = true;});
        saveMessages(messages);
      }
      updateChatsCount();
    }

    function openChat(chatId = null, jobId = null, employerEmail = null, seekerEmail = null, jobTitle = null) {
      if(!currentUser) {
        document.getElementById('loginModal').style.display = 'flex';
        return;
      }
      if(jobId && employerEmail && seekerEmail) {
        const chat = getOrCreateChat(employerEmail, seekerEmail, jobId, jobTitle);
        chatId = chat.id;
      }
      currentChatId = chatId;
      renderChatList();
      renderChatMessages();
      document.getElementById('chatModal').style.display = 'flex';
    }

    function renderChatList() {
      const list = document.getElementById('chatList');
      const userChats = chats.filter(c => c.participant1 === currentUser.email || c.participant2 === currentUser.email)
        .sort((a,b) => (b.lastMessageTime || b.createdAt) - (a.lastMessageTime || a.createdAt));
      
      if(!userChats.length) {
        list.innerHTML = '<div style="text-align:center;padding:20px">Нет чатов</div>';
        return;
      }
      
      list.innerHTML = userChats.map(chat => {
        const other = chat.participant1 === currentUser.email ? chat.participant2 : chat.participant1;
        const otherName = getUserName(other);
        const unread = chat.participant1 === currentUser.email ? chat.unreadCount1 : chat.unreadCount2;
        return `
          <div class="chat-list-item ${chat.id === currentChatId ? 'active' : ''}" onclick="selectChat('${chat.id}')">
            <div class="chat-avatar">${otherName.substring(0,2).toUpperCase()}</div>
            <div class="chat-info">
              <div class="chat-name">${escapeHtml(otherName)} ${unread ? `<span class="unread-badge">${unread}</span>` : ''}</div>
              ${chat.jobTitle ? `<div class="chat-preview">📋 ${escapeHtml(chat.jobTitle)}</div>` : ''}
            </div>
          </div>
        `;
      }).join('');
    }

    function selectChat(chatId) {
      currentChatId = chatId;
      const chat = chats.find(c => c.id === chatId);
      if(chat) {
        markMessagesAsRead(chatId, currentUser.email);
        const other = chat.participant1 === currentUser.email ? chat.participant2 : chat.participant1;
        const otherName = getUserName(other);
        document.getElementById('currentChatName').textContent = `Чат с ${otherName}`;
      }
      renderChatList();
      renderChatMessages();
      document.getElementById('chatInputContainer').style.display = 'flex';
    }

    function renderChatMessages() {
      const container = document.getElementById('chatMessages');
      if(!currentChatId) {
        container.innerHTML = '<div style="text-align:center;padding:40px">Выберите чат</div>';
        return;
      }
      const msgs = getChatMessages(currentChatId);
      if(!msgs.length) {
        container.innerHTML = '<div style="text-align:center;padding:40px">Нет сообщений</div>';
        return;
      }
      
      container.innerHTML = msgs.map(msg => {
        const isOwn = msg.sender === currentUser.email;
        const senderName = isOwn ? 'Вы' : getUserName(msg.sender);
        const time = new Date(msg.timestamp).toLocaleTimeString('ru-RU', {hour:'2-digit', minute:'2-digit'});
        
        return `
          <div class="chat-message ${isOwn ? 'own' : 'other'}">
            ${!isOwn ? `<div class="message-avatar">${senderName.substring(0,2).toUpperCase()}</div>` : ''}
            <div class="message-content">
              <div class="message-header">
                <span class="message-sender">${escapeHtml(senderName)}</span>
                <span class="message-time">${time}</span>
              </div>
              <div class="message-bubble">${escapeHtml(msg.text)}</div>
            </div>
            ${isOwn ? `<div class="message-avatar">${currentUser.name.substring(0,2).toUpperCase()}</div>` : ''}
          </div>
        `;
      }).join('');
      
      container.scrollTop = container.scrollHeight;
    }

    function startChatWithSeeker(seekerEmail, jobId, jobTitle) {
      openChat(null, jobId, currentUser.email, seekerEmail, jobTitle);
    }

    function createJobCard(job){
      const card = document.createElement('article');
      card.className = 'job' + (job.employerId === currentUser?.email ? ' employer-job' : '') + (Date.now() - job.createdAt < 86400000 ? ' new-job' : '');
      
      let actions = '';
      if(isEmployerMode) {
        const isOwner = job.employerId === currentUser?.email;
        actions = `
          <div style="display:flex;flex-direction:row;gap:8px;align-items:center;">
            <button class="chat-btn chat-employer" data-job-id="${job.id}" data-job-title="${escapeHtml(job.title)}">💬 Чат</button>
            <div style="display:flex;flex-direction:column;gap:8px;">
              <button class="btn applications" data-id="${job.id}">📊 Отклики (${getApplicationsCount(job.id)})</button>
              ${isOwner ? `<button class="ghost edit-job" data-id="${job.id}">✏️ Редактировать</button>` : ''}
            </div>
          </div>
        `;
      } else {
        actions = `
          <div style="display:flex;flex-direction:row;gap:8px;align-items:center;">
            <button class="chat-btn chat-seeker" data-job-id="${job.id}" data-employer="${job.employerId || 'admin@teenhustle.ru'}" data-job-title="${escapeHtml(job.title)}">💬 Чат</button>
            <div style="display:flex;flex-direction:column;gap:8px;">
              <button class="btn apply" data-id="${job.id}">Откликнуться</button>
              <button class="ghost fav" data-id="${job.id}">❤️ Сохранить</button>
            </div>
          </div>
        `;
      }
      
      card.innerHTML = `
        <div class="meta">
          <h3>${escapeHtml(job.title)} ${Date.now() - job.createdAt < 86400000 ? '<span class="new-badge">NEW</span>' : ''}</h3>
          <div><small>${escapeHtml(job.company || job.location)}</small> <small>•</small> <small>${escapeHtml(job.location)}</small> ${job.salary ? `<small>•</small><small style="color:var(--accent)">${escapeHtml(job.salary)}</small>` : ''}</div>
          <p>${escapeHtml(job.description)}</p>
          <div class="chips">
            <span class="chip">${escapeHtml(job.type)}</span>
            <span class="chip">${job.remote ? 'Удалённо' : job.hoursPerWeek + ' ч/нед'}</span>
            <span class="chip">от ${job.МинимальныйВозраст} лет</span>
            ${job.tags.slice(0,3).map(t => `<span class="chip">${escapeHtml(t)}</span>`).join('')}
          </div>
        </div>
        <div class="actions">${actions}</div>
      `;
      
      setTimeout(() => {
        if(!isEmployerMode) {
          card.querySelector('.apply')?.addEventListener('click', () => openApplyModal(job.id));
          const favBtn = card.querySelector('.fav');
          favBtn?.addEventListener('click', () => toggleFav(job.id, favBtn));
          if(loadFavorites().includes(job.id)) { favBtn.textContent = '✓ Сохранено'; favBtn.style.color = 'var(--accent)'; }
          card.querySelector('.chat-seeker')?.addEventListener('click', function() {
            openChat(null, this.dataset.jobId, this.dataset.employer, currentUser.email, this.dataset.jobTitle);
          });
        } else {
          card.querySelector('.applications')?.addEventListener('click', () => viewApplications(job.id));
          card.querySelector('.edit-job')?.addEventListener('click', () => openJobForm(job.id));
          card.querySelector('.chat-employer')?.addEventListener('click', function() {
            openChatList(this.dataset.jobId, this.dataset.jobTitle);
          });
        }
      }, 0);
      
      return card;
    }

    function openChatList(jobId, jobTitle) {
      const apps = loadApplications().filter(a => a.jobId === jobId);
      if(!apps.length) {
        showNotification('📭', 'Нет откликов', 'Никто не откликнулся');
        return;
      }
      const modal = document.createElement('div');
      modal.className = 'modal-backdrop';
      modal.style.display = 'flex';
      modal.innerHTML = `
        <div class="modal">
          <header><strong>Чат с соискателями - ${escapeHtml(jobTitle)}</strong><button class="ghost" onclick="this.closest('.modal-backdrop').remove()">✕</button></header>
          <div class="chat-list">${apps.map(a => `
            <div class="chat-list-item" onclick="startChatWithSeeker('${a.email}', '${jobId}', '${escapeHtml(jobTitle)}'); this.closest('.modal-backdrop').remove()">
              <div class="chat-avatar">${a.name.split(' ').map(n=>n[0]).join('').substring(0,2).toUpperCase()}</div>
              <div class="chat-info"><div class="chat-name">${escapeHtml(a.name)}</div><div>${escapeHtml(a.email)}</div></div>
            </div>
          `).join('')}</div>
        </div>
      `;
      document.body.appendChild(modal);
    }

    function renderJobs(list, reset=true){
      const container = document.getElementById('jobs');
      if(reset){ container.innerHTML = ''; page = 0; }
      const sorted = sortJobsByDate([...list]);
      const slice = sorted.slice(page * pageSize, (page + 1) * pageSize);
      slice.forEach(j => container.appendChild(createJobCard(j)));
      page++;
      document.getElementById('loadMore').style.display = (page * pageSize < list.length) ? 'inline-block' : 'none';
      updateStats(list);
    }

    function updateStats(list) {
      document.getElementById('stat-count').textContent = list.length;
      document.getElementById('stat-remote').textContent = list.filter(j => j.remote).length;
      document.getElementById('stat-types').textContent = new Set(list.map(j => j.type)).size;
    }

    function performSearch(e){
      e?.preventDefault();
      const q = document.getElementById('q').value.trim().toLowerCase();
      const type = document.getElementById('type').value;
      const loc = document.getElementById('location').value.trim().toLowerCase();
      const age = document.getElementById('age').value;
      const maxHours = document.getElementById('maxHours').value;
      
      visibleJobs = jobsData.filter(j => {
        if(q && !(j.title + j.description + j.tags.join(' ')).toLowerCase().includes(q)) return false;
        if(type && j.type !== type) return false;
        if(loc) {
          if(loc.includes('дом') && !j.remote) return false;
          else if(!loc.includes('дом') && !j.location.toLowerCase().includes(loc)) return false;
        }
        if(age && Number(age) < j.МинимальныйВозраст) return false;
        if(maxHours && j.hoursPerWeek > Number(maxHours)) return false;
        return true;
      });
      
      isShowingFavorites = false;
      renderJobs(visibleJobs, true);
      showNotification('🔍', 'Поиск', `Найдено: ${visibleJobs.length}`);
    }

    function toggleFav(id, btn){
      const favs = loadFavorites();
      const idx = favs.indexOf(id);
      if(idx === -1) { favs.push(id); btn.textContent = '✓ Сохранено'; btn.style.color = 'var(--accent)'; showNotification('❤️', 'Сохранено', 'В избранном'); }
      else { favs.splice(idx, 1); btn.textContent = '❤️ Сохранить'; btn.style.color = ''; showNotification('💔', 'Удалено', 'Из избранного'); }
      saveFavorites(favs);
      if(isShowingFavorites) showFavorites();
    }

    function showFavorites(){
      if(isEmployerMode) {
        viewAllCandidates();
      } else {
        const favs = loadFavorites();
        visibleJobs = jobsData.filter(j => favs.includes(j.id));
        isShowingFavorites = true;
        renderJobs(visibleJobs, true);
      }
    }

    function openApplyModal(jobId){
      if(!currentUser) { document.getElementById('loginModal').style.display = 'flex'; return; }
      document.getElementById('modalTitle').textContent = 'Откликнуться: ' + jobsData.find(j => j.id === jobId).title;
      document.getElementById('jobId').value = jobId;
      document.getElementById('modal').style.display = 'flex';
    }

    function closeModal(){ document.getElementById('modal').style.display = 'none'; }

    function viewApplications(jobId){
      document.getElementById('employerModalTitle').textContent = 'Отклики: ' + jobsData.find(j => j.id === jobId).title;
      const apps = loadApplications().filter(a => a.jobId === jobId);
      const list = document.getElementById('candidatesList');
      const empty = document.getElementById('emptyCandidatesState');
      
      if(apps.length) {
        list.style.display = 'block'; empty.style.display = 'none';
        list.innerHTML = apps.map(a => `
          <div class="candidate-item" data-app-id='${JSON.stringify({email:a.email, timestamp:a.timestamp})}'>
            <div><strong>${escapeHtml(a.name)}</strong> <span style="color:var(--accent)">${a.age} лет</span></div>
            <div>Email: ${escapeHtml(a.email)}</div>
            <div>Навыки: ${escapeHtml(a.skills)}</div>
            <div style="display:flex;gap:8px;margin-top:12px">
              <button class="ghost" onclick="openChat(null, '${jobId}', '${currentUser.email}', '${a.email}', '${jobsData.find(j=>j.id===jobId)?.title}')">💬 Чат</button>
              <button class="btn" style="font-size:0.8rem;padding:6px 10px" onclick="acceptCandidate(this, '${a.email}', '${a.timestamp}')">✅ Принять</button>
              <button class="reject-btn" onclick="rejectCandidate(this, '${a.email}', '${a.timestamp}')">❌ Отказать</button>
            </div>
          </div>
        `).join('');
      } else {
        list.style.display = 'none'; empty.style.display = 'block';
      }
      document.getElementById('employerModal').style.display = 'flex';
    }

    function viewAllCandidates(){
      document.getElementById('employerModalTitle').textContent = 'Все кандидаты';
      const apps = loadApplications().filter(a => jobsData.find(j => j.id === a.jobId && j.employerId === currentUser?.email));
      const list = document.getElementById('candidatesList');
      const empty = document.getElementById('emptyCandidatesState');
      
      if(apps.length) {
        list.style.display = 'block'; empty.style.display = 'none';
        list.innerHTML = apps.map(a => {
          const job = jobsData.find(j => j.id === a.jobId);
          return `
            <div class="candidate-item" data-app-id='${JSON.stringify({email:a.email, timestamp:a.timestamp})}'>
              <div><strong>${escapeHtml(a.name)}</strong> <span style="color:var(--accent)">${a.age} лет</span></div>
              <div>Вакансия: ${job ? escapeHtml(job.title) : 'Неизвестно'}</div>
              <div>Email: ${escapeHtml(a.email)}</div>
              <div style="display:flex;gap:8px;margin-top:12px">
                <button class="ghost" onclick="openChat(null, '${a.jobId}', '${currentUser.email}', '${a.email}', '${job?.title}')">💬 Чат</button>
                <button class="btn" style="font-size:0.8rem;padding:6px 10px" onclick="acceptCandidate(this, '${a.email}', '${a.timestamp}')">✅ Принять</button>
                <button class="reject-btn" onclick="rejectCandidate(this, '${a.email}', '${a.timestamp}')">❌ Отказать</button>
              </div>
            </div>
          `;
        }).join('');
      } else {
        list.style.display = 'none'; empty.style.display = 'block';
      }
      document.getElementById('employerModal').style.display = 'flex';
    }

    function acceptCandidate(button, email, timestamp) {
      const candidateItem = button.closest('.candidate-item');
      const appId = {email, timestamp};
      
      if (confirm(`Принять кандидата на работу? На email ${email} будет отправлено приглашение.`)) {
        candidateItem.classList.add('removing');
        setTimeout(() => {
          if (removeApplication(appId)) {
            candidateItem.remove();
            const remainingCandidates = document.querySelectorAll('.candidate-item');
            if (remainingCandidates.length === 0) {
              document.getElementById('candidatesList').style.display = 'none';
              document.getElementById('emptyCandidatesState').style.display = 'block';
            }
            updateCandidatesCount();
            showNotification('✅', 'Кандидат принят!', `Приглашение отправлено на ${email}`);
          }
        }, 300);
      }
    }

    function rejectCandidate(button, email, timestamp) {
      const candidateItem = button.closest('.candidate-item');
      const appId = {email, timestamp};
      
      if (confirm(`Отказать кандидату? На email ${email} будет отправлено уведомление об отказе.`)) {
        candidateItem.classList.add('removing');
        setTimeout(() => {
          if (removeApplication(appId)) {
            candidateItem.remove();
            const remainingCandidates = document.querySelectorAll('.candidate-item');
            if (remainingCandidates.length === 0) {
              document.getElementById('candidatesList').style.display = 'none';
              document.getElementById('emptyCandidatesState').style.display = 'block';
            }
            updateCandidatesCount();
            showNotification('❌', 'Отказ отправлен', `Кандидату на email ${email}`);
          }
        }, 300);
      }
    }

    function closeEmployerModal(){ document.getElementById('employerModal').style.display = 'none'; }

    function openJobForm(jobId = null){
      if(!currentUser || currentUser.mode !== 'employer') { showNotification('⚠️', 'Только для работодателей'); return; }
      const form = document.getElementById('jobForm');
      form.reset();
      currentJobTags = [];
      updateTagsDisplay();
      
      if(jobId) {
        const job = jobsData.find(j => j.id === jobId);
        if(!job) return;
        document.getElementById('jobFormTitle').textContent = 'Редактировать';
        document.getElementById('submitJobBtn').textContent = 'Сохранить';
        document.getElementById('deleteJobBtn').style.display = 'block';
        document.getElementById('editingJobId').value = jobId;
        document.getElementById('jobTitle').value = job.title;
        document.getElementById('jobCompany').value = job.company || '';
        document.getElementById('jobLocation').value = job.location;
        document.getElementById('jobType').value = job.type;
        document.getElementById('jobRemote').checked = job.remote;
        document.getElementById('jobHours').value = job.hoursPerWeek;
        document.getElementById('jobMinAge').value = job.МинимальныйВозраст;
        document.getElementById('jobDescription').value = job.description;
        document.getElementById('jobSalary').value = job.salary || '';
        currentJobTags = [...(job.tags || [])];
        updateTagsDisplay();
      } else {
        document.getElementById('jobFormTitle').textContent = 'Опубликовать';
        document.getElementById('submitJobBtn').textContent = 'Опубликовать';
        document.getElementById('deleteJobBtn').style.display = 'none';
        document.getElementById('editingJobId').value = '';
        document.getElementById('jobMinAge').value = 14;
        document.getElementById('jobHours').value = 10;
      }
      document.getElementById('jobFormModal').style.display = 'flex';
    }

    function closeJobFormModal(){ document.getElementById('jobFormModal').style.display = 'none'; }

    function addTagFromInput(){
      const input = document.getElementById('jobTagsInput');
      const tag = input.value.trim();
      if(tag && !currentJobTags.includes(tag)) { currentJobTags.push(tag); updateTagsDisplay(); }
      input.value = '';
    }

    function removeTag(tag){
      const idx = currentJobTags.indexOf(tag);
      if(idx > -1) { currentJobTags.splice(idx, 1); updateTagsDisplay(); }
    }

    function updateTagsDisplay(){
      const container = document.getElementById('tagsContainer');
      container.innerHTML = currentJobTags.map(t => `<span class="tag-item">${escapeHtml(t)} <button type="button" onclick="removeTag('${escapeHtml(t)}')">&times;</button></span>`).join('');
    }

    function saveJob(formData){
      const editingId = document.getElementById('editingJobId').value;
      const jobData = {
        title: formData.title, company: formData.company || 'Частное лицо', location: formData.location,
        type: formData.type, remote: formData.remote, hoursPerWeek: parseInt(formData.hoursPerWeek) || 0,
        МинимальныйВозраст: parseInt(formData.minAge), description: formData.description,
        tags: currentJobTags, salary: formData.salary, employerId: currentUser.email,
        createdAt: editingId ? jobsData.find(j => j.id === editingId)?.createdAt : Date.now()
      };
      
      if(editingId) {
        const idx = jobsData.findIndex(j => j.id === editingId);
        if(idx !== -1) { jobData.id = editingId; jobsData[idx] = {...jobsData[idx], ...jobData}; }
        showNotification('✅', 'Обновлено', 'Вакансия сохранена');
      } else {
        jobData.id = 'job_' + Date.now();
        jobData.createdAt = Date.now();
        jobsData.push(jobData);
        showNotification('🎉', 'Опубликовано!', 'Вакансия добавлена');
      }
      
      saveJobsToStorage();
      closeJobFormModal();
      visibleJobs = jobsData.slice();
      renderJobs(visibleJobs, true);
    }

    function deleteJob(jobId){
      if(!confirm('Удалить вакансию?')) return;
      const idx = jobsData.findIndex(j => j.id === jobId);
      if(idx !== -1) { jobsData.splice(idx, 1); saveJobsToStorage(); }
      closeJobFormModal();
      visibleJobs = jobsData.slice();
      renderJobs(visibleJobs, true);
      showNotification('🗑️', 'Удалено', 'Вакансия удалена');
    }

    function showMyApplications(){
      const apps = loadApplications().filter(a => a.email === currentUser.email);
      const empty = document.getElementById('emptyApplicationsState');
      const list = document.getElementById('applicationsList');
      
      if(apps.length) {
        empty.style.display = 'none'; list.style.display = 'block';
        list.innerHTML = apps.map(a => {
          const job = jobsData.find(j => j.id === a.jobId);
          return `<div class="application-item"><div class="application-title">${job ? escapeHtml(job.title) : 'Неизвестно'}</div><div class="application-status">✓ Отправлена</div></div>`;
        }).join('');
      } else {
        empty.style.display = 'block'; list.style.display = 'none';
      }
      document.getElementById('myApplicationsModal').style.display = 'flex';
    }

    document.addEventListener('DOMContentLoaded', () => {
      loadJobsFromStorage();
      chats = loadChats();
      messages = loadMessages();
      
      const savedUser = localStorage.getItem('currentUser');
      if(savedUser) {
        currentUser = JSON.parse(savedUser);
        isEmployerMode = currentUser.mode === 'employer';
        updateProfileUI();
        updateChatsCount();
        updateCandidatesCount();
        showNotification('🔄', 'С возвращением!', currentUser.name);
      } else {
        document.getElementById('loginModal').style.display = 'flex';
      }

      document.getElementById('userTypeSeeker').addEventListener('change', updateAgeField);
      document.getElementById('userTypeEmployer').addEventListener('change', updateAgeField);
      
      document.getElementById('loginForm').addEventListener('submit', e => {
        e.preventDefault();
        const name = document.getElementById('loginName').value;
        const email = document.getElementById('loginEmail').value;
        const age = parseInt(document.getElementById('loginAge').value);
        const mode = document.querySelector('input[name="userType"]:checked').value;
        
        if(mode === 'seeker' && (age < 14 || age > 17)) { showNotification('❌', 'Ошибка', 'Возраст 14-17'); return; }
        if(mode === 'employer' && age < 18) { showNotification('❌', 'Ошибка', 'Возраст 18+'); return; }
        
        currentUser = {name, email, age, mode};
        isEmployerMode = mode === 'employer';
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        document.getElementById('loginModal').style.display = 'none';
        updateProfileUI();
        updateActionButton();
        updateFavsButton();
        updateChatsCount();
        updateCandidatesCount();
        renderJobs(visibleJobs, true);
        showNotification('✅', 'Успешно!', `Добро пожаловать, ${name}!`);
      });

      document.getElementById('closeLoginBtn').addEventListener('click', () => {
        document.getElementById('loginModal').style.display = 'none';
      });

      document.getElementById('profileEditForm').addEventListener('submit', e => {
        e.preventDefault();
        currentUser.name = document.getElementById('editProfileName').value;
        currentUser.email = document.getElementById('editProfileEmail').value;
        currentUser.age = parseInt(document.getElementById('editProfileAge').value);
        currentUser.bio = document.getElementById('editProfileBio').value;
        currentUser.phone = document.getElementById('editProfilePhone').value;
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        updateProfileUI();
        document.getElementById('profileEditModal').style.display = 'none';
        showNotification('✅', 'Профиль обновлён', 'Изменения сохранены');
      });

      document.getElementById('closeProfileEditModal').addEventListener('click', () => {
        document.getElementById('profileEditModal').style.display = 'none';
      });
      document.getElementById('cancelProfileEdit').addEventListener('click', () => {
        document.getElementById('profileEditModal').style.display = 'none';
      });

      document.getElementById('applyForm').addEventListener('submit', e => {
        e.preventDefault();
        const name = document.getElementById('appName').value.trim();
        const email = document.getElementById('appEmail').value.trim();
        const age = Number(document.getElementById('appAge').value);
        const skills = document.getElementById('appSkills').value.trim();
        const motivation = document.getElementById('appMotivation').value.trim();
        const note = document.getElementById('appNote').value.trim();
        const jobId = document.getElementById('jobId').value;
        
        if(!name || !email || !skills) { showNotification('❌', 'Ошибка', 'Заполните поля'); return; }
        
        const apps = loadApplications();
        apps.push({jobId, name, age, email, skills, motivation, note, timestamp: new Date().toISOString()});
        saveApplications(apps);
        closeModal();
        showNotification('✅', 'Заявка отправлена!', 'Работодатель рассмотрит');
      });

      document.getElementById('jobForm').addEventListener('submit', e => {
        e.preventDefault();
        const data = {
          title: document.getElementById('jobTitle').value.trim(),
          company: document.getElementById('jobCompany').value.trim(),
          location: document.getElementById('jobLocation').value.trim(),
          type: document.getElementById('jobType').value,
          remote: document.getElementById('jobRemote').checked,
          hoursPerWeek: document.getElementById('jobHours').value,
          minAge: document.getElementById('jobMinAge').value,
          description: document.getElementById('jobDescription').value.trim(),
          salary: document.getElementById('jobSalary').value.trim()
        };
        if(!data.title || !data.location || !data.type || !data.description) {
          showNotification('❌', 'Ошибка', 'Заполните обязательные поля');
          return;
        }
        saveJob(data);
      });

      document.getElementById('jobTagsInput').addEventListener('keydown', e => {
        if(e.key === 'Enter') { e.preventDefault(); addTagFromInput(); }
      });

      document.getElementById('deleteJobBtn').addEventListener('click', () => {
        const id = document.getElementById('editingJobId').value;
        if(id) deleteJob(id);
      });

      document.getElementById('chat-menu-btn').addEventListener('click', () => openChat());
      document.getElementById('closeChatModal').addEventListener('click', () => {
        document.getElementById('chatModal').style.display = 'none';
      });
      
      document.getElementById('sendMessageBtn').addEventListener('click', () => {
        const input = document.getElementById('chatInput');
        const text = input.value.trim();
        if(text && currentChatId) {
          sendMessage(currentChatId, currentUser.email, text);
          input.value = '';
          renderChatMessages();
          renderChatList();
        }
      });

      document.getElementById('chatInput').addEventListener('keydown', e => {
        if(e.key === 'Enter') { e.preventDefault(); document.getElementById('sendMessageBtn').click(); }
      });

      document.getElementById('action-button').addEventListener('click', () => {
        if(!currentUser) { document.getElementById('loginModal').style.display = 'flex'; return; }
        isEmployerMode ? openJobForm() : showMyApplications();
      });

      document.getElementById('searchBtn').addEventListener('click', performSearch);
      document.getElementById('q').addEventListener('keydown', e => { if(e.key === 'Enter') performSearch(e); });
      document.getElementById('clear').addEventListener('click', () => {
        document.getElementById('q').value = '';
        document.getElementById('type').value = '';
        document.getElementById('location').value = '';
        document.getElementById('age').value = '';
        document.getElementById('maxHours').value = '';
        visibleJobs = jobsData.slice();
        renderJobs(visibleJobs, true);
      });
      
      document.getElementById('loadMore').addEventListener('click', () => renderJobs(visibleJobs, false));
      document.getElementById('show-favs').addEventListener('click', showFavorites);
      
      document.getElementById('closeModal').addEventListener('click', closeModal);
      document.getElementById('cancelApply').addEventListener('click', closeModal);
      document.getElementById('closeEmployerModal').addEventListener('click', closeEmployerModal);
      document.getElementById('cancelEmployerModal').addEventListener('click', closeEmployerModal);
      document.getElementById('closeJobFormModal').addEventListener('click', closeJobFormModal);
      document.getElementById('cancelJobForm').addEventListener('click', closeJobFormModal);
      
      document.getElementById('closeMyApplicationsModal').addEventListener('click', () => {
        document.getElementById('myApplicationsModal').style.display = 'none';
      });
      document.getElementById('cancelMyApplicationsModal').addEventListener('click', () => {
        document.getElementById('myApplicationsModal').style.display = 'none';
      });

      document.getElementById('dev-menu-btn').addEventListener('click', () => {
        document.getElementById('devModal').style.display = 'flex';
      });
      document.getElementById('closeDevModal').addEventListener('click', () => {
        document.getElementById('devModal').style.display = 'none';
      });
      document.getElementById('cancelDevModal').addEventListener('click', () => {
        document.getElementById('devModal').style.display = 'none';
      });

      document.querySelectorAll('.feature-card').forEach(card => {
        card.addEventListener('click', function() {
          const feature = this.dataset.feature;
          if(feature === 'profile') openProfileEdit();
          else if(feature === 'messages') openChat();
          else showNotification('🔧', 'В разработке', 'Функция скоро появится');
        });
      });

      document.querySelectorAll('.footer-link').forEach(link => {
        link.addEventListener('click', e => {
          e.preventDefault();
          document.getElementById(e.target.dataset.page + 'Modal').style.display = 'flex';
        });
      });
      
      document.querySelectorAll('.close-footer-modal').forEach(btn => {
        btn.addEventListener('click', function() {
          document.getElementById(this.dataset.modal).style.display = 'none';
        });
      });

      window.addEventListener('keydown', e => {
        if(e.key === 'Escape') {
          document.querySelectorAll('.modal-backdrop').forEach(m => m.style.display = 'none');
        }
      });

      const profileToggle = document.getElementById('profileToggle');
      const profileDropdown = document.getElementById('profileDropdown');
      profileToggle.addEventListener('click', e => {
        e.stopPropagation();
        profileDropdown.classList.toggle('show');
      });
      document.addEventListener('click', () => profileDropdown.classList.remove('show'));
      profileDropdown.addEventListener('click', e => e.stopPropagation());

      visibleJobs = jobsData.slice();
      renderJobs(visibleJobs, true);
      
      setTimeout(() => showNotification('👋', 'Добро пожаловать!', 'Teen Hustle'), 1000);
    });

    window.showNotification = showNotification;
    window.removeTag = removeTag;
    window.addTagFromInput = addTagFromInput;
    window.openChat = openChat;
    window.selectChat = selectChat;
    window.startChatWithSeeker = startChatWithSeeker;
    window.acceptCandidate = acceptCandidate;
    window.rejectCandidate = rejectCandidate;
  </script>
</body>
</html>
