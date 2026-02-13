
<h1 align="center">Automated X (Twitter) Trends → Telegram Bot using n8n & Docker</h1>
<img width="1600" height="1200" alt="Shot (4)" src="https://github.com/user-attachments/assets/0d24be3f-bf9e-48fe-bb1d-54c0e4e80ebe" />


<h1 align="center">🚀 XTrends Telegram Bot</h1>

<p align="center">
  <b>Automated X (Twitter) Trends → Clean Telegram Summaries</b><br/>
  <sub>Self-hosted · n8n · Docker · No paid APIs</sub>
</p>

<hr/>

<h2>✨ Overview</h2>

<p>
  <b>XTrends-TelegramBot-with-n8n</b> automatically tracks the <b>Top 5 trending topics on X (Twitter)</b>
  and sends a <b>clean, readable summary</b> to <b>Telegram</b> using <b>n8n</b> and <b>Docker</b>.
</p>

<ul>
  <li>✔ Runs on local machine or server</li>
  <li>✔ Fully self-hosted</li>
  <li>✔ No Twitter API</li>
  <li>✔ No paid services</li>
</ul>

<hr/>

<h2>📌 Features</h2>

<ul>
  <li>⏰ Scheduled execution (fully automatic)</li>
  <li>📈 Top 5 X (Twitter) trends</li>
  <li>📰 Google News RSS integration</li>
  <li>🧹 Headline cleanup (sources & duplicates removed)</li>
  <li>✉️ Single, well-formatted Telegram message</li>
  <li>🤖 Uses your own Telegram bot</li>
</ul>

<hr/>

<h2>🧠 How It Works</h2>

<ol>
  <li>n8n runs inside a Docker container</li>
  <li>A Schedule Trigger starts the workflow</li>
  <li>Google News RSS is queried</li>
  <li>Headlines are filtered and deduplicated</li>
  <li>A formatted message is sent to Telegram</li>
</ol>

<p><i>Everything is automated end-to-end.</i></p>

<hr/>

<h2>🧰 Requirements</h2>

<ul>
  <li>🐳 Docker</li>
  <li>🧩 Docker Compose</li>
  <li>💬 Telegram account</li>
</ul>

<p>
  <i>On Windows, Docker Desktop must be installed (WSL2 enabled).</i>
</p>

<hr/>

<h2>⚠️ Important Concept</h2>

<p>
  This repository <b>does NOT include a running n8n instance</b>.
</p>

<p><b>What this repository provides:</b></p>
<ul>
  <li>Docker setup for n8n</li>
  <li>Ready-to-import n8n workflow</li>
</ul>

<p><b>What each user must do:</b></p>
<ul>
  <li>Run n8n locally or on a server</li>
  <li>Import the workflow</li>
  <li>Activate (Publish) the workflow</li>
</ul>

<p><i>This is standard n8n behavior.</i></p>

<hr/>

<h2>🤖 Step 1 — Create a Telegram Bot</h2>

<ol>
  <li>Open Telegram and search for <b>@BotFather</b></li>
  <li>Send <code>/newbot</code></li>
  <li>Choose a name and username</li>
  <li>Copy the Bot Token you receive</li>
</ol>

<p>This token will be used as:</p>
<pre>BOT_TR</pre>

<hr/>

<h2>💬 Step 2 — Get Your Chat ID</h2>

<ol>
  <li>Open your bot and send any message (e.g. <code>hello</code>)</li>
  <li>Open the following URL in your browser:</li>
</ol>

<pre>https://api.telegram.org/bot&lt;YOUR_BOT_TOKEN&gt;/getUpdates</pre>

<p>Find the following field:</p>

<pre>"chat": { "id": 123456789 }</pre>

<p>This value will be used as:</p>
<pre>CHAT_TR</pre>

<hr/>

<h2>🔐 Step 3 — Environment Variables</h2>

<p>Create a file named <b>variables.env</b> in the project root.</p>

<ul>
  <li>Add your Telegram bot token</li>
  <li>Add your Telegram chat ID</li>
</ul>

<p>
  ❌ Do <b>NOT</b> commit this file<br/>
  ✅ Optionally include <code>variables.env.example</code>
</p>

<hr/>

<h2>🐳 Step 4 — Start n8n</h2>

<p>Run the following command:</p>

<pre>docker-compose up -d</pre>

<p>Open n8n UI:</p>

<pre>http://localhost:5678</pre>

<hr/>

<h2>🔄 Step 5 — Import the Workflow</h2>

<ol>
  <li>Open <b>Workflows</b> in n8n UI</li>
  <li>Click <b>Import from File</b></li>
  <li>Select the workflow JSON file</li>
  <li>Workflow editor will open</li>
</ol>

<hr/>

<h2>▶️ Step 6 — Activate the Workflow</h2>

<p>
  Imported workflows are <b>inactive by default</b>.
</p>

<ol>
  <li>Open the workflow</li>
  <li>Click <b>Inactive → Active</b></li>
</ol>

<p>
  Once activated, the workflow runs automatically based on schedule.
</p>

<hr/>

<h2>⏰ Recommended Schedule</h2>

<ul>
  <li>🕛 12:00</li>
  <li>🕕 18:00</li>
  <li>🌙 23:00</li>
</ul>

<p>Timezone: <b>Europe / Istanbul</b></p>

<hr/>

<h2>🔒 Security Notes</h2>

<ul>
  <li>❌ Never commit <code>variables.env</code></li>
  <li>❌ Never share bot tokens</li>
  <li>✅ Use environment variables only</li>
</ul>

<hr/>

<h2>🎉 Summary</h2>

<ul>
  <li>✔ Fully automated X trends tracking</li>
  <li>✔ Telegram notifications</li>
  <li>✔ Secure & self-hosted</li>
  <li>✔ Beginner-friendly setup</li>
</ul>

<p align="center">
  ⭐ If this project helped you, consider giving it a star!
</p>
