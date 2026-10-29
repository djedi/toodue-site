<script>
  const app = 'https://app.toodue.com/';

  const features = [
    {
      icon: '📥',
      title: 'Inbox, Today, Upcoming, Projects',
      body: 'The four views you actually use. Capture everything into the Inbox, plan your day in Today, and see the week ahead in Upcoming — responsive from phone to desktop.'
    },
    {
      icon: '🗂️',
      title: 'A full task model',
      body: 'Name, description, date and time, hard deadlines, P1–P4 priorities, sub-tasks, comments, and file attachments. Everything a real task needs, nothing it doesn’t.'
    },
    {
      icon: '👥',
      title: 'Nested projects & sharing',
      body: 'Organize projects inside projects, drag to reorder, and invite anyone by email to collaborate. Everyone stays in sync automatically.'
    },
    {
      icon: '⚡',
      title: 'Real-time everywhere',
      body: 'Changes push to every open device and every project member instantly. Check something off on your phone and watch it disappear on your laptop.'
    },
    {
      icon: '📅',
      title: 'Calendar integration',
      body: 'Two-way Google Calendar sync: your dated tasks appear on a dedicated calendar, and rescheduling an event there updates the task. Prefer subscriptions? Every account gets a private iCal feed for Apple Calendar, Fantastical, and friends.'
    },
    {
      icon: '📱',
      title: 'Install it like a native app',
      body: 'TooDue is a PWA — add it to your home screen on iPhone or Android and it runs full-screen with its own icon, plus light, dark, and system themes.'
    },
    {
      icon: '🚀',
      title: 'Small and very fast',
      body: 'The whole backend is a single compiled binary built in Rust. Pages load instantly, actions feel immediate, and the server sips resources.'
    },
    {
      icon: '🔓',
      title: 'Open source & self-hostable',
      body: 'Your tasks are yours. Use our hosted app, or run the whole thing yourself with one Docker container — a single binary and a single data volume.'
    }
  ];

  const faqs = [
    {
      q: 'Is it really free?',
      a: 'Yes — while TooDue is in development, every feature is free on the hosted app. When paid plans arrive they will be priced fairly, early users will get plenty of notice, and self-hosting will always be free.'
    },
    {
      q: 'What does “in development” mean for me?',
      a: 'TooDue is young and improving fast. The core — tasks, projects, sharing, sync, calendars — works well today, and new features ship regularly. You may occasionally spot rough edges; we fix them quickly.'
    },
    {
      q: 'Is there an iPhone / Android app?',
      a: 'TooDue installs as a PWA on both platforms (instructions above) and behaves like a native app: home-screen icon, full-screen, fast. Dedicated native apps are on the roadmap.'
    },
    {
      q: 'Can I get my data out?',
      a: 'Always. TooDue is open source, and if you self-host, your data lives in a plain SQLite database you fully control. No lock-in, ever.'
    },
    {
      q: 'What’s coming next?',
      a: 'Labels, filters, reminders, and recurring tasks are at the top of the roadmap, followed by native mobile apps.'
    }
  ];

  const demoTasks = [
    { name: 'Send the launch email', meta: 'Today · Marketing', p: 'p1', done: false },
    { name: 'Review pull request #42', meta: 'Today 2:00 PM · Work', p: 'p2', done: false },
    { name: 'Book flights for October', meta: 'Deadline Fri · Personal', p: 'p3', done: false },
    { name: 'Water the plants', meta: 'Today · Home', p: 'p4', done: true }
  ];
</script>

<svelte:head>
  <title>TooDue — a fast, open-source to-do app for people who ship</title>
  <meta
    name="description"
    content="TooDue is a fast, open-source task manager: projects, priorities, sharing, real-time sync, and calendar integration. Free while in development — sign up in seconds."
  />
  <meta property="og:title" content="TooDue — a fast, open-source to-do app" />
  <meta
    property="og:description"
    content="Projects, priorities, sharing, real-time sync, and calendar integration. Free while in development."
  />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://toodue.com/" />
  <meta property="og:image" content="https://toodue.com/og-image.png" />
  <meta property="og:image:width" content="1200" />
  <meta property="og:image:height" content="630" />
  <meta
    property="og:image:alt"
    content="TooDue's Today view with sample tasks, next to the tagline: A fast, open-source to-do app you can self-host."
  />
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:image" content="https://toodue.com/og-image.png" />
  <link rel="canonical" href="https://toodue.com/" />
</svelte:head>

<header class="nav">
  <a class="brand" href="/" aria-label="TooDue home">
    <img class="brand-logo" src="/toodue-logo.svg" alt="TooDue" width="44" height="44" />
  </a>
  <nav>
    <a href="#features">Features</a>
    <a href="#install">Install</a>
    <a href="#faq">FAQ</a>
    <a class="btn btn-ghost" href={app}>Log in</a>
    <a class="btn btn-primary" href={app}>Sign up free</a>
    <a href="https://docs.toodue.com">API docs</a>
  </nav>
</header>

<main>
  <section class="hero">
    <div class="hero-copy">
      <p class="badge">🚧 In development · 100% free for now</p>
      <h1>Get things <span class="grad">done</span>, not managed.</h1>
      <p class="sub">
        TooDue is a fast, open-source to-do app with the features that matter — projects,
        priorities, deadlines, sharing, and real-time sync across every device — without the
        bloat, and without the subscription. At least for now.
      </p>
      <div class="cta-row">
        <a class="btn btn-primary btn-lg" href={app}>Sign up free</a>
        <a class="btn btn-ghost btn-lg" href="#features">See what it does</a>
      </div>
      <p class="fine">No credit card. No trial clock. Works on iPhone, Android, and desktop.</p>
    </div>

    <div class="mockup" aria-hidden="true">
      <div class="mockup-bar">
        <span class="dot"></span><span class="dot"></span><span class="dot"></span>
        <span class="mockup-title">Today</span>
      </div>
      <ul class="mockup-list">
        {#each demoTasks as t}
          <li class:done={t.done}>
            <span class="check {t.p}">{#if t.done}✓{/if}</span>
            <span class="task-text">
              <span class="task-name">{t.name}</span>
              <span class="task-meta">{t.meta}</span>
            </span>
          </li>
        {/each}
      </ul>
      <div class="mockup-sync">⚡ Synced just now</div>
    </div>
  </section>

  <section id="features" class="section">
    <h2>Everything you need. Nothing you have to ignore.</h2>
    <p class="section-sub">
      Built by someone who lives in their task list, for people who do the same.
    </p>
    <div class="grid">
      {#each features as f}
        <article class="card">
          <div class="card-icon">{f.icon}</div>
          <h3>{f.title}</h3>
          <p>{f.body}</p>
        </article>
      {/each}
    </div>
  </section>

  <section id="install" class="section">
    <h2>Put it on your home screen</h2>
    <p class="section-sub">
      TooDue is a progressive web app — install it once and it opens full-screen with its own
      icon, just like an app from the store. Takes about fifteen seconds.
    </p>
    <div class="install-grid">
      <article class="card">
        <h3>🍎 iPhone &amp; iPad</h3>
        <ol>
          <li>Open <a href={app}>app.toodue.com</a> in <strong>Safari</strong> and sign in.</li>
          <li>Tap the <strong>Share</strong> button (the square with an arrow pointing up).</li>
          <li>Scroll down and tap <strong>Add to Home Screen</strong>.</li>
          <li>Tap <strong>Add</strong>. TooDue now launches from your home screen, full-screen.</li>
        </ol>
      </article>
      <article class="card">
        <h3>🤖 Android</h3>
        <ol>
          <li>Open <a href={app}>app.toodue.com</a> in <strong>Chrome</strong> and sign in.</li>
          <li>Tap the <strong>⋮ menu</strong> in the top-right corner.</li>
          <li>Tap <strong>Add to Home screen</strong> (or <strong>Install app</strong>).</li>
          <li>Confirm — TooDue installs with its own icon and runs like a native app.</li>
        </ol>
      </article>
    </div>
    <p class="fine center">
      On desktop, look for the install icon in your browser's address bar (Chrome and Edge).
    </p>
  </section>

  <section class="section banner-wrap">
    <div class="banner">
      <h2>Free while we build it — and honest about the trade.</h2>
      <p>
        TooDue is under active development. That means you get every feature free right now, new
        improvements land all the time, and your feedback actually shapes the product. Down the
        road we'll add fair, affordable paid plans for the hosted service — but self-hosting the
        open-source version will stay free forever, and early users will never be surprised by a
        paywall.
      </p>
      <div class="cta-row center">
        <a class="btn btn-primary btn-lg" href={app}>Create your free account</a>
        <a class="btn btn-ghost btn-lg" href="https://github.com/djedi/toodue">View the source</a>
      </div>
    </div>
  </section>

  <section id="faq" class="section faq">
    <h2>Questions, answered</h2>
    <div class="faq-list">
      {#each faqs as f}
        <details>
          <summary>{f.q}</summary>
          <p>{f.a}</p>
        </details>
      {/each}
    </div>
  </section>
</main>

<footer>
  <p>
    <strong>TooDue</strong> — get things done, not managed.
    <a href={app}>Open the app</a> · <a href="https://docs.toodue.com">API docs</a> · <a href="https://github.com/djedi/toodue">GitHub</a>
    · <a href="/privacy">Privacy</a> · <a href="/terms">Terms</a> · <a href="/support">Support</a>
  </p>
  <p class="fine">© 2026 TooDue. Built with Rust, Svelte, and an unreasonable love of task lists.</p>
</footer>

<style>
  .nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    max-width: 72rem;
    margin: 0 auto;
    padding: 1.1rem 1.5rem;
  }

  .brand {
    display: inline-flex;
    align-items: center;
    color: var(--text);
    text-decoration: none;
  }

  .brand-logo {
    display: block;
    width: 4rem;
    height: 4rem;
    object-fit: contain;
  }

  @media (max-width: 640px) {
    .brand-logo {
      width: 3.25rem;
      height: 3.25rem;
    }
  }

  .nav nav {
    display: flex;
    align-items: center;
    gap: 1.1rem;
  }

  .nav nav > a:not(.btn) {
    color: var(--muted);
    text-decoration: none;
    font-weight: 500;
  }

  .nav nav > a:not(.btn):hover {
    color: var(--text);
  }

  @media (max-width: 640px) {
    .nav nav > a:not(.btn) {
      display: none;
    }
  }

  .btn {
    display: inline-block;
    padding: 0.5rem 1rem;
    border-radius: 0.6rem;
    font-weight: 700;
    text-decoration: none;
    white-space: nowrap;
    transition: transform 0.1s ease, background 0.15s ease;
  }

  .btn:active {
    transform: scale(0.97);
  }

  .btn-primary {
    background: var(--accent);
    color: #082f49;
  }

  .btn-primary:hover {
    background: var(--accent-soft);
  }

  .btn-ghost {
    color: var(--text);
    border: 1px solid var(--border);
  }

  .btn-ghost:hover {
    border-color: var(--accent);
  }

  .btn-lg {
    padding: 0.8rem 1.5rem;
    font-size: 1.05rem;
    border-radius: 0.75rem;
  }

  main {
    max-width: 72rem;
    margin: 0 auto;
    padding: 0 1.5rem;
  }

  .hero {
    display: grid;
    grid-template-columns: 1.15fr 1fr;
    align-items: center;
    gap: 3rem;
    padding: 4rem 0 5rem;
  }

  @media (max-width: 860px) {
    .hero {
      grid-template-columns: 1fr;
      padding-top: 2rem;
    }
  }

  .badge {
    display: inline-block;
    background: rgba(56, 189, 248, 0.12);
    border: 1px solid rgba(56, 189, 248, 0.35);
    color: var(--accent-soft);
    border-radius: 999px;
    padding: 0.3rem 0.9rem;
    font-size: 0.85rem;
    font-weight: 600;
    margin: 0 0 1.2rem;
  }

  h1 {
    font-size: clamp(2.4rem, 6vw, 3.9rem);
    line-height: 1.05;
    letter-spacing: -0.045em;
    margin: 0 0 1.2rem;
  }

  .grad {
    background: linear-gradient(120deg, #38bdf8, #818cf8);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }

  .sub {
    color: var(--muted);
    font-size: 1.15rem;
    max-width: 34rem;
    margin: 0 0 1.8rem;
  }

  .cta-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.8rem;
  }

  .cta-row.center {
    justify-content: center;
  }

  .fine {
    color: var(--p4);
    font-size: 0.85rem;
    margin-top: 1rem;
  }

  .center {
    text-align: center;
  }

  /* mockup */
  .mockup {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 1rem;
    box-shadow: 0 24px 60px rgba(2, 6, 23, 0.6);
    overflow: hidden;
  }

  .mockup-bar {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.7rem 1rem;
    border-bottom: 1px solid var(--border);
  }

  .dot {
    width: 0.65rem;
    height: 0.65rem;
    border-radius: 50%;
    background: #334155;
  }

  .mockup-title {
    margin-left: 0.6rem;
    font-weight: 700;
    font-size: 0.9rem;
  }

  .mockup-list {
    list-style: none;
    margin: 0;
    padding: 0.4rem 0;
  }

  .mockup-list li {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    padding: 0.65rem 1rem;
  }

  .mockup-list li.done {
    opacity: 0.45;
  }

  .mockup-list li.done .task-name {
    text-decoration: line-through;
  }

  .check {
    flex: none;
    width: 1.25rem;
    height: 1.25rem;
    border-radius: 50%;
    border: 2px solid;
    display: grid;
    place-items: center;
    font-size: 0.75rem;
    font-weight: 800;
  }

  .check.p1 { border-color: var(--p1); color: var(--p1); background: rgba(248, 113, 113, 0.12); }
  .check.p2 { border-color: var(--p2); color: var(--p2); background: rgba(251, 146, 60, 0.12); }
  .check.p3 { border-color: var(--p3); color: var(--p3); background: rgba(96, 165, 250, 0.12); }
  .check.p4 { border-color: var(--p4); color: var(--p4); }

  .task-text {
    display: flex;
    flex-direction: column;
    min-width: 0;
  }

  .task-name {
    font-weight: 600;
    font-size: 0.95rem;
  }

  .task-meta {
    color: var(--muted);
    font-size: 0.78rem;
  }

  .mockup-sync {
    border-top: 1px solid var(--border);
    padding: 0.55rem 1rem;
    font-size: 0.78rem;
    color: var(--accent-soft);
  }

  /* sections */
  .section {
    padding: 4rem 0;
  }

  h2 {
    font-size: clamp(1.7rem, 4vw, 2.4rem);
    letter-spacing: -0.03em;
    text-align: center;
    margin: 0 0 0.8rem;
  }

  .section-sub {
    text-align: center;
    color: var(--muted);
    max-width: 40rem;
    margin: 0 auto 2.8rem;
    font-size: 1.08rem;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
    gap: 1.2rem;
  }

  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 1rem;
    padding: 1.5rem;
  }

  .card h3 {
    margin: 0 0 0.5rem;
    font-size: 1.08rem;
    letter-spacing: -0.02em;
  }

  .card p {
    margin: 0;
    color: var(--muted);
    font-size: 0.95rem;
  }

  .card-icon {
    font-size: 1.6rem;
    margin-bottom: 0.7rem;
  }

  .install-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(19rem, 1fr));
    gap: 1.2rem;
    max-width: 56rem;
    margin: 0 auto;
  }

  .install-grid ol {
    margin: 0;
    padding-left: 1.2rem;
    color: var(--muted);
  }

  .install-grid li {
    margin-bottom: 0.55rem;
  }

  .install-grid strong {
    color: var(--text);
  }

  .banner-wrap {
    padding-bottom: 2rem;
  }

  .banner {
    background: linear-gradient(140deg, rgba(56, 189, 248, 0.14), rgba(129, 140, 248, 0.1));
    border: 1px solid rgba(56, 189, 248, 0.3);
    border-radius: 1.25rem;
    padding: 3rem 2rem;
    text-align: center;
  }

  .banner p {
    color: var(--text);
    opacity: 0.85;
    max-width: 46rem;
    margin: 0 auto 1.8rem;
  }

  .faq-list {
    max-width: 44rem;
    margin: 0 auto;
  }

  details {
    border: 1px solid var(--border);
    border-radius: 0.8rem;
    background: var(--card);
    padding: 0.9rem 1.2rem;
    margin-bottom: 0.8rem;
  }

  summary {
    font-weight: 700;
    cursor: pointer;
  }

  details p {
    color: var(--muted);
    margin: 0.7rem 0 0.2rem;
  }

  footer {
    border-top: 1px solid var(--border);
    margin-top: 3rem;
    padding: 2.2rem 1.5rem 2.8rem;
    text-align: center;
    color: var(--muted);
  }

  footer p {
    margin: 0.3rem 0;
  }
</style>
