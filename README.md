((я так чувствую))

Презентация: https://disk.yandex.ru/d/7qZvJgd7J-kI6w
P.s.(гитхабу не нравится презентация)

Код:
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Teen Hustle — Поиск работы для подростков</title>

  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --accent:#08a0ff; --muted:#98a6b2; --glass: rgba(255,255,255,0.03);
      --max-width:1100px; --radius:12px; font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%;background:linear-gradient(180deg,#071124 0%, #041325 60%); color:#e6eef6;}
    .wrap{max-width:var(--max-width);margin:28px auto;padding:20px;}
    header{display:flex;gap:20px;align-items:center;justify-content:space-between}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,#0ea5e9,#7c3aed);display:grid;place-items:center;font-weight:700;color:#021025}
    h1{font-size:1.35rem;margin:0}
    p.lead{margin:0;color:var(--muted);font-size:0.95rem}

    .profile-container{position:fixed;top:20px;right:20px;display:flex;align-items:center;gap:12px;z-index:1000;background:var(--card);padding:10px 15px;border-radius:var(--radius);border:1px solid rgba(255,255,255,0.05);box-shadow:0 4px 12px rgba(0,0,0,0.3);backdrop-filter:blur(10px)}
    .profile-avatar{width:40px;height:40px;border-radius:50%;background:linear-gradient(135deg,#7c3aed,#0ea5e9);display:flex;align-items:center;justify-content:center;font-weight:600;color:#021025;cursor:pointer;border:2px solid rgba(255,255,255,0.1);transition:all 0.3s ease;font-size:0.9rem}
    .profile-avatar:hover{border-color:var(--accent);transform:scale(1.05)}
    .profile-info{display:flex;flex-direction:column;align-items:flex-end}
    .profile-name{font-weight:600;font-size:0.9rem;color:#e6eef6}
    .profile-status{font-size:0.75rem;color:var(--muted);display:flex;align-items:center;gap:6px}
    .status-dot{width:6px;height:6px;border-radius:50%;background:#10b981}
    .profile-dropdown{position:absolute;top:100%;right:0;margin-top:10px;background:var(--card);border-radius:var(--radius);padding:12px;min-width:200px;box-shadow:0 10px 25px rgba(0,0,0,0.3);border:1px solid rgba(255,255,255,0.05);display:none;z-index:1001}
    .profile-dropdown.show{display:block}
    .dropdown-header{padding:8px 12px;border-bottom:1px solid rgba(255,255,255,0.05);margin-bottom:8px}
    .dropdown-item{display:flex;align-items:center;gap:10px;padding:10px 12px;border-radius:8px;color:var(--muted);text-decoration:none;transition:all 0.2s ease;cursor:pointer}
    .dropdown-item:hover{background:var(--glass);color:#e6eef6}
    .dropdown-divider{height:1px;background:rgba(255,255,255,0.05);margin:8px 0}

    .controls{display:grid;grid-template-columns:1fr 320px;gap:16px;margin:18px 0}
    .searchbox{background:var(--glass);padding:12px;border-radius:12px;display:flex;gap:8px;align-items:center}
    input[type="search"], select, input[type="number"]{background:transparent;border:0;color:inherit;font-size:0.95rem;outline:none;padding:6px 8px;width:100%}
    button.btn{background:var(--accent);border:0;padding:10px 12px;border-radius:10px;color:#021025;font-weight:600;cursor:pointer}
    button.ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px 10px;border-radius:10px;color:var(--muted)}
    .filters{display:flex;gap:8px;flex-wrap:wrap;align-items:center;justify-content:flex-end}

    main{display:grid;grid-template-columns:1fr 360px;gap:20px}
    .job-list{display:grid;gap:12px}
    .job{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:12px;border-radius:10px;display:flex;gap:12px;align-items:flex-start}
    .job .meta{flex:1}
    .job h3{margin:0;font-size:1.05rem}
    .chips{display:flex;gap:8px;margin-top:8px;flex-wrap:wrap}
    .chip{background:rgba(255,255,255,0.03);padding:6px 8px;border-radius:999px;font-size:0.82rem;color:var(--muted)}
    .job .actions{display:flex;flex-direction:column;gap:8px}
    .job small{color:var(--muted)}

    aside.card{background:var(--card);padding:14px;border-radius:12px}
    .card h4{margin:4px 0 10px 0}
    .quick-stats{display:flex;gap:8px;flex-wrap:wrap}
    .stat{background:rgba(255,255,255,0.02);padding:10px;border-radius:10px;min-width:100px;text-align:center}

    .modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.6);display:none;align-items:center;justify-content:center;padding:20px}
    .modal{background:#021023;padding:16px;border-radius:12px;max-width:520px;width:100%}
    .modal header{display:flex;justify-content:space-between;align-items:center}
    .modal form{display:grid;gap:8px;margin-top:8px}
    label{font-size:0.85rem;color:var(--muted)}
    input[type="text"], input[type="email"], textarea{background:transparent;border:1px solid rgba(255,255,255,0.04);padding:8px;border-radius:8px;color:inherit}
    textarea{min-height:90px;resize:vertical}
    .row{display:flex;gap:8px}
    .row > *{flex:1}

    footer{margin-top:22px;text-align:center;color:var(--muted);font-size:0.88rem}

    @media (max-width:960px){
      main{grid-template-columns:1fr}
      .controls{grid-template-columns:1fr;align-items:start}
      .filters{justify-content:flex-start}
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
          <p class="lead">Поиск работы подросткам</p>
        </div>
      </div>

      <div class="filters" aria-hidden="false">
        <button class="ghost" id="show-favs" title="Show saved favorites">❤ Сохраненнные <span id="fav-count" style="margin-left:6px;color:var(--muted)">0</span></button>
        <button class="ghost" id="post-job">Опубликовать вакансию</button>
      </div>
    </header>

    <div class="profile-container">
      <div class="profile-info">
        <div class="profile-name">Данила Шипиганович</div>
        <div class="profile-status">
          <div class="status-dot"></div>
          <span>В сети</span>
        </div>
      </div>
      <div class="profile-avatar" id="profileToggle">ДШ</div>
      <div class="profile-dropdown" id="profileDropdown">
        <div class="dropdown-header">
          <strong>Danila.Shipiganovich</strong>
          <div style="font-size:0.8rem;color:var(--muted);margin-top:4px">schpigpnowi4.danick@mail.ru</div>
        </div>
        <div class="dropdown-item">❗❗ Соискатель</div>
        <div class="dropdown-item">👤 Мой профиль</div>
        <div class="dropdown-item">📋 Мои заявки</div>
        <div class="dropdown-divider"></div>
        <div class="dropdown-item">⚙ Настройки</div>
        <div class="dropdown-item">🚪 Выйти</div>
      </div>
    </div>

    <div class="controls" role="search" aria-label="Job search and filters">
      <div class="searchbox" style="align-items:center">
        <input id="q" type="search" placeholder="Поиск работы школьникам" aria-label="Search jobs" />
        <select id="type" aria-label="Job type">
          <option value="">Любая категория</option>
          <option value="part-time">Разгрузка</option>
          <option value="internship">Расфасовщик</option>
          <option value="volunteer">Помощник</option>
          <option value="gig">Тестировщик</option>
        </select>
        <input id="location" type="search" placeholder="Локация (город/из дома)" aria-label="Location" />
        <button class="btn" id="searchBtn" aria-label="Search">Поиск</button>
      </div>

      <div style="display:flex;flex-direction:column;gap:8px;align-items:flex-end">
        <div style="display:flex;gap:8px">
          <label style="display:flex;align-items:center;gap:6px"><small class="muted">Возраст:</small>
            <input id="age" type="number" min="14" max="17" placeholder="?" style="width:84px" aria-label="Your age" />
          </label>
          <select id="maxHours" aria-label="Max hours per week" title="Max hours per week">
            <option value="">Любое количество часов</option>
            <option value="10">≤10 часов в неделю</option>
            <option value="20">≤20 часов в неделю</option>
            <option value="30">≤30 часов в неделю</option>
          </select>
        </div>
        <div style="display:flex;gap:8px">
          <button class="ghost" id="clear">Очистить</button>
          <button class="btn" id="advancedToggle">Фильтры</button>
        </div>
      </div>
    </div>

    <main>
      <section aria-labelledby="results-title">
        <h2 id="results-title" style="font-size:1.05rem;margin:6px 0 12px 0">Результат:</h2>

        <div class="job-list" id="jobs" role="list" aria-live="polite"></div>

        <div style="margin-top:12px;display:flex;gap:8px;align-items:center">
          <button class="ghost" id="loadMore">Загрузить больше вакансий</button>
        </div>
      </section>

      <aside class="card" aria-labelledby="sidebar-title">
        <h4 id="sidebar-title">Быстрая статистика</h4>
        <div class="quick-stats" id="stats">
          <div class="stat"><strong id="stat-count">5</strong><div style="font-size:.82rem;color:var(--muted)">Вакансии</div></div>
          <div class="stat"><strong id="stat-remote">2</strong><div style="font-size:.82rem;color:var(--muted)">Из дома</div></div>
          <div class="stat"><strong id="stat-types">5</strong><div style="font-size:.82rem;color:var(--muted)">Типы</div></div>
        </div>

        <hr style="border:none;height:1px;background:rgba(255,255,255,0.02);margin:12px 0">

        <div>
          <h4 style="margin-bottom:6px">Советы для тинэйджеров:</h4>
          <ul style="margin:0;padding-left:18px;color:var(--muted);font-size:.95rem">
            <li>Применимо только к вакансиям, на которые по закону разрешено нанимать сотрудников моложе 18 лет!</li>
            <li>Используйте простое электронное письмо и краткое резюме или описание навыков!</li>
            <li>Если вы трудоустроены на одну вакансию, то можете быть устроены и на другую(за не выполненную работу - штраф от работодателя(можно оспорить))</li>
          </ul>
        </div>

        <hr style="border:none;height:1px;background:rgba(255,255,255,0.02);margin:12px 0">

        <div>
          <h4 style="margin-bottom:6px">Работодатель? Опубликуйте вакансию!</h4>
          <p style="margin:0;color:var(--muted)">Мы рекомендуем указать чёткие требования к возрасту и рабочему времени!</p>
        </div>
      </aside>
    </main>

    <footer>
      <p style="margin:8px 0 0 0">Прототип для защиты в МГТУ имени Баумана. йоу</p>
    </footer>
  </div>

  <div class="modal-backdrop" id="modal" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal" role="document">
      <header>
        <strong id="modalTitle">Apply</strong>
        <button id="closeModal" class="ghost" aria-label="Close">✕</button>
      </header>

      <form id="applyForm" novalidate>
        <input type="hidden" id="jobId" />
        <label for="appName">ФИО</label>
        <input id="appName" type="text" required placeholder="Данила Олегович Шипиганович" />
        <label for="appEmail">Email</label>
        <input id="appEmail" type="email" required placeholder="schpigpnowi4.danick@mail.ru" />
        <label for="appAge">Возраст</label>
        <input id="appAge" type="number" required min="13" max="99" placeholder="14" />
        <label for="appNote">Короткое сообщение+Ваши скиллы(+Если имеется резюме то желательно прикрепить через "ЯндексДиск".)</label>
        <textarea id="appNote" placeholder="Я хорош(а) в..."></textarea>
        <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
          <button type="button" class="ghost" id="cancelApply">Закрыть</button>
          <button type="submit" class="btn">Отправить</button>
        </div>
      </form>
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
    });

    const jobsData = [
      {id:'j1',title:'Выгрузка фуры.',company:'Магнит',location:'ул. Братиславская, 14, Москва',type:'разгрузка',remote:false,hoursPerWeek:0,МинимальныйВозраст:14,description:'Выгружаете фуру - получаете деньги за смену',tags:['Физическая работа','Оплата за выполненную работу']},
      {id:'j2',title:'Упаковщик-комплектовщик.',company:'Мармеладыч',location:'ул. Матросова, 134, Тольятти',type:'Расфасовщик',remote:false,hoursPerWeek:8,МинимальныйВозраст:16,description:'Расфасовываете товар по выданному примеру',tags:['Внимательность','Монотонная работа']},
      {id:'j3',title:'Выгульщик Собак и/или Няня для домашних животных.',location:'Выезд на адрес',type:'Помощник',remote:false,hoursPerWeek:0,МинимальныйВозраст:14,description:'Выгуливаешь собак/сидишь с домашними животными и получаешь оплату в конце недели',tags:['Животные','Няня для животных','Договорные часы работы']},
      {id:'j4',title:'Рукоделие и продажа изделий.',location:'Ваш дом',type:'Ручная работа',remote:false,hoursPerWeek:0,МинимальныйВозраст:16,description:'Продаешь изделия на заказ и получаешь деньги в конце дня',tags:['Работа на заказ','Удаленная работа','Отправка результата почтой']},
      {id:'j5',title:'Тестировщик приложений',company:'Valve',location:'Ваш дом',type:'Тестировщик',remote:false,hoursPerWeek:10,МинимальныйВозраст:14,description:'Тестируете приложение. Ищите наличие багов/недочетеов/ошибок и сообщаете о них работодателю',tags:['Тестировщик','Удаленная работа','Активное общение с работодателем']}
    ];

    let visibleJobs = [];
    let pageSize = 4;
    let page = 0;

    const $jobs = document.getElementById('jobs');
    const $q = document.getElementById('q');
    const $type = document.getElementById('type');
    const $location = document.getElementById('location');
    const $age = document.getElementById('age');
    const $maxHours = document.getElementById('maxHours');
    const $searchBtn = document.getElementById('searchBtn');
    const $clear = document.getElementById('clear');
    const $loadMore = document.getElementById('loadMore');
    const $resultsSummary = document.getElementById('resultsSummary');
    const $statCount = document.getElementById('stat-count');
    const $statRemote = document.getElementById('stat-remote');
    const $statTypes = document.getElementById('stat-types');
    const $favCount = document.getElementById('fav-count');
    const $showFavs = document.getElementById('show-favs');
    const $postJob = document.getElementById('post-job');

    const modal = document.getElementById('modal');
    const modalTitle = document.getElementById('modalTitle');
    const jobIdField = document.getElementById('jobId');

    const LS_FAVS = 'teen_hustle_favorites_v1';

    function loadFavorites(){
      try{return JSON.parse(localStorage.getItem(LS_FAVS) || '[]');}catch(e){return [];}
    }
    function saveFavorites(arr){
      localStorage.setItem(LS_FAVS, JSON.stringify(arr));
      updateFavCount();
    }
    function updateFavCount(){
      const favs = loadFavorites();
      $favCount.textContent = favs.length;
    }
    updateFavCount();

    function createJobCard(job){
      const card = document.createElement('article');
      card.className = 'job';
      card.setAttribute('role','listitem');
      card.innerHTML = `
        <div class="meta">
          <h3>${escapeHtml(job.title)}</h3>
          <div style="display:flex;gap:8px;align-items:center;margin-top:6px">
            <small style="color:var(--muted)">${escapeHtml(job.company)}</small>
            <small style="color:var(--muted)">•</small>
            <small style="color:var(--muted)">${escapeHtml(job.location)}</small>
          </div>
          <p style="margin:8px 0 0 0;color:var(--muted);font-size:.95rem">${escapeHtml(job.description)}</p>
          <div class="chips" aria-hidden="false">
            <span class="chip">${escapeHtml(job.type)}</span>
            <span class="chip">${job.remote ? 'remote' : job.hoursPerWeek + ' часов в неделю'}</span>
            <span class="chip">мин. возраст: ${job.МинимальныйВозраст}</span>
            ${job.tags.slice(0,3).map(t => `<span class="chip">${escapeHtml(t)}</span>`).join('')}
          </div>
        </div>
        <div class="actions">
          <button class="btn apply" data-id="${job.id}" aria-label="Apply to ${escapeHtml(job.title)}">Откликнуться!</button>
          <button class="ghost fav" data-id="${job.id}" aria-pressed="false">❤ Сохранить!</button>
          <small style="color:var(--muted)">${job.type}</small>
        </div>
      `;
      card.querySelector('.apply').addEventListener('click', () => openApplyModal(job.id));
      const favBtn = card.querySelector('.fav');
      favBtn.addEventListener('click', () => toggleFav(job.id, favBtn));
      const favs = loadFavorites();
      if (favs.includes(job.id)) {
        favBtn.setAttribute('aria-pressed','true'); favBtn.textContent = '✓ Сохранено!';
      }
      return card;
    }

    function renderJobs(list, reset=true){
      if (reset){ $jobs.innerHTML = ''; page = 0; }
      const start = page * pageSize;
      const end = start + pageSize;
      const slice = list.slice(start, end);
      slice.forEach(job => $jobs.appendChild(createJobCard(job)));
      page++;
      $loadMore.style.display = (page * pageSize < list.length) ? 'inline-block' : 'none';
      $resultsSummary.textContent = `${list.length} result${list.length===1?'':'s'}`;
      $statCount.textContent = list.length;
      $statRemote.textContent = list.filter(j => j.remote).length;
      $statTypes.textContent = new Set(list.map(j => j.type)).size;
    }

    function matchesFilter(job, q, type, loc, ageVal, maxHoursVal){
      const hay = (job.title + ' ' + job.company + ' ' + job.description + ' ' + job.tags.join(' ')).toLowerCase();
      if (q && !hay.includes(q.toLowerCase())) return false;
      if (type && job.type !== type) return false;
      if (loc) {
        const lc = loc.toLowerCase();
        if (lc === 'remote' && !job.remote) return false;
        if (!job.remote && lc !== 'remote' && !job.location.toLowerCase().includes(lc)) return false;
      }
      if (ageVal) {
        if (Number(ageVal) < Number(job.МинимальныйВозраст)) return false;
      }
      if (maxHoursVal) {
        if (job.hoursPerWeek > Number(maxHoursVal)) return false;
      }
      return true;
    }

    function performSearch(e){
      if (e) e.preventDefault && e.preventDefault();
      const q = $q.value.trim();
      const type = $type.value;
      const loc = $location.value.trim();
      const ageVal = $age.value ? Number($age.value) : null;
      const maxHoursVal = $maxHours.value ? Number($maxHours.value) : null;
      if (ageVal && ageVal < 13) {
        alert('This platform is designed for ages 13 and up. If you are under 13, please have a parent or guardian help you.');
        $age.focus();
        return;
      }
      visibleJobs = jobsData.filter(job => matchesFilter(job, q, type, loc, ageVal, maxHoursVal));
      renderJobs(visibleJobs, true);
    }

    function toggleFav(id, button){
      const favs = loadFavorites();
      const idx = favs.indexOf(id);
      if (idx === -1){
        favs.push(id);
        button.setAttribute('aria-pressed','true'); button.textContent = '✓ Сохраненно';
      } else {
        favs.splice(idx,1);
        button.setAttribute('aria-pressed','false'); button.textContent = '❤ Сохранить';
      }
      saveFavorites(favs);
    }

    function showFavorites(){
      const favs = loadFavorites();
      const list = jobsData.filter(j => favs.includes(j.id));
      renderJobs(list, true);
    }

    function openApplyModal(jobId){
      const job = jobsData.find(j => j.id === jobId);
      modalTitle.textContent = 'Откликнуться на - ' + job.title;
      jobIdField.value = jobId;
      modal.style.display = 'flex';
      modal.setAttribute('aria-hidden','false');
      document.getElementById('appName').focus();
    }
    function closeModal(){
      modal.style.display = 'none';
      modal.setAttribute('aria-hidden','true');
      document.getElementById('applyForm').reset();
    }

    document.getElementById('closeModal').addEventListener('click', closeModal);
    document.getElementById('cancelApply').addEventListener('click', closeModal);
    window.addEventListener('keydown', e => { if (e.key === 'Escape') closeModal(); });

    document.getElementById('applyForm').addEventListener('submit', function(e){
      e.preventDefault();
      const name = document.getElementById('appName').value.trim();
      const email = document.getElementById('appEmail').value.trim();
      const age = Number(document.getElementById('appAge').value);
      const note = document.getElementById('appNote').value.trim();
      const jobId = document.getElementById('jobId').value;
      if (!name || !email) { alert('Please complete name and email'); return; }
      if (age < 13) { alert('Applicants must be 13 or older.'); return; }
      closeModal();
      alert('Application sent (mock). In production this would submit your application to the employer.');
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
      $q.value=''; $type.value=''; $location.value=''; $age.value=''; $maxHours.value='';
      visibleJobs = jobsData.slice();
      renderJobs(visibleJobs, true);
    });
    $loadMore.addEventListener('click', () => renderJobs(visibleJobs, false));
    $showFavs.addEventListener('click', showFavorites);

    $postJob.addEventListener('click', () => {
      alert('Employer posting flow not implemented in prototype. Build a secure backend and a verification step for employers before accepting posts.');
    });

    visibleJobs = jobsData.slice();
    renderJobs(visibleJobs, true);

    document.getElementById('searchBtn').addEventListener('click', () => {
      document.getElementById('results-title').focus && document.getElementById('results-title').focus();
    });

    window.TeenHustle = { jobsData, performSearch, showFavorites, loadFavorites, saveFavorites };
  </script>
</body>
</html>
    window.TeenHustle = { jobsData, performSearch, showFavorites, loadFavorites, saveFavorites };
  </script>
</body>
</html>
