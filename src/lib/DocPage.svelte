<script>
  let { title, updated, children } = $props();
</script>

<svelte:head>
  <title>{title} · TooDue</title>
</svelte:head>

<header class="doc-nav">
  <a href="/" class="brand"><img src="/toodue-logo.svg" alt="TooDue" width="48" height="48" /></a>
  <nav><a href="/privacy">Privacy</a><a href="/terms">Terms</a><a href="/support">Support</a></nav>
</header>

<main class="doc">
  <h1>{title}</h1>
  {#if updated}<p class="updated">Last updated {updated}</p>{/if}
  {@render children()}
</main>

<footer class="doc-footer">
  <p>© 2026 TooDue · <a href="/">Home</a> · <a href="https://app.toodue.com/">Open the app</a></p>
</footer>

<style>
  .doc-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 46rem;
    margin: 0 auto;
    padding: 1rem 1.5rem;
  }
  .doc-nav nav {
    display: flex;
    gap: 1.2rem;
  }
  .doc-nav nav a {
    color: var(--muted);
    text-decoration: none;
  }
  .doc-nav nav a:hover {
    color: var(--text);
  }
  .brand img {
    display: block;
  }
  .doc {
    max-width: 46rem;
    margin: 0 auto;
    padding: 1rem 1.5rem 3rem;
  }
  .doc :global(h1) {
    font-size: 2.2rem;
    line-height: 1.2;
    margin: 1rem 0 0.25rem;
  }
  .doc :global(h2) {
    font-size: 1.25rem;
    margin: 2.2rem 0 0.5rem;
  }
  .doc :global(p),
  .doc :global(li) {
    color: #cbd5e1;
  }
  .updated {
    color: var(--muted) !important;
    font-size: 0.9rem;
  }
  .doc-footer {
    border-top: 1px solid var(--border);
    padding: 2rem 1.5rem;
    text-align: center;
    color: var(--muted);
  }
</style>
