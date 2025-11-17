🔗 TinyLink — Premium Serverless URL Shortener

TinyLink is a sleek, modern, and blazing-fast URL shortener built on top of a fully serverless AWS architecture.
It transforms long URLs into clean, reliable short links — packaged inside a polished UI with interactive animations, smooth transitions, and full Light/Dark mode support.

👉 Live Website: https://www.tinylink.sbs

🌟 What This Project Does

TinyLink enables users to:

🔗 Shorten long URLs instantly

⚡ Generate unique short codes backed by AWS

🚀 Redirect at high speed with Lambda

📜 Access full history of shortened links (saved locally)

🧽 Delete individual history entries or clear all

🌓 Switch between Light and Dark themes

📱 Enjoy a smooth, fully responsive UI

🎨 Experience a highly animated, glass-styled design

TinyLink combines a premium user interface with a production-style backend — without any servers to manage.

🚀 Features

✨ One-click URL shortening
✨ AWS Lambda–powered redirect system
✨ DynamoDB storage (no SQL, no servers, 99.99% uptime)
✨ Local history with timestamps
✨ Auto-copy and open link actions
✨ Light/Dark mode with animated theme toggle
✨ Fully responsive, mobile-first design
✨ GitHub Pages hosting for the frontend
✨ Transparent redirect fallback system

🧩 How the Architecture Works

TinyLink is divided into two parts:
(A) Frontend — runs in browser
(B) Backend — fully serverless AWS stack

🏗️ Project Framework / Tech Stack
🔹 Frontend

HTML, CSS, Tailwind

Vanilla JavaScript (Fetch API, DOM, LocalStorage)

Hosted on GitHub Pages (static, fast, free)

🔹 Backend (AWS)

API Gateway → public REST endpoints

Lambda (Python)

shorten_url → creates short code

redirect_url → redirects visitors

DynamoDB table UrlTable

PK: shortCode

Attributes: longUrl, createdAt, clicks

CloudWatch Logs (monitoring)

IAM roles with least-privilege

Automatic scaling (serverless)

🔄 End-to-End Flow

This is exactly how the system works from the moment a user enters a URL:

A. User Action (Frontend)

User enters a long URL

Clicks Shorten URL

JS sends a POST request to:

POST https://{api-id}.execute-api.{region}.amazonaws.com/prod/shorten


Body sent:

{ "longUrl": "<your-url>" }


🔍 Role: Collect input, call API, show the short result.

B. API Gateway Receives the Request

Acts as the public-facing REST endpoint

Validates the method

Passes the JSON payload to the Lambda function

Uses CORS so the browser can call it

🔍 Role: Securely route HTTP → Lambda.

C. shorten_url Lambda Runs

Inside Lambda:

Validates if longUrl starts with http

Generates a 6-character shortCode

Checks DynamoDB to ensure uniqueness

Writes the entry:

{
  "shortCode": "a1B2c3",
  "longUrl": "https://example.com/long-url",
  "createdAt": "2025-11-13T12:00:00Z",
  "clicks": 0
}


Returns:

{ "shortUrl": "https://{api-id}.execute-api.../a1B2c3" }


🔍 Role: Core logic — create → validate → save → return.

D. Frontend Receives Response

Displays the short link

Adds it to the history section

Enables copy/open actions

🔍 Role: Show the final result.

E. Someone Visits a Short URL

When a visitor opens:

https://tinylink.sbs/abc123


GitHub Pages cannot run backend code — so your redirect fallback page takes over.

You built:

<script>
const code = window.location.pathname.substring(1);
window.location.href =
  `https://nel0n9hinl.execute-api.us-east-1.amazonaws.com/prod/${code}`;
</script>


✔ This forwards the visitor to the Lambda redirect endpoint
✔ Solves the 404 issue
✔ Works for all short links on your custom domain

F. redirect_url Lambda Runs

Steps:

Reads URL path param {code}

Looks up in DynamoDB

If found:

Increments click count

Returns HTTP 302 → Location: <longUrl>

If missing:

Returns 404 or friendly HTML

🔍 Role: Fetch → redirect → track usage.

G. Browser Redirects Finally

A 302 redirect forces browser to navigate to the real destination instantly.

🎨 Frontend Highlights

Your frontend is not just functional — it’s premium:

Neon auras + blur lighting

Glassmorphism cards

Animated theme toggle

Responsive grid layout

Tailwind custom styling

History list with deletion

Smooth transitions everywhere

All controlled by simple, readable JavaScript.

🧠 Why This Stack?
Why AWS Lambda?

Because it's serverless, fast, free for low usage, and scales automatically.

Why DynamoDB?

Instant reads, instant writes, no schema, no servers.

Why GitHub Pages for Frontend?

Free, global CDN, zero maintenance.

Why two Lambda functions?

Separation of concerns:

One for shortening

One for redirection

Keeps things clean and easy to debug.

🔧 Getting Started — Run Locally

You can preview the frontend locally:

1. Clone the repository
git clone https://github.com/your-username/tinylink.git
cd tinylink

2. Open the HTML file

Just open:

index.html

3. Update API Base (if testing local AWS mocks)

In your JS:

// const API_BASE = "http://127.0.0.1:5000";
const API_BASE = "https://nel0n9hinl.execute-api.us-east-1.amazonaws.com/prod";

📸 Preview

TinyLink UI

🌐 Live Website
https://www.tinylink.sbs/
👉 https://www.tinylink.sbs

Hosted on GitHub Pages with full AWS backend support.
