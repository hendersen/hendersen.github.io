---
permalink: /
title: "Dianqi Han"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm an Assistant Professor in the Department of Computer Science and Engineering at the University of Texas at Arlington (UTA). I received a Ph.D. degree in Computer Engineering from [Arizona State University (ASU)](https://www.asu.edu/). Before that, I received a M.Sc. degree in Electrical and Computer Engineering from [University of California, Davis](https://www.ucdavis.edu/) , and a B.E. in Information Security from [University of Science and Technology of China (USTC)](https://en.ustc.edu.cn/). My research interests are security and privacy in networked systems, including mobile security, cyber-physical systems, wireless sensing, 5G and NextG systems, and smart grid.

**Openings**: I'm looking for highly motivated Ph.D. students to join my group. If you are interested, please send me an email with your CV and transcripts.


<body>
  <main class="container">
    <section id="news" class="news" aria-labelledby="news-title">
      <header class="news__header">
        <h2 id="news-title" class="news__title">News</h2>
        <div class="news__tools">
          <label class="news__search" aria-label="Filter news">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
            <input id="news-filter" type="search" placeholder="Filter by text or tag…" aria-controls="news-list" />
          </label>
          <a class="news__rss" href="/rss.xml" aria-label="RSS feed">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M6 18a2 2 0 1 1-4 0 2 2 0 0 1 4 0Zm-4-8a2 2 0 0 1 2-2c8.837 0 16 7.163 16 16a2 2 0 1 1-4 0C16 18.268 11.732 14 6 14a2 2 0 0 1-2-2Zm0-6a2 2 0 0 1 2-2C15.941 2 22 8.059 22 16a2 2 0 1 1-4 0c0-5.523-4.477-10-10-10a2 2 0 0 1-2-2Z"/></svg>
            <span>RSS</span>
          </a>
        </div>
      </header>

      <ul id="news-list" class="news__list" role="list">
        <!-- Example items; duplicate & edit as needed -->
  

        <li class="news-item" data-tags="grant,nsf,service">
          <div class="news-item__date">
            <time datetime="2025-07-31"><small>July</small> 31, 2025</time>
          </div>
          <div class="news-item__content">
            <h3> Our project on multimodal sensing-based security mechanisms has been funded by NSF CSR program</h3>
            <p>Grateful for the support! We will open-source datasets and tools as the project progresses.</p>
            <div class="tags"><span class="tag">grant</span><span class="tag">NSF</span></div>
          </div>
        </li>

        <li class="news-item" data-tags="paper,award,security">
          <div class="news-item__date">
            <time datetime="2025-07-01"><small>July</small> 01, 2025</time>
          </div>
          <div class="news-item__content">
            <h3>
              Paper accepted to <em>IEEE CNS 2025</em>
              <span class="badge-new" hidden>New</span>
            </h3>
            <p>Our work on mmWave sensing vulnerabilities was accepted to CNS 2025. Congratulations to Aliu and Wentao! </p>
            <div class="tags" aria-label="Tags">
              <span class="tag">paper</span>
              <span class="tag">security</span>
              <span class="tag">award</span>
            </div>
          </div>
        </li>

        <li class="news-item" data-tags="grant,nsf,service">
          <div class="news-item__date">
            <time datetime="2025-04-28"><small>April</small> 28, 2025</time>
          </div>
          <div class="news-item__content">
            <h3>Our project on mmWave-based remote diagnose on drone malfunctions has been funded by UTA REP program </h3>
            <p>Thank you UTA for the support! </p>
            <div class="tags"><span class="tag">grant</span><span class="tag">NSF</span></div>
          </div>
        </li>

      <div id="news-empty" class="news__empty" hidden>No news matched your filter.</div>
    </section>
  </main>

  <script>
    // --- Simple client-side filter by text or tag ---
    const input = document.getElementById('news-filter');
    const list = document.getElementById('news-list');
    const empty = document.getElementById('news-empty');

    function normalize(s){ return (s || '').toLowerCase().trim(); }

    function applyFilter(){
      const q = normalize(input.value);
      let visibleCount = 0;
      for(const item of list.querySelectorAll('.news-item')){
        const text = normalize(item.textContent);
        const tags = normalize(item.getAttribute('data-tags'));
        const match = !q || text.includes(q) || tags.includes(q);
        item.style.display = match ? '' : 'none';
        if(match) visibleCount++;
      }
      empty.hidden = visibleCount !== 0;
    }
    input.addEventListener('input', applyFilter);

    // --- Show "New" badge if within last 45 days ---
    const now = new Date();
    const NEW_WINDOW_DAYS = 45;
    for(const li of list.querySelectorAll('.news-item')){
      const t = li.querySelector('time');
      if(!t) continue;
      const date = new Date(t.getAttribute('datetime'));
      const diffDays = (now - date) / 86400000;
      const badge = li.querySelector('.badge-new');
      if(badge) badge.hidden = !(diffDays >= 0 && diffDays <= NEW_WINDOW_DAYS);
    }

    // Optional: ensure keyboard focus ring on search when using tab
    input.addEventListener('keydown', (e)=>{ if(e.key === 'Escape'){ input.value=''; applyFilter(); input.blur(); }});
  </script>
</body>
