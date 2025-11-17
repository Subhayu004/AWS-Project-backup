<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title># 🔗 TinyLink — Premium Serverless URL Shortener</title>
  <style>
    :root{
      --bg:#0b0f15;
      --card:#0f1720;
      --muted:#9aa4b2;
      --accent:#7c3aed;
      --glass: rgba(255,255,255,0.04);
      --mono: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace;
      --radius:14px;
    }
    html,body{height:100%}
    body{
      margin:0;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg,#020205 0%, #071129 60%);
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      padding:28px;
    }
    .container{max-width:960px;margin:0 auto}
    header{display:flex;align-items:center;gap:16px;margin-bottom:22px}
    .logo{
      width:56px;height:56px;border-radius:12px;display:flex;align-items:center;justify-content:center;
      background:linear-gradient(135deg,#6d28d9,#8b5cf6);
      box-shadow:0 8px 30px rgba(124,58,237,0.15);
      font-weight:800;font-family:var(--mono);letter-spacing:0.06em;
    }
    h1{font-size:22px;margin:0 0 6px 0}
    p.lead{margin:0;color:var(--muted);}
    hr{border:0;border-top:1px solid rgba(255,255,255,0.04);margin:26px 0}
    section{margin-bottom:20px}
    h2{font-size:16px;margin:8px 0 12px 0;color:#fff}
    ul{margin:8px 0 12px 0;padding-left:20px}
    li{margin:6px 0}
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:var(--radius);padding:18px;border:1px solid rgba(255,255,255,0.03);
      box-shadow:0 6px 30px rgba(2,6,23,0.6);
    }
    .feature-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
    .feature{background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.02)}
    .muted{color:var(--muted)}
    .code{
      background:#071428;padding:14px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);
      font-family:var(--mono);font-size:13px;color:#dbeafe;overflow:auto;
    }
    pre{margin:0}
    a{color:var(--accent);text-decoration:none}
    a:hover{text-decoration:underline}
    .screenshot{width:100%;border-radius:10px;border:1px solid rgba(255,255,255,0.04);display:block;margin-top:12px}
    .grid-2{display:grid;grid-template-columns:1fr 320px;gap:18px}
    @media (max-width:880px){.grid-2{grid-template-columns:1fr}}
    .meta{font-size:13px;color:var(--muted)}
    .btn{
      display:inline-block;padding:8px 12px;border-radius:10px;background:linear-gradient(90deg,#6d28d9,#8b5cf6);
      color:white;font-weight:600;text-decoration:none;border:1px solid rgba(255,255,255,0.06)
    }
    .small{font-size:13px;color:var(--muted)}
    .footer{margin-top:28px;padding-top:20px;border-top:1px solid rgba(255,255,255,0.03);color:var(--muted);font-size:13px}
    .badge{display:inline-block;padding:6px 8px;background:rgba(255,255,255,0.03);border-radius:8px;margin-right:8px;font-size:12px;color:var(--muted)}
    .code.inline{display:inline-block;padding:2px 6px;background:rgba(255,255,255,0.02);border-radius:6px;font-family:var(--mono)}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">TINY</div>
      <div>
        <h1># 🔗 TinyLink — Premium Serverless URL Shortener</h1>
        <p class="lead">TinyLink is a fast, elegant, production-styled URL shortener built with a serverless AWS backend and a polished HTML/CSS/JS frontend.</p>
      </div>
    </header>

    <section class="card">
      <p class="meta">Live Website: <a href="https://www.tinylink.sbs" target="_blank" rel="noopener">https://www.tinylink.sbs</a></p>
      <hr>

      <h2>🌟 What TinyLink Does</h2>
      <ul>
        <li>🔗 Shorten long URLs instantly</li>
        <li>⚡ Fast serverless redirects via AWS Lambda</li>
        <li>📜 Local history of shortened links saved to <span class="code.inline">localStorage</span></li>
        <li>🌓 Light / Dark theme with an animated toggle</li>
        <li>📱 Fully responsive, mobile-first UI</li>
      </ul>

      <h2>🚀 Features</h2>
      <div class="feature-grid">
        <div class="feature"><strong>Instant shortening</strong><div class="small muted">One POST request, one short code.</div></div>
        <div class="feature"><strong>Serverless backend</strong><div class="small muted">API Gateway + Lambda + DynamoDB.</div></div>
        <div class="feature"><strong>Local history</strong><div class="small muted">Persist last 50 entries in the browser.</div></div>
        <div class="feature"><strong>Auto-redirect fallback</strong><div class="small muted">Redirect page forwards to AWS redirect lambda.</div></div>
        <div class="feature"><strong>Animated UI</strong><div class="small muted">Glassmorphism, neon auras, smooth transitions.</div></div>
        <div class="feature"><strong>Easy to host</strong><div class="small muted">Frontend on GitHub Pages, backend on AWS.</div></div>
      </div>
    </section>

    <section class="card grid-2" aria-labelledby="architecture">
      <div>
        <h2 id="architecture">🧩 How the Architecture Works</h2>
        <p class="muted">TinyLink has two main parts:</p>

        <h3>Frontend</h3>
        <ul>
          <li>HTML + Tailwind + custom CSS</li>
          <li>Vanilla JavaScript (Fetch API, DOM, localStorage)</li>
          <li>Hosted on GitHub Pages (static site)</li>
        </ul>

        <h3>Backend (AWS)</h3>
        <ul>
          <li>API Gateway — REST endpoints</li>
          <li>AWS Lambda (Python) — two functions:
            <ul>
              <li><span class="code.inline">shorten_url</span> — generate short code, write to DynamoDB</li>
              <li><span class="code.inline">redirect_url</span> — lookup and 302 redirect</li>
            </ul>
          </li>
          <li>DynamoDB table <span class="code.inline">UrlTable</span> with PK <span class="code.inline">shortCode</span></li>
          <li>CloudWatch for logs and monitoring</li>
        </ul>

        <h3>Why this split?</h3>
        <p class="small muted">It keeps front and back concerns separate. The frontend is static (cheap, CDN-backed). The backend is serverless (scales on demand, no servers to manage).</p>

        <hr>

        <h2>🔄 End-to-End Flow</h2>
        <ol>
          <li><strong>User</strong> pastes a long URL and clicks <em>Shorten</em>. Frontend POSTs JSON to API Gateway.</li>
          <li><strong>API Gateway</strong> forwards to Lambda (<span class="code.inline">shorten_url</span>).</li>
          <li><strong>shorten_url Lambda</strong> validates, generates a 6-char code, writes to DynamoDB, returns the short code.</li>
          <li><strong>Frontend</strong> shows the short URL and saves it to local history.</li>
          <li><strong>Visitor</strong> opens <code>https://your-domain/{code}</code>. The fallback redirect page (on GitHub Pages) forwards the path to the API Gateway redirect endpoint.</li>
          <li><strong>redirect_url Lambda</strong> looks up the code, increments click count, and responds with HTTP 302 to the original URL.</li>
        </ol>
      </div>

      <aside>
        <div class="meta">Quick reference</div>
        <div style="margin:12px 0">
          <div class="badge">API: API Gateway</div>
          <div class="badge">Compute: Lambda (Python)</div>
          <div class="badge">DB: DynamoDB</div>
        </div>

        <h3>Sample item in DynamoDB</h3>
        <div class="code" style="margin-top:8px">
<pre><code>{
  "shortCode": "a1B2c3",
  "longUrl": "https://very-long-link.com/...",
  "createdAt": "2025-11-13T12:00:00Z",
  "clicks": 0
}</code></pre>
        </div>

        <h3 style="margin-top:12px">Shorten endpoint</h3>
        <div class="code" style="margin-top:8px">
<pre><code>POST https://{api-id}.execute-api.{region}.amazonaws.com/prod/shorten
Content-Type: application/json

{"longUrl": "https://example.com/very/long/url"}</code></pre>
        </div>
      </aside>
    </section>

    <section class="card">
      <h2>🛠️ Implementation Details — Frontend</h2>

      <h3>Key JS snippets</h3>
      <div class="code">
<pre><code>// API base (example)
const API_BASE = 'https://nel0n9hinl.execute-api.us-east-1.amazonaws.com/prod';

// Validation
function isValidUrl(url){ return /^https?:\/\//i.test(url) }

// POST to shorten
const response = await fetch(`${API_BASE}/shorten`, {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ longUrl })
});
const data = await response.json();
if (!response.ok || !data.shortCode) throw new Error(data.error || 'Failed to shorten URL');

// final short url (on your domain)
currentShortUrl = `${window.location.origin}/${data.shortCode}`;
</code></pre>
      </div>

      <h3 style="margin-top:12px">Local history</h3>
      <p class="small muted">History is saved to <span class="code.inline">localStorage</span> under key <span class="code.inline">tinylink_history</span>. Items are stored with an ID and timestamp and capped at 50 entries.</p>

      <h3 style="margin-top:12px">Auto-redirect fallback (important)</h3>
      <p class="small muted">Because GitHub Pages is static, opening <code>https://tinylink.sbs/abc123</code> won't call Lambda directly. The fallback HTML page you added reads the path and forwards the visitor to the API Gateway redirect endpoint:</p>

      <div class="code" style="margin-top:8px">
<pre><code>&lt;!-- redirect.html --&gt;
&lt;!-- placed on your static site at /index.html or /redirect.html --&gt;
&lt;script&gt;
  const code = window.location.pathname.substring(1);
  if (code) {
    window.location.href = `https://nel0n9hinl.execute-api.us-east-1.amazonaws.com/prod/${code}`;
  } else {
    document.write("&lt;h2&gt;Invalid link&lt;/h2&gt;");
  }
&lt;/script&gt;</code></pre>
      </div>

      <p class="small muted">This is the fix you implemented to avoid 404s when a short URL is visited from the custom domain. It simply re-routes the browser to the API Gateway path that your Lambda redirect handler understands.</p>
    </section>

    <section class="card">
      <h2>🛠️ Implementation Details — Backend (Lambda)</h2>

      <h3>shorten_url (pseudo-Python)</h3>
      <div class="code">
<pre><code>def lambda_handler(event, context):
    body = json.loads(event['body'])
    long_url = body.get('longUrl', '').strip()
    if not long_url.startswith('http'):
        return { 'statusCode': 400, 'body': json.dumps({'error':'invalid url'}) }

    short_code = generate_code(6)     # alphanumeric
    # check DynamoDB for collisions; retry if exists
    put_item_to_dynamodb(short_code, long_url, now_iso(), 0)

    return {
      "statusCode": 200,
      "body": json.dumps({ "shortCode": short_code })
    }</code></pre>
      </div>

      <h3 style="margin-top:12px">redirect_url (pseudo-Python)</h3>
      <div class="code">
<pre><code>def lambda_handler(event, context):
    code = event['pathParameters']['code']
    item = dynamodb.get_item(TableName='UrlTable', Key={'shortCode':{'S':code}})
    if not item:
        return { 'statusCode': 404, 'body': 'Not found' }

    long_url = item['longUrl']
    # optionally increment click counter
    dynamodb.update_item(... increment clicks ...)

    return {
      'statusCode': 302,
      'headers': {'Location': long_url}
    }</code></pre>
      </div>

      <p class="small muted">Give Lambda a minimal execution role with permissions to read/write the DynamoDB table and write logs to CloudWatch.</p>
    </section>

    <section class="card">
      <h2>🔧 Getting Started — Run Locally</h2>

      <ol>
        <li><strong>Clone</strong>:
          <div class="code" style="margin-top:8px"><pre><code>git clone https://github.com/your-username/tinylink.git
cd tinylink</code></pre></div>
        </li>

        <li><strong>Open the frontend</strong>:
          <div class="small muted">Open <code>index.html</code> in your browser. No build step required for the static UI.</div>
        </li>

        <li><strong>Test against API Gateway</strong>:
          Update <code>API_BASE</code> in your JS file:
          <div class="code" style="margin-top:8px"><pre><code>// const API_BASE = "http://127.0.0.1:5000";
const API_BASE = "https://nel0n9hinl.execute-api.us-east-1.amazonaws.com/prod";</code></pre></div>
        </li>

        <li><strong>Deploy backend</strong>:
          <div class="small muted">Deploy Lambdas, create an API Gateway REST API, wire a DynamoDB table named <code>UrlTable</code>, add IAM role and CORS.</div>
        </li>
      </ol>
    </section>

    <section class="card">
      <h2>📸 Preview</h2>
      <img src="assets/screenshot.png" alt="TinyLink preview" class="screenshot" />
    </section>

    <section class="card">
      <h2>🌐 Live Website</h2>
      <p>Visit: <a class="btn" href="https://www.tinylink.sbs" target="_blank" rel="noopener">https://www.tinylink.sbs</a></p>
    </section>

    <section class="card">
      <h2>❤️ Credits</h2>
      <p class="small muted">Made by <strong>Subhayu &amp; Sreyasi</strong>. Frontend styling, animations, and serverless glue crafted by you.</p>
    </section>

    <footer class="footer">
      <div class="meta">If you want this converted into a printable PDF, a GitHub Pages-friendly docs folder, or a version with badges and shields — say the word and I’ll generate it.</div>
    </footer>
  </div>
</body>
</html>


