<script>
  import DocPage from '$lib/DocPage.svelte';
</script>

<DocPage title="Privacy Policy" updated="October 29, 2026">
  <p>
    TooDue is a to-do app. This policy explains what we collect when you use the hosted service at app.toodue.com
    and the TooDue apps for iPhone and Android, and what we do with it. The short version: we store what you need to
    manage your tasks, we don't sell it, we don't show ads, and we don't track you.
  </p>

  <h2>What we collect</h2>
  <ul>
    <li><strong>Account details:</strong> your name, email address and a salted, hashed password (we never see or store the plain password).</li>
    <li><strong>Your content:</strong> projects, tasks, sub-tasks, comments, file attachments and project templates you create, and the members of projects you share.</li>
    <li><strong>Sign-in sessions:</strong> a random session token kept on your device so you stay signed in.</li>
    <li><strong>Integrations you turn on:</strong> if you connect Google Calendar, we store the OAuth tokens Google gives us and the IDs of the calendar events we create. If you connect an AI agent or create an API key, we store a hashed key or token and when it was last used.</li>
    <li><strong>Server logs:</strong> standard request logs (IP address, time, request path) kept briefly for security and debugging.</li>
  </ul>

  <h2>What we don't do</h2>
  <ul>
    <li>No advertising, ad networks or third-party analytics SDKs, in the apps or on the site.</li>
    <li>No selling or renting your data, and no tracking across other companies' apps or websites.</li>
    <li>No reading your tasks except when you ask for support or we must to keep the service running or comply with the law.</li>
  </ul>

  <h2>How your data is used</h2>
  <p>
    Only to run TooDue: storing and syncing your tasks across your devices and with people you share projects with,
    keeping your account secure, and sending the calendar events you asked us to create.
  </p>

  <h2>Third parties</h2>
  <ul>
    <li><strong>Google Calendar</strong>, only if you connect it. TooDue's use of information received from Google APIs adheres to the Google API Services User Data Policy, including the Limited Use requirements.</li>
    <li><strong>AI agents you connect</strong> (for example via MCP) can read and change the tasks you grant them access to. You can disconnect them any time in Settings.</li>
    <li><strong>Hosting:</strong> TooDue runs on servers we rent; the hosting provider doesn't get access to your content beyond operating the hardware.</li>
  </ul>

  <h2>Security</h2>
  <p>All traffic is encrypted with HTTPS. Passwords are hashed with Argon2. API keys and agent tokens are stored hashed.</p>

  <h2>Retention and deletion</h2>
  <p>
    We keep your data while your account exists. You can delete your account at any time in the app: open
    <strong>Settings → Delete account</strong>. That immediately and permanently removes your account, your projects,
    tasks, comments, attachments, API keys and integrations. Tasks you added to someone else's shared project stay in
    that project. Backups roll off within 30 days. You can also email
    <a href="mailto:support@toodue.com">support@toodue.com</a> and we'll delete it for you.
  </p>

  <h2>Self-hosting</h2>
  <p>If you run your own TooDue server, your data lives on that server and this policy doesn't apply to it.</p>

  <h2>Children</h2>
  <p>TooDue isn't directed to children under 13, and we don't knowingly collect their data.</p>

  <h2>Your rights</h2>
  <p>
    You can access, export, correct or delete your data. Most of this you can do in the app; for anything else,
    email <a href="mailto:support@toodue.com">support@toodue.com</a>.
  </p>

  <h2>Changes</h2>
  <p>If we change this policy we'll update the date above, and tell you in the app for material changes.</p>

  <h2>Contact</h2>
  <p>Questions? <a href="mailto:support@toodue.com">support@toodue.com</a></p>
</DocPage>
