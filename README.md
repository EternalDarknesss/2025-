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

    .modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.8);display:none;align-items:center;justify-content:center;padding:20px}
    .modal{background:#021023;padding:16px;border-radius:12px;max-width:520px;width:100%;max-height:90vh;overflow-y:auto;border:1px solid rgba(255,255,255,0.1)}
    .modal header{display:flex;justify-content:space-between;align-items:center}
    .modal header strong{color:#ffffff}
    .modal form{display:grid;gap:8px;margin-top:8px}
    label{font-size:0.85rem;color:#ffffff;opacity:0.9}
    input[type="text"], input[type="email"], textarea{background:transparent;border:1px solid rgba(255,255,255,0.15);padding:8px;border-radius:8px;color:#ffffff}
    input[type="text"]::placeholder, input[type="email"]::placeholder, textarea::placeholder{color:rgba(255,255,255,0.5)}
    textarea{min-height:90px;resize:vertical}
    .row{display:flex;gap:8px}
    .row > *{flex:1}
    
    .checkbox-group{display:flex;flex-direction:column;gap:6px;margin:8px 0}
    .checkbox-item{display:flex;align-items:flex-start;gap:8px}
    .checkbox-item input[type="checkbox"]{margin-top:3px}
    .checkbox-item label{font-size:0.8rem;color:#ffffff;opacity:0.9;line-height:1.3}

    .resume-section{background:rgba(255,255,255,0.05);padding:12px;border-radius:8px;margin:8px 0;border:1px solid rgba(255,255,255,0.08)}
    .resume-section h5{margin:0 0 8px 0;color:#ffffff;font-size:0.9rem}
    .resume-content{font-size:0.85rem;color:#ffffff;line-height:1.5;opacity:0.9}
    .resume-link{color:var(--accent);text-decoration:none;font-size:0.8rem;display:inline-flex;align-items:center;gap:4px}
    .resume-link:hover{text-decoration:underline}

    .candidate-item{background:rgba(255,255,255,0.05);padding:12px;border-radius:8px;margin-bottom:12px;border:1px solid rgba(255,255,255,0.08);transition:all 0.3s ease}
    .candidate-item.removing{opacity:0;transform:translateX(-20px);max-height:0;padding:0;margin:0;overflow:hidden;border:0}

    footer{margin-top:22px;text-align:center;color:#ffffff;font-size:0.88rem;opacity:0.9}

    @media (max-width:960px){
      main{grid-template-columns:1fr}
      .filters-section{grid-template-columns:1fr;gap:12px}
      .filter-group:last-child{grid-column:1;margin-top:8px}
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
      </div>
    </header>

    <div class="profile-container">
      <div class="profile-info">
        <div class="profile-name">
          <span>Имя Фамилия</span>
          <span class="profile-age">16 лет</span>
        </div>
        <div class="profile-status">
        </div>
      </div>
      <div class="profile-avatar" id="profileToggle">ИФ</div>
      <div class="profile-dropdown" id="profileDropdown">
        <div class="dropdown-header">
          <strong>Имя Фамилия</strong>
          <div style="font-size:0.8rem;margin-top:4px">тинэйджерпочта@mail.ru</div>
          <div style="font-size:0.8rem;margin-top:2px;color:var(--accent)">16 лет</div>
        </div>
        
        <div class="mode-switcher">
          <span class="mode-label">Соискатель</span>
          <label class="switch">
            <input type="checkbox" id="modeToggle">
            <span class="slider"></span>
          </label>
          <span class="mode-label">Работодатель</span>
        </div>
        
        <div class="dropdown-item" id="mode-display">👤 Режим: Соискатель</div>
        <div class="dropdown-divider"></div>
        <div class="dropdown-item">⚙ Настройки</div>
        <div class="dropdown-item">🚪 Выйти</div>
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
    </footer>
  </div>

  <div class="modal-backdrop" id="modal" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal" role="document">
      <header>
        <strong id="modalTitle">Откликнуться на вакансию</strong>
        <button id="closeModal" class="ghost" aria-label="Закрыть">✕</button>
      </header>

      <form id="applyForm" novalidate>
        <input type="hidden" id="jobId" />
        
        <div class="row">
          <div>
            <label for="appName">ФИО</label>
            <input id="appName" type="text" required placeholder="Фамилия Имя Отчество" />
          </div>
          <div>
            <label for="appAge">Ваш возраст</label>
            <input id="appAge" type="number" required min="14" max="17" placeholder="14" title="Введите возраст от 14 до 17 лет" />
          </div>
        </div>
        
        <div>
          <label for="appEmail">Email</label>
            <input id="appEmail" type="email" required placeholder="тинэйджерпочта@mail.ru" />
        </div>
        
        <label for="appSkills">Ваши навыки и умения</label>
        <textarea id="appSkills" placeholder="Перечислите ваши навыки через запятую..." required></textarea>
        
        <label for="appMotivation">Почему вы хотите работать именно у нас?</label>
        <textarea id="appMotivation" placeholder="Расскажите о вашей мотивации..." rows="3"></textarea>
        
        <div class="checkbox-group">
          <div class="checkbox-item">
            <input type="checkbox" id="appGuardian" name="appGuardian" required>
            <label for="appGuardian">Подтверждаю, что имею согласие родителей/опекунов на трудоустройство</label>
          </div>
          <div class="checkbox-item">
            <input type="checkbox" id="appSchedule" name="appSchedule" required>
            <label for="appSchedule">Готов(а) соблюдать рабочий график и согласовывать изменения с работодателем</label>
          </div>
          <div class="checkbox-item">
            <input type="checkbox" id="appDocuments" name="appDocuments" required>
            <label for="appDocuments">Имею все необходимые документы (паспорт, СНИЛС, ИНН, мед.справка)</label>
          </div>
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
        
        <div id="candidatesList" style="display:none">

        </div>
      </div>
      
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button type="button" class="ghost" id="cancelEmployerModal">Закрыть</button>
      </div>
    </div>
  </div>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
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
      
      clearFavoritesOnFirstLoad();
      initializeUserMode();
    });

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
    let isEmployerMode = false;
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
        $modeToggle.checked = true;
      } else {
        isEmployerMode = false;
        $modeToggle.checked = false;
      }
      updateModeDisplay();
      updateActionButton();
      updateFavsButton();
      renderJobs(visibleJobs, true); // Важно: обновляем отображение при инициализации
      
      $modeToggle.addEventListener('change', function() {
        isEmployerMode = this.checked;
        localStorage.setItem(LS_USER_MODE, isEmployerMode ? 'employer' : 'seeker');
        updateModeDisplay();
        updateActionButton();
        updateFavsButton();
        renderJobs(visibleJobs, true);
      });
    }

    function updateModeDisplay() {
      if (isEmployerMode) {
        $modeDisplay.innerHTML = '👔 Режим: Работодатель';
        $modeDisplay.style.color = '';
      } else {
        $modeDisplay.innerHTML = '👤 Режим: Соискатель';
        $modeDisplay.style.color = '';
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
        alert('Для подростков от 14 до 17 лет включительно');
        $age.focus();
        return;
      }
      
      isShowingFavorites = false;
      visibleJobs = jobsData.filter(job => matchesFilter(job, q, type, loc, ageVal, maxHoursVal));
      renderJobs(visibleJobs, true);
    }

    function toggleFav(id, button){
      const favs = loadFavorites();
      const idx = favs.indexOf(id);
      if (idx === -1){
        favs.push(id);
        button.setAttribute('aria-pressed','true'); 
        button.textContent = '✓ Сохранено!';
        button.style.color = 'var(--accent)';
      } else {
        favs.splice(idx,1);
        button.setAttribute('aria-pressed','false'); 
        button.textContent = '❤ Сохранить!';
        button.style.color = '';
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
      }
    }

    function openApplyModal(jobId){
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
          const resumeExamples = [
            "Ссылка на резюме в Google Docs",
          ];
          const randomResume = resumeExamples[Math.floor(Math.random() * resumeExamples.length)];
          
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
                <a href="${randomResume}" target="_blank" class="resume-link" onclick="event.stopPropagation();">
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
      alert(`Написать кандидату на email: ${email}`);
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
            
            alert(`✅ Кандидат принят! Приглашение отправлено на ${email}`);
          } else {
            alert('Ошибка: не удалось найти заявку кандидата');
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
            
            alert(`❌ Кандидату отправлен отказ на email ${email}`);
          } else {
            alert('Ошибка: не удалось найти заявку кандидата');
          }
        }, 300);
      }
    }

    function editJob(jobId) {
      alert('Редактирование вакансии ' + jobId + ' (функция в разработке)');
    }

    document.getElementById('closeModal').addEventListener('click', closeModal);
    document.getElementById('cancelApply').addEventListener('click', closeModal);
    
    document.getElementById('closeEmployerModal').addEventListener('click', closeEmployerModal);
    document.getElementById('cancelEmployerModal').addEventListener('click', closeEmployerModal);
    
    window.addEventListener('keydown', e => { 
      if (e.key === 'Escape') {
        closeModal();
        closeEmployerModal();
      }
    });

    document.getElementById('applyForm').addEventListener('submit', function(e){
      e.preventDefault();
      
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
        alert('Пожалуйста, заполните все обязательные поля: ФИО и Email'); 
        return; 
      }
      
      if (age < 14 || age > 17) { 
        alert('Вакансии доступны только для подростков от 14 до 17 лет включительно!'); 
        document.getElementById('appAge').focus();
        return; 
      }
      
      if (!guardian || !schedule || !documents) {
        alert('Для подачи заявки необходимо согласиться со всеми условиями (согласие родителей, график работы, наличие документов)');
        return;
      }
      
      if (!skills) {
        alert('Пожалуйста, укажите хотя бы один навык или умение');
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
      
      alert('✅ Заявка успешно отправлена! Работодатель рассмотрит её в ближайшее время. Ожидайте ответа на указанный email.');
    });

    $actionButton.addEventListener('click', function() {
      if (isEmployerMode) {
        alert('Функция публикации вакансии (в разработке)');
      } else {
        const applications = loadApplications();
        const userEmail = 'тинэйджерпочта@mail.ru';
        const userApplications = applications.filter(app => app.email === userEmail);
        
        if (userApplications.length === 0) {
          alert('У вас пока нет отправленных заявок.');
        } else {
          alert(`У вас ${userApplications.length} отправленных заявок. (функция просмотра в разработке)`);
        }
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
      clearFavorites: function() {
        saveFavorites([]);
        updateFavCount();
        if (isShowingFavorites && !isEmployerMode) {
          showFavorites();
        }
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
